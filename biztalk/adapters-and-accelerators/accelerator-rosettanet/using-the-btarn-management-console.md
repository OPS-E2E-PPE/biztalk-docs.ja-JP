---
title: BTARN 管理コンソールの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, activating
- activating agreements
- BTARN Management Console, Scope pane
- tracking
- creating, trading partners
- BTARN Management Console, agreements
- process configuration
- agreements, modifying
- BTARN Management Console, home organizations
- agreements, creating
- BTARN Management Console, trading partners
- agreements, deleting
- deleting, agreements
- BTARN Management Console
- agreements, listing
- modifying, trading partners
- creating, agreements
- trading partners, creating
- modifying, agreements
- BAM tracking
- Scope pane [BTARN Management Console]
- trading partners, modifying
- trading partners, deleting
- BTARN Management Console, process configurations
- deleting, trading partners
- BTARN Management Console, about BTARN Management Console
- home organizations
ms.assetid: 000ee93d-eb1d-4ff8-a9cf-0547beff027d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35c054e78f09edbe84d799b7218d4921b83795c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977923"
---
# <a name="using-the-btarn-management-console"></a><span data-ttu-id="16db0-102">BTARN 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="16db0-102">Using the BTARN Management Console</span></span>
<span data-ttu-id="16db0-103">ここでは、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16db0-103">This topic describes how to administer [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] from the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span>  
  
 <span data-ttu-id="16db0-104">開く、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールをクリックして**開始**をポイントして、**プログラム**をポイントして、 **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]をクリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-104">Open the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console by clicking **Start**, pointing to **Programs**, pointing to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then clicking [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
 <span data-ttu-id="16db0-105">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールのスコープ (左) ペインには、すべての [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成ノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16db0-105">The scope (left) pane of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console includes all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration nodes.</span></span> <span data-ttu-id="16db0-106">結果 (右) ペインには、スコープ ペインで選択した構成項目の特定のインスタンスがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="16db0-106">The results (right) pane includes all the specific instances of whatever configuration items you have selected in the scope pane.</span></span>  
  
## <a name="operations-in-the-scope-pane"></a><span data-ttu-id="16db0-107">スコープ ペインでの操作</span><span class="sxs-lookup"><span data-stu-id="16db0-107">Operations in the Scope Pane</span></span>  
 <span data-ttu-id="16db0-108">スコープ ペイン内のノードについて、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16db0-108">You can perform the following operations on nodes in the scope pane:</span></span>  
  
- <span data-ttu-id="16db0-109">パートナー送信ポートで使用する [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送受信パイプラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="16db0-109">Set the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send and receive pipelines that you want to use for partner send ports.</span></span> <span data-ttu-id="16db0-110">詳細については、[設定 BTARN 送信パイプラインと受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-110">For more information, see [Setting BTARN Send and Receive Pipelines](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md).</span></span>  
  
- <span data-ttu-id="16db0-111">ビジネス アクティビティ監視 (BAM) の追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="16db0-111">Enable Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="16db0-112">詳細については、[BAM の追跡を有効にする](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-112">For more information, see [Enabling BAM Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md).</span></span>  
  
- <span data-ttu-id="16db0-113">新しくインポートした構成をスコープ ペインで、[構成] ノードを右クリックし、をクリックして、コンソールに表示されることを確認**更新**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-113">Make sure that any newly imported configuration is visible in the console by right-clicking the configuration node in the scope pane, and then clicking **Refresh**.</span></span>  
  
- <span data-ttu-id="16db0-114">右クリックし、結果ウィンドウで、追加の列を表示、**プロセス構成設定**または**契約**を指す、スコープ ペインでノード**ビュー**、し、クリックすると**列の追加/削除**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-114">View additional columns in the results pane by right-clicking the **Process Configuration Settings** or **Agreement** node in the scope pane, pointing to **View**, and then clicking **Add/Remove columns**.</span></span> <span data-ttu-id="16db0-115">使用して、使用可能な列と表示されている列の間で列を移動、**を追加または削除**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="16db0-115">Move columns between the available columns and displayed columns by using the **Add or Remove** button.</span></span> <span data-ttu-id="16db0-116">このコマンドは、既定では [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に表示されませんが、使用できる列が多数あるアグリーメントで特に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="16db0-116">This command is especially useful for agreements that have many available columns that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not display by default.</span></span>  
  
## <a name="process-configurations"></a><span data-ttu-id="16db0-117">プロセス構成</span><span class="sxs-lookup"><span data-stu-id="16db0-117">Process Configurations</span></span>  
 <span data-ttu-id="16db0-118">プロセス構成設定について、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16db0-118">You can perform the following operations on a process configuration:</span></span>  
  
-   <span data-ttu-id="16db0-119">右クリックして新しいプロセス構成を追加、**プロセス構成設定**スコープ ノードを指す**新規**、 をクリックし、**プロセス構成**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-119">Add a new process configuration by right-clicking the **Process Configuration Settings** scope node, pointing to **New**, and then clicking **Process Configuration**.</span></span> <span data-ttu-id="16db0-120">詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-120">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
-   <span data-ttu-id="16db0-121">結果ウィンドウでプロセス構成を右クリックし、をクリックして既存のプロセス構成を編集**プロパティ**、またはプロセス構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="16db0-121">Edit an existing process configuration by right-clicking the process configuration in the results pane, and then clicking **Properties**, or by double-clicking the process configuration.</span></span> <span data-ttu-id="16db0-122">詳細については、[を作成またはプロセス構成の編集方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-122">For more information, see [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
-   <span data-ttu-id="16db0-123">結果ウィンドウでプロセス構成を右クリックし、をクリックして既存のプロセス構成を削除**削除**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-123">Delete an existing process configuration by right-clicking the process configuration in the results pane, and then clicking **Delete**.</span></span>  
  
-   <span data-ttu-id="16db0-124">新しい構成を基準とする結果ウィンドウで、構成を右クリックし、をクリックして、既存のプロセス構成に基づいて、新しいプロセス構成を作成**コピーから新しいプロセス構成**.</span><span class="sxs-lookup"><span data-stu-id="16db0-124">Create a new process configuration based on an existing process configuration by right-clicking the configuration in the results pane that you want to base the new configuration on, and then clicking **New Process Configuration from Copy**.</span></span> <span data-ttu-id="16db0-125">これにより、新しい表示されます**プロセス構成のプロパティ**が設定された、既存の構成 ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="16db0-125">This will display a new **Process Configuration Properties** dialog box populated with the settings of the existing configuration.</span></span> <span data-ttu-id="16db0-126">新しい入力**コードを表示**、順にクリックします**OK**新しい構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="16db0-126">Enter a new **Display code**, and then click **OK** to create the new configuration.</span></span> <span data-ttu-id="16db0-127">詳細については、[PIP 仕様を使用して、プロセス構成を作成する](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-127">For more information, see [Using the PIP Specification to Create a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).</span></span>  
  
-   <span data-ttu-id="16db0-128">結果ウィンドウで特定の構成を右クリックし、をクリックして、プロセス構成が関連付けられているすべての契約の一覧を表示する**を表示する契約**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-128">Show a list of all the agreements that a process configuration is associated with by right-clicking the specific configuration in the results pane, and then clicking **Show Agreements**.</span></span> <span data-ttu-id="16db0-129">フォーカスを移すこれは、**契約**スコープ ペインでノードし、結果ウィンドウで、関連付けられているアグリーメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="16db0-129">This will shift the focus to the **Agreements** node in the scope pane and display the associated agreements in the results pane.</span></span> <span data-ttu-id="16db0-130">右クリックし、アグリーメントの完全な一覧に戻すことができます、**契約**スコープ ウィンドウで、クリックすると、ノード**すべて表示**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-130">You can revert to a complete list of agreements by right-clicking the **Agreements** node in the scope pane, and then clicking **Show All**.</span></span>  
  
## <a name="home-organizations"></a><span data-ttu-id="16db0-131">ホーム組織</span><span class="sxs-lookup"><span data-stu-id="16db0-131">Home Organizations</span></span>  
 <span data-ttu-id="16db0-132">ホーム組織について、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16db0-132">You can perform the following operations on a home organization:</span></span>  
  
-   <span data-ttu-id="16db0-133">右クリックして新しいホーム組織を追加、**ホーム組織**スコープ ノードを指す**新規**、 をクリックし、**ホーム組織**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-133">Add a new home organization by right-clicking the **Home Organizations** scope node, pointing to **New**, and then clicking **Home Organization**.</span></span> <span data-ttu-id="16db0-134">詳細については、[を作成または編集、ホーム組織](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-134">For more information, see [Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md).</span></span>  
  
-   <span data-ttu-id="16db0-135">結果ウィンドウでホーム組織を右クリックし、をクリックして既存のホーム組織を編集**プロパティ**、ホーム組織をダブルクリックして、します。</span><span class="sxs-lookup"><span data-stu-id="16db0-135">Edit an existing home organization by right-clicking the home organization in the results pane, and then clicking **Properties**, or by double-clicking the home organization.</span></span> <span data-ttu-id="16db0-136">詳細については、[を作成または編集、ホーム組織](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-136">For more information, see [Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md).</span></span>  
  
-   <span data-ttu-id="16db0-137">結果ウィンドウでホーム組織を右クリックし、をクリックして既存のホーム組織を削除**削除**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-137">Delete an existing home organization by right-clicking the home organization in the results pane, and then clicking **Delete**.</span></span>  
  
## <a name="partners"></a><span data-ttu-id="16db0-138">パートナー</span><span class="sxs-lookup"><span data-stu-id="16db0-138">Partners</span></span>  
 <span data-ttu-id="16db0-139">パートナーについて、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16db0-139">You can perform the following operations on a partner:</span></span>  
  
-   <span data-ttu-id="16db0-140">右クリックして新しいパートナーを追加、**パートナー**スコープ ノードを指す**新規**、 をクリックし、**パートナー**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-140">Add a new partner by right-clicking the **Partners** scope node, pointing to **New**, and then clicking **Partner**.</span></span> <span data-ttu-id="16db0-141">詳細については、[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-141">For more information, see [Creating or Editing a Partner](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).</span></span>  
  
-   <span data-ttu-id="16db0-142">結果ウィンドウで、パートナーを右クリックし、をクリックして既存のパートナーを編集**プロパティ**、または、パートナーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="16db0-142">Edit an existing partner by right-clicking the partner in the results pane, and then clicking **Properties**, or by double-clicking the partner.</span></span> <span data-ttu-id="16db0-143">詳細については、[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-143">For more information, see [Creating or Editing a Partner](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).</span></span>  
  
-   <span data-ttu-id="16db0-144">結果ウィンドウで、パートナーを右クリックし、をクリックして既存のパートナーを削除**削除**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-144">Delete an existing partner by right-clicking the partner in the results pane, and then clicking **Delete**.</span></span>  
  
## <a name="agreements"></a><span data-ttu-id="16db0-145">契約</span><span class="sxs-lookup"><span data-stu-id="16db0-145">Agreements</span></span>  
 <span data-ttu-id="16db0-146">アグリーメントについて、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16db0-146">You can perform the following operations on an agreement:</span></span>  
  
-   <span data-ttu-id="16db0-147">右クリックして新しい契約を追加、**契約**スコープ ノードを指す**新規**、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-147">Add a new agreement by right-clicking the **Agreements** scope node, pointing to **New**, and then clicking **Agreement**.</span></span> <span data-ttu-id="16db0-148">詳細については、[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-148">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
-   <span data-ttu-id="16db0-149">結果ウィンドウで、アグリーメントを右クリックし、をクリックして既存のアグリーメントを編集**プロパティ**、または、アグリーメントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="16db0-149">Edit an existing agreement by right-clicking the agreement in the results pane, and then clicking **Properties**, or by double-clicking the agreement.</span></span> <span data-ttu-id="16db0-150">詳細については、[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16db0-150">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
-   <span data-ttu-id="16db0-151">結果ウィンドウで、アグリーメントを右クリックし、をクリックして既存のアグリーメントを削除**削除**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-151">Delete an existing agreement by right-clicking the agreement in the results pane, and then clicking **Delete**.</span></span>  
  
-   <span data-ttu-id="16db0-152">結果ウィンドウで、非アクティブ化されたアグリーメントを右クリックし、をクリックしてアグリーメントをアクティブ化**Activate**します。</span><span class="sxs-lookup"><span data-stu-id="16db0-152">Activate an agreement by right-clicking the deactivated agreement in the results pane, and then clicking **Activate**.</span></span> <span data-ttu-id="16db0-153">これにより、送信または受信されるアグリーメントに関連付けられたメッセージが有効になります。</span><span class="sxs-lookup"><span data-stu-id="16db0-153">This will enable messages associated with the agreement to be sent or received.</span></span> <span data-ttu-id="16db0-154">アグリーメントに関連付けられたメッセージが送信または受信されないように、アグリーメントを非アクティブ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="16db0-154">You can also deactivate an agreement to prevent any messages associated with the agreement from being sent or received.</span></span>  
  
-   <span data-ttu-id="16db0-155">プロセス構成が関連付けられているアグリーメントだけの一覧を表示した後は、アグリーメントの完全な一覧に戻すを右クリックし、**契約**スコープ ウィンドウで、クリックすると、ノード**すべて表示**.</span><span class="sxs-lookup"><span data-stu-id="16db0-155">Revert to a complete list of agreements, after showing a list of only the agreements that a process configuration is associated with, by right-clicking the **Agreements** node in the scope pane, and then clicking **Show All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16db0-156">参照</span><span class="sxs-lookup"><span data-stu-id="16db0-156">See Also</span></span>  
 <span data-ttu-id="16db0-157">[BTARN 送信の設定および受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="16db0-157">[Setting BTARN Send and Receive Pipelines](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md) </span></span>  
 <span data-ttu-id="16db0-158">[BAM 追跡を有効にします。](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="16db0-158">[Enabling BAM Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md) </span></span>  
 <span data-ttu-id="16db0-159">[作成またはプロセス構成を編集する方法](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="16db0-159">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="16db0-160">[作成またはホーム組織を編集します。](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="16db0-160">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 <span data-ttu-id="16db0-161">[作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md) </span><span class="sxs-lookup"><span data-stu-id="16db0-161">[Creating or Editing a Partner](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md) </span></span>  
 [<span data-ttu-id="16db0-162">アグリーメントの作成と編集</span><span class="sxs-lookup"><span data-stu-id="16db0-162">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)