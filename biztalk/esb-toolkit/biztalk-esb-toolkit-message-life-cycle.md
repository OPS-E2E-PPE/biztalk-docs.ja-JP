---
title: "BizTalk ESB Toolkit のメッセージのライフ サイクル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>BizTalk ESB Toolkit のメッセージのライフ サイクル
外部システムから開始され、最終的な送信先に到達する ESB 内を移動するメッセージのライフ サイクルを次に示します。  
  
1.  ランプでは、メッセージを受信します。 送信のパーティまたはクライアントによって、メッセージは可能性があります。 またはメッセージの処理命令を定義する旅程を含めることはできません。  
  
2.  ESB パイプライン コンポーネントを itinerary (存在する場合、SOAP ヘッダー内) にコピー、メッセージのコンテキストとして昇格させたプロパティ。 日程せず、メッセージを受信する場合は、メッセージのコンテンツやコンテキストによっては、データベースから適切な旅程を選択し、メッセージのコンテキストに旅行計画をコピーする、特定のパイプライン コンポーネントを構成できます。 メッセージの有効期間中は、旅行計画はメッセージ コンテキスト内で維持されます。  
  
3.  パイプラインで旅行計画が評価され、メッセージ ベースの itinerary サービスがメッセージを処理できます。 これらの itinerary サービスには、メッセージ変換可能性がありますも、ルーティングのエンドポイントを構成することもできます。  
  
4.  メッセージは、Microsoft BizTalk Server メッセージ ボックス データベースに発行されます。  
  
5.  BizTalk Server は、1 つまたは複数のサブスクライバーに対して、メッセージのメッセージとキューの昇格させたプロパティを評価します。  
  
6.  サブスクライバーでは、BizTalk Server の一般的なメカニズムを使用してメッセージを処理します。 サブスクライバーには、次のいずれかを指定できます。  
  
    -   直接バインドで構成されているフィルターを使用して BizTalk Server オーケストレーションの受信ポート  
  
    -   動的な BizTalk Server は送信ポートで、ESB 出口とも呼びますです。 旅行計画では、メッセージの処理を続行するポートを構成する方法を決定します。  
  
 Itinerary 入り口経由で到着するメッセージを代わりに、BizTalk Server オーケストレーションが ESB 処理のため、メッセージ ボックスのメッセージを発行することもできます。  
  
1.  メッセージが BizTalk Server オーケストレーション内で作成します。  
  
2.  メッセージのコンテキストには、ESB 行程が格納されます。  
  
3.  メッセージはメッセージ ボックス データベースに直接バインド ポート経由で公開します。