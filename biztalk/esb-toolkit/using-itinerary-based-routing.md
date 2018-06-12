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
ms.openlocfilehash: 9a0e0dad0f49e07c0941614dd0130d0e77c459ab
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848986"
---
# <a name="using-itinerary-based-routing"></a>行程ベースのルーティングを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程ベースのメッセージのルーティングを特定のメッセージの処理のシーケンスのステップとシナリオを有効にする回覧パターンを実装することによってデザイン時に認識できないため、メッセージごとに異なる場合がありますを提供します。 このパターンの実装では、ルーティング スリップを使用して、XML 形式でこれらの手順のコレクションを表現するし、どの手順が実行時に発生する必要がありますを決定します。 「ESB 行程」として頻繁に参照回覧の状態は、によって処理されるメッセージに対して実行する必要がありますの手順を定義する宣言型の命令の順序付きセットは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントと、BizTalk Server ランタイム。 ESB 行程で指定された特定の処理命令に関連付けられている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントであり、「ESB itinerary サービスです」とも呼びますが、。 ESB itinerary サービスの目的は、処理命令を実行し、回覧を示す次の命令の待機中の状態を更新します。  
  
 このセクションの日程ベースの処理機能の説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 ここで説明する内容は次のとおりです。  
  
-   [ESB スケジュール管理](../esb-toolkit/esb-itinerary-management.md)  
  
-   [オンランプとオフランプ](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [スケジュール サービスとしてメッセージングかオーケストレーションを選択する](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [パイプライン コンポーネントを利用し、既存のスケジュールを選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [パイプライン コンポーネントを利用し、スケジュールを読み取る](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [パイプライン コンポーネントを利用し、送信請求 - 応答のスケジュールをキャッシュする](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [スケジュール サブスクライバーを作成する](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [スケジュール サービスを実行する](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   ハイパーリンク"http://msdn.microsoft.com/library/ee236752(BTS.10).aspx"[行程ベースのルーティング コンポーネント](../esb-toolkit/itinerary-based-routing-artifacts.md)