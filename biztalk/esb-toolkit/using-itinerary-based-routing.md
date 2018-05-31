---
title: 行程ベースのルーティングを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc0a0eb3a212efccd4ddbe4e275042ecb850095
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295250"
---
# <a name="using-itinerary-based-routing"></a>行程ベースのルーティングを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程ベースのメッセージのルーティングを特定のメッセージの処理のシーケンスのステップとシナリオを有効にする回覧パターンを実装することによってデザイン時に認識できないため、メッセージごとに異なる場合がありますを提供します。 このパターンの実装では、ルーティング スリップを使用して、XML 形式でこれらの手順のコレクションを表現するし、どの手順が実行時に発生する必要がありますを決定します。 「ESB 行程」として頻繁に参照回覧の状態は、によって処理されるメッセージに対して実行する必要がありますの手順を定義する宣言型の命令の順序付きセットは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントと、BizTalk Server ランタイム。 ESB 行程で指定された特定の処理命令に関連付けられている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントであり、「ESB itinerary サービスです」とも呼びますが、。 ESB itinerary サービスの目的は、処理命令を実行し、回覧を示す次の命令の待機中の状態を更新します。  
  
 このセクションの日程ベースの処理機能の説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 ここで説明する内容は次のとおりです。  
  
-   [ESB Itinerary 管理](../esb-toolkit/esb-itinerary-management.md)  
  
-   [ランプで、ランプ オフ](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [メッセージングの使い分けとオーケストレーション Itinerary サービス](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [パイプライン コンポーネントを使用して、既存の日程を選択するには](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [パイプライン コンポーネントを使用して、日程を読み取る](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [パイプライン コンポーネントを使用して、送信請求-応答の日程をキャッシュするには](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [Itinerary サブスクライバーを作成します。](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [Itinerary サービスを実行します。](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   ハイパーリンク"http://msdn.microsoft.com/en-us/library/ee236752 (BTS.10).aspx"[行程ベースのルーティング コンポーネント](../esb-toolkit/itinerary-based-routing-artifacts.md)