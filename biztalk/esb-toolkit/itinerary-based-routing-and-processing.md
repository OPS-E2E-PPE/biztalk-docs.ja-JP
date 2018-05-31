---
title: 行程ベースのルーティングと処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8354538-e45c-487d-a380-59f497ea060f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7600408837ed2ef40e11bc179bf0739fb15c5a61
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006747"
---
# <a name="itinerary-based-routing-and-processing"></a>行程ベースのルーティングと処理
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]カスタム パイプライン コンポーネントを使用してルーティング スリップ パターンを実装します。 メッセージのメタデータとその他の要因は、適切な回覧、各メッセージに使用する、日程とも呼ばれるを決定に使用されます。 この回覧では、メッセージ変換を実行する、オーケストレーション サービスを呼び出す、およびメッセージを BizTalk Server が実行するステップをルーティング、中核となる BizTalk Server エンジンからメッセージの処理命令を効果的に分離することを定義することができます。  
  
 行程の処理方法の詳細については、次を参照してください。[主要なシナリオと開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)です。