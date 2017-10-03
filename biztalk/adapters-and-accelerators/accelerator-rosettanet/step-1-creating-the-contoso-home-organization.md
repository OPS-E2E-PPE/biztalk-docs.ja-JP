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
ms.openlocfilehash: 21e6afcc3aca274d968b15f2bbe93c2226e54a48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-creating-the-contoso-home-organization"></a><span data-ttu-id="17dbf-102">手順 1: Contoso ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="17dbf-102">Step 1: Creating the Contoso Home Organization</span></span>
<span data-ttu-id="17dbf-103">ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso のホーム組織を作成します。</span><span class="sxs-lookup"><span data-stu-id="17dbf-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create the Contoso home organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="17dbf-104">BTARN 管理コンソールを起動するには</span><span class="sxs-lookup"><span data-stu-id="17dbf-104">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="17dbf-105">Contoso のコンピューターでをクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**  をクリックし、 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="17dbf-105">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft  BizTalk \<version> Accelerator for RosettaNet** and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-home-organization"></a><span data-ttu-id="17dbf-106">ホーム組織を作成するには</span><span class="sxs-lookup"><span data-stu-id="17dbf-106">To create the home organization</span></span>  
  
1.  <span data-ttu-id="17dbf-107">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**ホーム組織**、 をポイント**新規**、クリックして**ホーム組織**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-107">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Home Organizations**, point to **New**, and then click **Home Organization**.</span></span>  
  
2.  <span data-ttu-id="17dbf-108">新しいホーム組織のプロパティ ダイアログ ボックスで、**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="17dbf-108">In the New Home Organization Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="17dbf-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="17dbf-109">Use this</span></span>|<span data-ttu-id="17dbf-110">目的</span><span class="sxs-lookup"><span data-stu-id="17dbf-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="17dbf-111">**名前**</span><span class="sxs-lookup"><span data-stu-id="17dbf-111">**Name**</span></span>|<span data-ttu-id="17dbf-112">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="17dbf-113">**[GBI]**</span><span class="sxs-lookup"><span data-stu-id="17dbf-113">**GBI**</span></span>|<span data-ttu-id="17dbf-114">型**123456789**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-114">Type **123456789**.</span></span> <span data-ttu-id="17dbf-115">**注:**を同じコンピューターでループバック チュートリアルを実行する場合は、異なる 123456789 以外は、[gbi] に値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17dbf-115">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "123456789".</span></span>|  
    |<span data-ttu-id="17dbf-116">**ホーム組織の分類**</span><span class="sxs-lookup"><span data-stu-id="17dbf-116">**Home Organization Classification**</span></span>|<span data-ttu-id="17dbf-117">選択**製造元**ドロップダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="17dbf-117">Select **Manufacturer** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="17dbf-118">クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="17dbf-118">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="17dbf-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="17dbf-119">Use this</span></span>|<span data-ttu-id="17dbf-120">目的</span><span class="sxs-lookup"><span data-stu-id="17dbf-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="17dbf-121">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="17dbf-121">**Contact Name**</span></span>|<span data-ttu-id="17dbf-122">型**John doe さん**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-122">Type **John Doe**.</span></span>|  
    |<span data-ttu-id="17dbf-123">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="17dbf-123">**E-mail Address**</span></span>|<span data-ttu-id="17dbf-124">型 **jdoe@contoso.com**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-124">Type **jdoe@contoso.com**.</span></span>|  
    |<span data-ttu-id="17dbf-125">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="17dbf-125">**Telephone Number**</span></span>|<span data-ttu-id="17dbf-126">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-126">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="17dbf-127">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="17dbf-127">**Fax Number**</span></span>|<span data-ttu-id="17dbf-128">型**555-555-5555**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-128">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="17dbf-129">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="17dbf-129">**Supply Chain Code**</span></span>|<span data-ttu-id="17dbf-130">型**電子部品**です。</span><span class="sxs-lookup"><span data-stu-id="17dbf-130">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="17dbf-131">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17dbf-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17dbf-132">参照</span><span class="sxs-lookup"><span data-stu-id="17dbf-132">See Also</span></span>  
 [<span data-ttu-id="17dbf-133">手順 2: Fabrikam パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="17dbf-133">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)