---
title: 手順 3:Fabrikam 0 C のパートナーの 2 つの取引先アグリーメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 4552f712-f226-423f-b06d-98e943e8efd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c937ecadc7b526bf67c11099aed2cd4aed100d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281124"
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a><span data-ttu-id="d56b7-102">手順 3:Fabrikam 0 C のパートナーの 2 つの取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="d56b7-102">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="d56b7-103">Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d56b7-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="d56b7-104">0c2 の新しい取引先パートナー アグリーメントを作成するプロセス PIP (Partner Interface)。</span><span class="sxs-lookup"><span data-stu-id="d56b7-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="d56b7-105">BTARN 管理コンソールを開始するには</span><span class="sxs-lookup"><span data-stu-id="d56b7-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="d56b7-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="d56b7-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="d56b7-107">2 取引先パートナー契約の 0 C を作成するには</span><span class="sxs-lookup"><span data-stu-id="d56b7-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="d56b7-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**契約**、 をポイント**新規**、順にクリックします**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="d56b7-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="d56b7-109">新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d56b7-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="d56b7-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d56b7-110">Use this</span></span>          |                        <span data-ttu-id="d56b7-111">目的</span><span class="sxs-lookup"><span data-stu-id="d56b7-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="d56b7-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="d56b7-112">**Name**</span></span>          |             <span data-ttu-id="d56b7-113">型**Fabrikam_To_Contoso_0C2**します。</span><span class="sxs-lookup"><span data-stu-id="d56b7-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="d56b7-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="d56b7-114">**Process Configuration**</span></span> |    <span data-ttu-id="d56b7-115">選択**STD_0C2_R01.02**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="d56b7-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="d56b7-116">**My Organization**</span></span>    |       <span data-ttu-id="d56b7-117">選択**Fabrikam**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-117">Select **Fabrikam** from the drop-down list.</span></span>        |
   | <span data-ttu-id="d56b7-118">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="d56b7-118">**Partner Organization**</span></span>  |        <span data-ttu-id="d56b7-119">選択**Contoso**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="d56b7-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="d56b7-120">**RNIF Version**</span></span>      |       <span data-ttu-id="d56b7-121">選択**V02.00.01**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="d56b7-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="d56b7-122">**Home Role**</span></span>       | <span data-ttu-id="d56b7-123">選択**Initiator (開始)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-123">Select **Initiator (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="d56b7-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="d56b7-124">**Usage**</span></span>         |         <span data-ttu-id="d56b7-125">選択**テスト**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="d56b7-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="d56b7-126">をクリックして、**ポート**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d56b7-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="d56b7-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d56b7-127">Use this</span></span>    |                          <span data-ttu-id="d56b7-128">目的</span><span class="sxs-lookup"><span data-stu-id="d56b7-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="d56b7-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="d56b7-129">**Action URL**</span></span> | <span data-ttu-id="d56b7-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="d56b7-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="d56b7-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="d56b7-131">**Signal URL**</span></span> | <span data-ttu-id="d56b7-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="d56b7-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="d56b7-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="d56b7-133">**Sync URL**</span></span>  | <span data-ttu-id="d56b7-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="d56b7-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="d56b7-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d56b7-135">Click **OK**.</span></span>  

5. <span data-ttu-id="d56b7-136">右クリックし、 **Fabrikam_To_Contoso_0C2**アグリーメント、およびクリック**Activate**します。</span><span class="sxs-lookup"><span data-stu-id="d56b7-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d56b7-137">参照</span><span class="sxs-lookup"><span data-stu-id="d56b7-137">See Also</span></span>  
 [<span data-ttu-id="d56b7-138">手順 4:Fabrikam 0C4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="d56b7-138">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)