---
title: 手順 1:Contoso ホーム組織の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3893d582a85708190f1f030b06187fcd8f152bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281596"
---
# <a name="step-1-creating-the-contoso-home-organization"></a><span data-ttu-id="a8a43-102">手順 1:Contoso ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="a8a43-102">Step 1: Creating the Contoso Home Organization</span></span>
<span data-ttu-id="a8a43-103">この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Contoso ホーム組織を作成する管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a8a43-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create the Contoso home organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="a8a43-104">BTARN 管理コンソールを開始するには</span><span class="sxs-lookup"><span data-stu-id="a8a43-104">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="a8a43-105">Contoso コンピューターでは、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**。し**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a8a43-105">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft  BizTalk \<version\> Accelerator for RosettaNet** and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-home-organization"></a><span data-ttu-id="a8a43-106">ホーム組織を作成するには</span><span class="sxs-lookup"><span data-stu-id="a8a43-106">To create the home organization</span></span>  

1. <span data-ttu-id="a8a43-107">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**ホーム組織**、 をポイント**新規**、順にクリックします**ホーム組織**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-107">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Home Organizations**, point to **New**, and then click **Home Organization**.</span></span>  

2. <span data-ttu-id="a8a43-108">新しいホーム組織のプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a8a43-108">In the New Home Organization Properties dialog box, on the **General** tab, do the following:</span></span>  


   |               <span data-ttu-id="a8a43-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a8a43-109">Use this</span></span>               |                                                                              <span data-ttu-id="a8a43-110">目的</span><span class="sxs-lookup"><span data-stu-id="a8a43-110">To do this</span></span>                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               <span data-ttu-id="a8a43-111">**名前**</span><span class="sxs-lookup"><span data-stu-id="a8a43-111">**Name**</span></span>               |                                                                           <span data-ttu-id="a8a43-112">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-112">Type **CONTOSO**.</span></span>                                                                           |
   |               <span data-ttu-id="a8a43-113">**GBI**</span><span class="sxs-lookup"><span data-stu-id="a8a43-113">**GBI**</span></span>                | <span data-ttu-id="a8a43-114">型**123456789**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-114">Type **123456789**.</span></span> <span data-ttu-id="a8a43-115">**注:** 同じコンピューターで、Loopback チュートリアルを実行した場合の gbi に 123456789 以外の異なる値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8a43-115">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "123456789".</span></span> |
   | <span data-ttu-id="a8a43-116">**ホーム組織の分類**</span><span class="sxs-lookup"><span data-stu-id="a8a43-116">**Home Organization Classification**</span></span> |                                                           <span data-ttu-id="a8a43-117">選択**製造元**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="a8a43-117">Select **Manufacturer** from the drop-down list.</span></span>                                                            |


3. <span data-ttu-id="a8a43-118">をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a8a43-118">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="a8a43-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a8a43-119">Use this</span></span>        |               <span data-ttu-id="a8a43-120">目的</span><span class="sxs-lookup"><span data-stu-id="a8a43-120">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="a8a43-121">**連絡先の名前**</span><span class="sxs-lookup"><span data-stu-id="a8a43-121">**Contact Name**</span></span>    |           <span data-ttu-id="a8a43-122">型**John Doe**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-122">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="a8a43-123">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="a8a43-123">**E-mail Address**</span></span>   | <span data-ttu-id="a8a43-124">型 <strong>jdoe@contoso.com</strong>します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-124">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="a8a43-125">**電話番号**</span><span class="sxs-lookup"><span data-stu-id="a8a43-125">**Telephone Number**</span></span>  |         <span data-ttu-id="a8a43-126">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-126">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="a8a43-127">**Fax 番号**</span><span class="sxs-lookup"><span data-stu-id="a8a43-127">**Fax Number**</span></span>     |         <span data-ttu-id="a8a43-128">型**555-555-5555**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-128">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="a8a43-129">**サプライ チェーン コード**</span><span class="sxs-lookup"><span data-stu-id="a8a43-129">**Supply Chain Code**</span></span> |     <span data-ttu-id="a8a43-130">型**電子部品**します。</span><span class="sxs-lookup"><span data-stu-id="a8a43-130">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="a8a43-131">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8a43-131">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a8a43-132">参照</span><span class="sxs-lookup"><span data-stu-id="a8a43-132">See Also</span></span>  
 [<span data-ttu-id="a8a43-133">手順 2:Fabrikam 取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="a8a43-133">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)