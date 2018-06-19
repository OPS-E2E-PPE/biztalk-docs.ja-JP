---
title: エンベロープの構成 (EDIFACT トランザクション セットの設定) |Microsoft ドキュメント
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
ms.openlocfilehash: 7a1d910f52d9ea90ae0c486356a7ecb3b01bf07a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234634"
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a><span data-ttu-id="f4683-102">エンベロープの構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="f4683-102">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="f4683-103">**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する EDIFACT エンコード インターチェンジの UNG および UNH セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="f4683-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG and UNH segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="f4683-104">UNG セグメントは、EDIFACT エンコード インターチェンジの機能グループを識別および指定するヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="f4683-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="f4683-105">UNG セグメントには、機能グループに含まれているドキュメントの種類とバージョンのほか、機能グループが準備された日時に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4683-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
 <span data-ttu-id="f4683-106">UNH セグメントは、EDIFACT エンコード インターチェンジのメッセージ ヘッダー セグメントです。</span><span class="sxs-lookup"><span data-stu-id="f4683-106">The UNH segment is the message header segment of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="f4683-107">UNH セグメントは、メッセージの種類と、そのメッセージの種類の公開の保守を担当する機関に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f4683-107">It provides information about the message type, and the agency responsible for maintaining the publication of the message type.</span></span> <span data-ttu-id="f4683-108">このセグメントは、インターチェンジ内のドキュメントの開始点と、それに続くドキュメントの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="f4683-108">This segment indicates the start of a document in an interchange and the type of document that follows.</span></span>  
  
 <span data-ttu-id="f4683-109">**機能グループ ヘッダー (UNG)**  セクションに関連付ける**UNG**の値を使った**UNH**値と名前空間。</span><span class="sxs-lookup"><span data-stu-id="f4683-109">In the **Functional group header (UNG)** section, you associate **UNG** values with **UNH** values and a namespace.</span></span> <span data-ttu-id="f4683-110">BizTalk Server が、BizTalk XML メッセージに設定される値を持つことを判断するとき、 **UNH**要素および**ターゲットの名前空間**BizTalk Server では、グリッドの行、読み込みます、 **UNG**データ要素にグリッドの同じ行からの値。</span><span class="sxs-lookup"><span data-stu-id="f4683-110">When BizTalk Server determines that a BizTalk XML message has the values set for the **UNH** elements and the **Target namespace** in a row of the grid, BizTalk Server will populate the **UNG** data elements with the values from the same row of the grid.</span></span> <span data-ttu-id="f4683-111">値、 **UNH**要素および**ターゲットの名前空間**一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4683-111">The values of the **UNH** elements and the **Target namespace** must be unique.</span></span>  
  
 <span data-ttu-id="f4683-112">メッセージとの一致にいない場合、 **UNH**要素および**ターゲットの名前空間**任意の行では、BizTalk Server はメッセージに設定の値を持つ、 **UNG**既定の行の要素。</span><span class="sxs-lookup"><span data-stu-id="f4683-112">If a message does not have a match with the **UNH** elements and the **Target namespace** in any row, BizTalk Server will populate the message with the values of the **UNG** elements in the default row.</span></span> <span data-ttu-id="f4683-113">メッセージとの一致を持っていない場合でも、これらの値を使用するが、 **UNH**要素および**ターゲットの名前空間**既定の行。</span><span class="sxs-lookup"><span data-stu-id="f4683-113">These values will be used even if the message does not have a match with the **UNH** elements and the **Target namespace** of the default row.</span></span>  
  
 <span data-ttu-id="f4683-114">BizTalk エンジンは、BizTalk XML メッセージは、UNH 要素およびターゲットの名前空間に設定される値であると判断した場合、エンジンはへの追加メッセージに UNG 要素の値が提供される、グリッド内でそれらの設定、**グループの作成セグメント**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="f4683-114">When the BizTalk engine determines that a BizTalk XML message has the values set for the UNH elements and the Target namespace, the engine will populate the UNG elements in the message with the values set for them in the grid, provided the **Create Grouping Segments** checkbox is checked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4683-115">**機能グループ ヘッダー (UNG)** セクションで、グリッドで、いずれかのフィールドの設定を入力してその設定を削除、行全体を削除する必要が、またはページは検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4683-115">In the **Functional group header (UNG)**  section, if you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4683-116">すべてのプロパティが無効になっている**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブ、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェックパーティ A のボックス同じ ページで、ただし、すべてのプロパティが有効に、**パーティ B には、パーティ A が->**  A の作成中にチェック ボックスをオンの場合 タブ</span><span class="sxs-lookup"><span data-stu-id="f4683-116">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4683-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4683-117">Prerequisites</span></span>  
 <span data-ttu-id="f4683-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4683-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-and-unh-segments"></a><span data-ttu-id="f4683-119">UNG セグメントと UNH セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="f4683-119">To define the UNG and UNH segments</span></span>  
  
