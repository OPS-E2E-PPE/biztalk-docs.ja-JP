---
title: '手順 3: Contoso 0 C のパートナーの 2 つの取引先アグリーメントの作成 |Microsoft Docs'
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
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eedd57a9c18c689d6357cf1467e08b6951cfc531
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977635"
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a><span data-ttu-id="3e00d-102">手順 3: Contoso 0 C のパートナーの 2 つの取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="3e00d-102">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="3e00d-103">Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3e00d-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="3e00d-104">0C2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e00d-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="3e00d-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="3e00d-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="3e00d-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3e00d-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="3e00d-107">0C2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e00d-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="3e00d-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をクリックして**新規**、 をクリックし、**契約**.</span><span class="sxs-lookup"><span data-stu-id="3e00d-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="3e00d-109">新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3e00d-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="3e00d-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3e00d-110">Use this</span></span>          |                        <span data-ttu-id="3e00d-111">目的</span><span class="sxs-lookup"><span data-stu-id="3e00d-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="3e00d-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="3e00d-112">**Name**</span></span>          |             <span data-ttu-id="3e00d-113">型**Fabrikam_To_Contoso_0C2**します。</span><span class="sxs-lookup"><span data-stu-id="3e00d-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="3e00d-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="3e00d-114">**Process configuration**</span></span> |    <span data-ttu-id="3e00d-115">選択**STD_0C2_R01.02**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="3e00d-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="3e00d-116">**My organization**</span></span>    |        <span data-ttu-id="3e00d-117">選択**Contoso**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-117">Select **Contoso** from the drop-down list.</span></span>        |
   | <span data-ttu-id="3e00d-118">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="3e00d-118">**Partner organization**</span></span>  |       <span data-ttu-id="3e00d-119">選択**Fabrikam**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-119">Select **Fabrikam** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="3e00d-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="3e00d-120">**RNIF version**</span></span>      |       <span data-ttu-id="3e00d-121">選択**V02.00.01**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="3e00d-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="3e00d-122">**Home role**</span></span>       | <span data-ttu-id="3e00d-123">選択**Responder (応答)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-123">Select **Responder (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="3e00d-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="3e00d-124">**Usage**</span></span>         |         <span data-ttu-id="3e00d-125">選択**テスト**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3e00d-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="3e00d-126">をクリックして、**ポート**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3e00d-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="3e00d-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3e00d-127">Use this</span></span>    |                          <span data-ttu-id="3e00d-128">目的</span><span class="sxs-lookup"><span data-stu-id="3e00d-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="3e00d-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="3e00d-129">**Action URL**</span></span> | <span data-ttu-id="3e00d-130">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="3e00d-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="3e00d-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="3e00d-131">**Signal URL**</span></span> | <span data-ttu-id="3e00d-132">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="3e00d-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="3e00d-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="3e00d-133">**Sync URL**</span></span>  | <span data-ttu-id="3e00d-134">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="3e00d-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="3e00d-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e00d-135">Click **OK**.</span></span>  

5. <span data-ttu-id="3e00d-136">右クリックし、 **Fabrikam_To_Contoso_0C2**アグリーメント、およびクリック**Activate**します。</span><span class="sxs-lookup"><span data-stu-id="3e00d-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3e00d-137">参照</span><span class="sxs-lookup"><span data-stu-id="3e00d-137">See Also</span></span>  
 [<span data-ttu-id="3e00d-138">手順 4: Contoso 0C4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="3e00d-138">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)