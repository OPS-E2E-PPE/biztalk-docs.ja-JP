---
title: '手順 2: Fabrikam パートナー組織の作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de00977edecb97420742a6510c3290cfe3c76ea5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964968"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a><span data-ttu-id="9d694-102">手順 2: Fabrikam パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="9d694-102">Step 2: Creating the Fabrikam Partner Organization</span></span>
<span data-ttu-id="9d694-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して新しい取引先を作成します。</span><span class="sxs-lookup"><span data-stu-id="9d694-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="9d694-104">このチュートリアルでは、Fabrikam 組織という取引先を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d694-104">The trading partner for this tutorial is the Fabrikam organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="9d694-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="9d694-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="9d694-106">Contoso のコンピューターでをクリックして**開始**、指す**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**、クリックして **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="9d694-106">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="9d694-107">Fabrikam という名前の取引先を作成するには</span><span class="sxs-lookup"><span data-stu-id="9d694-107">To create Fabrikam as a trading partner</span></span>  
  
1.  <span data-ttu-id="9d694-108"> **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、クリックして**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="9d694-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  
  
2.  <span data-ttu-id="9d694-109">新しいパートナーのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作、**:**</span><span class="sxs-lookup"><span data-stu-id="9d694-109">In the New Partner Properties dialog box, on the **General** tab, do the following **:**</span></span>  
  
    |<span data-ttu-id="9d694-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9d694-110">Use this</span></span>|<span data-ttu-id="9d694-111">目的</span><span class="sxs-lookup"><span data-stu-id="9d694-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9d694-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="9d694-112">**Name**</span></span>|<span data-ttu-id="9d694-113">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="9d694-114">**[GBI]**</span><span class="sxs-lookup"><span data-stu-id="9d694-114">**GBI**</span></span>|<span data-ttu-id="9d694-115">型**987654321**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-115">Type **987654321**.</span></span> <span data-ttu-id="9d694-116">**注:** を同じコンピューターでループバック チュートリアルを実行する場合は、異なる 987654321 以外は、[gbi] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d694-116">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "987654321".</span></span>|  
    |<span data-ttu-id="9d694-117">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="9d694-117">**Partner Classification**</span></span>|<span data-ttu-id="9d694-118">選択**Shopper**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="9d694-118">Select **Shopper** from the drop-down list.</span></span>|  
    |<span data-ttu-id="9d694-119">**署名証明書**</span><span class="sxs-lookup"><span data-stu-id="9d694-119">**Signature Certificate**</span></span>|<span data-ttu-id="9d694-120">選択**Fabrikam Signature [Thumbprint]** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="9d694-120">Select **Fabrikam Signature [Thumbprint]** from the drop-down list.</span></span>|  
    |<span data-ttu-id="9d694-121">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="9d694-121">**Encryption Certificate**</span></span>|<span data-ttu-id="9d694-122">選択**Fabrikam Encryption [Thumbprint]** ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="9d694-122">Select **Fabrikam Encryption [Thumbprint]** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="9d694-123">クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="9d694-123">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="9d694-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9d694-124">Use this</span></span>|<span data-ttu-id="9d694-125">目的</span><span class="sxs-lookup"><span data-stu-id="9d694-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9d694-126">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="9d694-126">**Contact Name**</span></span>|<span data-ttu-id="9d694-127">型**Jane Doe**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-127">Type **Jane Doe**.</span></span>|  
    |<span data-ttu-id="9d694-128">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="9d694-128">**E-mail Address**</span></span>|<span data-ttu-id="9d694-129">型 **jdoe@fabrikam.com**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-129">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="9d694-130">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="9d694-130">**Telephone Number**</span></span>|<span data-ttu-id="9d694-131">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-131">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="9d694-132">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="9d694-132">**Fax Number**</span></span>|<span data-ttu-id="9d694-133">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-133">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="9d694-134">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="9d694-134">**Supply chain code**</span></span>|<span data-ttu-id="9d694-135">型**電子部品**です。</span><span class="sxs-lookup"><span data-stu-id="9d694-135">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="9d694-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d694-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d694-137">参照</span><span class="sxs-lookup"><span data-stu-id="9d694-137">See Also</span></span>  
 [<span data-ttu-id="9d694-138">手順 3: Contoso 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="9d694-138">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)