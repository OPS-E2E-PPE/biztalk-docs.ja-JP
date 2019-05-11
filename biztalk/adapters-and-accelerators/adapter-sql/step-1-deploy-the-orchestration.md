---
title: 手順 1:オーケストレーションの展開 |Microsoft Docs
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
ms.openlocfilehash: 570b5e0996864fa047c2b196338c1294804a5b11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367888"
---
# <a name="step-1-deploy-the-orchestration"></a><span data-ttu-id="846ac-102">手順 1:オーケストレーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="846ac-102">Step 1: Deploy the Orchestration</span></span>
<span data-ttu-id="846ac-103">![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span><span class="sxs-lookup"><span data-stu-id="846ac-103">![Step 1 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")</span></span>  
  
 <span data-ttu-id="846ac-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="846ac-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="846ac-105">**目標:** この手順では、オーケストレーション ソリューションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="846ac-105">**Objective:** In this step, deploy the orchestration solution.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="846ac-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="846ac-106">Prerequisites</span></span>  
 <span data-ttu-id="846ac-107">」の手順を完了する必要があります[レッスン 4。注文テーブルに対して挿入操作を実行](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)します。</span><span class="sxs-lookup"><span data-stu-id="846ac-107">You must have completed the steps in [Lesson 4: Perform an Insert Operation on the Purchase Order Table](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md).</span></span>  
  
### <a name="to-deploy-the-solution"></a><span data-ttu-id="846ac-108">ソリューションを展開するには</span><span class="sxs-lookup"><span data-stu-id="846ac-108">To deploy the solution</span></span>  
  
1.  <span data-ttu-id="846ac-109">ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="846ac-109">In Solution Explorer, right-click the solution name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="846ac-110">プロパティ ページ ダイアログ ボックスのツリー コントロールで展開**構成プロパティ**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="846ac-110">In the properties pages dialog box, in the tree control, expand **Configuration Properties**, and then click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="846ac-111">**構成**] ページの [、**デプロイ**列は、BizTalk プロジェクトに対して、チェック ボックスを選択しをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="846ac-111">On the **Configuration** page, in the **Deploy** column, select the check box against the BizTalk project, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="846ac-112">ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="846ac-112">In Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
     <span data-ttu-id="846ac-113">画面の下部にある出力ウィンドウは次のようになります。**展開します。1 正常終了、0 失敗、0 スキップ**します。</span><span class="sxs-lookup"><span data-stu-id="846ac-113">The Output pane at the bottom of the screen should read: **Deploy: 1 succeeded, 0 failed, 0 skipped**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="846ac-114">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="846ac-114">What did I just do?</span></span>  
 <span data-ttu-id="846ac-115">この手順では、BizTalk オーケストレーションをデプロイ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="846ac-115">In this step, you deployed the BizTalk orchestration to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="846ac-116">次の手順</span><span class="sxs-lookup"><span data-stu-id="846ac-116">Next Steps</span></span>  
 <span data-ttu-id="846ac-117">物理ポートを作成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、」の説明に従って[手順 2。ポートを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)します。</span><span class="sxs-lookup"><span data-stu-id="846ac-117">You create the physical ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, as described in [Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846ac-118">参照</span><span class="sxs-lookup"><span data-stu-id="846ac-118">See Also</span></span>  
 <span data-ttu-id="846ac-119">[手順 2:ポートを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span><span class="sxs-lookup"><span data-stu-id="846ac-119">[Step 2: Configure the Ports](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md) </span></span>  
 [<span data-ttu-id="846ac-120">レッスン 5: ソリューションを展開する</span><span class="sxs-lookup"><span data-stu-id="846ac-120">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)