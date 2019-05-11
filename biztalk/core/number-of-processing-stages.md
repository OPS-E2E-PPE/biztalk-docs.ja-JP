---
title: 処理ステージの数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3db73745d137486011c2b56031f64b41f59f8639
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323528"
---
# <a name="number-of-processing-stages"></a><span data-ttu-id="387a6-102">処理ステージの数</span><span class="sxs-lookup"><span data-stu-id="387a6-102">Number of Processing Stages</span></span>
<span data-ttu-id="387a6-103">ソリューションは、(ステージを入れ替えてプロセスの実行時間の長い注文を中断することがなく変更を行うことができるようにに、注文プロセスをステージに分割します。</span><span class="sxs-lookup"><span data-stu-id="387a6-103">The solution separates the order process into stages, so that it is possible to modify the process (by replacing stages) without disrupting long-running orders.</span></span> <span data-ttu-id="387a6-104">プロセスをステージに分割する方法の詳細についてを参照してください「ビジネス プロセスの分割」 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="387a6-104">For more information about how the process was divided into stages, see "Dividing Business Processes" in [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="387a6-105">現在のバージョン ソリューションにはには、2 つだけの処理ステージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="387a6-105">The current version of the solution contains only two processing stages.</span></span> <span data-ttu-id="387a6-106">ただし、さらに多くを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="387a6-106">It could, however, contain many more.</span></span> <span data-ttu-id="387a6-107">ステージでは、プロセスをバージョンより多くのポイントを提供し、処理ステージの最新バージョンの操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="387a6-107">More stages provide more points where you can version the process and continue working on the latest version of a processing stage.</span></span> <span data-ttu-id="387a6-108">ただし、各ステージには、処理時間が増加メッセージ ボックス データベースを通過する調整メッセージのオーバーヘッドが導入されています。</span><span class="sxs-lookup"><span data-stu-id="387a6-108">However, each stage introduces the overhead of additional coordinating messages going through the MessageBox database, which increases processing time.</span></span> <span data-ttu-id="387a6-109">複数のステージの数が過剰なかどうかを判断するソリューションのパフォーマンスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="387a6-109">You must monitor the solution's performance to determine if the number of multiple stages is excessive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="387a6-110">参照</span><span class="sxs-lookup"><span data-stu-id="387a6-110">See Also</span></span>  
 <span data-ttu-id="387a6-111">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="387a6-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="387a6-112">プロセス マネージャーのロジック</span><span class="sxs-lookup"><span data-stu-id="387a6-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)