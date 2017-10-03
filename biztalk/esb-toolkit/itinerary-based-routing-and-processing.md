---
title: "行程ベースのルーティングと処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8354538-e45c-487d-a380-59f497ea060f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5405e1e37834071bb4a1295b5e99bde3bf6ec846
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing-and-processing"></a>行程ベースのルーティングと処理
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]カスタム パイプライン コンポーネントを使用してルーティング スリップ パターンを実装します。 メッセージのメタデータとその他の要因は、適切な回覧、各メッセージに使用する、日程とも呼ばれるを決定に使用されます。 この回覧できますメッセージ変換を実行するオーケストレーション サービスを呼び出すし、定義するステップのメッセージのルーティング[!INCLUDE[prague](../includes/prague-md.md)]中核となる BizTalk Server エンジンからメッセージの処理命令を効果的に分離することで実行されます。  
  
 行程の処理方法の詳細については、次を参照してください。[主要なシナリオと開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)です。