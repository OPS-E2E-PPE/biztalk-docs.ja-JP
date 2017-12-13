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
ms.openlocfilehash: dd5d3f29a2a369f37589f3356da1a1183d8cb91b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-creating-the-contoso-partner-organization"></a><span data-ttu-id="045af-102">手順 2: Contoso パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="045af-102">Step 2: Creating the Contoso Partner Organization</span></span>
<span data-ttu-id="045af-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して新しい取引先を作成します。</span><span class="sxs-lookup"><span data-stu-id="045af-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="045af-104">このチュートリアルでは、Contoso 組織という取引先を使用します。</span><span class="sxs-lookup"><span data-stu-id="045af-104">The trading partner for this tutorial is the Contoso organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="045af-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="045af-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="045af-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="045af-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="045af-107">Fabrikam という名前の取引先を作成するには</span><span class="sxs-lookup"><span data-stu-id="045af-107">To create Fabrikam as a trading partner</span></span>  
  
1.  <span data-ttu-id="045af-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、クリックして**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="045af-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  
  
2.  <span data-ttu-id="045af-109">新しいパートナーのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作、**:**</span><span class="sxs-lookup"><span data-stu-id="045af-109">In the New Partner Properties dialog box, on the **General** tab, do the following**:**</span></span>  
  
    |<span data-ttu-id="045af-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="045af-110">Use this</span></span>|<span data-ttu-id="045af-111">目的</span><span class="sxs-lookup"><span data-stu-id="045af-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="045af-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="045af-112">**Name**</span></span>|<span data-ttu-id="045af-113">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="045af-113">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="045af-114">**[GBI]**</span><span class="sxs-lookup"><span data-stu-id="045af-114">**GBI**</span></span>|<span data-ttu-id="045af-115">型**123456789**です。</span><span class="sxs-lookup"><span data-stu-id="045af-115">Type **123456789**.</span></span>|  
    |<span data-ttu-id="045af-116">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="045af-116">**Partner Classification**</span></span>|<span data-ttu-id="045af-117">選択**製造元**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="045af-117">Select **Manufacturer** from the drop-down list.</span></span>|  
    |<span data-ttu-id="045af-118">**署名証明書**</span><span class="sxs-lookup"><span data-stu-id="045af-118">**Signature Certificate**</span></span>|<span data-ttu-id="045af-119">選択**Contoso Signature [Thumbprint]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="045af-119">Select **Contoso Signature [Thumbprint]** from the drop-down list.</span></span>|  
    |<span data-ttu-id="045af-120">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="045af-120">**Encryption Certificate**</span></span>|<span data-ttu-id="045af-121">選択**Contoso Encryption [Thumbprint]**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="045af-121">Select **Contoso Encryption [Thumbprint]** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="045af-122">クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="045af-122">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="045af-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="045af-123">Use this</span></span>|<span data-ttu-id="045af-124">目的</span><span class="sxs-lookup"><span data-stu-id="045af-124">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="045af-125">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="045af-125">**Contact Name**</span></span>|<span data-ttu-id="045af-126">型**John doe さん**です。</span><span class="sxs-lookup"><span data-stu-id="045af-126">Type **John Doe**.</span></span>|  
    |<span data-ttu-id="045af-127">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="045af-127">**E-mail Address**</span></span>|<span data-ttu-id="045af-128">型 **jdoe@contoso.com**です。</span><span class="sxs-lookup"><span data-stu-id="045af-128">Type **jdoe@contoso.com**.</span></span>|  
    |<span data-ttu-id="045af-129">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="045af-129">**Telephone Number**</span></span>|<span data-ttu-id="045af-130">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="045af-130">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="045af-131">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="045af-131">**Fax Number**</span></span>|<span data-ttu-id="045af-132">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="045af-132">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="045af-133">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="045af-133">**Supply chain code**</span></span>|<span data-ttu-id="045af-134">型**電子部品**です。</span><span class="sxs-lookup"><span data-stu-id="045af-134">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="045af-135">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="045af-135">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="045af-136">参照</span><span class="sxs-lookup"><span data-stu-id="045af-136">See Also</span></span>  
 [<span data-ttu-id="045af-137">手順 3: Fabrikam 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="045af-137">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)