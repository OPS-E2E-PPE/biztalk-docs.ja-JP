---
title: コンポーネントのビジネス プロセス管理ソリューション |Microsoft Docs
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
ms.openlocfilehash: 195d40becd4eb35b757379c4d3c51c4feeb4f684
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356703"
---
# <a name="components-of-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのコンポーネント
このセクションでは、ビジネス プロセス管理ソリューションの BizTalk Server の主要コンポーネントについて説明します。 ソース ファイルについては、次を参照してください。 [、ビジネス プロセス管理ソリューションのファイルの在庫](../core/file-inventory-for-the-business-process-management-solution.md)します。  
  
## <a name="orchestrations"></a>オーケストレーション  
 これには 2 つの主なオーケストレーションがあります。**OrderBroker**と**OrderManager**します。 **OrderBroker**オーケストレーションは、Web サービスを通じて、または FTP を介したバッチ処理で顧客の要求を受け入れるし、Microsoft メッセージ キュー (MSMQ) キューを後方への返信を送信します。 要求の移動、 **OrderBroker**を**OrderManager**します。 2 つのオーケストレーションは、メッセージ ボックス データベースを介して直接バインドされています。  
  
 **OrderManager**を使用して 2 つの非同期処理ステージを通して要求を実行、 **CableOrder1**と**CableOrder2**オーケストレーションします。 まとめて、 **CableOrder1**と**CableOrder2**オーケストレーションは、1 つのビジネス プロセスを表します。 ただし、プロセスは、注文処理を妨げずにステージを変更できるようにまで、2 つのオーケストレーションに分けられています。 ステージのデザインの詳細についてを参照してください「ビジネス プロセスの分割」 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。  
  
 **CableOrder1**オーケストレーションは、**検証**オーケストレーションが注文を検証し、要求コードをアクションに変換する、順序を分析して、Analyze オーケストレーションを呼び出すし、呼び出します**Activate**、**キャンセル**、または**変更**に応じて必要なアクションのオーケストレーション。 **CableOrder2**呼び出すことによってオーケストレーションが注文の完了を処理、**完了**オーケストレーションします。 注意して**CableOrder1**と**CableOrder2**を使用して、**呼び出す**図形を下位のオーケストレーションを呼び出します。  
  
> [!NOTE]
>  **キャンセル**オーケストレーションには呼び出す補正ブロックが含まれています、 **Activate**オーケストレーションします。 これにより、順序が正しく、取り消し要求に対する補正の一部として復元することができます。  
  
 **CableOrder1**と**CableOrder2**オーケストレーションは直接バインドを使用します。 これらのオーケストレーションの直接バインドの詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションの実装が強調表示](../core/implementation-highlights-of-the-business-process-management-solution.md)します。  
  
 これらを使用して、処理中に中断できるように、オーケストレーションの多くが書き込まれる、 **Interrupt**オーケストレーションします。 割り込みメカニズムの詳細については、次を参照してください。[プロセス マネージャのロジック](../core/process-manager-logic.md)します。  
  
## <a name="back-end-applications"></a>バックエンド アプリケーション  
 ビジネス プロセス管理ソリューションでは、バックエンド アプリケーションのすべてのシミュレーションを使用します。 **CableOrder1**、 **CableOrder2**、すべてを使用するオーケストレーションは、特殊なを使用および**OrderHandler**オブジェクト。 **OrderHandler** .NET リモート処理を使用して、注文管理システムのシミュレーションと通信します。 **CableProvisioningSystemClient**と**BTSScnBPMProvisioning** (、 **CableProvisioningSystemServer**プロジェクト) アセンブリのフロント エンドとバックエンドの両端をシミュレートします。それぞれのシステムを管理する順序。  
  
 ソリューションは、Windows フォーム アプリケーションを使用して**BSTScnBPMFacilities** (、 **FacilitiesSimulator**プロジェクト)、機能要求を処理する MSMQ サーバーをシミュレートします。  
  
 オーケストレーションは、これらのコンポーネントに加えて、注文とその処理の履歴を維持するために SQL Server データベースにエントリを作成します。  
  
## <a name="pipelines"></a>パイプライン  
 ソリューションでは、BizTalk 管理コンソールまたはバインド ファイルで構成されている既定の標準パイプラインのみを使用します。 パイプラインには、ただし、広範に利用インスタンスごとの構成。 FTP によって送信された注文の受信ポートでは、エンベロープを構成するのにインスタンスごとの構成を使用します。 インスタンスごとの構成の詳細については、次を参照してください。[パイプラインをデプロイする方法](../core/how-to-deploy-pipelines.md)します。  
  
## <a name="custom-adapter"></a>カスタム アダプター  
 ソリューションはカスタム アダプタを使用して、 **OpsAdapter**で検出されたいくつかのエラーを処理する、 **OrderManager**と**ErrorHandler**オーケストレーションします。 ソリューションでは、エラーを報告が指定されているポートでアダプターを使用します。 アダプターは、エラーを受け取り、オペレーション システムに送ります。 エラー報告の詳細については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。  
  
## <a name="client-application"></a>クライアント アプリケーション  
 ソリューションにはによって ASP.NET Web ページが含まれています、C#プログラム**CSRMain.aspx**、カスタマ サービス システムをシミュレートするためにします。  
  
## <a name="other-assemblies"></a>その他のアセンブリ  
 ソリューションは 2 つの追加アセンブリを使用して**スキーマ**と**ユーティリティ**します。 **スキーマ**などに異なるオーケストレーション間通信を行うため、ソリューションを使用してメッセージを定義するアセンブリ、 **Interrupt**メッセージ。 ソリューションで定義されているいくつかの .NET メッセージも使用して、 **SchemaClasses**アセンブリ。  
  
 **ユーティリティ**アセンブリには、ユーティリティ クラスと、SSO シークレット ストアから構成値を読み取ると、エラー処理を支援する、ソリューションに特定の例外の種類の定義に、メッセージの処理に役立つメソッドが含まれています。 アセンブリにも含まれています、 **Recaller**オブジェクト。  
  
 他のアセンブリに含まれるマップやスキーマ アセンブリなど**OrderBrokerMaps**、 **OrderBrokerSchemas**、**マップ**、 **MessagingSchemas**、および**SchemaClasses**します。  
  
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