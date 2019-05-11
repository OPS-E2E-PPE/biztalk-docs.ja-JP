---
title: PeopleSoft の HTTP ホストとポートを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18675298b03e380ed53629a74fff31dfb4680068
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390103"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a>PeopleSoft の HTTP ホストとポートを作成します。
PeopleSoft のメッセージ公開アーキテクチャは、統合ブローカーと呼ばれます。 統合ブローカーの主要なコンポーネントは次のとおりです。  
  
- ゲートウェイ  
  
- 公開ノード  
  
- サブスクライバー ノード  
  
  3 つすべてが連携して、HTTP リスナーの URL にメッセージを発行します。 発行を設定する必要がありますノード。 PeopleSoft が、既定の公開ノード、ローカル メッセージ ノードとも呼ばれます。 ノードおよび公開ノードのトランザクションを有効にする必要があります。 サブスクリプション ノードの種類を外部ノードとして設定して、ノードと、トランザクションをアクティブ化する必要があります。 このノードに対しても HTTP 接続情報を設定でき、型を設定します。  
  
  PeopleSoft の HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成するのにには、PeopleSoft Integration Broker を使用します。 メッセージでの手順を使用して、アクティブおよびルーティングが確認する[メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [統合ゲートウェイと HTTP 出力コネクタを構成する方法](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [新しいゲートウェイ ノードを作成する方法](../core/how-to-create-a-new-gateway-node.md)  
  
-   [トランザクションを追加する方法](../core/how-to-add-a-transaction.md)  
  
-   [HTTP ノードをテストする方法](../core/how-to-test-the-http-node.md)