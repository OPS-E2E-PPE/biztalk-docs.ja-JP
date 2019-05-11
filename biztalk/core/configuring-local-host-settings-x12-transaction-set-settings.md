---
title: ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 897a8f5c9cacd84f8a54f06276c0170fba7045cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390840"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a><span data-ttu-id="a8700-102">ローカル ホスト設定の構成 (X12 トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="a8700-102">Configuring Local Host Settings (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="a8700-103">受信インターチェンジを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理およびインターチェンジの検証に使用する必要があるスキーマを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8700-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="a8700-104">多数のドキュメント、スキーマに関連付けられたターゲット名前空間の決定し、使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="a8700-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="a8700-105">パーティ アグリーメントに関するこのページでは、ターゲット名前空間の決定に使用されるプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="a8700-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="a8700-106">どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]決定スキーマについては、「[アグリーメントの解決、スキーマ探索、および EDI メッセージの受信を承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8700-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8700-107">このトピックでは、HIPAA 関連の設定にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="a8700-107">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8700-108">プロパティが無効になりません**パーティ A にパーティ B-> **オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、\*\*パーティ B には、パーティ A が-> \*\* A を作成するときに、チェック ボックスを選択した場合のタブ</span><span class="sxs-lookup"><span data-stu-id="a8700-108">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a8700-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a8700-109">Prerequisites</span></span>  
 <span data-ttu-id="a8700-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8700-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="a8700-111">Target Namespace を決定します。</span><span class="sxs-lookup"><span data-stu-id="a8700-111">Determining the Target Namespace</span></span>  
 <span data-ttu-id="a8700-112">**カスタマイズのターゲットの名前空間**グリッド用に設定できるターゲットの名前空間、名前空間のいずれかに付属の標準スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a8700-112">In the **Customize Target namespace** grid, you can set the target namespaces to one of the namespaces for the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a8700-113">値の関連付けるグリッドで、 **Target Namespace**アプリケーション送信者の値を持つ要素 (**GS2**) およびトランザクション セット識別コード (**ST1**)。</span><span class="sxs-lookup"><span data-stu-id="a8700-113">In the grid, you associate a value of the **Target Namespace** element with values of the application sender (**GS2**) and transaction set identifier code (**ST1**).</span></span> <span data-ttu-id="a8700-114">メッセージを受信した場合の**GS2**と**ST1**データ要素に合わせて、グリッドの行で、メッセージの処理に対応する名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8700-114">When BizTalk receives a message whose **GS2** and **ST1** data elements match those in a row of the grid, BizTalk will use the corresponding namespace to process the message.</span></span> <span data-ttu-id="a8700-115">入力した要素の値は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8700-115">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="a8700-116">メッセージとの一致を持たない場合、 **GS2**と**ST1**グリッドで、BizTalk Server の任意の行のデータ要素は対象の行で、名前空間を使用して、メッセージを処理、 **を既定値**列がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a8700-116">If a message does not have a match with the **GS2** and **ST1** data elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="a8700-117">既定のターゲット名前空間として機能します。</span><span class="sxs-lookup"><span data-stu-id="a8700-117">That serves as the default target namespace.</span></span> <span data-ttu-id="a8700-118">BizTalk Server での既定の名前空間を使用して名前空間が識別されない場合`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`します。</span><span class="sxs-lookup"><span data-stu-id="a8700-118">If no namespace is identified, BizTalk Server will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8700-119">グリッドで、フィールドのいずれかの設定を入力し、その設定を削除して場合、は、行全体を削除する必要がありますか、ページが検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="a8700-119">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8700-120">このグリッドを使用しての図解は、EDI インターフェイス開発チュートリアルでは、具体的からインターチェンジを受信するパーティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="a8700-120">For an illustration of using this grid, run through the EDI Interface Developer tutorial, specifically setting up a party to receive an interchange from.</span></span> <span data-ttu-id="a8700-121">詳細については、次を参照してください。[手順 4。取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8700-121">For more information, see [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="a8700-122">トランザクション セットのローカル ホスト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="a8700-122">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="a8700-123">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="a8700-123">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="a8700-124">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a8700-124">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a8700-125">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**ローカル ホスト設定**します。</span><span class="sxs-lookup"><span data-stu-id="a8700-125">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="a8700-126">選択**変換には 10 進形式 Nn を底 10 の数値が含まれる**を BizTalk Server での中間 XML で底 10 の数値形式 Nn で指定されている EDI 番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="a8700-126">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8700-127">この変換後の中間 XML に長さの検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a8700-127">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="a8700-128">これは、底 10 の数値書式の数値は、Nn 形式で、長さ、数より大きい値のいずれかを行う、10 進数を含まれているために発生します。</span><span class="sxs-lookup"><span data-stu-id="a8700-128">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="a8700-129">値を追加することで、この問題を解決できます**1**最小値/最大長の値にします。</span><span class="sxs-lookup"><span data-stu-id="a8700-129">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4.  <span data-ttu-id="a8700-130">トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に **(省略可能)** または**必須**を選択できます**空アイテムの作成末尾の区切り記号に XML タグを**がインターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a8700-130">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5.  <span data-ttu-id="a8700-131">**Target Namespace のカスタマイズ**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a8700-131">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="a8700-132">選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="a8700-132">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="a8700-133">**St1 の場合**列では、トランザクションの値を選択しますが、ドロップダウン リストから識別子コードを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8700-133">In the **For ST1** column, select a value for the Transaction set identifier code from the drop-down list.</span></span>  
  
    3.  <span data-ttu-id="a8700-134">**GS2**列、2 つの文字の最小値、最大 15 文字のアプリケーション送信者の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8700-134">In the **GS2** column, enter an alphanumeric value for the Application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="a8700-135">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="a8700-135">This is a required field.</span></span>  
  
    4.  <span data-ttu-id="a8700-136">**Target Namespace**列で、ドロップダウン リストから選択するか、グリッドの行のデータ要素と、インターチェンジのフィールドの間で一致が見つからない場合は、インターチェンジに使用するターゲットの名前空間を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8700-136">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a8700-137">これらの値は、いる BizTalk Server が受信したインターチェンジに関連付けられた値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="a8700-137">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    5.  <span data-ttu-id="a8700-138">使用するその他のターゲット名前空間は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a8700-138">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    6.  <span data-ttu-id="a8700-139">一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="a8700-139">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="a8700-140">をクリックして**適用**を変更を受け入れるか、をクリックする**OK**を入力し、変更を検証して、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a8700-140">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8700-141">参照</span><span class="sxs-lookup"><span data-stu-id="a8700-141">See Also</span></span>  
 [<span data-ttu-id="a8700-142">トランザクション セットの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="a8700-142">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)