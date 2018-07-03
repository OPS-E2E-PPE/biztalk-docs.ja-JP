---
title: '手順 5: Contoso 3 a 2 取引先を作成するアグリーメントのパートナー |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: 5c602c9c-22bd-450f-bb14-6848b1414c03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d4004b7ac0d068a2f2621affc34f18ecf21f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970627"
---
# <a name="step-5-creating-the-contoso-3a2-trading-partner-agreement"></a><span data-ttu-id="21d9e-102">手順 5: Contoso 3 a 2 取引先パートナー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="21d9e-102">Step 5: Creating the Contoso 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="21d9e-103">Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="21d9e-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="21d9e-104">3A2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="21d9e-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="21d9e-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="21d9e-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="21d9e-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="21d9e-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="21d9e-107">3A2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="21d9e-107">To create the 3A2 trading partner agreement</span></span>  

1. <span data-ttu-id="21d9e-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**契約**、 をポイント**新規**、順にクリックします**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="21d9e-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="21d9e-109">**新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21d9e-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="21d9e-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="21d9e-110">Use this</span></span>          |                            <span data-ttu-id="21d9e-111">目的</span><span class="sxs-lookup"><span data-stu-id="21d9e-111">To do this</span></span>                            |
   |---------------------------|------------------------------------------------------------------|
   |         <span data-ttu-id="21d9e-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="21d9e-112">**Name**</span></span>          |                <span data-ttu-id="21d9e-113">型**Fabrikam_To_Contoso_3A2**します。</span><span class="sxs-lookup"><span data-stu-id="21d9e-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>                 |
   | <span data-ttu-id="21d9e-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="21d9e-114">**Process Configuration**</span></span> |      <span data-ttu-id="21d9e-115">選択**STD_3A2_R02.00.00A**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>      |
   |    <span data-ttu-id="21d9e-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="21d9e-116">**My Organization**</span></span>    |           <span data-ttu-id="21d9e-117">選択**Contoso**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-117">Select **Contoso** from the drop-down list.</span></span>            |
   | <span data-ttu-id="21d9e-118">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="21d9e-118">**Partner Organization**</span></span>  |           <span data-ttu-id="21d9e-119">選択**Fabrikam**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-119">Select **Fabrikam** from the drop-down list.</span></span>           |
   |     <span data-ttu-id="21d9e-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="21d9e-120">**RNIF Version**</span></span>      |          <span data-ttu-id="21d9e-121">選択**V02.00.01**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-121">Select **V02.00.01** from the drop-down list.</span></span>           |
   |       <span data-ttu-id="21d9e-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="21d9e-122">**Home Role**</span></span>       | <span data-ttu-id="21d9e-123">選択**Product Supplier (応答側)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-123">Select **Product Supplier (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="21d9e-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="21d9e-124">**Usage**</span></span>         |             <span data-ttu-id="21d9e-125">選択**テスト**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="21d9e-125">Select **Test** from the drop-down list.</span></span>             |


3. <span data-ttu-id="21d9e-126">をクリックして、**ポート**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="21d9e-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="21d9e-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="21d9e-127">Use this</span></span>    |                          <span data-ttu-id="21d9e-128">目的</span><span class="sxs-lookup"><span data-stu-id="21d9e-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="21d9e-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="21d9e-129">**Action URL**</span></span> | <span data-ttu-id="21d9e-130">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="21d9e-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="21d9e-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="21d9e-131">**Signal URL**</span></span> | <span data-ttu-id="21d9e-132">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="21d9e-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="21d9e-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="21d9e-133">**Sync URL**</span></span>  | <span data-ttu-id="21d9e-134">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="21d9e-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="21d9e-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21d9e-135">Click **OK**.</span></span>  

5. <span data-ttu-id="21d9e-136">右クリックし、 **Fabrikam_To_Contoso_3A2**アグリーメント、およびクリック**Activate**します。</span><span class="sxs-lookup"><span data-stu-id="21d9e-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="21d9e-137">参照</span><span class="sxs-lookup"><span data-stu-id="21d9e-137">See Also</span></span>  
 [<span data-ttu-id="21d9e-138">手順 6: Contoso 3A4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="21d9e-138">Step 6: Creating the Contoso 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)