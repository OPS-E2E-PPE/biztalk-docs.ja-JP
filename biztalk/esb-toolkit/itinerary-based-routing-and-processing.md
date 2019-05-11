---
title: ルーティングと処理のスケジュールに基づく |Microsoft Docs
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
ms.openlocfilehash: 6593a9ff2a90f9b906352ecad1bec70e4f601994
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261544"
---
# <a name="itinerary-based-routing-and-processing"></a><span data-ttu-id="cabda-102">スケジュールに基づくルーティングと処理</span><span class="sxs-lookup"><span data-stu-id="cabda-102">Itinerary-Based Routing and Processing</span></span>
<span data-ttu-id="cabda-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]カスタム パイプライン コンポーネントを使用してルーティング スリップ パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="cabda-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] implements a routing slip pattern through the use of custom pipeline components.</span></span> <span data-ttu-id="cabda-104">メッセージのメタデータとその他の要因は、適切なルーティング スリップを各メッセージに使用する、スケジュールとも呼ばれますの決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cabda-104">Message metadata and other factors are used to determine the appropriate routing slip, also known as an itinerary, to be used for each message.</span></span> <span data-ttu-id="cabda-105">回覧用紙がこのでは、メッセージ変換を実行、オーケストレーションのサービスを呼び出す、およびメッセージを BizTalk Server を実行する手順のルーティング、中核となる BizTalk Server エンジンからのメッセージの処理命令を効果的に分離することを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="cabda-105">This routing slip can perform message transformation, invoke orchestration services, and define message routing steps that BizTalk Server will execute, effectively decoupling message processing instructions from the core BizTalk Server engine.</span></span>  
  
 <span data-ttu-id="cabda-106">スケジュールの処理方法の詳細については、次を参照してください。[主要なシナリオおよび開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)します。</span><span class="sxs-lookup"><span data-stu-id="cabda-106">For more information on how itineraries are processed, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>