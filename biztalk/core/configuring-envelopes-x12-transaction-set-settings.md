---
title: "エンベロープ (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 519062fa4647cdc2c7c39dda19373ff888eaf601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a><span data-ttu-id="efc0e-102">エンベロープの構成 (X12 トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="efc0e-102">Configuring Envelopes (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="efc0e-103">**エンベロープ**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する X12 エンコード インターチェンジの GS および ST セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-103">In the **Envelops** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS and ST segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="efc0e-104">GS セグメントは、X12 エンコード インターチェンジの機能グループを識別および指定します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span> <span data-ttu-id="efc0e-105">ST セグメントは、X12 エンコード インターチェンジのメッセージ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="efc0e-105">An ST segment is the message header for an X12-encoded interchange.</span></span>  
  
 <span data-ttu-id="efc0e-106">このページでは、値を関連付ける、 **GS1**、 **GS2**、 **GS3**、 **GS4**、 **GS5**、 **GS7**、および**GS8**データ要素の値を持つ、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**データ要素です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-106">In this page, you associate values of the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements with values of the **Transaction Type**, **Version/Release**, and **Target namespace** data elements.</span></span> <span data-ttu-id="efc0e-107">判断した場合、BizTalk XML メッセージに設定される値を持つ、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**グリッドの行要素BizTalk の設定は、 **GS1**、 **GS2**、 **GS3**、 **GS4**、 **GS5**、 **GS7**、および**GS8**グリッドの同じ行から値を持つインターチェンジの送信のエンベロープ内のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-107">When BizTalk determines that a BizTalk XML message has the values set for the **Transaction Type**, **Version/Release**, and **Target namespace** elements in a row of the grid, BizTalk will populate the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements in the envelope of the outgoing interchange with the values from the same row of the grid.</span></span> <span data-ttu-id="efc0e-108">値、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**要素を一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc0e-108">The values of the **Transaction Type**, **Version/Release**, and **Target namespace** elements must be unique.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc0e-109">グリッド内のいずれかのフィールドに設定を入力した後、その設定を削除する場合は、行全体を削除する必要があります。行全体を削除しないと、ページの検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-109">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efc0e-110">このトピックは、HIPAA 関連の設定にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="efc0e-110">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="efc0e-111">すべてのプロパティが無効になっている**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブ、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェックパーティ A のボックス同じ ページで、ただし、すべてのプロパティが有効に、**パーティ B には、パーティ A が->**  A の作成中にチェック ボックスをオンの場合 タブ</span><span class="sxs-lookup"><span data-stu-id="efc0e-111">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="efc0e-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="efc0e-112">Prerequisites</span></span>  
 <span data-ttu-id="efc0e-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efc0e-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-and-st-segments"></a><span data-ttu-id="efc0e-114">GS セグメントと ST セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="efc0e-114">To define the GS and ST segments</span></span>  
  
