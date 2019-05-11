---
title: エンベロープ (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b478f566301e01fa26d1d72e8eadf80caafa9e7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391269"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a><span data-ttu-id="836b3-102">エンベロープの構成 (X12 トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="836b3-102">Configuring Envelopes (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="836b3-103">**Envelops**のページ、**トランザクション セットの設定** セクションで、BizTalk Server が、パーティに送信する X12 エンコード インターチェンジの GS および ST セグメントを生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="836b3-103">In the **Envelops** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS and ST segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="836b3-104">GS セグメントは、識別し、X12 エンコード インターチェンジの機能グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="836b3-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span> <span data-ttu-id="836b3-105">ST セグメントは、X12 エンコード インターチェンジのメッセージ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="836b3-105">An ST segment is the message header for an X12-encoded interchange.</span></span>  
  
 <span data-ttu-id="836b3-106">値の関連付けるこのページで、 **GS1**、 **GS2**、 **GS3**、 **GS4**、 **GS5**、 **GS7**、および**GS8**データ要素の値を持つ、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**データ要素です。</span><span class="sxs-lookup"><span data-stu-id="836b3-106">In this page, you associate values of the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements with values of the **Transaction Type**, **Version/Release**, and **Target namespace** data elements.</span></span> <span data-ttu-id="836b3-107">BizTalk が、BizTalk XML メッセージに設定された値を判断するとき、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**グリッドの行要素BizTalk の設定は、 **GS1**、 **GS2**、 **GS3**、 **GS4**、 **GS5**、 **GS7**、および**GS8**グリッドの同じ行から値を持つインターチェンジの送信のエンベロープ内のデータ要素です。</span><span class="sxs-lookup"><span data-stu-id="836b3-107">When BizTalk determines that a BizTalk XML message has the values set for the **Transaction Type**, **Version/Release**, and **Target namespace** elements in a row of the grid, BizTalk will populate the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements in the envelope of the outgoing interchange with the values from the same row of the grid.</span></span> <span data-ttu-id="836b3-108">値、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**要素は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="836b3-108">The values of the **Transaction Type**, **Version/Release**, and **Target namespace** elements must be unique.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="836b3-109">グリッドで、フィールドのいずれかの設定を入力し、その設定を削除して場合、は、行全体を削除する必要がありますか、ページが検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="836b3-109">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="836b3-110">このトピックでは、HIPAA 関連の設定にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="836b3-110">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="836b3-111">すべてのプロパティが無効になって**パーティ A にパーティ B]-> [** オフにした場合、一方向アグリーメント タブ、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェックパーティ A のボックス同じページで、ただし、すべてのプロパティが有効に、**パーティ B には、パーティ A が]-> [** A を作成するときに、チェック ボックスを選択した場合のタブ</span><span class="sxs-lookup"><span data-stu-id="836b3-111">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="836b3-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="836b3-112">Prerequisites</span></span>  
 <span data-ttu-id="836b3-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="836b3-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-and-st-segments"></a><span data-ttu-id="836b3-114">GS および ST セグメントを定義するには</span><span class="sxs-lookup"><span data-stu-id="836b3-114">To define the GS and ST segments</span></span>  
  
1.  <span data-ttu-id="836b3-115">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="836b3-115">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="836b3-116">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="836b3-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="836b3-117">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**エンベロープ**します。</span><span class="sxs-lookup"><span data-stu-id="836b3-117">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="836b3-118">グリッドの行では、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-118">In a row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="836b3-119">**トランザクション タイプ**フィールドに、ドロップダウン リストからのトランザクション セット識別コードの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="836b3-119">For the **Transaction Type** field, select a value for the transaction set identifier code from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="836b3-120">**バージョン/リリース**、1 つの文字の最小値、最大 12 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-120">For **Version/Release**, enter an alphanumeric value with a minimum of one character and a maximum of 12 characters.</span></span>  
  
    -   <span data-ttu-id="836b3-121">**ターゲットの名前空間**要素、ドロップダウン リストから値を選択します。 または、名前空間を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-121">For **Target namespace** elements, select a value from the drop-down list, or enter a namespace.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="836b3-122">これらの BizTalk Server を構築しているインターチェンジに関連付けられている値と比較する値は。</span><span class="sxs-lookup"><span data-stu-id="836b3-122">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="836b3-123">グリッドの同じ行で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-123">In the same row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="836b3-124">**GS1**、ドロップダウン リストから機能コードの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="836b3-124">For **GS1**, select a value for the functional code from the drop-down list.</span></span> <span data-ttu-id="836b3-125">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="836b3-125">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="836b3-126">**GS2**、2 つの文字の最小値、最大 15 文字のアプリケーション送信者の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-126">For **GS2**, enter an alphanumeric value for the application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="836b3-127">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="836b3-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="836b3-128">**GS3**、2 つの文字の最小値、最大 15 文字のアプリケーション受信者の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-128">For **GS3**, enter an alphanumeric value for the application receiver with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="836b3-129">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="836b3-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="836b3-130">**GS4**、 **CCYYMMDD**または**YYMMDD**します。</span><span class="sxs-lookup"><span data-stu-id="836b3-130">For **GS4**, select **CCYYMMDD** or **YYMMDD**.</span></span> <span data-ttu-id="836b3-131">これは省略可能なフィールド</span><span class="sxs-lookup"><span data-stu-id="836b3-131">This is an optional field</span></span>  
  
    -   <span data-ttu-id="836b3-132">**GS5**、 **HHMM**、 **HHMMSS**、または**HHMMSSdd**。</span><span class="sxs-lookup"><span data-stu-id="836b3-132">For **GS5**, select **HHMM**, **HHMMSS**, or **HHMMSSdd**.</span></span> <span data-ttu-id="836b3-133">これは省略可能なフィールド</span><span class="sxs-lookup"><span data-stu-id="836b3-133">This is an optional field</span></span>  
  
    -   <span data-ttu-id="836b3-134">**GS7**、ドロップダウン リストから担当機関の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="836b3-134">For **GS7**, select a value for the responsible agency from the drop-down list.</span></span> <span data-ttu-id="836b3-135">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="836b3-135">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="836b3-136">**GS8**、1 つの文字の最小値 ~ 12 文字の最大数と識別されたドキュメントの英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-136">For **GS8**, enter an alphanumeric value for the document identified with a minimum of one character and a maximum of 12 characters.</span></span> <span data-ttu-id="836b3-137">これは、オプションのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="836b3-137">This is an optional field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="836b3-138">これらの値は、BizTalk Server は、構築している場合、インターチェンジの GS フィールドに入力されます、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**同じ行の要素がインターチェンジに関連付けられているものと一致します。</span><span class="sxs-lookup"><span data-stu-id="836b3-138">These will be the values that BizTalk Server will enter in the GS fields of the interchange it is building if the **Transaction Type**, **Version/Release**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="836b3-139">手順 3. および 4. をグリッドに追加の行を入力します。</span><span class="sxs-lookup"><span data-stu-id="836b3-139">Repeat steps 3 and 4 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="836b3-140">グリッドの 1 つの行をクリックして**既定**既定行として指定します。</span><span class="sxs-lookup"><span data-stu-id="836b3-140">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="836b3-141">メッセージとの一致を持たない場合、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**任意の行では、BizTalk Server 内の要素がメッセージに設定されます値を持つ、 **GS1**、 **GS2**、 **GS3**、 **GS5**、 **GS7**、および**GS8**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="836b3-141">If a message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **GS1**, **GS2**, **GS3**, **GS5**, **GS7**, and **GS8** elements in the default row.</span></span> <span data-ttu-id="836b3-142">メッセージとの一致を持っていない場合でも、これらの値を使用するが、**トランザクションの種類**、**バージョン/リリース**と**ターゲットの名前空間**既定行の要素。</span><span class="sxs-lookup"><span data-stu-id="836b3-142">These values will be used even if the message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="836b3-143">既定値には、選択した受信ドキュメントと一致しないがない場合、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**すべての行の要素は中断されます.</span><span class="sxs-lookup"><span data-stu-id="836b3-143">If no default is selected, incoming documents that do not match the **Transaction Type**, **Version/Release**, and **Target namespace** elements of any rows will be suspended.</span></span>  
  
7.  <span data-ttu-id="836b3-144">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="836b3-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836b3-145">参照</span><span class="sxs-lookup"><span data-stu-id="836b3-145">See Also</span></span>  
 [<span data-ttu-id="836b3-146">トランザクション セットの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="836b3-146">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)