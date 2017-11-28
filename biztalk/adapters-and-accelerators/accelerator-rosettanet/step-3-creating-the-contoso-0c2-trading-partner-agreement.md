---
title: "手順 3: Contoso 0 C 2 取引先アグリーメントの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85ff2722deb6ab8ba38bda34b6c68b62cb7dbccb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a><span data-ttu-id="dd414-102">手順 3: Contoso 0 C 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="dd414-102">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="dd414-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd414-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="dd414-104">0C2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd414-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="dd414-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="dd414-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="dd414-106">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**、クリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="dd414-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="dd414-107">0C2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="dd414-107">To create the 0C2 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="dd414-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、をクリックして**新規**、クリックして**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="dd414-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="dd414-109">新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="dd414-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="dd414-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dd414-110">Use this</span></span>|<span data-ttu-id="dd414-111">目的</span><span class="sxs-lookup"><span data-stu-id="dd414-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="dd414-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="dd414-112">**Name**</span></span>|<span data-ttu-id="dd414-113">型**Fabrikam_To_Contoso_0C2**です。</span><span class="sxs-lookup"><span data-stu-id="dd414-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>|  
    |<span data-ttu-id="dd414-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="dd414-114">**Process configuration**</span></span>|<span data-ttu-id="dd414-115">選択**STD_0C2_R01.02**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="dd414-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="dd414-116">**My organization**</span></span>|<span data-ttu-id="dd414-117">選択**Contoso**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-117">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="dd414-118">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="dd414-118">**Partner organization**</span></span>|<span data-ttu-id="dd414-119">選択**Fabrikam**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-119">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="dd414-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="dd414-120">**RNIF version**</span></span>|<span data-ttu-id="dd414-121">選択**[v02.00.01]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="dd414-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="dd414-122">**Home role**</span></span>|<span data-ttu-id="dd414-123">選択**Responder (応答側)**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-123">Select **Responder (Responder)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="dd414-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="dd414-124">**Usage**</span></span>|<span data-ttu-id="dd414-125">選択**テスト**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="dd414-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="dd414-126">クリックして、**ポート**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="dd414-126">Click the **Ports** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="dd414-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dd414-127">Use this</span></span>|<span data-ttu-id="dd414-128">目的</span><span class="sxs-lookup"><span data-stu-id="dd414-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="dd414-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="dd414-129">**Action URL**</span></span>|<span data-ttu-id="dd414-130">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dd414-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="dd414-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="dd414-131">**Signal URL**</span></span>|<span data-ttu-id="dd414-132">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dd414-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="dd414-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="dd414-133">**Sync URL**</span></span>|<span data-ttu-id="dd414-134">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dd414-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
  
4.  <span data-ttu-id="dd414-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd414-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="dd414-136">右クリックし、 **Fabrikam_To_Contoso_0C2**アグリーメント、およびクリック**Activate**です。</span><span class="sxs-lookup"><span data-stu-id="dd414-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd414-137">参照</span><span class="sxs-lookup"><span data-stu-id="dd414-137">See Also</span></span>  
 [<span data-ttu-id="dd414-138">手順 4: Contoso 0 C 4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="dd414-138">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)