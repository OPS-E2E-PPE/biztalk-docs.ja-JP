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
ms.openlocfilehash: 7600408837ed2ef40e11bc179bf0739fb15c5a61
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="itinerary-based-routing-and-processing"></a><span data-ttu-id="36850-102">行程ベースのルーティングと処理</span><span class="sxs-lookup"><span data-stu-id="36850-102">Itinerary-Based Routing and Processing</span></span>
<span data-ttu-id="36850-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]カスタム パイプライン コンポーネントを使用してルーティング スリップ パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="36850-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a routing slip pattern through the use of custom pipeline components.</span></span> <span data-ttu-id="36850-104">メッセージのメタデータとその他の要因は、適切な回覧、各メッセージに使用する、日程とも呼ばれるを決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="36850-104">Message metadata and other factors are used to determine the appropriate routing slip, also known as an itinerary, to be used for each message.</span></span> <span data-ttu-id="36850-105">この回覧では、メッセージ変換を実行する、オーケストレーション サービスを呼び出す、およびメッセージを BizTalk Server が実行するステップをルーティング、中核となる BizTalk Server エンジンからメッセージの処理命令を効果的に分離することを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="36850-105">This routing slip can perform message transformation, invoke orchestration services, and define message routing steps that BizTalk Server will execute, effectively decoupling message processing instructions from the core BizTalk Server engine.</span></span>  
  
 <span data-ttu-id="36850-106">行程の処理方法の詳細については、次を参照してください。[主要なシナリオと開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)です。</span><span class="sxs-lookup"><span data-stu-id="36850-106">For more information on how itineraries are processed, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>