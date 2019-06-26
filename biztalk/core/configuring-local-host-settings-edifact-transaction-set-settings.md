---
title: ローカル ホスト設定の構成 (EDIFACT トランザクション セットの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d918e422384a68875e2bf6625ca983c1819f1d61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390927"
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="f4f8e-102">ローカル ホストの設定の構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="f4f8e-102">Configuring Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="f4f8e-103">受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="f4f8e-104">多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="f4f8e-105">パーティ アグリーメントに関するこのページでは、ターゲット名前空間の決定に使用されるプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="f4f8e-106">BizTalk Server が、スキーマを決定する方法が記載[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4f8e-107">プロパティが無効になりません**パーティ A にパーティ B->** オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が->**  A を作成するときに、チェック ボックスを選択した場合のタブ</span><span class="sxs-lookup"><span data-stu-id="f4f8e-107">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f4f8e-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="f4f8e-108">Prerequisites</span></span>  
 <span data-ttu-id="f4f8e-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="f4f8e-110">Target Namespace を決定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-110">Determining the Target Namespace</span></span>  
 <span data-ttu-id="f4f8e-111">**Target Namespace のカスタマイズ**グリッドで、Microsoft に付属する標準スキーマの名前空間のいずれかにターゲットの名前空間を設定することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-111">In the **Customize Target Namespace** grid, you can set the target namespace to one of the namespaces for the standard schemas shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f4f8e-112">値の関連付けるグリッドで、 **Target Namespace**要素の値、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、および**UNG2.2**要素。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-112">In the grid, you associate a value of the **Target Namespace** element with values of the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements.</span></span> <span data-ttu-id="f4f8e-113">メッセージを受信した場合の**UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**と**UNG2.2**要素に合わせて、グリッドの行で、BizTalk は対応する名前空間を使用してメッセージを処理するために使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-113">When BizTalk receives a message whose **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements match those in a row of the grid, BizTalk will use the corresponding namespace to determine the schema that it will use to process the message.</span></span> <span data-ttu-id="f4f8e-114">入力した要素の値は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-114">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="f4f8e-115">メッセージとの一致を持たない場合、 **UNH2.1**、 **UNH2.2**、 **UNH2.3**、 **UNH2.5**、 **UNG2.1**、**UNG2.2**グリッドで、BizTalk Server の行の各要素では、対象の行の名前空間を使用してメッセージを処理します。、**既定**列がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-115">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="f4f8e-116">既定のターゲット名前空間として機能します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-116">That serves as the default target namespace.</span></span> <span data-ttu-id="f4f8e-117">BizTalk での既定の名前空間を使用して名前空間が識別されない場合`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-117">If no namespace is identified, BizTalk will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4f8e-118">グリッドで、フィールドのいずれかの設定を入力し、その設定を削除して場合、は、行全体を削除する必要がありますか、ページが検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-118">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="f4f8e-119">トランザクション セットのローカル ホスト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f4f8e-119">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="f4f8e-120">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="f4f8e-121">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f4f8e-122">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**ローカル ホスト設定**します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="f4f8e-123">トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に **(省略可能)** または**必須**を選択できます**空アイテムの作成末尾の区切り記号に XML タグを**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-123">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="f4f8e-124">選択**小数点区切り文字として使用してドット (.)** を有効にする BizTalk Server では、10 進数を含むインターチェンジから作成された XML メッセージにドット (.) を含めます。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-124">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="f4f8e-125">**Target Namespace のカスタマイズ**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-125">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="f4f8e-126">選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-126">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="f4f8e-127">**UNH2.1**列、メッセージの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-127">In the **UNH2.1** column, specify the message type.</span></span> <span data-ttu-id="f4f8e-128">(最大で 6 文字)。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-128">(maximum, six characters).</span></span>  
  
    3.  <span data-ttu-id="f4f8e-129">**UNH2.2**列、メッセージのバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-129">In the **UNH2.2**  column, specify the message version number.</span></span> <span data-ttu-id="f4f8e-130">最低限、1 つの文字 (最大 3 つの文字)。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-130">(minimum, one character; maximum, three characters).</span></span>  
  
    4.  <span data-ttu-id="f4f8e-131">**UNH2.3**列、メッセージ リリース番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-131">In the **UNH2.3** column, specify the message release number.</span></span> <span data-ttu-id="f4f8e-132">最低限、1 つの文字 (最大 3 つの文字)。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-132">(minimum, one character; maximum, three characters).</span></span>  
  
    5.  <span data-ttu-id="f4f8e-133">**UNH2.5**列で、割り当てコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-133">In the **UNH2.5** column, specify the assigned code.</span></span> <span data-ttu-id="f4f8e-134">(最大 6 文字です。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-134">(maximum, six characters.</span></span> <span data-ttu-id="f4f8e-135">必要があります英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-135">Must be alphanumeric).</span></span>  
  
    6.  <span data-ttu-id="f4f8e-136">**UNG2.1**列で、アプリケーション送信者 id を 1 つの文字、最大 35 文字の最小の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-136">In the **UNG2.1** column, enter an alphanumeric value for the application sender identification with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="f4f8e-137">このフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-137">This field is required.</span></span>  
  
    7.  <span data-ttu-id="f4f8e-138">**UNG2.2**列で、アプリケーション送信者コードの修飾子を 1 つの文字の最小値、最大 4 つの文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-138">In the **UNG2.2** column, enter an alphanumeric value for the application sender code qualifier with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="f4f8e-139">このフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-139">This field is optional.</span></span>  
  
    8.  <span data-ttu-id="f4f8e-140">**Target Namespace**列で、ドロップダウン リストから選択するか、グリッドの行のデータ要素と、インターチェンジのフィールドの間で一致が見つからない場合は、インターチェンジに使用するターゲットの名前空間を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-140">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f4f8e-141">これらの値は、いる BizTalk Server が受信したインターチェンジに関連付けられた値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-141">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    9. <span data-ttu-id="f4f8e-142">使用するその他のターゲット名前空間は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-142">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    10. <span data-ttu-id="f4f8e-143">一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-143">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="f4f8e-144">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4f8e-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f8e-145">参照</span><span class="sxs-lookup"><span data-stu-id="f4f8e-145">See Also</span></span>  
 [<span data-ttu-id="f4f8e-146">トランザクション セットの設定を構成する (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f4f8e-146">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)