---
title: 手順 4:取引アグリーメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa9be8b5435b212838a40059e784b0f54c17b36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280991"
---
# <a name="step-4-create-a-trade-agreement"></a><span data-ttu-id="ea333-102">手順 4:取引アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea333-102">Step 4: Create a Trade Agreement</span></span>
<span data-ttu-id="ea333-103">この手順で、Microsoft® を使用してホームとパートナーの組織間の取引アグリーメントを作成する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ea333-103">In this step, you create a trade agreement between the home and partner organization using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span>  

### <a name="to-create-a-trade-agreement"></a><span data-ttu-id="ea333-104">取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="ea333-104">To create a trade agreement</span></span>  

1. <span data-ttu-id="ea333-105">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン\>Accelerator for RosettaNet**、右クリックして**契約**、 をクリックして**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="ea333-105">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="ea333-106">**新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea333-106">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="ea333-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ea333-107">Use this</span></span>          |                     <span data-ttu-id="ea333-108">目的</span><span class="sxs-lookup"><span data-stu-id="ea333-108">To do this</span></span>                     |
   |---------------------------|----------------------------------------------------|
   |         <span data-ttu-id="ea333-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="ea333-109">**Name**</span></span>          |             <span data-ttu-id="ea333-110">型**売買契約**します。</span><span class="sxs-lookup"><span data-stu-id="ea333-110">Type **Trade Agreement**.</span></span>              |
   | <span data-ttu-id="ea333-111">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="ea333-111">**Process Configuration**</span></span> | <span data-ttu-id="ea333-112">選択**STD_0C1_R01.02**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ea333-112">Select **STD_0C1_R01.02** from the drop-down list.</span></span> |
   |    <span data-ttu-id="ea333-113">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="ea333-113">**My organization**</span></span>    |      <span data-ttu-id="ea333-114">選択**ホーム**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ea333-114">Select **HOME** from the drop-down list.</span></span>      |
   | <span data-ttu-id="ea333-115">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="ea333-115">**Partner organization**</span></span>  |    <span data-ttu-id="ea333-116">選択**パートナー**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ea333-116">Select **PARTNER** from the drop-down list.</span></span>     |
   |       <span data-ttu-id="ea333-117">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="ea333-117">**Home role**</span></span>       |   <span data-ttu-id="ea333-118">選択**イニシエーター**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="ea333-118">Select **Initiator** from the drop-down list.</span></span>    |


3. <span data-ttu-id="ea333-119">**新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**ポート** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ea333-119">In the **New Agreement Properties** dialog box, on the **Ports** tab, do the following:</span></span>  


   |    <span data-ttu-id="ea333-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ea333-120">Use this</span></span>    |                                         <span data-ttu-id="ea333-121">目的</span><span class="sxs-lookup"><span data-stu-id="ea333-121">To do this</span></span>                                         |
   |----------------|--------------------------------------------------------------------------------------------|
   | <span data-ttu-id="ea333-122">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="ea333-122">**Action URL**</span></span> |                   <span data-ttu-id="ea333-123">型 **<http://localhost/BTARNApp/RNIFReceive.aspx>** します。</span><span class="sxs-lookup"><span data-stu-id="ea333-123">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   | <span data-ttu-id="ea333-124">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="ea333-124">**Signal URL**</span></span> |                   <span data-ttu-id="ea333-125">型 **<http://localhost/BTARNApp/RNIFReceive.aspx>** します。</span><span class="sxs-lookup"><span data-stu-id="ea333-125">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   |  <span data-ttu-id="ea333-126">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="ea333-126">**Sync URL**</span></span>  | <span data-ttu-id="ea333-127">空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="ea333-127">Leave blank.</span></span> <span data-ttu-id="ea333-128">同期 URL が必要なため、同期プロセス PIP (Partner Interface) ではありません。</span><span class="sxs-lookup"><span data-stu-id="ea333-128">Sync URL is not required for the synchronous Partner Interface Process (PIP).</span></span> |


4. <span data-ttu-id="ea333-129">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="ea333-129">Click **Apply**, and then click **OK**.</span></span>  

   <span data-ttu-id="ea333-130">取引先アグリーメントを作成した後は、アクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea333-130">After you create the trade agreement, you must activate it.</span></span>  

### <a name="to-activate-the-trade-agreement"></a><span data-ttu-id="ea333-131">取引先アグリーメントをアクティブ化するには</span><span class="sxs-lookup"><span data-stu-id="ea333-131">To activate the trade agreement</span></span>  

- <span data-ttu-id="ea333-132">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックして**契約**を右クリックして**取引先アグリーメント**で結果ウィンドウをクリック**Activate**.</span><span class="sxs-lookup"><span data-stu-id="ea333-132">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], click **Agreements**, right-click **Trade Agreement** in the results pane, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ea333-133">参照</span><span class="sxs-lookup"><span data-stu-id="ea333-133">See Also</span></span>  
 [<span data-ttu-id="ea333-134">手順 5:ミラー アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="ea333-134">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)