---
title: "手順 6: Fabrikam 3A4 取引を作成するパートナーの契約 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e5b034e2da0101cb8ce37ad193fa04e8c3d6d16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a><span data-ttu-id="986b7-102">手順 6: Fabrikam 3A4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="986b7-102">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="986b7-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="986b7-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="986b7-104">3A4 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="986b7-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="986b7-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="986b7-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="986b7-106">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**、クリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="986b7-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="986b7-107">3A4 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="986b7-107">To create the 3A4 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="986b7-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、をポイント**新規**、クリックして**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="986b7-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="986b7-109">**新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="986b7-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="986b7-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="986b7-110">Use this</span></span>|<span data-ttu-id="986b7-111">目的</span><span class="sxs-lookup"><span data-stu-id="986b7-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="986b7-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="986b7-112">**Name**</span></span>|<span data-ttu-id="986b7-113">型**Fabrikam_To_Contoso_3A4**です。</span><span class="sxs-lookup"><span data-stu-id="986b7-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>|  
    |<span data-ttu-id="986b7-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="986b7-114">**Process Configuration**</span></span>|<span data-ttu-id="986b7-115">選択**STD_3A4_V02.02**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="986b7-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="986b7-116">**My Organization**</span></span>|<span data-ttu-id="986b7-117">選択**Fabrikam**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-117">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="986b7-118">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="986b7-118">**Partner Organization**</span></span>|<span data-ttu-id="986b7-119">選択**Contoso**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-119">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="986b7-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="986b7-120">**RNIF Version**</span></span>|<span data-ttu-id="986b7-121">選択**[v02.00.01]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="986b7-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="986b7-122">**Home Role**</span></span>|<span data-ttu-id="986b7-123">選択**Buyer (開始側)**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-123">Select **Buyer (Initiator)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="986b7-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="986b7-124">**Usage**</span></span>|<span data-ttu-id="986b7-125">選択**テスト**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="986b7-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="986b7-126">**ポート** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="986b7-126">On the **Ports** tab, do the following:</span></span>  
  
    |<span data-ttu-id="986b7-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="986b7-127">Use this</span></span>|<span data-ttu-id="986b7-128">目的</span><span class="sxs-lookup"><span data-stu-id="986b7-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="986b7-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="986b7-129">**Action URL**</span></span>|<span data-ttu-id="986b7-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="986b7-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="986b7-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="986b7-131">**Signal URL**</span></span>|<span data-ttu-id="986b7-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="986b7-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="986b7-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="986b7-133">**Sync URL**</span></span>|<span data-ttu-id="986b7-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="986b7-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
  
4.  <span data-ttu-id="986b7-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="986b7-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="986b7-136">右クリックし、 **Fabrikam_To_Contoso_3A4**アグリーメントをクリックして**Activate**です。</span><span class="sxs-lookup"><span data-stu-id="986b7-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986b7-137">参照</span><span class="sxs-lookup"><span data-stu-id="986b7-137">See Also</span></span>  
 [<span data-ttu-id="986b7-138">手順 7: ビルドと LOBWebApplication SDK サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="986b7-138">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)