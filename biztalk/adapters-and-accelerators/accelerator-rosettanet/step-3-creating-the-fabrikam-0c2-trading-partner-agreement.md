---
title: '手順 3: Fabrikam 0 C 2 取引先アグリーメントの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 746256a744a5d89f325ccaecb7d71185383f8efd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965456"
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a><span data-ttu-id="85bc0-102">手順 3: Fabrikam 0 C 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="85bc0-102">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="85bc0-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="85bc0-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="85bc0-104">0C2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="85bc0-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="85bc0-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="85bc0-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="85bc0-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="85bc0-107">0C2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="85bc0-107">To create the 0C2 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="85bc0-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をポイント**新規**、クリックして**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="85bc0-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="85bc0-109">新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="85bc0-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="85bc0-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="85bc0-110">Use this</span></span>|<span data-ttu-id="85bc0-111">目的</span><span class="sxs-lookup"><span data-stu-id="85bc0-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="85bc0-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="85bc0-112">**Name**</span></span>|<span data-ttu-id="85bc0-113">型**Fabrikam_To_Contoso_0C2**です。</span><span class="sxs-lookup"><span data-stu-id="85bc0-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>|  
    |<span data-ttu-id="85bc0-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="85bc0-114">**Process Configuration**</span></span>|<span data-ttu-id="85bc0-115">選択**STD_0C2_R01.02**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85bc0-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="85bc0-116">**My Organization**</span></span>|<span data-ttu-id="85bc0-117">選択**Fabrikam**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-117">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85bc0-118">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="85bc0-118">**Partner Organization**</span></span>|<span data-ttu-id="85bc0-119">選択**Contoso**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-119">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85bc0-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="85bc0-120">**RNIF Version**</span></span>|<span data-ttu-id="85bc0-121">選択 **[v02.00.01]** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85bc0-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="85bc0-122">**Home Role**</span></span>|<span data-ttu-id="85bc0-123">選択**Initiator (開始側)** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-123">Select **Initiator (Initiator)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85bc0-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="85bc0-124">**Usage**</span></span>|<span data-ttu-id="85bc0-125">選択**テスト**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="85bc0-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="85bc0-126">クリックして、**ポート**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="85bc0-126">Click the **Ports** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="85bc0-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="85bc0-127">Use this</span></span>|<span data-ttu-id="85bc0-128">目的</span><span class="sxs-lookup"><span data-stu-id="85bc0-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="85bc0-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="85bc0-129">**Action URL**</span></span>|<span data-ttu-id="85bc0-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="85bc0-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="85bc0-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="85bc0-131">**Signal URL**</span></span>|<span data-ttu-id="85bc0-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="85bc0-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="85bc0-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="85bc0-133">**Sync URL**</span></span>|<span data-ttu-id="85bc0-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="85bc0-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
  
4.  <span data-ttu-id="85bc0-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85bc0-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="85bc0-136">右クリックし、 **Fabrikam_To_Contoso_0C2**アグリーメント、およびクリック**Activate**です。</span><span class="sxs-lookup"><span data-stu-id="85bc0-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bc0-137">参照</span><span class="sxs-lookup"><span data-stu-id="85bc0-137">See Also</span></span>  
 [<span data-ttu-id="85bc0-138">手順 4: Fabrikam 0C4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="85bc0-138">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)