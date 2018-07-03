---
title: バッチの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82755840-4e00-4fed-80e0-1a22b248c0bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af801bd6ec61c883d81e7ea6fd15e92f2186b777
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021529"
---
# <a name="managing-batches"></a><span data-ttu-id="0628f-102">バッチの管理</span><span class="sxs-lookup"><span data-stu-id="0628f-102">Managing Batches</span></span>
<span data-ttu-id="0628f-103">リリースを手動で制御する方法の上部にあるコントロールを使用して、インターチェンジをバッチ処理、**バッチ構成**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス (で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール) X12 と EDIFACT エンコードの両方にします。</span><span class="sxs-lookup"><span data-stu-id="0628f-103">How to control manually the release of batched interchanges, using the controls at the top of the **Batch Configuration** page of the one-way agreement tab of the **Agreement Properties** dialog box (in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console) for both X12 and EDIFACT encoding.</span></span> <span data-ttu-id="0628f-104">この作業には、次の制御が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0628f-104">This involves the following controls:</span></span>  
  
- <span data-ttu-id="0628f-105">**バッチの開始**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-105">**Starting a batch**.</span></span> <span data-ttu-id="0628f-106">バッチ処理オーケストレーションのインスタンスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0628f-106">Activates an instance of the batching orchestration.</span></span> <span data-ttu-id="0628f-107">選択した後、**開始**ボタン、バッチ処理要素インスタンスがアクティベーションの範囲内にある場合に収集されます。</span><span class="sxs-lookup"><span data-stu-id="0628f-107">After you select the **Start** button, batching elements are collected when the instance is within the activation range.</span></span>  
  
- <span data-ttu-id="0628f-108">**バッチの上書き**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-108">**Overriding a batch**.</span></span> <span data-ttu-id="0628f-109">既存の要素を使用してバッチを作成し、すぐに送信します。</span><span class="sxs-lookup"><span data-stu-id="0628f-109">Creates a batch using existing elements and immediately sends it.</span></span> <span data-ttu-id="0628f-110">バッチの送信後、バッチ処理オーケストレーションは、確立された設定に基づいてバッチ処理を再開します。</span><span class="sxs-lookup"><span data-stu-id="0628f-110">After the batch is sent, the batching orchestration resumes batch processing according to the established settings.</span></span>  
  
- <span data-ttu-id="0628f-111">**バッチの停止**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-111">**Stopping a batch**.</span></span> <span data-ttu-id="0628f-112">バッチ処理オーケストレーションのアクティブなインスタンスを非アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="0628f-112">Deactivates an activated instance of the batching orchestration.</span></span> <span data-ttu-id="0628f-113">選択した後、**停止**ボタン、オーケストレーション既存のバッチ要素からバッチを作成する場合、インターチェンジを EDI 送信パイプラインに配信し、終了します。</span><span class="sxs-lookup"><span data-stu-id="0628f-113">After you select the **Stop** button, the orchestration creates a batch from existing batch elements, delivers the interchange to the EDI send pipeline, and terminates.</span></span>  
  
  <span data-ttu-id="0628f-114">これらの制御は単一のバッチ構成に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="0628f-114">The controls act upon a single batch configuration.</span></span>  
  
  <span data-ttu-id="0628f-115">キーを押すときに BizTalk がアクション、**開始**ボタンによって異なります、**フィルター**条件、**リリース**条件、および**アクティベーション**範囲の設定、**バッチ構成**ページ。</span><span class="sxs-lookup"><span data-stu-id="0628f-115">The actions that BizTalk takes when you press the **Start** button depend upon the **Filter** criteria, **Release** criteria, and **Activation** range settings on the **Batch Configuration** page.</span></span> <span data-ttu-id="0628f-116">フィルター条件によって、バッチ処理の対象となるメッセージが決まります。</span><span class="sxs-lookup"><span data-stu-id="0628f-116">The filter criteria determine which messages are batched.</span></span> <span data-ttu-id="0628f-117">バッチがリリースされたときに、リリース条件を決定します。</span><span class="sxs-lookup"><span data-stu-id="0628f-117">The release criteria determine when batches are released.</span></span> <span data-ttu-id="0628f-118">アクティベーションの範囲のプロパティによって、バッチ処理オーケストレーションのアクティブなインスタンスがバッチ処理要素を収集するかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="0628f-118">The activation range properties determine whether an activated instance of the batching orchestration will collect elements for batching.</span></span> <span data-ttu-id="0628f-119">これらの設定の詳細については、次を参照してください。[送信バッチの構成](../core/configuring-an-outgoing-batch.md)します。</span><span class="sxs-lookup"><span data-stu-id="0628f-119">For more information about these settings, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  

