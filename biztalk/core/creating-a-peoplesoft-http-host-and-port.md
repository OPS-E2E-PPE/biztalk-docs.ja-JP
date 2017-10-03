---
title: "PeopleSoft HTTP ホストおよびポートを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673b2a2acdcd5248391f245ab990d424aefd298
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a>PeopleSoft の HTTP ホストとポートを作成する
PeopleSoft のメッセージ公開アーキテクチャは、Integration Broker と呼ばれています。 Integration Broker の主なコンポーネントは次のとおりです。  
  
-   ゲートウェイ  
  
-   公開ノード  
  
-   サブスクライバー ノード  
  
 これら 3 つが連携して、HTTP リスナーの URL にメッセージを公開します。 公開ノードを設定する必要があります。 PeopleSoft には既定の公開ノードがあり、ローカル メッセージ ノードとも呼ばれます。 ノードおよび公開ノードのトランザクションをアクティブ化する必要があります。 サブスクリプション ノードの種類を外部ノードとして設定した後、ノードとトランザクションをアクティブ化する必要があります。 このノードの場合は、また、タイプを HTTP に設定し、接続情報も設定します。  
  
 PeopleSoft によってイベントの送信に使用される PeopleSoft HTTP ホストおよびポートを作成するには、PeopleSoft Integration Broker を使用します。 確認すること、メッセージがアクティブでルーティング」の手順を使用して、[メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [統合ゲートウェイと HTTP 出力コネクタを構成する方法](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [新しいゲートウェイ ノードを作成する方法](../core/how-to-create-a-new-gateway-node.md)  
  
-   [トランザクションを追加する方法](../core/how-to-add-a-transaction.md)  
  
-   [HTTP ノードをテストする方法](../core/how-to-test-the-http-node.md)