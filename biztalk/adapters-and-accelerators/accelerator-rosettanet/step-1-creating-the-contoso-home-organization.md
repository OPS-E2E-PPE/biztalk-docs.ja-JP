---
title: "手順 1: Contoso ホーム組織の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06c1a9c4cf224055cc910e97902092fa476feb5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-creating-the-contoso-home-organization"></a><span data-ttu-id="ed85c-102">手順 1: Contoso ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="ed85c-102">Step 1: Creating the Contoso Home Organization</span></span>
<span data-ttu-id="ed85c-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso のホーム組織を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed85c-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create the Contoso home organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="ed85c-104">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="ed85c-104">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="ed85c-105">Contoso のコンピューターでをクリックして**開始**、指す**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet** をクリックし、  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ed85c-105">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft  BizTalk \<version\> Accelerator for RosettaNet** and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-home-organization"></a><span data-ttu-id="ed85c-106">ホーム組織を作成するには</span><span class="sxs-lookup"><span data-stu-id="ed85c-106">To create the home organization</span></span>  
  
1.  <span data-ttu-id="ed85c-107">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**ホーム組織**、 をポイント**新規**、クリックして**ホーム組織**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-107">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Home Organizations**, point to **New**, and then click **Home Organization**.</span></span>  
  
2.  <span data-ttu-id="ed85c-108">新しいホーム組織のプロパティ ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ed85c-108">In the New Home Organization Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="ed85c-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed85c-109">Use this</span></span>|<span data-ttu-id="ed85c-110">目的</span><span class="sxs-lookup"><span data-stu-id="ed85c-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed85c-111">**名前**</span><span class="sxs-lookup"><span data-stu-id="ed85c-111">**Name**</span></span>|<span data-ttu-id="ed85c-112">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="ed85c-113">**[GBI]**</span><span class="sxs-lookup"><span data-stu-id="ed85c-113">**GBI**</span></span>|<span data-ttu-id="ed85c-114">型**123456789**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-114">Type **123456789**.</span></span> <span data-ttu-id="ed85c-115">**注:**を同じコンピューターでループバック チュートリアルを実行する場合は、異なる 123456789 以外は、[gbi] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed85c-115">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "123456789".</span></span>|  
    |<span data-ttu-id="ed85c-116">**ホーム組織の分類**</span><span class="sxs-lookup"><span data-stu-id="ed85c-116">**Home Organization Classification**</span></span>|<span data-ttu-id="ed85c-117">選択**製造元**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="ed85c-117">Select **Manufacturer** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="ed85c-118">クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ed85c-118">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="ed85c-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed85c-119">Use this</span></span>|<span data-ttu-id="ed85c-120">目的</span><span class="sxs-lookup"><span data-stu-id="ed85c-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ed85c-121">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="ed85c-121">**Contact Name**</span></span>|<span data-ttu-id="ed85c-122">型**John doe さん**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-122">Type **John Doe**.</span></span>|  
    |<span data-ttu-id="ed85c-123">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="ed85c-123">**E-mail Address**</span></span>|<span data-ttu-id="ed85c-124">型 **jdoe@contoso.com**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-124">Type **jdoe@contoso.com**.</span></span>|  
    |<span data-ttu-id="ed85c-125">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="ed85c-125">**Telephone Number**</span></span>|<span data-ttu-id="ed85c-126">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-126">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="ed85c-127">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="ed85c-127">**Fax Number**</span></span>|<span data-ttu-id="ed85c-128">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-128">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="ed85c-129">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="ed85c-129">**Supply Chain Code**</span></span>|<span data-ttu-id="ed85c-130">型**電子部品**です。</span><span class="sxs-lookup"><span data-stu-id="ed85c-130">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="ed85c-131">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed85c-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed85c-132">参照</span><span class="sxs-lookup"><span data-stu-id="ed85c-132">See Also</span></span>  
 [<span data-ttu-id="ed85c-133">手順 2: Fabrikam 取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="ed85c-133">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)