<span data-ttu-id="0628f-120">このトピックでは、開始、停止、上書き、およびバッチを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0628f-120">This topic shows you how to start, stop, override, and delete batches.</span></span>  

> [!NOTE]
>  <span data-ttu-id="0628f-121">バッチを構成する方法の詳細については、次を参照してください。[構成 X12 バッチ処理](../core/configuring-batching-x12.md)または[EDIFACT バッチ処理の構成](../core/configuring-batching-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="0628f-121">For instructions on how to configure batches, see [Configuring X12 Batching](../core/configuring-batching-x12.md) or [Configuring EDIFACT Batching](../core/configuring-batching-edifact.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="0628f-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="0628f-122">Prerequisites</span></span>  
 <span data-ttu-id="0628f-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0628f-123">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0628f-124">メンバー、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループが開始、停止、またはより優先される、バッチがバッチ処理する関連構成の設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0628f-124">A member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group can start, stop, or override a batch, but cannot change any configuration setting related to batching.</span></span> <span data-ttu-id="0628f-125">バッチ構成を変更するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0628f-125">You must be a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to change batch configuration.</span></span>  
  
## <a name="start-stop-and-override-batches"></a><span data-ttu-id="0628f-126">開始、停止、およびバッチの上書き</span><span class="sxs-lookup"><span data-stu-id="0628f-126">Start, stop, and override batches</span></span>  
  
1. <span data-ttu-id="0628f-127">開いている**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、BizTalk グループを展開し、選択、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-127">Open **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, expand the BizTalk group, and select **Parties**.</span></span>  
  
2. <span data-ttu-id="0628f-128">**パーティとビジネス プロファイル**ページの**契約**セクションで、開始、停止、または上書きするバッチの構成とのアグリーメントを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0628f-128">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to start, stop, or override.</span></span>  
  
3. <span data-ttu-id="0628f-129">一方向アグリーメント タブで、**アグリーメントのプロパティ**を選択、**バッチ構成**ページ。</span><span class="sxs-lookup"><span data-stu-id="0628f-129">In the one-way agreement tab of the **Agreement Properties**, select the **Batch Configuration** page.</span></span>  
  
4. <span data-ttu-id="0628f-130">**バッチ構成** ページで、開始、停止、または上書きするバッチのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0628f-130">On the **Batch Configuration** page, select the tab for the batch that you want to start, stop, or override.</span></span>  
  
5. <span data-ttu-id="0628f-131">フィルター条件、リリース条件、およびアクティベーションの範囲のプロパティが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0628f-131">Verify that the filter criteria, release criteria, and activation range properties are as they should be.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0628f-132">メンバーである場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループが、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、起動、停止、または上書きをバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="0628f-132">If you are a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators group, but not the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group, you can start, stop, or override batches.</span></span> <span data-ttu-id="0628f-133">ただし、バッチの構成設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0628f-133">But, you cannot change batch configuration settings.</span></span> <span data-ttu-id="0628f-134">設定を変更する場合は、表示と選択し**OK**、アクセス許可エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0628f-134">The settings are visible to you, but if you change a setting, and then select **OK**, you get a permissions error.</span></span>  
  
6. <span data-ttu-id="0628f-135">バッチ処理オーケストレーションのインスタンスがアクティブ化されていない場合は、選択**開始**インスタンスをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="0628f-135">If an instance of the batching orchestration has not been activated, select **Start** to activate an instance.</span></span>  
  
   > [!NOTE]
   >  - <span data-ttu-id="0628f-136">バッチ処理オーケストレーションのインスタンスがアクティブ化されていない場合を伝えることができます、**開始**ボタンが有効になっていると**バッチ処理がアクティブでない**だけ下に表示される、 **を開始**コントロール。</span><span class="sxs-lookup"><span data-stu-id="0628f-136">You can tell that an instance of the batching orchestration has not been activated if the **Start** button is enabled, and **Batching is not activated** is displayed just beneath the **Start** control.</span></span>  
   >  - <span data-ttu-id="0628f-137">クリックした場合、**開始**ボタンをクリックして、バッチ処理オーケストレーションのインスタンスがアクティブ化が要素がバッチに収集されないことを確認で datetime、**アクティベーション**テキスト ボックスが経過しました。</span><span class="sxs-lookup"><span data-stu-id="0628f-137">If you have clicked the **Start** button, and an instance of the batching orchestration has been activated, but no elements are being collected for the batch, then verify that the datetime in the **Activation** text box has transpired.</span></span> <span data-ttu-id="0628f-138">ない場合、**アクティベーション**を現在の日付または過去の日付を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0628f-138">If not, the **Activation** date must be set to the current date or earlier.</span></span>  
  
7. <span data-ttu-id="0628f-139">リリース条件が満たされていないときにバッチ インターチェンジを送信する **オーバーライド**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-139">To send a batched interchange when the release criteria have not been met, select **Override**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0628f-140">選択**オーバーライド**送信されるバッチ インターチェンジですがバッチ処理オーケストレーション インスタンスや、アクティベーション条件、リリース条件のアクティブ化の状態には影響しません。</span><span class="sxs-lookup"><span data-stu-id="0628f-140">Selecting **Override** results in a batched interchange being sent, but does not affect the activation status of the batching orchestration instance, the activation criteria, or the release criteria.</span></span>  
  
8. <span data-ttu-id="0628f-141">バッチ処理オーケストレーションのインスタンスを非アクティブ化する次のように選択します。**停止**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-141">To deactivate the instance of the batching orchestration, select **Stop**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0628f-142">選択**停止**に送信されるバッチ インターチェンジとバッチ処理オーケストレーション インスタンスが終了しています。</span><span class="sxs-lookup"><span data-stu-id="0628f-142">Selecting **Stop** results in a batched interchange being sent, and the batching orchestration instance being terminated.</span></span>  
  
9. <span data-ttu-id="0628f-143">選択**OK**または**キャンセル**を閉じる、**アグリーメントのプロパティ**。</span><span class="sxs-lookup"><span data-stu-id="0628f-143">Select **OK** or **Cancel** to close the **Agreement Properties**.</span></span>  

## <a name="delete-batches"></a><span data-ttu-id="0628f-144">バッチを削除します。</span><span class="sxs-lookup"><span data-stu-id="0628f-144">Delete batches</span></span>  
  
1. <span data-ttu-id="0628f-145">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-145">In **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration**, select **Parties**.</span></span>  
  
2. <span data-ttu-id="0628f-146">**パーティとビジネス プロファイル**ページの**契約**セクションで、削除するバッチの構成とのアグリーメントを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0628f-146">In the **Parties and Business Profiles** page, under the **Agreements** section, right-click the agreement with the batch configuration that you want to delete.</span></span>  
  
3. <span data-ttu-id="0628f-147">一方向アグリーメント タブで、**アグリーメントのプロパティ**ダイアログ ボックスで、**バッチ構成**ページ。</span><span class="sxs-lookup"><span data-stu-id="0628f-147">In the one-way agreement tab of the **Agreement Properties** dialog box, select the **Batch Configuration** page.</span></span>  
  
4. <span data-ttu-id="0628f-148">**バッチ構成** ページで、削除するバッチのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="0628f-148">On the **Batch Configuration** page, select the tab for the batch that you want to delete.</span></span>  
  
5. <span data-ttu-id="0628f-149">タブ ページの右上隅で選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-149">On the right-hand corner of the tab page, select **Delete**.</span></span>  
  
6. <span data-ttu-id="0628f-150">選択**OK**を閉じる、**アグリーメントのプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0628f-150">Select **OK** to close the **Agreement Properties**.</span></span>  

  
## <a name="see-also"></a><span data-ttu-id="0628f-151">参照</span><span class="sxs-lookup"><span data-stu-id="0628f-151">See Also</span></span>  
 [<span data-ttu-id="0628f-152">送信バッチの構成</span><span class="sxs-lookup"><span data-stu-id="0628f-152">Configuring an Outgoing Batch</span></span>](../core/configuring-an-outgoing-batch.md)  
 [<span data-ttu-id="0628f-153">EDI および AS2 ソリューションの管理</span><span class="sxs-lookup"><span data-stu-id="0628f-153">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)