1.  <span data-ttu-id="f4683-120">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="f4683-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="f4683-121">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f4683-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f4683-122">一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**エンベロープ**です。</span><span class="sxs-lookup"><span data-stu-id="f4683-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="f4683-123">グリッドの行に、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-123">In a row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="f4683-124">**メッセージの種類 UNH2.1**列で、トランザクション セットの種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-124">In the **For message type UNH2.1** column, enter a transaction set type.</span></span> <span data-ttu-id="f4683-125">最大文字数は 6 文字です。</span><span class="sxs-lookup"><span data-stu-id="f4683-125">(Maximum, six characters).</span></span>  
  
    -   <span data-ttu-id="f4683-126">**UNH2.2**列で、メッセージのバージョン番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-126">In the **UNH2.2**  column, enter the message version number.</span></span> <span data-ttu-id="f4683-127">(1 ～ 3 文字です)。</span><span class="sxs-lookup"><span data-stu-id="f4683-127">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="f4683-128">**UNH2.3**列で、メッセージ リリース番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-128">In the **UNH2.3** column, enter the message release number.</span></span> <span data-ttu-id="f4683-129">(1 ～ 3 文字です)。</span><span class="sxs-lookup"><span data-stu-id="f4683-129">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="f4683-130">**UNH2.5**列で、割り当てコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-130">In the **UNH2.5** column, enter the assigned code.</span></span> <span data-ttu-id="f4683-131">(最大文字数は 6 文字です。</span><span class="sxs-lookup"><span data-stu-id="f4683-131">(Maximum, six characters.</span></span> <span data-ttu-id="f4683-132">英数字である必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f4683-132">Must be alphanumeric).</span></span>  
  
    -   <span data-ttu-id="f4683-133">**ターゲットの名前空間**列で、スキーマのターゲットの名前空間を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4683-133">In the **Target namespace** column, select the target namespace of the schema.</span></span> <span data-ttu-id="f4683-134">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-134">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f4683-135">これらの値は、BizTalk Server で作成中のインターチェンジに関連付けられている値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="f4683-135">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="f4683-136">グリッドの同じ行に、次の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-136">In the same row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="f4683-137">**UNG1** (機能グループ id) に、1 つの文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-137">For the **UNG1** (Functional group identification), enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="f4683-138">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-138">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-139">**UNG2.1** (アプリケーション送信者 id)、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-139">For **UNG2.1** (Application sender identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="f4683-140">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-140">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-141">**UNG2.2** (アプリケーション送信者コード修飾子)、最大 4 文字の英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-141">For **UNG2.2** (Application sender code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="f4683-142">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f4683-142">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="f4683-143">**UNG3.1** (アプリケーション受信者 id)、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-143">For **UNG3.1** (Application recipient identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="f4683-144">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-144">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-145">**UNG3.2** (アプリケーション受信者コードの修飾子)、最大 4 文字の英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-145">For **UNG3.2** (Application recipient code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="f4683-146">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f4683-146">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="f4683-147">**UNG6** (制御機関)、1、2 つの最大値以下で英数字値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-147">For **UNG6** (Controlling agency), enter an alphanumeric value with a minimum of one and a maximum of two.</span></span> <span data-ttu-id="f4683-148">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-148">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-149">**UNG7.1** (メッセージの種類のバージョン番号)、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-149">For **UNG7.1** (Message type version number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="f4683-150">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-150">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-151">**UNG7.2** (メッセージの種類のリリース番号)、1 つの文字の最小値、最大 3 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-151">For **UNG7.2** (Message type release number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="f4683-152">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-152">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-153">**UNG7.3** (関連付けの割り当てコード)、1 文字の最小値、最大 6 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-153">For **UNG7.3** (Association assigned code), enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="f4683-154">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-154">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f4683-155">**UNG8** (アプリケーションのパスワード)、1 つの文字の最小値、最大 14 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-155">For **UNG8** (Application password), enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="f4683-156">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="f4683-156">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f4683-157">これらは、BizTalk Server で入力する場合の構築には、インターチェンジの UNG フィールドの値となる、**メッセージの種類 UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**の同じ行の要素がインターチェンジに関連付けられているものと一致します。</span><span class="sxs-lookup"><span data-stu-id="f4683-157">These will be the values that BizTalk Server will enter in the UNG fields of the interchange it is building if the  **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="f4683-158">手順 4. および手順 5. を繰り返して、追加行をグリッドに入力します。</span><span class="sxs-lookup"><span data-stu-id="f4683-158">Repeat steps 4 and 5 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="f4683-159">グリッドで 1 つの行をクリックして**既定**既定の行として指定します。</span><span class="sxs-lookup"><span data-stu-id="f4683-159">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4683-160">メッセージとの一致にいない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**のターゲット名前空間**任意の行では、BizTalk Server 内の要素の値を持つメッセージの設定は、 **UNG1**、 **UNG2.1**、 **UNG2.2**、 **[Ung3.1]**、 **UNG3.2**、 **UNG6**、 **UNG7.1**、 **UNG7.2**、 **UNG7.3**、および**UNG8**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="f4683-160">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **UNG1**, **UNG2.1**, **UNG2.2**, **UNG3.1**, **UNG3.2**, **UNG6**, **UNG7.1**, **UNG7.2**, **UNG7.3**, and **UNG8** elements in the default row.</span></span> <span data-ttu-id="f4683-161">これらの値は、メッセージとの一致を持っていない場合でも、使用は、**メッセージの種類 UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**既定の行の要素。</span><span class="sxs-lookup"><span data-stu-id="f4683-161">These values will be used even if the message does not have a match with the **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4683-162">既定の行が選択されていないと、メッセージには、一致するものはありません、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、および**ターゲットの名前空間**BizTalk のいずれかの行要素は、メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="f4683-162">If no default row is selected, and the message does not have a match for the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk will suspend the message.</span></span>  
  
7.  <span data-ttu-id="f4683-163">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4683-163">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4683-164">参照</span><span class="sxs-lookup"><span data-stu-id="f4683-164">See Also</span></span>  
 [<span data-ttu-id="f4683-165">トランザクション セットの構成設定 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f4683-165">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)