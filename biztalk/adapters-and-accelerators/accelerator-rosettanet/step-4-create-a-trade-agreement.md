---
title: "手順 4: 取引先アグリーメントの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b94acad2b71694223b0566f86edfcfa86610099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-trade-agreement"></a><span data-ttu-id="04fb6-102">手順 4: 取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="04fb6-102">Step 4: Create a Trade Agreement</span></span>
<span data-ttu-id="04fb6-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、ホーム組織と取引先組織間の取引アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="04fb6-103">In this step, you create a trade agreement between the home and partner organization using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span>  
  
### <a name="to-create-a-trade-agreement"></a><span data-ttu-id="04fb6-104">取引アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="04fb6-104">To create a trade agreement</span></span>  
  
1.  <span data-ttu-id="04fb6-105"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン > Accelerator for RosettaNet**を右クリックして**契約** をクリックして**新しい**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="04fb6-105">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version> Accelerator for RosettaNet**, right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="04fb6-106">**新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="04fb6-106">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="04fb6-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="04fb6-107">Use this</span></span>|<span data-ttu-id="04fb6-108">目的</span><span class="sxs-lookup"><span data-stu-id="04fb6-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="04fb6-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="04fb6-109">**Name**</span></span>|<span data-ttu-id="04fb6-110">型**取引アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="04fb6-110">Type **Trade Agreement**.</span></span>|  
    |<span data-ttu-id="04fb6-111">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="04fb6-111">**Process Configuration**</span></span>|<span data-ttu-id="04fb6-112">選択**STD_0C1_R01.02**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="04fb6-112">Select **STD_0C1_R01.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="04fb6-113">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="04fb6-113">**My organization**</span></span>|<span data-ttu-id="04fb6-114">選択**ホーム**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="04fb6-114">Select **HOME** from the drop-down list.</span></span>|  
    |<span data-ttu-id="04fb6-115">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="04fb6-115">**Partner organization**</span></span>|<span data-ttu-id="04fb6-116">選択**パートナー**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="04fb6-116">Select **PARTNER** from the drop-down list.</span></span>|  
    |<span data-ttu-id="04fb6-117">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="04fb6-117">**Home role**</span></span>|<span data-ttu-id="04fb6-118">選択**イニシエーター**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="04fb6-118">Select **Initiator** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="04fb6-119">**新しいアグリーメントのプロパティ** ダイアログ ボックスで、**ポート** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="04fb6-119">In the **New Agreement Properties** dialog box, on the **Ports** tab, do the following:</span></span>  
  
    |<span data-ttu-id="04fb6-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="04fb6-120">Use this</span></span>|<span data-ttu-id="04fb6-121">目的</span><span class="sxs-lookup"><span data-stu-id="04fb6-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="04fb6-122">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="04fb6-122">**Action URL**</span></span>|<span data-ttu-id="04fb6-123">型**http://localhost/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="04fb6-123">Type **http://localhost/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="04fb6-124">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="04fb6-124">**Signal URL**</span></span>|<span data-ttu-id="04fb6-125">型**http://localhost/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="04fb6-125">Type **http://localhost/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="04fb6-126">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="04fb6-126">**Sync URL**</span></span>|<span data-ttu-id="04fb6-127">空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="04fb6-127">Leave blank.</span></span> <span data-ttu-id="04fb6-128">同期 URL は、同期 PIP (Partner Interface Process) には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="04fb6-128">Sync URL is not required for the synchronous Partner Interface Process (PIP).</span></span>|  
  
4.  <span data-ttu-id="04fb6-129">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="04fb6-129">Click **Apply**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="04fb6-130">取引アグリーメントを作成したら、アクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04fb6-130">After you create the trade agreement, you must activate it.</span></span>  
  
### <a name="to-activate-the-trade-agreement"></a><span data-ttu-id="04fb6-131">取引アグリーメントをアクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="04fb6-131">To activate the trade agreement</span></span>  
  
-   <span data-ttu-id="04fb6-132">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックして**契約**を右クリックして**取引先アグリーメント**をクリックして結果ペイン**Activate**.</span><span class="sxs-lookup"><span data-stu-id="04fb6-132">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], click **Agreements**, right-click **Trade Agreement** in the results pane, and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04fb6-133">参照</span><span class="sxs-lookup"><span data-stu-id="04fb6-133">See Also</span></span>  
 [<span data-ttu-id="04fb6-134">手順 5: ミラー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="04fb6-134">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)