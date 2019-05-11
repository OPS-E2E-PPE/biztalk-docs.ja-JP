---
title: 手順 2:Fabrikam 取引先組織の作成 |Microsoft Docs
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
ms.openlocfilehash: d3940cd1379a48b9ec7762612acd98521af407c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281227"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a><span data-ttu-id="0459b-102">手順 2:Fabrikam 取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="0459b-102">Step 2: Creating the Fabrikam Partner Organization</span></span>
<span data-ttu-id="0459b-103">この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール、新しい取引を作成します。</span><span class="sxs-lookup"><span data-stu-id="0459b-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="0459b-104">このチュートリアルでは、取引先パートナーは、Fabrikam 組織です。</span><span class="sxs-lookup"><span data-stu-id="0459b-104">The trading partner for this tutorial is the Fabrikam organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="0459b-105">BTARN 管理コンソールを開始するには</span><span class="sxs-lookup"><span data-stu-id="0459b-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="0459b-106">Contoso コンピューターでは、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**。、 をクリックし、 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0459b-106">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="0459b-107">取引先パートナーとして Fabrikam を作成するには</span><span class="sxs-lookup"><span data-stu-id="0459b-107">To create Fabrikam as a trading partner</span></span>  

1. <span data-ttu-id="0459b-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、 をクリックし、**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="0459b-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  

2. <span data-ttu-id="0459b-109">新しいパートナーのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います<strong>:</strong></span><span class="sxs-lookup"><span data-stu-id="0459b-109">In the New Partner Properties dialog box, on the **General** tab, do the following<strong>:</strong></span></span>  


   |          <span data-ttu-id="0459b-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0459b-110">Use this</span></span>          |                                                                              <span data-ttu-id="0459b-111">目的</span><span class="sxs-lookup"><span data-stu-id="0459b-111">To do this</span></span>                                                                               |
   |----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          <span data-ttu-id="0459b-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="0459b-112">**Name**</span></span>          |                                                                          <span data-ttu-id="0459b-113">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-113">Type **FABRIKAM**.</span></span>                                                                           |
   |          <span data-ttu-id="0459b-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="0459b-114">**GBI**</span></span>           | <span data-ttu-id="0459b-115">型**987654321**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-115">Type **987654321**.</span></span> <span data-ttu-id="0459b-116">**注:** 同じコンピューターで、Loopback チュートリアルを実行した場合の gbi に 987654321 以外の異なる値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0459b-116">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "987654321".</span></span> |
   | <span data-ttu-id="0459b-117">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="0459b-117">**Partner Classification**</span></span> |                                                              <span data-ttu-id="0459b-118">選択**買い物客**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0459b-118">Select **Shopper** from the drop-down list.</span></span>                                                              |
   | <span data-ttu-id="0459b-119">**証明書の署名**</span><span class="sxs-lookup"><span data-stu-id="0459b-119">**Signature Certificate**</span></span>  |                                                  <span data-ttu-id="0459b-120">選択**Fabrikam Signature [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0459b-120">Select **Fabrikam Signature [Thumbprint]** from the drop-down list.</span></span>                                                  |
   | <span data-ttu-id="0459b-121">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="0459b-121">**Encryption Certificate**</span></span> |                                                 <span data-ttu-id="0459b-122">選択**Fabrikam Encryption [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="0459b-122">Select **Fabrikam Encryption [Thumbprint]** from the drop-down list.</span></span>                                                  |


3. <span data-ttu-id="0459b-123">をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0459b-123">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="0459b-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0459b-124">Use this</span></span>        |                <span data-ttu-id="0459b-125">目的</span><span class="sxs-lookup"><span data-stu-id="0459b-125">To do this</span></span>                |
   |-----------------------|------------------------------------------|
   |   <span data-ttu-id="0459b-126">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="0459b-126">**Contact Name**</span></span>    |            <span data-ttu-id="0459b-127">型**Jane Doe**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-127">Type **Jane Doe**.</span></span>            |
   |  <span data-ttu-id="0459b-128">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="0459b-128">**E-mail Address**</span></span>   | <span data-ttu-id="0459b-129">型 <strong>jdoe@fabrikam.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="0459b-129">Type <strong>jdoe@fabrikam.com</strong>.</span></span> |
   | <span data-ttu-id="0459b-130">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="0459b-130">**Telephone Number**</span></span>  |          <span data-ttu-id="0459b-131">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-131">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="0459b-132">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="0459b-132">**Fax Number**</span></span>     |          <span data-ttu-id="0459b-133">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-133">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="0459b-134">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="0459b-134">**Supply chain code**</span></span> |     <span data-ttu-id="0459b-135">型**電子部品**します。</span><span class="sxs-lookup"><span data-stu-id="0459b-135">Type **Electronic Components**.</span></span>      |


4. <span data-ttu-id="0459b-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0459b-136">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0459b-137">参照</span><span class="sxs-lookup"><span data-stu-id="0459b-137">See Also</span></span>  
 [<span data-ttu-id="0459b-138">ステップ 3:Contoso 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="0459b-138">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)