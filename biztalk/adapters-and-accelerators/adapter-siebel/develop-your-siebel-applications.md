---
title: BizTalk Server で Siebel アプリケーションの開発 |Microsoft Docs
description: WCF を使用して Siebel アプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)
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
ms.openlocfilehash: 6d65dd25f3b2bbcc90acda9fcdc5cb0eb3b2f5c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002427"
---
# <a name="develop-your-siebel-applications"></a>Siebel アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel の成果物の操作を呼び出します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]消費されることができます。  
  
-   で、BizTalk Server ソリューションに物理ポートのバインド。  
  
-   クライアント プロキシのインスタンスでメソッドの呼び出し。  
  
-   としてホストされる WCF サービスを使用します。  
  
-   によって、WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  
  
-   ADO.NET インターフェイス。  
  
## <a name="biztalk-vs-wcf-service-vs-wcf-channel-vs-adonet"></a>BizTalk と WCF サービスと WCF チャネルと ADO.NET
 次の表では:  
  
- 使用して Siebel システムで実行できるさまざまな操作を一覧表示、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
- アプローチのかを示します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、WCF チャネル モデル、または ADO.NET インターフェイス)、操作を実行するために使用できます。  
  
- 選択した方法を使用してタスクの実行について詳細情報へのリンクを提供します。  
  
|                                   タスク                                    |                                                                                       BizTalk Server                                                                                        |                                                                                    WCF サービス モデル                                                                                    |                                                                              WCF チャネル モデル                                                                               |                                                                                                                        ADO.NET インターフェイス                                                                                                                        |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ビジネス コンポーネントに対する基本的な Insert、Update、Delete、およびクエリの操作 |              [ビジネス コンポーネントを使用して BizTalk Server と Siebel アダプターに対する操作を実行します。](run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md)              |     [WCF サービス モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。](run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md)     | [WCF チャネル モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。](run-tasks-on-business-components-with-the-siebel-adapter-using-a-wcf-channel.md) | [Siebel ビジネス コンポーネントで SELECT クエリを実行](run-a-select-query-on-business-components-with-siebel.md)**注:** を使って選択操作を実行することができますのみ、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]します。 |
|             MVG フィールドを持つビジネス コンポーネントに対する操作             |   [MVG フィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行します。](run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md)    | [MVG フィールドを持つ WCF サービス モデルを使用して Siebel アダプターでのビジネス コンポーネントに対する操作を実行します。](work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md) |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |
|          候補リストのフィールドでビジネス コンポーネントに対する操作           | [候補リストのフィールドを使用して BizTalk Server と Siebel アダプターのビジネス コンポーネントに対する操作を実行します。](run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md) |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |
|                        ビジネス サービスを呼び出す                         |                [ビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプターを呼び出す](invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)                |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                    [Siebel ビジネス サービスに対して EXECUTE 操作を実行します。](run-an-execute-operation-on-business-services-with-siebel.md)                                                                    |
|            統合オブジェクトでのビジネス サービスを呼び出す            |           [Siebel アダプターを使用して統合オブジェクトでのビジネス サービス メソッドの呼び出し](run-business-service-methods-with-integration-objects-using-the-siebel-adapter.md)            |                                                                                                                                                                                         |                                                                                                                                                                              |                                                                                                                                                                                                                                                                 |

## <a name="next-steps"></a>次のステップ  
 このセクションのトピックでは提供情報、手順、および使用するアプリケーションの開発に役立つ例、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューションをプログラミングします。 

- [Siebel システムへの接続の作成](create-a-connection-to-the-siebel-system.md)
- [Visual Studio で Siebel 操作のメタデータを取得する](get-metadata-for-siebel-operations-in-visual-studio.md)
- [メタデータ ノード ID](metadata-node-ids1.md)
- [バインド プロパティの操作](read-about-biztalk-adapter-for-siebel-binding-properties.md)
- [Siebel アダプターを使用して BizTalk アプリケーションを開発する](develop-biztalk-applications-using-the-siebel-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発する](develop-siebel-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発する](develop-siebel-applications-using-the-wcf-channel-model3.md)
- [.NET Framework Data Provider for Siebel eBusiness Applications を使用する](use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
- [SharePoint での Siebel アダプターの使用](use-the-siebel-adapter-with-sharepoint.md)
- [サンプル](samples-for-the-siebel-adapter.md)
- [ServiceModel メタデータ ユーティリティ ツールを BizTalk Adapter for Siebel eBusiness Applications と一緒に使用する](use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)