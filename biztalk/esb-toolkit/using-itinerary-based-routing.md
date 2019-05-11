---
title: スケジュールに基づくルーティングを使用して |Microsoft Docs
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
ms.openlocfilehash: 3b09610d1c8952ae077fc872e7cd0c073a33eef4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396450"
---
# <a name="using-itinerary-based-routing"></a>スケジュールに基づくルーティングを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュールに基づくメッセージのルーティング シナリオを有効にすると、特定のメッセージの処理のシーケンスのステップに回覧用紙がパターンを実装することでデザイン時に認識できないため、メッセージごとに異なる場合がありますを提供します。 このパターンの実装では、ルーティング スリップを使用して、XML 形式でこれらの手順のコレクションを表現するし、どの手順が実行時に発生する必要がありますを決定します。 「ESB 行程」と呼ばれる頻繁に回覧用紙の状態は、手順は、によって処理されるメッセージに対して実行する必要がありますを定義する宣言型の命令の順序付けされたセット[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントと BizTalk Server ランタイム。 ESB スケジュールで指定された特定の処理命令が関連付けられている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントで、「ESB スケジュール サービス」ですとも呼ばれます。 ESB スケジュール サービスの目的は、処理命令を実行し、回覧先を示す次の命令の待機中の状態を更新するには。  

 このセクションの処理のスケジュールに基づく機能を説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 ここで説明する内容は次のとおりです。  

- [ESB スケジュール管理](../esb-toolkit/esb-itinerary-management.md)  

- [オンランプとオフランプ](../esb-toolkit/on-ramps-and-off-ramps.md)  

- [スケジュール サービスとしてメッセージングかオーケストレーションを選択する](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  

- [パイプライン コンポーネントを利用し、既存のスケジュールを選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  

- [パイプライン コンポーネントを利用し、スケジュールを読み取る](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  

- [パイプライン コンポーネントを利用し、送信請求 - 応答のスケジュールをキャッシュする](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  

- [スケジュール サブスクライバーを作成する](../esb-toolkit/creating-itinerary-subscribers.md)  

- [スケジュール サービスを実行する](../esb-toolkit/executing-an-itinerary-service.md)  

- HYPERLINK"<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>"[スケジュールに基づくルーティング アイテム](../esb-toolkit/itinerary-based-routing-artifacts.md)
