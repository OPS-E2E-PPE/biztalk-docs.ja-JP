---
title: 手順 2:Contoso 取引先組織の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating partner organizations
ms.assetid: ebb3b166-3781-40b9-89d4-2ca0c83d05f3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d540a24be7ae5421956a3ad80536490f5a9fef6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281285"
---
# <a name="step-2-creating-the-contoso-partner-organization"></a><span data-ttu-id="31530-102">手順 2:Contoso 取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="31530-102">Step 2: Creating the Contoso Partner Organization</span></span>
<span data-ttu-id="31530-103">この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール、新しい取引を作成します。</span><span class="sxs-lookup"><span data-stu-id="31530-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="31530-104">このチュートリアルでは、取引先パートナーは、Contoso 組織です。</span><span class="sxs-lookup"><span data-stu-id="31530-104">The trading partner for this tutorial is the Contoso organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="31530-105">BTARN 管理コンソールを開始するには</span><span class="sxs-lookup"><span data-stu-id="31530-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="31530-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="31530-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="31530-107">取引先パートナーとして Fabrikam を作成するには</span><span class="sxs-lookup"><span data-stu-id="31530-107">To create Fabrikam as a trading partner</span></span>  

1. <span data-ttu-id="31530-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、 をクリックし、**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="31530-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  

2. <span data-ttu-id="31530-109">新しいパートナーのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います<strong>:</strong></span><span class="sxs-lookup"><span data-stu-id="31530-109">In the New Partner Properties dialog box, on the **General** tab, do the following<strong>:</strong></span></span>  


   |          <span data-ttu-id="31530-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="31530-110">Use this</span></span>          |                             <span data-ttu-id="31530-111">目的</span><span class="sxs-lookup"><span data-stu-id="31530-111">To do this</span></span>                              |
   |----------------------------|---------------------------------------------------------------------|
   |          <span data-ttu-id="31530-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="31530-112">**Name**</span></span>          |                          <span data-ttu-id="31530-113">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="31530-113">Type **CONTOSO**.</span></span>                          |
   |          <span data-ttu-id="31530-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="31530-114">**GBI**</span></span>           |                         <span data-ttu-id="31530-115">型**123456789**します。</span><span class="sxs-lookup"><span data-stu-id="31530-115">Type **123456789**.</span></span>                         |
   | <span data-ttu-id="31530-116">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="31530-116">**Partner Classification**</span></span> |          <span data-ttu-id="31530-117">選択**製造元**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="31530-117">Select **Manufacturer** from the drop-down list.</span></span>           |
   | <span data-ttu-id="31530-118">**証明書の署名**</span><span class="sxs-lookup"><span data-stu-id="31530-118">**Signature Certificate**</span></span>  | <span data-ttu-id="31530-119">選択**Contoso Signature [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="31530-119">Select **Contoso Signature [Thumbprint]** from the drop-down list.</span></span>  |
   | <span data-ttu-id="31530-120">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="31530-120">**Encryption Certificate**</span></span> | <span data-ttu-id="31530-121">選択**Contoso Encryption [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="31530-121">Select **Contoso Encryption [Thumbprint]** from the drop-down list.</span></span> |


3. <span data-ttu-id="31530-122">をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="31530-122">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="31530-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="31530-123">Use this</span></span>        |               <span data-ttu-id="31530-124">目的</span><span class="sxs-lookup"><span data-stu-id="31530-124">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="31530-125">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="31530-125">**Contact Name**</span></span>    |           <span data-ttu-id="31530-126">型**John Doe**します。</span><span class="sxs-lookup"><span data-stu-id="31530-126">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="31530-127">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="31530-127">**E-mail Address**</span></span>   | <span data-ttu-id="31530-128">型 <strong>jdoe@contoso.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="31530-128">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="31530-129">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="31530-129">**Telephone Number**</span></span>  |         <span data-ttu-id="31530-130">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="31530-130">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="31530-131">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="31530-131">**Fax Number**</span></span>     |         <span data-ttu-id="31530-132">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="31530-132">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="31530-133">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="31530-133">**Supply chain code**</span></span> |     <span data-ttu-id="31530-134">型**電子部品**します。</span><span class="sxs-lookup"><span data-stu-id="31530-134">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="31530-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31530-135">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="31530-136">参照</span><span class="sxs-lookup"><span data-stu-id="31530-136">See Also</span></span>  
 [<span data-ttu-id="31530-137">ステップ 3:Fabrikam 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="31530-137">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)