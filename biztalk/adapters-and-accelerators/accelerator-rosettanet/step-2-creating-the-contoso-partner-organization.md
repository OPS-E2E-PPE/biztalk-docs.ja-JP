---
title: "手順 2: Contoso パートナー組織の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating partner organizations
ms.assetid: ebb3b166-3781-40b9-89d4-2ca0c83d05f3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d64ddd2c9913ac85a493108548a655a25f153c3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-the-contoso-partner-organization"></a><span data-ttu-id="f68a3-102">手順 2: Contoso パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="f68a3-102">Step 2: Creating the Contoso Partner Organization</span></span>
<span data-ttu-id="f68a3-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して新しい取引先を作成します。</span><span class="sxs-lookup"><span data-stu-id="f68a3-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="f68a3-104">このチュートリアルでは、Contoso 組織という取引先を使用します。</span><span class="sxs-lookup"><span data-stu-id="f68a3-104">The trading partner for this tutorial is the Contoso organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="f68a3-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="f68a3-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="f68a3-106">をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**、クリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f68a3-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="f68a3-107">Fabrikam という名前の取引先を作成するには</span><span class="sxs-lookup"><span data-stu-id="f68a3-107">To create Fabrikam as a trading partner</span></span>  
  
1.  <span data-ttu-id="f68a3-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、をポイント**新規**、クリックして**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="f68a3-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  
  
2.  <span data-ttu-id="f68a3-109">新しいパートナーのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作、**:**</span><span class="sxs-lookup"><span data-stu-id="f68a3-109">In the New Partner Properties dialog box, on the **General** tab, do the following**:**</span></span>  
  
    |<span data-ttu-id="f68a3-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f68a3-110">Use this</span></span>|<span data-ttu-id="f68a3-111">目的</span><span class="sxs-lookup"><span data-stu-id="f68a3-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f68a3-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="f68a3-112">**Name**</span></span>|<span data-ttu-id="f68a3-113">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-113">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="f68a3-114">**[GBI]**</span><span class="sxs-lookup"><span data-stu-id="f68a3-114">**GBI**</span></span>|<span data-ttu-id="f68a3-115">型**123456789**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-115">Type **123456789**.</span></span>|  
    |<span data-ttu-id="f68a3-116">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="f68a3-116">**Partner Classification**</span></span>|<span data-ttu-id="f68a3-117">選択**製造元**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="f68a3-117">Select **Manufacturer** from the drop-down list.</span></span>|  
    |<span data-ttu-id="f68a3-118">**署名証明書**</span><span class="sxs-lookup"><span data-stu-id="f68a3-118">**Signature Certificate**</span></span>|<span data-ttu-id="f68a3-119">選択**Contoso Signature [Thumbprint]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="f68a3-119">Select **Contoso Signature [Thumbprint]** from the drop-down list.</span></span>|  
    |<span data-ttu-id="f68a3-120">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="f68a3-120">**Encryption Certificate**</span></span>|<span data-ttu-id="f68a3-121">選択**Contoso Encryption [Thumbprint]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="f68a3-121">Select **Contoso Encryption [Thumbprint]** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="f68a3-122">クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f68a3-122">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="f68a3-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f68a3-123">Use this</span></span>|<span data-ttu-id="f68a3-124">目的</span><span class="sxs-lookup"><span data-stu-id="f68a3-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f68a3-125">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="f68a3-125">**Contact Name**</span></span>|<span data-ttu-id="f68a3-126">型**John doe さん**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-126">Type **John Doe**.</span></span>|  
    |<span data-ttu-id="f68a3-127">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="f68a3-127">**E-mail Address**</span></span>|<span data-ttu-id="f68a3-128">型 **jdoe@contoso.com**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-128">Type **jdoe@contoso.com**.</span></span>|  
    |<span data-ttu-id="f68a3-129">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="f68a3-129">**Telephone Number**</span></span>|<span data-ttu-id="f68a3-130">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-130">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="f68a3-131">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="f68a3-131">**Fax Number**</span></span>|<span data-ttu-id="f68a3-132">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-132">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="f68a3-133">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="f68a3-133">**Supply chain code**</span></span>|<span data-ttu-id="f68a3-134">型**電子部品**です。</span><span class="sxs-lookup"><span data-stu-id="f68a3-134">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="f68a3-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f68a3-135">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68a3-136">参照</span><span class="sxs-lookup"><span data-stu-id="f68a3-136">See Also</span></span>  
 [<span data-ttu-id="f68a3-137">手順 3: Fabrikam 0 C 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="f68a3-137">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)