---
title: CIDX eStandards メッセージ交換 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2aef1c49ca4bb87ef2e9388b9cdfcc86d2f35f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988867"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a><span data-ttu-id="12d41-102">CIDX eStandards メッセージ交換</span><span class="sxs-lookup"><span data-stu-id="12d41-102">Setting Up CIDX eStandards Message Exchange</span></span>
<span data-ttu-id="12d41-103">ここでは、Chemical Data Exchange (CIDX) eStandards メッセージ交換のセットアップ方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="12d41-103">This topic describes how to set up Chemical Data Exchange (CIDX) eStandards message exchange.</span></span> <span data-ttu-id="12d41-104">CIDX では、次の 3 つのプロパティが次のように設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d41-104">CIDX requires that you set the following three properties:</span></span>  
  
- <span data-ttu-id="12d41-105">`Standard` プロセス構成設定にプロパティ**CIDX**</span><span class="sxs-lookup"><span data-stu-id="12d41-105">`Standard` property in the process configuration settings to **CIDX**</span></span>  
  
- <span data-ttu-id="12d41-106">プロセス構成設定の `Is Single Action` プロパティが `True` に設定されている。</span><span class="sxs-lookup"><span data-stu-id="12d41-106">`Is Single Action` property in the process configuration settings to `True`</span></span>  
  
- <span data-ttu-id="12d41-107">`0A1 agreement` プロパティを取引先アグリーメントに**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="12d41-107">`0A1 agreement` property in the trading partner agreement to **No 0A1**</span></span>  
  
  <span data-ttu-id="12d41-108">CIDX と RosettaNet の違いについては、次を参照してください。 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)します。</span><span class="sxs-lookup"><span data-stu-id="12d41-108">For information about the differences between CIDX and RosettaNet, see [CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span></span>  
  
### <a name="to-set-up-cidx-message-exchange"></a><span data-ttu-id="12d41-109">CIDX メッセージ交換をセットアップするには</span><span class="sxs-lookup"><span data-stu-id="12d41-109">To set up CIDX message exchange</span></span>  
  
1. <span data-ttu-id="12d41-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="12d41-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="12d41-111">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。</span><span class="sxs-lookup"><span data-stu-id="12d41-111">In the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span></span>  
  
3. <span data-ttu-id="12d41-112">右クリック**プロセス構成設定**、 をポイント**新規**、 をクリックし、**プロセス構成**します。</span><span class="sxs-lookup"><span data-stu-id="12d41-112">Right-click **Process Configuration Settings**, point to **New**, and then click **Process Configuration**.</span></span>  
  
4. <span data-ttu-id="12d41-113">新しいプロセス構成のプロパティ ダイアログ ボックスで、上、**全般** タブの**標準**プロパティで、 **CIDX**。</span><span class="sxs-lookup"><span data-stu-id="12d41-113">In the New Process Configuration Properties dialog box, on the **General** tab, for the **Standard** property, select **CIDX**.</span></span>  
  
5. <span data-ttu-id="12d41-114">**アクティビティ** タブの**シングル アクション**プロパティで、 **True**。</span><span class="sxs-lookup"><span data-stu-id="12d41-114">On the **Activity** tab, for the **Is Single Action** property, select **True**.</span></span>  
  
6. <span data-ttu-id="12d41-115">必要に応じて、その他のプロセス構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="12d41-115">Enter other process configuration settings as needed.</span></span> <span data-ttu-id="12d41-116">これらの設定については、表を参照して[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="12d41-116">For information about these settings, see the table in [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
7. <span data-ttu-id="12d41-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12d41-117">Click **OK**.</span></span>  
  
8. <span data-ttu-id="12d41-118">右クリックして**契約**、 をポイント**新規**、順にクリックします**契約**します。</span><span class="sxs-lookup"><span data-stu-id="12d41-118">Right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
9. <span data-ttu-id="12d41-119">**全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブで、さまざまな設定値を入力します。</span><span class="sxs-lookup"><span data-stu-id="12d41-119">On the **General**, **Ports**, **Protocol**, and **Custom Properties** tabs, enter the values for the various settings.</span></span> <span data-ttu-id="12d41-120">これらの設定については、表を参照して[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。</span><span class="sxs-lookup"><span data-stu-id="12d41-120">For information about these settings, see the table in [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
10. <span data-ttu-id="12d41-121">新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般** タブの**0A1 アグリーメント**プロパティで、 **0A1**。</span><span class="sxs-lookup"><span data-stu-id="12d41-121">In the New Agreement Properties dialog box, on the **General** tab, for the **0A1 agreement** property, select **No 0A1**.</span></span>  
  
11. <span data-ttu-id="12d41-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12d41-122">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12d41-123">参照</span><span class="sxs-lookup"><span data-stu-id="12d41-123">See Also</span></span>  
 <span data-ttu-id="12d41-124">[作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="12d41-124">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="12d41-125">[作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="12d41-125">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 <span data-ttu-id="12d41-126">[作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="12d41-126">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 [<span data-ttu-id="12d41-127">パートナーの作成と編集</span><span class="sxs-lookup"><span data-stu-id="12d41-127">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)