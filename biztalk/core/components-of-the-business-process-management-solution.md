---
title: ビジネス コンポーネントのプロセス管理ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, back-end systems, process management solutions
- process management solution tutorial, client applications
- orchestrations, process management solutions
- adapters, process management solutions
- process management solution tutorial, adapters
- client applications, process management solutions
- process management solution tutorial, components
- process management solution tutorial, orchestrations
- pipelines, process management solutions
- process management solution tutorial, pipelines
- assemblies, process management solutions
- process management solution tutorial, assemblies
ms.assetid: e3ccebb9-b677-4c17-acd2-0f986f7bd3f0
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b63234dbf4a8dc62a620bf2b384b832e4887b0d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234146"
---
# <a name="components-of-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのコンポーネント
このセクションでは、ビジネス プロセス管理ソリューションの BizTalk Server 主要コンポーネントについて説明します。 ソース ファイルについては、次を参照してください。[ビジネス プロセス管理ソリューションのファイル一覧](../core/file-inventory-for-the-business-process-management-solution.md)です。  
  
## <a name="orchestrations"></a>オーケストレーション  
 2 つの主なオーケストレーションがある: **OrderBroker**と**OrderManager**です。 **OrderBroker**オーケストレーション Web サービスを介して、または FTP を介したバッチ処理で、顧客の要求を受け入れるし、Microsoft メッセージ キュー (MSMQ) キューを介して返さ応答を送信します。 後の要求、 **OrderBroker**を**OrderManager**です。 この 2 つのオーケストレーションはメッセージ ボックス データベースを介して直接バインドされています。  
  
 **OrderManager**を使用して 2 つの非同期処理ステージを通して要求を実行、 **CableOrder1**と**CableOrder2**オーケストレーションです。 まとめると、 **CableOrder1**と**CableOrder2**オーケストレーションは、1 つのビジネス プロセスを表します。 プロセスが 2 つのオーケストレーションに分割されているのは、注文の処理を妨げずにステージを変更できるようにするためです。 ステージの設計に関する詳細についてを参照してください「ビジネス プロセスの分割」[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
 **CableOrder1**オーケストレーションは、**検証**順序を検証し、アクション、要求コードに変換するオーケストレーションは、Analyze オーケストレーションは、注文を分析してから**Activate**、**キャンセル**、または**変更**によっては、必要なアクションのオーケストレーションです。 **CableOrder2**オーケストレーションを呼び出して、注文の完了を処理する、**完了**オーケストレーションです。 注意して**CableOrder1**と**CableOrder2**使用**呼び出す**下位のオーケストレーションを呼び出すための図形です。  
  
> [!NOTE]
>  **キャンセル**オーケストレーションには呼び出す補正ブロックが含まれています、 **Activate**オーケストレーションです。 これによって、取り消し要求に対する補正の一部として注文が正しく復元されます。  
  
 **CableOrder1**と**CableOrder2**オーケストレーションの直接バインドを使用します。 これらのオーケストレーションの直接バインドの詳細については、次を参照してください。[ビジネス プロセス管理ソリューションの実装が強調表示](../core/implementation-highlights-of-the-business-process-management-solution.md)です。  
  
 使用した処理中にそれらを中断できるように、オーケストレーションの多くが書き込まれる、 **Interrupt**オーケストレーションです。 割り込みメカニズムの詳細については、次を参照してください。[プロセス マネージャのロジック](../core/process-manager-logic.md)です。  
  
## <a name="back-end-applications"></a>バックエンド アプリケーション  
 ビジネス プロセス管理ソリューションでは、すべてのバックエンド アプリケーションのシミュレーションを使用しています。 **CableOrder1**、 **CableOrder2**、すべてを使用するオーケストレーション調べ、特殊な**OrderHandler**オブジェクト。 **OrderHandler** .NET リモート処理を使用して、注文管理システムのシミュレーションと通信します。 **CableProvisioningSystemClient**と**BTSScnBPMProvisioning** (、 **CableProvisioningSystemServer**プロジェクト) アセンブリのフロント エンドとバックエンドの両端をシミュレートします。それぞれのシステムを管理する順序です。  
  
 ソリューションは、Windows フォーム アプリケーションを使用して**BSTScnBPMFacilities** (、 **FacilitiesSimulator**プロジェクト)、機能要求を処理する MSMQ サーバーをシミュレートするためにします。  
  
 これらのコンポーネントに加えて、オーケストレーションは、注文とその処理の履歴を維持するために SQL Server データベースへのエントリ記入も行います。  
  
## <a name="pipelines"></a>パイプライン  
 BizTalk 管理コンソールまたはバインド ファイルで構成された既定の標準パイプラインのみが使用されます。 ただし、パイプラインはインスタンスごとの構成を使用します。 FTP によって送信された注文の受信ポートはインスタンスごとの構成を使用してエンベロープを構成します。 インスタンスごとの構成の詳細については、次を参照してください。[パイプラインを展開する方法](../core/how-to-deploy-pipelines.md)です。  
  
## <a name="custom-adapter"></a>カスタム アダプター  
 ソリューションは、カスタム アダプターを使用して、 **OpsAdapter**で検出されたいくつかのエラーを処理する、 **OrderManager**と**ErrorHandler**オーケストレーションです。 エラー報告が指定されているポートのアダプターが使用されます。 アダプターは受け取ったエラーを操作システムへ送ります。 エラー報告の詳細については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。  
  
## <a name="client-application"></a>クライアント アプリケーション  
 ソリューションには、c# プログラムによってバックアップされた ASP.NET Web ページが含まれています。 **CSRMain.aspx**、カスタマ サービス システムをシミュレートします。  
  
## <a name="other-assemblies"></a>その他のアセンブリ  
 ソリューションが 2 つの追加アセンブリを使用して**スキーマ**と**ユーティリティ**です。 **スキーマ**アセンブリなどの異なるオーケストレーション間通信するため、ソリューションを使用してメッセージを定義する、 **Interrupt**メッセージ。 ソリューションで定義されているいくつかの .NET メッセージも使用して、 **SchemaClasses**アセンブリ。  
  
 **ユーティリティ**アセンブリには、ユーティリティ クラスと、SSO シークレット ストアから構成値を読み取ると、エラー処理に役立てるために、ソリューションに固有の例外の種類を定義する、メッセージ処理に役立つメソッドが含まれています。 アセンブリにも含まれています、 **Recaller**オブジェクト。  
  
 他のアセンブリなどのマップおよびスキーマ アセンブリ**OrderBrokerMaps**、 **OrderBrokerSchemas**、**マップ**、 **MessagingSchemas**、および**SchemaClasses**です。  
  
 **ServiceLevelTracking**アセンブリには、注文や処理を追跡するために BAM と共に使用される一般的なアイテムが含まれています。 各ステージで使用される、注文処理アクションは、 **CableOrderActions**アセンブリ。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションでの処理](../core/processing-in-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [BAM によるビジネス プロセス管理ソリューションの監視](../core/monitoring-the-business-process-management-solution-with-bam.md)   
 [ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューション リファレンス](../core/business-process-management-solution-reference.md)   
 [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのファイル一覧](../core/file-inventory-for-the-business-process-management-solution.md)