1.  <span data-ttu-id="efc0e-115">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-115">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="efc0e-116">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="efc0e-117">一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**エンベロープ**です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-117">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="efc0e-118">グリッド行に、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-118">In a row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="efc0e-119">**トランザクション タイプ**フィールドで、ドロップダウン リストから、トランザクション セット識別コードの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-119">For the **Transaction Type** field, select a value for the transaction set identifier code from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="efc0e-120">**バージョン/リリース**、1 文字の最小値、最大 12 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-120">For **Version/Release**, enter an alphanumeric value with a minimum of one character and a maximum of 12 characters.</span></span>  
  
    -   <span data-ttu-id="efc0e-121">**ターゲットの名前空間**要素、ドロップダウン リストから値を選択するか名前空間を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-121">For **Target namespace** elements, select a value from the drop-down list, or enter a namespace.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="efc0e-122">これらの値は、BizTalk Server で作成中のインターチェンジに関連付けられている値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="efc0e-122">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="efc0e-123">グリッドの同じ行に、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-123">In the same row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="efc0e-124">**GS1**、ドロップダウン リストから機能コードの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-124">For **GS1**, select a value for the functional code from the drop-down list.</span></span> <span data-ttu-id="efc0e-125">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-125">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="efc0e-126">**GS2**、アプリケーション送信者に 2 つの文字の最小値と最大 15 文字の英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-126">For **GS2**, enter an alphanumeric value for the application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="efc0e-127">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="efc0e-128">**GS3**、アプリケーション受信者に 2 つの文字の最小値と最大 15 文字の英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-128">For **GS3**, enter an alphanumeric value for the application receiver with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="efc0e-129">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="efc0e-130">**GS4** **CCYYMMDD**または**YYMMDD**です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-130">For **GS4**, select **CCYYMMDD** or **YYMMDD**.</span></span> <span data-ttu-id="efc0e-131">このフィールドは省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="efc0e-131">This is an optional field</span></span>  
  
    -   <span data-ttu-id="efc0e-132">**GS5** **HHMM**、 **hhmmss 形式で指定**、または**HHMMSSdd**です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-132">For **GS5**, select **HHMM**, **HHMMSS**, or **HHMMSSdd**.</span></span> <span data-ttu-id="efc0e-133">このフィールドは省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="efc0e-133">This is an optional field</span></span>  
  
    -   <span data-ttu-id="efc0e-134">**GS7**、ドロップダウン リストから担当機関の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-134">For **GS7**, select a value for the responsible agency from the drop-down list.</span></span> <span data-ttu-id="efc0e-135">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-135">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="efc0e-136">**GS8**、1 つの文字の最小値と、最大で 12 文字の識別されたドキュメントの英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-136">For **GS8**, enter an alphanumeric value for the document identified with a minimum of one character and a maximum of 12 characters.</span></span> <span data-ttu-id="efc0e-137">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="efc0e-137">This is an optional field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="efc0e-138">これらは、BizTalk Server で入力する場合の構築には、インターチェンジの GS フィールドの値となります、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**の同じ行の要素がインターチェンジに関連付けられているものと一致します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-138">These will be the values that BizTalk Server will enter in the GS fields of the interchange it is building if the **Transaction Type**, **Version/Release**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="efc0e-139">手順 3. および 4. をグリッドに追加の行を入力してください.</span><span class="sxs-lookup"><span data-stu-id="efc0e-139">Repeat steps 3 and 4 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="efc0e-140">グリッドで 1 つの行をクリックして**既定**既定の行として指定します。</span><span class="sxs-lookup"><span data-stu-id="efc0e-140">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efc0e-141">メッセージとの一致にいない場合、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**行、BizTalk Server の各要素はメッセージに設定されます値を持つ、 **GS1**、 **GS2**、 **GS3**、 **GS5**、 **GS7**、および**GS8**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="efc0e-141">If a message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **GS1**, **GS2**, **GS3**, **GS5**, **GS7**, and **GS8** elements in the default row.</span></span> <span data-ttu-id="efc0e-142">メッセージとの一致を持っていない場合でも、これらの値を使用するが、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**既定の行の要素。</span><span class="sxs-lookup"><span data-stu-id="efc0e-142">These values will be used even if the message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efc0e-143">既定値に一致しない選択すると、受信ドキュメントが存在しない場合、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**すべての行の要素は中断されます.</span><span class="sxs-lookup"><span data-stu-id="efc0e-143">If no default is selected, incoming documents that do not match the **Transaction Type**, **Version/Release**, and **Target namespace** elements of any rows will be suspended.</span></span>  
  
7.  <span data-ttu-id="efc0e-144">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="efc0e-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc0e-145">参照</span><span class="sxs-lookup"><span data-stu-id="efc0e-145">See Also</span></span>  
 [<span data-ttu-id="efc0e-146">トランザクション セットの構成設定 (X12)</span><span class="sxs-lookup"><span data-stu-id="efc0e-146">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)