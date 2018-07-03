---
title: '手順 5: Fabrikam 3 a 2 取引先を作成するアグリーメントのパートナー |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: a5fafdc6-e9dd-4d15-98a2-8b603901308c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d69b129744df598d69b3209f4af46123ff22fda3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992362"
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a><span data-ttu-id="c28e0-102">手順 5: Fabrikam 3 a 2 取引先パートナー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-102">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="c28e0-103">Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c28e0-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="c28e0-104">3A2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="c28e0-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="c28e0-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="c28e0-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c28e0-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="c28e0-107">3A2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="c28e0-107">To create the 3A2 trading partner agreement</span></span>  

1. <span data-ttu-id="c28e0-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**契約**、 をポイント**新規**、順にクリックします**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="c28e0-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="c28e0-109">**新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c28e0-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="c28e0-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c28e0-110">Use this</span></span>          |                        <span data-ttu-id="c28e0-111">目的</span><span class="sxs-lookup"><span data-stu-id="c28e0-111">To do this</span></span>                        |
   |---------------------------|----------------------------------------------------------|
   |         <span data-ttu-id="c28e0-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="c28e0-112">**Name**</span></span>          |            <span data-ttu-id="c28e0-113">型**Fabrikam_To_Contoso_3A2**します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>             |
   | <span data-ttu-id="c28e0-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="c28e0-114">**Process Configuration**</span></span> |  <span data-ttu-id="c28e0-115">選択**STD_3A2_R02.00.00A**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>  |
   |    <span data-ttu-id="c28e0-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="c28e0-116">**My Organization**</span></span>    |       <span data-ttu-id="c28e0-117">選択**Fabrikam**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-117">Select **Fabrikam** from the drop-down list.</span></span>       |
   | <span data-ttu-id="c28e0-118">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="c28e0-118">**Partner Organization**</span></span>  |       <span data-ttu-id="c28e0-119">選択**Contoso**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="c28e0-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="c28e0-120">**RNIF Version**</span></span>      |      <span data-ttu-id="c28e0-121">選択**V02.00.01**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="c28e0-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="c28e0-122">**Home Role**</span></span>       | <span data-ttu-id="c28e0-123">選択**Customer (開始側)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-123">Select **Customer (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="c28e0-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c28e0-124">**Usage**</span></span>         |         <span data-ttu-id="c28e0-125">選択**テスト**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="c28e0-125">Select **Test** from the drop-down list.</span></span>         |


3. <span data-ttu-id="c28e0-126">をクリックして、**ポート**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c28e0-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="c28e0-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c28e0-127">Use this</span></span>    |                          <span data-ttu-id="c28e0-128">目的</span><span class="sxs-lookup"><span data-stu-id="c28e0-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="c28e0-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="c28e0-129">**Action URL**</span></span> | <span data-ttu-id="c28e0-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="c28e0-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="c28e0-131">**Signal URL**</span></span> | <span data-ttu-id="c28e0-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="c28e0-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="c28e0-133">**Sync URL**</span></span>  | <span data-ttu-id="c28e0-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="c28e0-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c28e0-135">Click **OK**.</span></span>  

5. <span data-ttu-id="c28e0-136">右クリックし、 **Fabrikam_To_Contoso_3A2**契約書とクリック**アクティブ化**します。</span><span class="sxs-lookup"><span data-stu-id="c28e0-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c28e0-137">参照</span><span class="sxs-lookup"><span data-stu-id="c28e0-137">See Also</span></span>  
 [<span data-ttu-id="c28e0-138">手順 6: Fabrikam 3A4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="c28e0-138">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)