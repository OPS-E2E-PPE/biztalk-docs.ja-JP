---
title: "手順 6: Contoso 3A4 取引を作成するパートナーの契約 |Microsoft ドキュメント"
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
ms.assetid: a20e40d8-7e3b-4930-8921-056ffddd08ea
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531a4b4a5446b51e01800caf582e40ce13bc288f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-6-creating-the-contoso-3a4-trading-partner-agreement"></a><span data-ttu-id="03482-102">手順 6: Contoso 3A4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="03482-102">Step 6: Creating the Contoso 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="03482-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="03482-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="03482-104">3A4 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="03482-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="03482-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="03482-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="03482-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="03482-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="03482-107">3A4 取引先アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="03482-107">To create the 3A4 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="03482-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をポイント**新規**、クリックして**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="03482-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="03482-109">新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="03482-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="03482-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="03482-110">Use this</span></span>|<span data-ttu-id="03482-111">目的</span><span class="sxs-lookup"><span data-stu-id="03482-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="03482-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="03482-112">**Name**</span></span>|<span data-ttu-id="03482-113">型**Fabrikam_To_Contoso_3A4**です。</span><span class="sxs-lookup"><span data-stu-id="03482-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>|  
    |<span data-ttu-id="03482-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="03482-114">**Process Configuration**</span></span>|<span data-ttu-id="03482-115">選択**STD_3A4_V02.02**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="03482-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="03482-116">**My Organization**</span></span>|<span data-ttu-id="03482-117">選択**Contoso**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-117">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="03482-118">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="03482-118">**Partner Organization**</span></span>|<span data-ttu-id="03482-119">選択**Fabrikam**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-119">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="03482-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="03482-120">**RNIF Version**</span></span>|<span data-ttu-id="03482-121">選択**[v02.00.01]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="03482-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="03482-122">**Home Role**</span></span>|<span data-ttu-id="03482-123">選択**Seller (応答側)**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-123">Select **Seller (Responder)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="03482-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="03482-124">**Usage**</span></span>|<span data-ttu-id="03482-125">選択**テスト**ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="03482-125">Select **Test** from the drop down-list.</span></span>|  
  
3.  <span data-ttu-id="03482-126">**ポート** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="03482-126">On the **Ports** tab, do the following:</span></span>  
  
    |<span data-ttu-id="03482-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="03482-127">Use this</span></span>|<span data-ttu-id="03482-128">目的</span><span class="sxs-lookup"><span data-stu-id="03482-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="03482-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="03482-129">**Action URL**</span></span>|<span data-ttu-id="03482-130">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="03482-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="03482-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="03482-131">**Signal URL**</span></span>|<span data-ttu-id="03482-132">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="03482-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="03482-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="03482-133">**Sync URL**</span></span>|<span data-ttu-id="03482-134">型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="03482-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
  
4.  <span data-ttu-id="03482-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03482-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="03482-136">右クリックし、 **Fabrikam_To_Contoso_3A4**アグリーメントをクリックして**Activate**です。</span><span class="sxs-lookup"><span data-stu-id="03482-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03482-137">参照</span><span class="sxs-lookup"><span data-stu-id="03482-137">See Also</span></span>  
 [<span data-ttu-id="03482-138">手順 7: DoubleAction SDK サンプルのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="03482-138">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)