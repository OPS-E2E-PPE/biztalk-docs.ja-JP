---
title: サービスのコンポーネント指向のソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d8560a9dd9862ec2a265de729afd1879fb206f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356727"
---
# <a name="components-of-the-service-oriented-solution"></a>サービスのコンポーネント指向のソリューション
このセクションでは、サービス指向ソリューションの主な BizTalk Server コンポーネントについて説明します。 次の図は、ソリューションの主なコンポーネントを示しています。  
  
 ![サービス指向ソリューションのフロー ダイアグラム](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")  
  
 サービス指向ソリューションには、3 つのバージョンのオーケストレーションがあります。  
  
- 3 つのバックエンド アプリケーションのすべてがスタブとして作成されるバージョン  
  
- 3 つのバックエンド アプリケーションのすべてがインラインで呼び出されるバージョン  
  
- アプリケーションに接続するためにアダプタを使用するバージョン  
  
  オーケストレーションのすべてのバージョンは、SDK\Senarios\SO\BTSSoln\Orchestrations ディレクトリにあります。  
  
  インライン バージョンのオーケストレーションでは、ソリューション内で要求と応答の間の待機時間が最短になります。  
  
  ソース ファイルについては、次を参照してください。[サービス指向ソリューションのファイルの在庫](../core/file-inventory-for-the-service-oriented-solution.md)します。  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a>サービス指向ソリューションのオーケストレーション  
 3 つのオーケストレーション**CustomerServiceReceiveSend**、 **CustomerServiceNativeRequestResponse**、および**CustomerService**ソリューションの大部分を作成します。 **CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**オーケストレーションが呼び出すフロント エンドとして機能、 **CustomerService**オーケストレーションします。 **CustomerService**オーケストレーション作業のほとんどでは、バックエンド アプリケーションに要求を送信、返信を収集、1 つのメッセージに返信を結合すること、およびフロント エンドを適切なメッセージを送信します。オーケストレーションです。 フロント エンド オーケストレーションを呼び出すため、 **CustomerService**オーケストレーション、フロント エンド オーケストレーションまで、 **CustomerService**オーケストレーションが終了します。  
  
 ソリューションが公開、 **CustomerServiceNativeRequestResponse**オーケストレーションを Web サービスとして。 **CustomerServiceReceiveSend**オーケストレーションは、MQSeries キューからメッセージを受け取る。  
  
## <a name="back-end-applications"></a>バックエンド アプリケーション  
 サービス指向ソリューションは、3 つのバックエンド アプリケーションと通信します。  
  
- **PaymentTracker**アプリケーションには、最近の支払いのシミュレートされた一覧が返されます。 **PaymentTracker** MQSeries キューから要求を読み取り、別の MQSeries キューへの応答を送信します。  
  
- **PendingTransaction**アプリケーションは、顧客アカウントに対して保留中のトランザクションの合計を報告します。 このアプリケーションは、Microsoft Host Integration Server (HIS) を使用してメインフレーム コンピュータ上の CICS/COBOL プログラムと通信するWeb サービスです。  
  
- SAP アプリケーションは、顧客の全体的な信用限度額に関する情報を提供します。 ソリューションは Web サービスとして SAP アプリケーションに接続します。 アプリケーションは [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] の SAP アダプターを使用して SAP システムと通信します。  
  
## <a name="pipelines"></a>パイプライン  
 サービス指向ソリューションは、2 つの場所で既定のパイプラインを使用して: の受信パイプライン、 **CustomerServiceReceiveSend**オーケストレーション、および**CustomerService**オーケストレーションの送信パイプラインを**PaymentTracker**します。 これらのパイプラインは両方ともカスタム コンポーネントを使用します。  
  
 受信パイプライン**CustomerServiceReceiveSend** 、カスタム パーティの解決コンポーネントを含む**SSO Ticket Issuer Pipeline Component**します。 メッセージを**CustomerServiceReceiveSend**オーケストレーションが受信資格情報はありません。 このオーケストレーションは、メッセージが音声自動応答装置 (IVR) から送信された場合に行われる処理をシミュレートします。 カスタム パイプライン コンポーネントが、BizTalk 受信ホストのサービス アカウントを使用して資格情報を追加します。  
  
 これに対して、メッセージ、 **CustomerSericeNativeRequestResponse**オーケストレーションを既に受信資格情報を持っています。 Web サービスの仮想フォルダが統合セキュリティ用に構成され、SOAP の受信場所がエンタープライズ シングル サインオン (SSO) を統合するように構成されているので、SOAP アダプタによってメッセージのチケットが生成されます。  
  
 その他のカスタムのパイプラインが表示されます、 **CustomerService**送信パイプライン、 **PaymentTracker**アプリケーション。 MQSeries ヘッダー設定パイプライン コンポーネントによって、2 つの MQSeries メッセージ ヘッダー プロパティの値が設定されます。 コンポーネントが 1 つ目のメッセージのデータ形式を設定 (**MQMD_Format**)、メッセージがの形式であることを示す、 **MQCIH**構造、CICS プログラムと通信するための一般的な。 2 番目のデータ自体の形式内で、 **MQCIH**構造 (**MQCIH_Format**) をメッセージが文字列に設定されています。  
  
 使用して、 **MQCIH**形式を使用すると、ユーザー ID とパスワードを渡す、 **MQCIH**構造体。 SSO 関連アプリケーションは、Payment Tracking システムのユーザーに渡された Id に、BizTalk アプリケーションの Windows ユーザー ID をマップ、 **MQCIH**構造体。  
  
> [!NOTE]
>  ソリューションのインライン バージョンは、オーケストレーションから同じパイプラインを呼び出して使用するので、 パイプライン コードを再使用することができます。  
  
## <a name="client-application"></a>クライアント アプリケーション  
 ソリューションには、C# で記述されたクライアント アプリケーションが含まれています。 このクライアント アプリケーションを使用して、要求を SOAP または MQSeries メッセージとして送信し、結果を検証できます。  
  
## <a name="other-assemblies"></a>その他のアセンブリ  
 アプリケーションには、上の概要図に示されていない補助アセンブリがいくつか含まれています。 **ユーティリティ**ソリューションのアセンブリのユーティリティ関数。  
  
 **ErrorHelper**アセンブリには、メッセージ、エラー コードに変換し、エラー メッセージをエラー コードに変換するクラスが含まれています。  
  
 **ServiceLevelTracking**アセンブリには、ビジネス アクティビティ監視 (BAM) API を使用して、サービス レベル アグリーメントによってデータを追跡するヘルパー メソッドが含まれています。  
  
 **ConfigHelper**アセンブリにはからソリューションの構成値を取得するヘルパ メソッドが含まれています、 **SSOConfigStore**アプリケーション。  
  
## <a name="see-also"></a>参照  
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)   
 [サービス指向ソリューションのファイルの在庫](../core/file-inventory-for-the-service-oriented-solution.md)