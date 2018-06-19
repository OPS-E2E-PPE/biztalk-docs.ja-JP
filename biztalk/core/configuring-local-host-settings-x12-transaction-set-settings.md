---
title: ローカル ホスト設定 (X12 トランザクション セットの設定) の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 8fcc099535e6a7b96c5c4bbdd29112da46af3522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234306"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a><span data-ttu-id="56890-102">ローカル ホスト設定の構成 (X12 トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="56890-102">Configuring Local Host Settings (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="56890-103">受信したインターチェンジを処理するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はインターチェンジの処理および検証に使用するスキーマを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56890-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="56890-104">この場合、スキーマに関連付けられたターゲット名前空間および使用するスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="56890-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="56890-105">パーティ アグリーメントに関するこのページで、ターゲット名前空間の決定に使用するプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="56890-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="56890-106">どの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマについては、「を決定[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。</span><span class="sxs-lookup"><span data-stu-id="56890-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56890-107">このトピックは、HIPAA 関連の設定にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="56890-107">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56890-108">プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合</span><span class="sxs-lookup"><span data-stu-id="56890-108">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="56890-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="56890-109">Prerequisites</span></span>  
 <span data-ttu-id="56890-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="56890-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="56890-111">ターゲットの名前空間の決定</span><span class="sxs-lookup"><span data-stu-id="56890-111">Determining the Target Namespace</span></span>  
 <span data-ttu-id="56890-112">**をカスタマイズするターゲットの名前空間**グリッド、用に設定できるターゲットの名前空間、名前空間のいずれかに付属の標準スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="56890-112">In the **Customize Target namespace** grid, you can set the target namespaces to one of the namespaces for the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="56890-113">グリッドの値を関連付ける、 **Target Namespace**アプリケーション送信者の値を持つ要素 (**GS2**) およびトランザクション セット識別コード (**ST1**)。</span><span class="sxs-lookup"><span data-stu-id="56890-113">In the grid, you associate a value of the **Target Namespace** element with values of the application sender (**GS2**) and transaction set identifier code (**ST1**).</span></span> <span data-ttu-id="56890-114">BizTalk がメッセージを受信すると持つ**GS2**と**ST1**データ要素に合わせて、グリッドの行で、メッセージの処理に対応する名前空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="56890-114">When BizTalk receives a message whose **GS2** and **ST1** data elements match those in a row of the grid, BizTalk will use the corresponding namespace to process the message.</span></span> <span data-ttu-id="56890-115">入力する要素の値は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="56890-115">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="56890-116">メッセージとの一致にいない場合、 **GS2**と**ST1**グリッドでは、BizTalk Server の任意の行のデータ要素は対象の行に、名前空間を使用してメッセージを処理、 **を既定値**列を選択します。</span><span class="sxs-lookup"><span data-stu-id="56890-116">If a message does not have a match with the **GS2** and **ST1** data elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="56890-117">それが既定のターゲットの名前空間として機能します。</span><span class="sxs-lookup"><span data-stu-id="56890-117">That serves as the default target namespace.</span></span> <span data-ttu-id="56890-118">名前空間が指定されていない場合、BizTalk Server は `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006` の既定の名前空間を使用します。</span><span class="sxs-lookup"><span data-stu-id="56890-118">If no namespace is identified, BizTalk Server will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56890-119">グリッド内のいずれかのフィールドに設定を入力した後、その設定を削除する場合は、行全体を削除する必要があります。行全体を削除しないと、ページの検証に失敗します。</span><span class="sxs-lookup"><span data-stu-id="56890-119">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56890-120">このグリッドの使用方法については、EDI インターフェイス開発チュートリアルで、インターチェンジの送信側パーティの設定に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56890-120">For an illustration of using this grid, run through the EDI Interface Developer tutorial, specifically setting up a party to receive an interchange from.</span></span> <span data-ttu-id="56890-121">詳細については、次を参照してください。[手順 4:、取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)です。</span><span class="sxs-lookup"><span data-stu-id="56890-121">For more information, see [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="56890-122">トランザクション セットのローカル ホスト設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="56890-122">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="56890-123">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="56890-123">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="56890-124">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="56890-124">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="56890-125">一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**ローカル ホストの設定**です。</span><span class="sxs-lookup"><span data-stu-id="56890-125">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="56890-126">選択**暗黙的な 10 進形式 Nn を底 10 の数値を変換**に BizTalk Server での中間 XML で底 10 の数値に形式 Nn で指定された EDI 番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="56890-126">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56890-127">この変換の後、中間 XML は長さの検証でエラーになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56890-127">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="56890-128">これは、底 10 の数値形式の番号に 10 進数が含まれるために発生するもので、その番号の長さは Nn 形式の番号より 1 だけ大きくなります。</span><span class="sxs-lookup"><span data-stu-id="56890-128">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="56890-129">この問題を解決するにはの値を追加して**1**最小値/最大長の値にします。</span><span class="sxs-lookup"><span data-stu-id="56890-129">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4.  <span data-ttu-id="56890-130">トランザクションの一部が設定した場合、検証の設定をセットとして**末尾の区切り記号のポリシー**に**オプション**または**必須**を選択できます**空を作成末尾の区切り記号のタグで XML**して、インターチェンジの送信者が末尾の区切り記号に空の XML タグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56890-130">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5.  <span data-ttu-id="56890-131">**カスタマイズ Target Namespace**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="56890-131">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="56890-132">選択、**既定**を定義する既定のターゲット名前空間を含む行のチェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="56890-132">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="56890-133">**St1 の場合**ドロップダウン リストからセット識別コードを列で、トランザクションの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="56890-133">In the **For ST1** column, select a value for the Transaction set identifier code from the drop-down list.</span></span>  
  
    3.  <span data-ttu-id="56890-134">**GS2**列で、アプリケーション送信者に 2 つの文字の最小値と最大 15 文字の英数字の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="56890-134">In the **GS2** column, enter an alphanumeric value for the Application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="56890-135">このフィールドは必須です。</span><span class="sxs-lookup"><span data-stu-id="56890-135">This is a required field.</span></span>  
  
    4.  <span data-ttu-id="56890-136">**Target Namespace**列で、ドロップダウン リストから選択するか、グリッドのどの行のデータ要素と、インターチェンジ内のフィールドの間で一致が検出されないときに、インターチェンジに対して使用されるターゲットの名前空間を入力します。</span><span class="sxs-lookup"><span data-stu-id="56890-136">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="56890-137">これらの値は、BizTalk Server が受信したインターチェンジに関連付けられている値と比較されます。</span><span class="sxs-lookup"><span data-stu-id="56890-137">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    5.  <span data-ttu-id="56890-138">使用するその他のターゲットの名前空間に対して、これらの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="56890-138">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    6.  <span data-ttu-id="56890-139">一覧からターゲットの名前空間を削除する行を選択し、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="56890-139">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="56890-140">をクリックして**適用**を変更を受け入れるか、をクリックして**OK**入力と、変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="56890-140">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56890-141">参照</span><span class="sxs-lookup"><span data-stu-id="56890-141">See Also</span></span>  
 [<span data-ttu-id="56890-142">トランザクション セットの構成設定 (X12)</span><span class="sxs-lookup"><span data-stu-id="56890-142">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)