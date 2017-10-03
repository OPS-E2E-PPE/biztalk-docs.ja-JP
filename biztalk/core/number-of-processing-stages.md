---
title: "処理ステージの数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f61c5c348e54ea096c921cb6fc63f0db339dbf4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-processing-stages"></a><span data-ttu-id="ab2e2-102">処理ステージの数</span><span class="sxs-lookup"><span data-stu-id="ab2e2-102">Number of Processing Stages</span></span>
<span data-ttu-id="ab2e2-103">このソリューションでは、発注プロセスを複数のステージに分割します。これにより、長時間にわたる注文の処理を中断することなく、ステージを入れ替えてプロセスの変更を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-103">The solution separates the order process into stages, so that it is possible to modify the process (by replacing stages) without disrupting long-running orders.</span></span> <span data-ttu-id="ab2e2-104">プロセスをステージに分割する方法の詳細についてを参照してください「ビジネス プロセスの分割」[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-104">For more information about how the process was divided into stages, see "Dividing Business Processes" in [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="ab2e2-105">現バージョンのソリューションには 2 つの処理ステージしか含まれていませんが、</span><span class="sxs-lookup"><span data-stu-id="ab2e2-105">The current version of the solution contains only two processing stages.</span></span> <span data-ttu-id="ab2e2-106">さらに多くのステージを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-106">It could, however, contain many more.</span></span> <span data-ttu-id="ab2e2-107">ステージを増やすと、プロセスの変更バージョンを作成して処理ステージの最新バージョンで作業を継続していくことのできるポイントが増えます。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-107">More stages provide more points where you can version the process and continue working on the latest version of a processing stage.</span></span> <span data-ttu-id="ab2e2-108">ただし、ステージが増えるごとにメッセージ ボックス データベースを通過する調整メッセージ分のオーバーヘッドが追加され、処理時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-108">However, each stage introduces the overhead of additional coordinating messages going through the MessageBox database, which increases processing time.</span></span> <span data-ttu-id="ab2e2-109">ソリューションのパフォーマンスを監視して、ステージ数が多すぎないかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab2e2-109">You must monitor the solution's performance to determine if the number of multiple stages is excessive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2e2-110">参照</span><span class="sxs-lookup"><span data-stu-id="ab2e2-110">See Also</span></span>  
 <span data-ttu-id="ab2e2-111">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ab2e2-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="ab2e2-112">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="ab2e2-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)