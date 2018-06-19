---
title: BizTalk server、Siebel アプリケーションの開発 |Microsoft ドキュメント
description: Siebel を WCF を使用してアプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bc04906-6d64-433c-b357-797ec5883279
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c1535a3aa7861effdad998d4d997fbcdfced02c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222602"
---
# <a name="develop-your-siebel-applications"></a>Siebel アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel の成果物の操作を呼び出します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]消費されることができます。  
  
-   を介して、物理ポートには、BizTalk Server ソリューションでのバインドです。  
  
-   クライアント プロキシのインスタンス上のメソッドの呼び出しです。  
  
-   としてホストされる WCF サービスを使用します。  
  
-   WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  
  
-   ADO.NET インターフェイスです。  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk と WCF サービスと WCF チャネルと ADO.NET
 次の表では:  
  
-   Siebel システムを使用して、実行できるさまざまな操作を一覧表示、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
-   アプローチのかを示します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービスのモデル、WCF チャネル モデル、または ADO.NET インターフェイス)、操作を実行するために使用できます。  
  
-   選択した方法を使用するタスクの実行に関する詳細情報へのリンクを示します。  
  
|タスク|BizTalk Server|WCF サービスのモデル|WCF チャネル モデル|ADO.NET インターフェイス|  
|----------|--------------------|-----------------------|-----------------------|-----------------------|  
|ビジネス コンポーネントの基本的な Insert、Update、Delete、およびクエリの操作|[ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターに対する操作を実行します。](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)|[WCF サービス モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行します。](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)|[WCF チャネル モデルを使用して、Siebel アダプターとビジネス コンポーネントでの操作を実行します。](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md)|[Siebel ビジネス コンポーネントに対して選択クエリを実行](run-a-select-query-on-business-components-with-siebel.md)**注:** を使用して、SELECT 操作を実行することができますのみ、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。|  
|MVG フィールドのビジネス コンポーネントに対する操作|[MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントでの操作を実行します。](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)|[WCF サービス モデルを使用して、Siebel アダプターと MVG フィールドのビジネス コンポーネントでの操作を実行します。](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md)|||  
|候補リストのフィールドのビジネス コンポーネントに対する操作|[候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行します。](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md)||||  
|ビジネス サービスを呼び出す|[ビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプターを呼び出し](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)|||[Siebel ビジネス サービスの実行操作を実行します。](run-an-execute-operation-on-business-services-with-siebel.md)|  
|統合オブジェクトとのビジネス サービスを呼び出す|[Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドを呼び出す](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)||||  

## <a name="next-steps"></a>次の手順  
 このセクションのトピックでは提供情報、プロシージャ、および例を使用するアプリケーションを開発するため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューションのプログラミングします。 

- [Siebel システムへの接続を作成します。](create-a-connection-to-the-siebel-system.md)
- [Visual Studio での Siebel 操作のメタデータを取得します。](get-metadata-for-siebel-operations-in-visual-studio.md)
- [メタデータのノード Id](metadata-node-ids1.md)
- [バインドのプロパティの使用](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [Siebel アダプターを使用して BizTalk アプリケーションを開発します。](develop-biztalk-applications-using-the-siebel-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発します。](develop-siebel-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発します。](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [SharePoint での Siebel アダプターを使用します。](use-the-siebel-adapter-with-sharepoint.md)
- [サンプル](samples-for-the-siebel-adapter.md)
- [BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用します。](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)