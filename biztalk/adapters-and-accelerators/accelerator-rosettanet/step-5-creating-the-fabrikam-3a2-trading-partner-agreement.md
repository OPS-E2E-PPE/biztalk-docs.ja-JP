---
title: '手順 5: Fabrikam 3 a 2 取引を作成するパートナーの契約 |Microsoft ドキュメント'
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
ms.openlocfilehash: 0c0c2de5e4d44ce591eaca1b1e46130132436bf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a><span data-ttu-id="862c6-102">手順 5: Fabrikam 3 a 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="862c6-102">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="862c6-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="862c6-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="862c6-104">3A2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="862c6-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="862c6-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="862c6-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="862c6-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="862c6-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="862c6-107">3A2 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="862c6-107">To create the 3A2 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="862c6-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をポイント**新規**、クリックして**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="862c6-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="862c6-109">**新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="862c6-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="862c6-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="862c6-110">Use this</span></span>|<span data-ttu-id="862c6-111">目的</span><span class="sxs-lookup"><span data-stu-id="862c6-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="862c6-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="862c6-112">**Name**</span></span>|<span data-ttu-id="862c6-113">型**Fabrikam_To_Contoso_3A2**です。</span><span class="sxs-lookup"><span data-stu-id="862c6-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>|  
    |<span data-ttu-id="862c6-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="862c6-114">**Process Configuration**</span></span>|<span data-ttu-id="862c6-115">選択**STD_3A2_R02.00.00A**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>|  
    |<span data-ttu-id="862c6-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="862c6-116">**My Organization**</span></span>|<span data-ttu-id="862c6-117">選択**Fabrikam**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-117">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="862c6-118">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="862c6-118">**Partner Organization**</span></span>|<span data-ttu-id="862c6-119">選択**Contoso**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-119">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="862c6-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="862c6-120">**RNIF Version**</span></span>|<span data-ttu-id="862c6-121">選択**[v02.00.01]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="862c6-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="862c6-122">**Home Role**</span></span>|<span data-ttu-id="862c6-123">選択**Customer (開始側)**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-123">Select **Customer (Initiator)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="862c6-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="862c6-124">**Usage**</span></span>|<span data-ttu-id="862c6-125">選択**テスト**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="862c6-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="862c6-126">クリックして、**ポート**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="862c6-126">Click the **Ports** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="862c6-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="862c6-127">Use this</span></span>|<span data-ttu-id="862c6-128">目的</span><span class="sxs-lookup"><span data-stu-id="862c6-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="862c6-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="862c6-129">**Action URL**</span></span>|<span data-ttu-id="862c6-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="862c6-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="862c6-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="862c6-131">**Signal URL**</span></span>|<span data-ttu-id="862c6-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="862c6-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="862c6-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="862c6-133">**Sync URL**</span></span>|<span data-ttu-id="862c6-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="862c6-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
  
4.  <span data-ttu-id="862c6-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="862c6-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="862c6-136">右クリックし、 **Fabrikam_To_Contoso_3A2**アグリーメントをクリックして**Activate**です。</span><span class="sxs-lookup"><span data-stu-id="862c6-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862c6-137">参照</span><span class="sxs-lookup"><span data-stu-id="862c6-137">See Also</span></span>  
 [<span data-ttu-id="862c6-138">手順 6: Fabrikam 3A4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="862c6-138">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)