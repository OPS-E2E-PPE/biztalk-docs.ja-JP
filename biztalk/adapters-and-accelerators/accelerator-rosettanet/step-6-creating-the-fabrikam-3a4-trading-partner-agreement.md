---
title: 手順 6:パートナー アグリーメントの Fabrikam 3A4 取引先を作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e42c269c088d58abc3b0003bbc6a5df110e95a4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280699"
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a><span data-ttu-id="07614-102">手順 6:Fabrikam 3A4 取引先パートナー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="07614-102">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="07614-103">Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="07614-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="07614-104">3A4 パートナー インターフェイス プロセス (PIP) の新しい取引先アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="07614-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="07614-105">BTARN 管理コンソールを開始するには</span><span class="sxs-lookup"><span data-stu-id="07614-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="07614-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="07614-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="07614-107">3A4 取引先パートナー契約を作成するには</span><span class="sxs-lookup"><span data-stu-id="07614-107">To create the 3A4 trading partner agreement</span></span>  

1. <span data-ttu-id="07614-108">**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**契約**、 をポイント**新規**、順にクリックします**アグリーメント**.</span><span class="sxs-lookup"><span data-stu-id="07614-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="07614-109">**新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="07614-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="07614-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07614-110">Use this</span></span>          |                      <span data-ttu-id="07614-111">目的</span><span class="sxs-lookup"><span data-stu-id="07614-111">To do this</span></span>                       |
   |---------------------------|-------------------------------------------------------|
   |         <span data-ttu-id="07614-112">**名前**</span><span class="sxs-lookup"><span data-stu-id="07614-112">**Name**</span></span>          |           <span data-ttu-id="07614-113">型**Fabrikam_To_Contoso_3A4**します。</span><span class="sxs-lookup"><span data-stu-id="07614-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>           |
   | <span data-ttu-id="07614-114">**プロセスの構成**</span><span class="sxs-lookup"><span data-stu-id="07614-114">**Process Configuration**</span></span> |  <span data-ttu-id="07614-115">選択**STD_3A4_V02.02**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>   |
   |    <span data-ttu-id="07614-116">**自分の所属組織**</span><span class="sxs-lookup"><span data-stu-id="07614-116">**My Organization**</span></span>    |     <span data-ttu-id="07614-117">選択**Fabrikam**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-117">Select **Fabrikam** from the drop-down list.</span></span>      |
   | <span data-ttu-id="07614-118">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="07614-118">**Partner Organization**</span></span>  |      <span data-ttu-id="07614-119">選択**Contoso**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-119">Select **Contoso** from the drop-down list.</span></span>      |
   |     <span data-ttu-id="07614-120">**RNIF のバージョン**</span><span class="sxs-lookup"><span data-stu-id="07614-120">**RNIF Version**</span></span>      |     <span data-ttu-id="07614-121">選択**V02.00.01**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-121">Select **V02.00.01** from the drop-down list.</span></span>     |
   |       <span data-ttu-id="07614-122">**ホーム ロール**</span><span class="sxs-lookup"><span data-stu-id="07614-122">**Home Role**</span></span>       | <span data-ttu-id="07614-123">選択**Buyer (開始側)** ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-123">Select **Buyer (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="07614-124">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="07614-124">**Usage**</span></span>         |       <span data-ttu-id="07614-125">選択**テスト**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="07614-125">Select **Test** from the drop-down list.</span></span>        |


3. <span data-ttu-id="07614-126">**ポート** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="07614-126">On the **Ports** tab, do the following:</span></span>  


   |    <span data-ttu-id="07614-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="07614-127">Use this</span></span>    |                          <span data-ttu-id="07614-128">目的</span><span class="sxs-lookup"><span data-stu-id="07614-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="07614-129">**アクションの URL**</span><span class="sxs-lookup"><span data-stu-id="07614-129">**Action URL**</span></span> | <span data-ttu-id="07614-130">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="07614-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="07614-131">**シグナル URL**</span><span class="sxs-lookup"><span data-stu-id="07614-131">**Signal URL**</span></span> | <span data-ttu-id="07614-132">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="07614-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="07614-133">**同期 URL**</span><span class="sxs-lookup"><span data-stu-id="07614-133">**Sync URL**</span></span>  | <span data-ttu-id="07614-134">型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="07614-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="07614-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07614-135">Click **OK**.</span></span>  

5. <span data-ttu-id="07614-136">右クリックし、 **Fabrikam_To_Contoso_3A4**契約書とクリック**アクティブ化**します。</span><span class="sxs-lookup"><span data-stu-id="07614-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="07614-137">参照</span><span class="sxs-lookup"><span data-stu-id="07614-137">See Also</span></span>  
 [<span data-ttu-id="07614-138">手順 7:LOBWebApplication SDK サンプルのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="07614-138">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)