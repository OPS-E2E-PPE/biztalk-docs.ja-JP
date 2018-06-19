---
title: '手順 1: 配置オーケストレーション |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8988fced-b2d5-4ee7-a851-20fc7c3dd087
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47565daf53f66fc5fc898e7c023ca09a34c78113
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224314"
---
# <a name="step-1-deploy-the-orchestration"></a><span data-ttu-id="287c6-102">手順 1: オーケストレーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="287c6-102">Step 1: Deploy the Orchestration</span></span>
<span data-ttu-id="287c6-103">![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="287c6-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="287c6-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="287c6-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="287c6-105">**目標:** このステップでオーケストレーション ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="287c6-105">**Objective:** In this step, deploy the orchestration solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="287c6-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="287c6-106">Prerequisites</span></span>  
 <span data-ttu-id="287c6-107">内の手順を完了する必要があります[レッスン 4: Purchase Order テーブルで挿入操作の実行](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)です。</span><span class="sxs-lookup"><span data-stu-id="287c6-107">You must have completed the steps in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
### <a name="to-deploy-the-solution"></a><span data-ttu-id="287c6-108">ソリューションを配置するには</span><span class="sxs-lookup"><span data-stu-id="287c6-108">To deploy the solution</span></span>  
  
1.  <span data-ttu-id="287c6-109">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="287c6-109">In Solution Explorer, right-click the solution name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="287c6-110">プロパティ ページ] ダイアログ ボックスのツリー コントロールで、[展開**構成プロパティ**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="287c6-110">In the properties pages dialog box, in the tree control, expand **Configuration Properties**, and then click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="287c6-111">**構成**] ページの [、**展開**列で、BizTalk プロジェクトに照らしてチェック ボックスをオンにし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="287c6-111">On the **Configuration** page, in the **Deploy** column, select the check box against the BizTalk project, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="287c6-112">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="287c6-112">In Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
     <span data-ttu-id="287c6-113">画面の下部にある出力ウィンドウを読み取る必要があります:**展開: 1 正常終了、0 失敗、0 スキップ**です。</span><span class="sxs-lookup"><span data-stu-id="287c6-113">The Output pane at the bottom of the screen should read: **Deploy: 1 succeeded, 0 failed, 0 skipped**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="287c6-114">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="287c6-114">What did I just do?</span></span>  
 <span data-ttu-id="287c6-115">この手順を BizTalk オーケストレーションが展開されている。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="287c6-115">In this step, you deployed the BizTalk orchestration to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="287c6-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="287c6-116">Next Steps</span></span>  
 <span data-ttu-id="287c6-117">物理ポートを作成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、」の説明に従って[手順 2: ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="287c6-117">You create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, as described in [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287c6-118">参照</span><span class="sxs-lookup"><span data-stu-id="287c6-118">See Also</span></span>  
 <span data-ttu-id="287c6-119">[手順 2: ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="287c6-119">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 [<span data-ttu-id="287c6-120">レッスン 5: ソリューションを配置します。</span><span class="sxs-lookup"><span data-stu-id="287c6-120">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)