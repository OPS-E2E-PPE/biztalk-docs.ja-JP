---
title: '手順 2: Contoso パートナー組織の作成 |Microsoft Docs'
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
ms.openlocfilehash: 97e811493c1347bc016671469da8a0dc18483e85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969779"
---
# <a name="step-2-creating-the-contoso-partner-organization"></a><span data-ttu-id="e4564-102">手順 2: Contoso パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="e4564-102">Step 2: Creating the Contoso Partner Organization</span></span>
<span data-ttu-id="e4564-103">この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール、新しい取引を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4564-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="e4564-104">このチュートリアルでは、Contoso 組織という取引先を使用します。</span><span class="sxs-lookup"><span data-stu-id="e4564-104">The trading partner for this tutorial is the Contoso organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="e4564-105">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="e4564-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="e4564-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="e4564-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="e4564-107">Fabrikam という名前の取引先を作成するには</span><span class="sxs-lookup"><span data-stu-id="e4564-107">To create Fabrikam as a trading partner</span></span>  

1. <span data-ttu-id="e4564-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、 をクリックし、**パートナー**.</span><span class="sxs-lookup"><span data-stu-id="e4564-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  

2. <span data-ttu-id="e4564-109">新しいパートナーのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います<strong>:</strong></span><span class="sxs-lookup"><span data-stu-id="e4564-109">In the New Partner Properties dialog box, on the **General** tab, do the following<strong>:</strong></span></span>  


   |          <span data-ttu-id="e4564-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e4564-110">Use this</span></span>          |                             <span data-ttu-id="e4564-111">目的</span><span class="sxs-lookup"><span data-stu-id="e4564-111">To do this</span></span>                              |
   |----------------------------|---------------------------------------------------------------------|
   |          <span data-ttu-id="e4564-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="e4564-112">**Name**</span></span>          |                          <span data-ttu-id="e4564-113">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-113">Type **CONTOSO**.</span></span>                          |
   |          <span data-ttu-id="e4564-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="e4564-114">**GBI**</span></span>           |                         <span data-ttu-id="e4564-115">型**123456789**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-115">Type **123456789**.</span></span>                         |
   | <span data-ttu-id="e4564-116">**パートナーの分類**</span><span class="sxs-lookup"><span data-stu-id="e4564-116">**Partner Classification**</span></span> |          <span data-ttu-id="e4564-117">選択**製造元**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="e4564-117">Select **Manufacturer** from the drop-down list.</span></span>           |
   | <span data-ttu-id="e4564-118">**証明書の署名**</span><span class="sxs-lookup"><span data-stu-id="e4564-118">**Signature Certificate**</span></span>  | <span data-ttu-id="e4564-119">選択**Contoso Signature [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="e4564-119">Select **Contoso Signature [Thumbprint]** from the drop-down list.</span></span>  |
   | <span data-ttu-id="e4564-120">**暗号化証明書**</span><span class="sxs-lookup"><span data-stu-id="e4564-120">**Encryption Certificate**</span></span> | <span data-ttu-id="e4564-121">選択**Contoso Encryption [Thumbprint]** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="e4564-121">Select **Contoso Encryption [Thumbprint]** from the drop-down list.</span></span> |


3. <span data-ttu-id="e4564-122">をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e4564-122">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="e4564-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e4564-123">Use this</span></span>        |               <span data-ttu-id="e4564-124">目的</span><span class="sxs-lookup"><span data-stu-id="e4564-124">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="e4564-125">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="e4564-125">**Contact Name**</span></span>    |           <span data-ttu-id="e4564-126">型**John Doe**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-126">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="e4564-127">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="e4564-127">**E-mail Address**</span></span>   | <span data-ttu-id="e4564-128">型 <strong>jdoe@contoso.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="e4564-128">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="e4564-129">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="e4564-129">**Telephone Number**</span></span>  |         <span data-ttu-id="e4564-130">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-130">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="e4564-131">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="e4564-131">**Fax Number**</span></span>     |         <span data-ttu-id="e4564-132">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-132">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="e4564-133">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="e4564-133">**Supply chain code**</span></span> |     <span data-ttu-id="e4564-134">型**電子部品**します。</span><span class="sxs-lookup"><span data-stu-id="e4564-134">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="e4564-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e4564-135">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4564-136">参照</span><span class="sxs-lookup"><span data-stu-id="e4564-136">See Also</span></span>  
 [<span data-ttu-id="e4564-137">手順 3: Fabrikam 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="e4564-137">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)