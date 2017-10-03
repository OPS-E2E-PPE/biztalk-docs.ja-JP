---
title: "コンポーネントのサービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
- service solution tutorial, assemblies
- service solution tutorial, components [BizTalk Server]
- service solution tutorial, client applications
- assemblies, service solutions
- orchestrations, service solutions
- client applications, service solutions
- back-end systems
- service solution tutorial, orchestrations
- service solution tutorial, back-end applications
ms.assetid: 97b7b754-abfb-48f9-87bf-7fe171121166
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50743b178f9394c74b137e265532542af2b579c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="components-of-the-service-oriented-solution"></a>コンポーネントのサービス指向ソリューション
このセクションでは、サービス指向ソリューションの主な BizTalk Server コンポーネントについて説明します。 次の図は、ソリューションの主なコンポーネントを示しています。  
  
 ![サービス指向ソリューションのフロー ダイアグラム](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")  
  
 サービス指向ソリューションには、3 つのバージョンのオーケストレーションがあります。  
  
-   3 つのバックエンド アプリケーションのすべてがスタブとして作成されるバージョン  
  
-   3 つのバックエンド アプリケーションのすべてがインラインで呼び出されるバージョン  
  
-   アプリケーションに接続するためにアダプタを使用するバージョン  
  
 オーケストレーションのすべてのバージョンは、SDK\Senarios\SO\BTSSoln\Orchestrations ディレクトリにあります。  
  
 インライン バージョンのオーケストレーションでは、ソリューション内で要求と応答の間の待機時間が最短になります。  
  
 ソース ファイルについては、次を参照してください。[サービス指向ソリューションのファイル一覧](../core/file-inventory-for-the-service-oriented-solution.md)です。  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a>サービス指向ソリューションのオーケストレーション  
 3 つのオーケストレーション**CustomerServiceReceiveSend**、 **CustomerServiceNativeRequestResponse**、および**CustomerService**ソリューションの大部分を作成します。 **CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**オーケストレーションを呼び出すフロント エンドとして機能、 **CustomerService**オーケストレーションです。 **CustomerService**オーケストレーションのほとんどの作業では、バックエンド アプリケーションに要求を送信する、返信を収集、単一のメッセージに返信を組み合わせること、およびフロント エンドを適切なメッセージを送信します。オーケストレーションです。 フロント エンド オーケストレーションを呼び出すため、 **CustomerService**まで待ってから、オーケストレーションのフロント エンド オーケストレーション、 **CustomerService**オーケストレーションが完了するとします。  
  
 ソリューションを公開、 **CustomerServiceNativeRequestResponse**オーケストレーションを Web サービスとして。 **CustomerServiceReceiveSend**オーケストレーションは、MQSeries キューからメッセージを受け取ります。  
  
## <a name="back-end-applications"></a>バックエンド アプリケーション  
 サービス指向ソリューションは、3 つのバックエンド アプリケーションと通信します。  
  
-   **PaymentTracker**アプリケーションが最近のお支払いのシミュレートされた一覧を返します。 **PaymentTracker** MQSeries キューから要求を読み取り、別の MQSeries キューへの応答を送信します。  
  
-   **PendingTransaction**アプリケーションは、顧客アカウントに対して保留中のトランザクションの合計を報告します。 このアプリケーションは、Microsoft Host Integration Server (HIS) を使用してメインフレーム コンピュータ上の CICS/COBOL プログラムと通信するWeb サービスです。  
  
-   SAP アプリケーションは、顧客の全体的な信用限度額に関する情報を提供します。 ソリューションは Web サービスとして SAP アプリケーションに接続します。 アプリケーションは [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] の SAP アダプターを使用して SAP システムと通信します。  
  
## <a name="pipelines"></a>パイプライン  
 サービス指向ソリューションは既定のパイプラインを使用して 2 つの場所: の受信パイプライン、 **CustomerServiceReceiveSend**オーケストレーション、および**CustomerService**オーケストレーションの送信パイプラインを**PaymentTracker**です。 これらのパイプラインは両方ともカスタム コンポーネントを使用します。  
  
 受信パイプライン**CustomerServiceReceiveSend** 、カスタム パーティの解決コンポーネントを含む**SSO Ticket Issuer Pipeline Component**です。 メッセージを**CustomerServiceReceiveSend**オーケストレーションが受信資格情報はありません。 このオーケストレーションは、メッセージが音声自動応答装置 (IVR) から送信された場合に行われる処理をシミュレートします。 カスタム パイプライン コンポーネントが、BizTalk 受信ホストのサービス アカウントを使用して資格情報を追加します。  
  
 これに対して、メッセージ、 **CustomerSericeNativeRequestResponse**オーケストレーションを既に受信資格情報を持っています。 Web サービスの仮想フォルダが統合セキュリティ用に構成され、SOAP の受信場所がエンタープライズ シングル サインオン (SSO) を統合するように構成されているので、SOAP アダプタによってメッセージのチケットが生成されます。  
  
 その他のカスタム パイプラインが表示されます、 **CustomerService**送信パイプラインを**PaymentTracker**アプリケーションです。 MQSeries ヘッダー設定パイプライン コンポーネントによって、2 つの MQSeries メッセージ ヘッダー プロパティの値が設定されます。 コンポーネントは、最初のメッセージ データ形式を設定 (**MQMD_Format**) の形式で、メッセージを示すように、 **MQCIH**構造体、CICS プログラムと通信するための一般的なです。 2 番目、データ自体の形式内で、 **MQCIH**構造 (**MQCIH_Format**)、メッセージは、文字列の表示に設定されています。  
  
 使用して、 **MQCIH**形式を使用すると、ユーザー ID とパスワードを渡す、 **MQCIH**構造体。 SSO 関連アプリケーションを Payment Tracking システムのユーザーに渡された Id に、BizTalk アプリケーションの Windows ユーザー ID をマップする、 **MQCIH**構造体。  
  
> [!NOTE]
>  ソリューションのインライン バージョンは、オーケストレーションから同じパイプラインを呼び出して使用するので、 パイプライン コードを再使用することができます。  
  
## <a name="client-application"></a>クライアント アプリケーション  
 ソリューションには、C# で記述されたクライアント アプリケーションが含まれています。 このクライアント アプリケーションを使用して、要求を SOAP または MQSeries メッセージとして送信し、結果を検証できます。  
  
## <a name="other-assemblies"></a>その他のアセンブリ  
 アプリケーションには、上の概要図に示されていない補助アセンブリがいくつか含まれています。 **ユーティリティ**ソリューションのアセンブリ ユーティリティ関数です。  
  
 **ErrorHelper**アセンブリには、メッセージ、エラー コードに変換し、エラー メッセージをエラー コードに変換するクラスが含まれています。  
  
 **ServiceLevelTracking**アセンブリには、ビジネス アクティビティ監視 (BAM) API を使用して、サービス レベル契約データを追跡するヘルパー メソッドが含まれます。  
  
 **ConfigHelper**アセンブリには、ソリューションからの構成値を取得するヘルパ メソッドが含まれている、 **SSOConfigStore**アプリケーションです。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)   
 [ファイル インベントリ サービス指向ソリューション](../core/file-inventory-for-the-service-oriented-solution.md)