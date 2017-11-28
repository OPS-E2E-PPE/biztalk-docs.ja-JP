---
title: "設定を CIDX eStandards メッセージ交換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4606dfc4b912d884a997bb65acb26cb4352448
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-up-cidx-estandards-message-exchange"></a><span data-ttu-id="4cab5-102">設定を CIDX eStandards メッセージ交換</span><span class="sxs-lookup"><span data-stu-id="4cab5-102">Setting Up CIDX eStandards Message Exchange</span></span>
<span data-ttu-id="4cab5-103">ここでは、Chemical Data Exchange (CIDX) eStandards メッセージ交換のセットアップ方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4cab5-103">This topic describes how to set up Chemical Data Exchange (CIDX) eStandards message exchange.</span></span> <span data-ttu-id="4cab5-104">CIDX では、次の 3 つのプロパティが次のように設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cab5-104">CIDX requires that you set the following three properties:</span></span>  
  
-   <span data-ttu-id="4cab5-105">`Standard`プロセス構成設定にプロパティ**CIDX**</span><span class="sxs-lookup"><span data-stu-id="4cab5-105">`Standard` property in the process configuration settings to **CIDX**</span></span>  
  
-   <span data-ttu-id="4cab5-106">プロセス構成設定の `Is Single Action` プロパティが `True` に設定されている。</span><span class="sxs-lookup"><span data-stu-id="4cab5-106">`Is Single Action` property in the process configuration settings to `True`</span></span>  
  
-   <span data-ttu-id="4cab5-107">`0A1 agreement`プロパティを取引先アグリーメントに**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="4cab5-107">`0A1 agreement` property in the trading partner agreement to **No 0A1**</span></span>  
  
 <span data-ttu-id="4cab5-108">CIDX と RosettaNet の違いの詳細については、次を参照してください。 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-108">For information about the differences between CIDX and RosettaNet, see [CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span></span>  
  
### <a name="to-set-up-cidx-message-exchange"></a><span data-ttu-id="4cab5-109">CIDX メッセージ交換をセットアップするには</span><span class="sxs-lookup"><span data-stu-id="4cab5-109">To set up CIDX message exchange</span></span>  
  
1.  <span data-ttu-id="4cab5-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="4cab5-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="4cab5-111">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。</span><span class="sxs-lookup"><span data-stu-id="4cab5-111">In the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span></span>  
  
3.  <span data-ttu-id="4cab5-112">右クリック**プロセス構成設定**、 をポイント**新規**、クリックして**プロセス構成**です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-112">Right-click **Process Configuration Settings**, point to **New**, and then click **Process Configuration**.</span></span>  
  
4.  <span data-ttu-id="4cab5-113">新しいプロセス構成のプロパティ ダイアログ ボックスで、**全般** タブの**標準**プロパティを選択**CIDX**です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-113">In the New Process Configuration Properties dialog box, on the **General** tab, for the **Standard** property, select **CIDX**.</span></span>  
  
5.  <span data-ttu-id="4cab5-114">**アクティビティ** タブの**シングル アクション**プロパティで、 **True**です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-114">On the **Activity** tab, for the **Is Single Action** property, select **True**.</span></span>  
  
6.  <span data-ttu-id="4cab5-115">必要に応じて、その他のプロセス構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cab5-115">Enter other process configuration settings as needed.</span></span> <span data-ttu-id="4cab5-116">これらの設定については、表を参照して[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-116">For information about these settings, see the table in [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
7.  <span data-ttu-id="4cab5-117">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cab5-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="4cab5-118">右クリック**契約**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-118">Right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
9. <span data-ttu-id="4cab5-119">**全般**、**ポート**、**プロトコル**、および**カスタム プロパティ**タブは、さまざまな設定の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="4cab5-119">On the **General**, **Ports**, **Protocol**, and **Custom Properties** tabs, enter the values for the various settings.</span></span> <span data-ttu-id="4cab5-120">これらの設定については、表を参照して[を作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-120">For information about these settings, see the table in [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
10. <span data-ttu-id="4cab5-121">新しいアグリーメントのプロパティ ダイアログ ボックスで、**全般** タブの**0A1 アグリーメント**プロパティを選択**非 0A1**です。</span><span class="sxs-lookup"><span data-stu-id="4cab5-121">In the New Agreement Properties dialog box, on the **General** tab, for the **0A1 agreement** property, select **No 0A1**.</span></span>  
  
11. <span data-ttu-id="4cab5-122">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cab5-122">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cab5-123">参照</span><span class="sxs-lookup"><span data-stu-id="4cab5-123">See Also</span></span>  
 <span data-ttu-id="4cab5-124">[作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4cab5-124">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="4cab5-125">[作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="4cab5-125">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 <span data-ttu-id="4cab5-126">[作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="4cab5-126">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 [<span data-ttu-id="4cab5-127">作成またはパートナーを編集します。</span><span class="sxs-lookup"><span data-stu-id="4cab5-127">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)