---
title: エンベロープの構成 (EDIFACT トランザクション セットの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec140def-6155-4b8a-8489-6e0a530bd697
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c62b963042c7a4f5ea141dd44faa4f914c30f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391310"
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a><span data-ttu-id="ec5ec-102">エンベロープの構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-102">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="ec5ec-103">**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNG および UNH セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG and UNH segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="ec5ec-104">UNG セグメントは、ヘッダーを識別し、EDIFACT エンコード インターチェンジの機能グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="ec5ec-105">種類と、機能グループ内のドキュメントのバージョンと共に、機能グループが準備された日時に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
 <span data-ttu-id="ec5ec-106">UNH セグメントは、EDIFACT エンコード インターチェンジのメッセージ ヘッダー セグメントです。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-106">The UNH segment is the message header segment of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="ec5ec-107">メッセージの種類とメッセージの種類の公開の保守を担当する機関に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-107">It provides information about the message type, and the agency responsible for maintaining the publication of the message type.</span></span> <span data-ttu-id="ec5ec-108">このセグメントでは、インターチェンジとそれに続くドキュメントの種類のドキュメントの先頭を示します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-108">This segment indicates the start of a document in an interchange and the type of document that follows.</span></span>  
  
 <span data-ttu-id="ec5ec-109">**機能グループ ヘッダー (UNG)**  セクションで、関連付けた**UNG**値**UNH**値と名前空間。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-109">In the **Functional group header (UNG)** section, you associate **UNG** values with **UNH** values and a namespace.</span></span> <span data-ttu-id="ec5ec-110">BizTalk Server が BizTalk XML メッセージに設定された値を判断するとき、 **UNH**要素と**ターゲットの名前空間**BizTalk Server では、グリッドの行を読み込みます、 **UNG** 、グリッドの同じ行から値を持つデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-110">When BizTalk Server determines that a BizTalk XML message has the values set for the **UNH** elements and the **Target namespace** in a row of the grid, BizTalk Server will populate the **UNG** data elements with the values from the same row of the grid.</span></span> <span data-ttu-id="ec5ec-111">値、 **UNH**要素と**ターゲットの名前空間**で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-111">The values of the **UNH** elements and the **Target namespace** must be unique.</span></span>  
  
 <span data-ttu-id="ec5ec-112">メッセージとの一致を持たない場合、 **UNH**要素と**ターゲットの名前空間**BizTalk Server のいずれかの行の値を持つメッセージに設定されます、 **UNG**既定の行の要素。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-112">If a message does not have a match with the **UNH** elements and the **Target namespace** in any row, BizTalk Server will populate the message with the values of the **UNG** elements in the default row.</span></span> <span data-ttu-id="ec5ec-113">メッセージとの一致を持っていない場合でも、これらの値を使用するが、 **UNH**要素と**ターゲットの名前空間**既定の行。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-113">These values will be used even if the message does not have a match with the **UNH** elements and the **Target namespace** of the default row.</span></span>  
  
 <span data-ttu-id="ec5ec-114">エンジンが提供されるグリッドで、それらの設定値を持つメッセージに UNG 要素を設定、BizTalk エンジン BizTalk XML メッセージの UNH 要素およびターゲットの名前空間の設定値であると判断した場合、**グループの作成セグメント**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-114">When the BizTalk engine determines that a BizTalk XML message has the values set for the UNH elements and the Target namespace, the engine will populate the UNG elements in the message with the values set for them in the grid, provided the **Create Grouping Segments** checkbox is checked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5ec-115">**機能グループ ヘッダー (UNG)** セクションで、グリッドで、フィールドのいずれかの設定を入力し、その設定を削除し、行全体を削除する必要があります、または、ページが検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-115">In the **Functional group header (UNG)**  section, if you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec5ec-116">すべてのプロパティが無効になって**パーティ A にパーティ B]-> [** オフにした場合、一方向アグリーメント タブ、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェックパーティ A のボックス同じページで、ただし、すべてのプロパティが有効に、**パーティ B には、パーティ A が]-> [** A を作成するときに、チェック ボックスを選択した場合のタブ</span><span class="sxs-lookup"><span data-stu-id="ec5ec-116">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ec5ec-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="ec5ec-117">Prerequisites</span></span>  
 <span data-ttu-id="ec5ec-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-and-unh-segments"></a><span data-ttu-id="ec5ec-119">UNG および UNH セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="ec5ec-119">To define the UNG and UNH segments</span></span>  
  
1.  <span data-ttu-id="ec5ec-120">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="ec5ec-121">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ec5ec-122">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**エンベロープ**します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="ec5ec-123">グリッドの行には、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-123">In a row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="ec5ec-124">**メッセージの種類 UNH2.1**列で、トランザクション セットの種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-124">In the **For message type UNH2.1** column, enter a transaction set type.</span></span> <span data-ttu-id="ec5ec-125">(最大で 6 文字)。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-125">(Maximum, six characters).</span></span>  
  
    -   <span data-ttu-id="ec5ec-126">**UNH2.2**列、メッセージのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-126">In the **UNH2.2**  column, enter the message version number.</span></span> <span data-ttu-id="ec5ec-127">最低限、1 つの文字 (最大 3 つの文字)。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-127">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="ec5ec-128">**UNH2.3**列、メッセージ リリース番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-128">In the **UNH2.3** column, enter the message release number.</span></span> <span data-ttu-id="ec5ec-129">最低限、1 つの文字 (最大 3 つの文字)。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-129">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="ec5ec-130">**UNH2.5**列で、割り当てコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-130">In the **UNH2.5** column, enter the assigned code.</span></span> <span data-ttu-id="ec5ec-131">(最大 6 文字です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-131">(Maximum, six characters.</span></span> <span data-ttu-id="ec5ec-132">必要があります英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-132">Must be alphanumeric).</span></span>  
  
    -   <span data-ttu-id="ec5ec-133">**ターゲットの名前空間**列で、スキーマのターゲットの名前空間を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-133">In the **Target namespace** column, select the target namespace of the schema.</span></span> <span data-ttu-id="ec5ec-134">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-134">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ec5ec-135">これらの BizTalk Server を構築しているインターチェンジに関連付けられている値と比較する値は。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-135">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="ec5ec-136">グリッドの同じ行では、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-136">In the same row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="ec5ec-137">**UNG1** (機能グループ id) に、1 つの文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-137">For the **UNG1** (Functional group identification), enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="ec5ec-138">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-138">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-139">**UNG2.1** (アプリケーション送信者 id)、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-139">For **UNG2.1** (Application sender identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="ec5ec-140">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-140">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-141">**UNG2.2** (アプリケーション送信者コード修飾子)、最大 4 文字の英数字値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-141">For **UNG2.2** (Application sender code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="ec5ec-142">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-142">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-143">**UNG3.1** (アプリケーション受信者 id)、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-143">For **UNG3.1** (Application recipient identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="ec5ec-144">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-144">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-145">**UNG3.2** (アプリケーション受信者コードの修飾子)、最大 4 文字の英数字値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-145">For **UNG3.2** (Application recipient code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="ec5ec-146">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-146">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-147">**UNG6** (制御機関) のいずれかの最小値、最大 2 つの英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-147">For **UNG6** (Controlling agency), enter an alphanumeric value with a minimum of one and a maximum of two.</span></span> <span data-ttu-id="ec5ec-148">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-148">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-149">**UNG7.1** (メッセージの種類のバージョン番号)、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-149">For **UNG7.1** (Message type version number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="ec5ec-150">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-150">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-151">**UNG7.2** (メッセージの種類のリリース番号)、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-151">For **UNG7.2** (Message type release number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="ec5ec-152">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-152">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-153">**UNG7.3** (関連付けの割り当てコード)、1 文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-153">For **UNG7.3** (Association assigned code), enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="ec5ec-154">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-154">This is a required field.</span></span>  
  
    -   <span data-ttu-id="ec5ec-155">**UNG8** (アプリケーションのパスワード)、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-155">For **UNG8** (Application password), enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="ec5ec-156">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-156">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="ec5ec-157">これらの値は、BizTalk Server は、構築している場合、インターチェンジの UNG フィールドに入力されます、**メッセージの種類 UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**同じ行の要素がインターチェンジに関連付けられているものと一致します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-157">These will be the values that BizTalk Server will enter in the UNG fields of the interchange it is building if the  **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="ec5ec-158">手順 4 と 5 をグリッドに追加の行を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-158">Repeat steps 4 and 5 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="ec5ec-159">グリッドの 1 つの行をクリックして**既定**既定行として指定します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-159">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec5ec-160">メッセージとの一致を持たない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**任意の行では、BizTalk Server 内の要素の値を持つメッセージが設定されます、 **UNG1**、 **UNG2.1**、 **UNG2.2**、 **UNG3.1**、 **UNG3.2**、 **UNG6**、 **UNG7.1**、 **UNG7.2**、 **UNG7.3**、および**UNG8**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-160">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **UNG1**, **UNG2.1**, **UNG2.2**, **UNG3.1**, **UNG3.2**, **UNG6**, **UNG7.1**, **UNG7.2**, **UNG7.3**, and **UNG8** elements in the default row.</span></span> <span data-ttu-id="ec5ec-161">これらの値は、メッセージとの一致を持っていない場合でも、使用は、**メッセージの種類 UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、**ターゲットの名前空間**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-161">These values will be used even if the message does not have a match with the **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec5ec-162">既定の行が選択されていないと、メッセージが用の一致しない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**BizTalk のいずれかの行要素は、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-162">If no default row is selected, and the message does not have a match for the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk will suspend the message.</span></span>  
  
7.  <span data-ttu-id="ec5ec-163">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ec5ec-163">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5ec-164">参照</span><span class="sxs-lookup"><span data-stu-id="ec5ec-164">See Also</span></span>  
 [<span data-ttu-id="ec5ec-165">トランザクション セットの設定を構成する (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="ec5ec-165">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)