---
title: 外部バッチ リリース メカニズムを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5633a448-cc29-4931-a3ad-206ae25c989b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88b6962cc0c83ab0ac4971f481b9ac1f185ca02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258138"
---
# <a name="implementing-an-external-batch-release-mechanism"></a><span data-ttu-id="562fe-102">外部バッチ リリース メカニズムの実装</span><span class="sxs-lookup"><span data-stu-id="562fe-102">Implementing an External Batch Release Mechanism</span></span>
<span data-ttu-id="562fe-103">外部リリースのトリガーを使用すると、バッチのリリースをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="562fe-103">You can trigger the release of a batch using an external release trigger.</span></span> <span data-ttu-id="562fe-104">外部リリースのトリガーでは、バックエンドの基幹業務アプリケーションによって、特定のしきい値に到達したときに、リリースを自動的にトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="562fe-104">The release could be automatically triggered by a back-end, line-of-business application upon reaching a certain threshold.</span></span> <span data-ttu-id="562fe-105">このメカニズムは、自動的に、スケジュールまたはトランザクション セットや文字の数によってバッチのリリースをトリガーするかをクリックして、バッチを手動でトリガーするだけでなく、**オーバーライド**ボタンをクリックして、**バッチ構成**一方向アグリーメント タブのページです。</span><span class="sxs-lookup"><span data-stu-id="562fe-105">This mechanism is in addition to automatically triggering the batch release by a schedule or a count of transaction sets or characters, or manually triggering the batch by clicking the **Override** button in the **Batch Configuration** page of the one-way agreement tab.</span></span>  
  
 <span data-ttu-id="562fe-106">外部リリースのトリガーを実装するには、OverrideControlMessage を処理する受信ポートと受信場所を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="562fe-106">To implement an external release trigger, you need to set up a receive port and location to process the OverrideControlMessage.</span></span> <span data-ttu-id="562fe-107">受信場所では `Edi.BatchControlMessageRecvPipeline` 受信パイプラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="562fe-107">The receive location must use the `Edi.BatchControlMessageRecvPipeline` receive pipeline.</span></span> <span data-ttu-id="562fe-108">このパイプラインは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が手動上書きメッセージを処理するために使用する BatchControlMessageRecvLoc 受信場所で使用されるパイプラインと同じです。</span><span class="sxs-lookup"><span data-stu-id="562fe-108">This is the same pipeline that is used by the BatchControlMessageRecvLoc receive location that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process manual override messages.</span></span> <span data-ttu-id="562fe-109">ただし、BatchControlMessageRecvLoc が SQL 型の受信場所であるのに対し、ここで外部リリースのトリガー用に設定する受信場所では、任意の種類のアダプターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="562fe-109">However, BatchControlMessageRecvLoc is a SQL-type receive location, while the receive location that you set up for an external release trigger can use any adapter type.</span></span>  
  
 <span data-ttu-id="562fe-110">外部バッチ リリースは、XML コントロール メッセージによってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="562fe-110">An external batch release is triggered by an XML control message.</span></span> <span data-ttu-id="562fe-111">バッチをトリガーするには、バックエンド アプリケーションでコントロール メッセージを受信場所にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="562fe-111">To trigger the batch, the back-end application routes the control message to the receive location.</span></span> <span data-ttu-id="562fe-112">コントロール メッセージを変更することにより、バッチをアクティブ化、上書き、または終了できます。</span><span class="sxs-lookup"><span data-stu-id="562fe-112">You can modify the control message to activate, override, or terminate the batch.</span></span> <span data-ttu-id="562fe-113">コントロール メッセージの作成方法については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562fe-113">See the procedure below for creating the control message.</span></span>  
  
 <span data-ttu-id="562fe-114">外部リリースのトリガーを有効にするを選択する必要があります、**外部リリースのトリガ**プロパティに、**バッチ構成**のページ、**アグリーメントのプロパティ**ダイアログX12 または EDIFACT のボックスです。</span><span class="sxs-lookup"><span data-stu-id="562fe-114">To enable the external release trigger, you must select the **External release trigger** property in the **Batch Configuration** page of the **Agreement Properties** dialog box for either X12 or EDIFACT.</span></span> <span data-ttu-id="562fe-115">このプロパティは、バッチ リリースには外部リリース メッセージが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="562fe-115">This property indicates that an external release message is required for batch release.</span></span> <span data-ttu-id="562fe-116">**オーバーライド**ボタン、**停止**ボタン、および**アクティブ化**の範囲 コントロールは有効なまま場合、**外部リリースのトリガー**プロパティには選択されています。</span><span class="sxs-lookup"><span data-stu-id="562fe-116">The **Override** button, **Stop** button, and **Activation** range controls remain valid if the **External release trigger** property has been selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="562fe-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="562fe-117">Prerequisites</span></span>  
 <span data-ttu-id="562fe-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="562fe-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a><span data-ttu-id="562fe-119">外部バッチ リリース トリガー メッセージ用の受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="562fe-119">To create a receive location for the external batch release trigger message</span></span>  
  
1.  <span data-ttu-id="562fe-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、一方向受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="562fe-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, create a one-way receive port.</span></span> <span data-ttu-id="562fe-121">受信ポートを作成する方法については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="562fe-121">For instructions on how to create a receive port, see [How to Create a Receive Port](../core/how-to-create-a-receive-port.md).</span></span>  
  
2.  <span data-ttu-id="562fe-122">この受信ポート内に一方向の受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="562fe-122">Create a one-way receive location in the receive port.</span></span>  
  
3.  <span data-ttu-id="562fe-123">トランスポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="562fe-123">Select the transport type.</span></span> <span data-ttu-id="562fe-124">この受信場所には、どの種類のトランスポートを選択してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="562fe-124">You can select any type for this receive location.</span></span> <span data-ttu-id="562fe-125">一般的には、FILE を選択して、ファイルを受信するフォルダーを入力する方法が多く用いられます。</span><span class="sxs-lookup"><span data-stu-id="562fe-125">A common solution is to select the FILE type, and enter a folder to receive the file.</span></span>  
  
4.  <span data-ttu-id="562fe-126">[受信パイプライン] で、[`BatchControlMessageRecvPipeline`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="562fe-126">For Receive pipeline, select `BatchControlMessageRecvPipeline`.</span></span>  
  
5.  <span data-ttu-id="562fe-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="562fe-127">Click **OK**.</span></span>  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a><span data-ttu-id="562fe-128">外部バッチ リリース トリガー メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="562fe-128">To create the external batch release trigger message</span></span>  
  
1.  <span data-ttu-id="562fe-129">メモ帳で新しいファイルを作成し、.xml 拡張子付きの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="562fe-129">In Notepad, create a new file and name it with an .xml extension.</span></span>  
  
2.  <span data-ttu-id="562fe-130">次の内容をファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="562fe-130">Add the following to the file:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ControlMessage xmlns="http://SQLControlMessage.IssueSelect">  
      <PAM_Control xmlns="http://SQLControlMessage.IssueSelect">  
        <DestinationParty>[Party ID]</DestinationParty>  
        <EdiMessageType>[0 for X12\HIPAA|1 for Edifact]</EdiMessageType>  
        <ActionType>EdiBatchOverride</ActionType>  
        <ActionDateTime>[yyyy-mm-ddThh:mm:ss.sss]</ActionDateTime>  
        <UsedOnce>0</UsedOnce>  
        <BatchId>[Batch ID]</BatchId>  
        <BatchName>[Batch Name]</BatchName>  
        <DestinationPartyName>[Destination Party/Partner name]</DestinationPartyName>  
        <SenderPartyName>[Sender Party/Partner name]</SenderPartyName>  
        <AgreementName>[Agreement Name]</AgreementName>  
        <ReceiverPartyNameType>[Receiver Party/Partner name]</ReceiverPartyNameType>  
        <ToBeBatched>1</ToBeBatched>  
      </PAM_Control>  
    </ControlMessage>  
    ```  
  
     <span data-ttu-id="562fe-131">上記内容の値を次のように置換します。</span><span class="sxs-lookup"><span data-stu-id="562fe-131">Replace the values in the above excerpt as follows:</span></span>  
  
    -   <span data-ttu-id="562fe-132">アクションの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="562fe-132">Specify the action type.</span></span> <span data-ttu-id="562fe-133">通常、 **ActionType**に設定する必要があります**EdiBatchOverride**アグリーメントで行われたバッチ設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="562fe-133">Typically, the **ActionType** must be set to **EdiBatchOverride** to override the batch settings done in the agreement.</span></span> <span data-ttu-id="562fe-134">設定することもできます**EdiBatchTerminate**外部トリガーを通じてバッチを終了します。</span><span class="sxs-lookup"><span data-stu-id="562fe-134">You can also set this to **EdiBatchTerminate** to terminate the batch through an external trigger.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="562fe-135">バッチをアクティブ化する外部リリースのトリガーを使用する必要がありますいないをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="562fe-135">Microsoft recommends you should not use external release trigger to activate a batch.</span></span> <span data-ttu-id="562fe-136">そのため、指定しないでください**ActionType**として**EdiBatchActivate**です。</span><span class="sxs-lookup"><span data-stu-id="562fe-136">So, you should not specify **ActionType** as **EdiBatchActivate**.</span></span>  
  
    -   <span data-ttu-id="562fe-137">バッチ ID およびバッチ名を特定します。</span><span class="sxs-lookup"><span data-stu-id="562fe-137">Determine the Batch ID and Batch Name.</span></span> <span data-ttu-id="562fe-138">これを行うには、開く、**アグリーメントのプロパティ** ダイアログ ボックス、および一方向アグリーメント タブで、をクリックして**バッチ構成**です。</span><span class="sxs-lookup"><span data-stu-id="562fe-138">To do so, open the **Agreement Properties** dialog box, and on the one-way agreement tab, click **Batch Configuration**.</span></span> <span data-ttu-id="562fe-139">オーバーライドしての値を入力するバッチのタブをクリックして**バッチ名**と**バッチ ID**にフィールド、 **BatchName**と**BatchID**制御メッセージのノードです。</span><span class="sxs-lookup"><span data-stu-id="562fe-139">Click the tab for the batch to be overridden and enter the value of **Batch name** and **Batch ID** fields into the **BatchName** and **BatchID** nodes of the control message.</span></span>  
  
    -   <span data-ttu-id="562fe-140">送信先パーティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="562fe-140">Specify the destination party name.</span></span> <span data-ttu-id="562fe-141">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル** ページで、バッチを受信するパーティまたはパートナーの名前を取得インターチェンジの場合します。</span><span class="sxs-lookup"><span data-stu-id="562fe-141">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, get the name of the party/partner that will be receiving the batched interchanges.</span></span> <span data-ttu-id="562fe-142">名前を入力、 **ReceiverPartyNameType**制御メッセージのノードです。</span><span class="sxs-lookup"><span data-stu-id="562fe-142">Enter the name in the **ReceiverPartyNameType** node of the control message.</span></span>  
  
    -   <span data-ttu-id="562fe-143">送信元パーティ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="562fe-143">Specify the sender party name.</span></span> <span data-ttu-id="562fe-144">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル** ページで、バッチ インターチェンジを送信するパーティまたはパートナーの名前を取得.</span><span class="sxs-lookup"><span data-stu-id="562fe-144">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, get the name of the party/partner that will be sending the batched interchanges.</span></span> <span data-ttu-id="562fe-145">名前を入力、 **SenderPartyName**制御メッセージのノードです。</span><span class="sxs-lookup"><span data-stu-id="562fe-145">Enter the name in the **SenderPartyName** node of the control message.</span></span>  
  
    -   <span data-ttu-id="562fe-146">アグリーメント名を指定します。</span><span class="sxs-lookup"><span data-stu-id="562fe-146">Specify the agreement name.</span></span> <span data-ttu-id="562fe-147">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル**] ページの [、**契約**] セクションで、必要がありますをオーバーライドするコントロール メッセージを使用して、[バッチ構成を持つアグリーメントを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="562fe-147">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement that has the batch configuration that needs be to overridden using the control message, and then click **Properties**.</span></span> <span data-ttu-id="562fe-148">**アグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、**全般プロパティ** ページから値をコピー、**名前**フィールドに、**アグリーメントのパラメーター**セクション、および貼り付けることで、 **AgreementName**制御メッセージのノードです。</span><span class="sxs-lookup"><span data-stu-id="562fe-148">In the **Agreement Properties** dialog box, in the **General** tab, on the **General Properties** page, copy the value from the **Name** field in the **Agreement Parameters** section, and paste it in the **AgreementName** node of the control message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="562fe-149">インポート先のパーティ ID を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="562fe-149">You do not need to specify a destination party ID.</span></span> <span data-ttu-id="562fe-150">要素は、下位互換性のためにのみ、コントロール メッセージで必要になります。</span><span class="sxs-lookup"><span data-stu-id="562fe-150">The element is required in the control message only for backward compatibility.</span></span>  
  
3.  <span data-ttu-id="562fe-151">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="562fe-151">Save the file.</span></span>  
  
### <a name="to-enable-the-external-release-trigger"></a><span data-ttu-id="562fe-152">外部リリースのトリガーを有効にするには</span><span class="sxs-lookup"><span data-stu-id="562fe-152">To enable the external release trigger</span></span>  
  
1.  <span data-ttu-id="562fe-153">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル**] ページの [、**契約**] セクションで、必要がありますをオーバーライドするコントロール メッセージを使用して、[バッチ構成を持つアグリーメントを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="562fe-153">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, click the **Parties** node, and from the **Parties and Business Profiles** page, in the **Agreements** section, right-click the agreement that has the batch configuration that needs be to overridden using the control message, and then click **Properties**.</span></span> <span data-ttu-id="562fe-154">**アグリーメントのプロパティ** ダイアログ ボックスの一方向アグリーメント タブのをクリックして**バッチ構成**です。</span><span class="sxs-lookup"><span data-stu-id="562fe-154">In the **Agreement Properties** dialog box, on the one-way agreement tab, click **Batch Configuration**.</span></span>  
  
2.  <span data-ttu-id="562fe-155">**バッチ構成**] ページで、外部リリースのトリガーを対象となるし [バッチのタブをクリックして、**リリース**セクションで、**外部リリースのトリガー**.</span><span class="sxs-lookup"><span data-stu-id="562fe-155">In the **Batch Configuration** page, click the tab for the batch for which you want to have an external release trigger, and then under the **Release** section, select **External release trigger**.</span></span>  
  
3.  <span data-ttu-id="562fe-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="562fe-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562fe-157">参照</span><span class="sxs-lookup"><span data-stu-id="562fe-157">See Also</span></span>  
 <span data-ttu-id="562fe-158">[EDI バッチの構成](../core/configuring-edi-batches.md) </span><span class="sxs-lookup"><span data-stu-id="562fe-158">[Configuring EDI Batches](../core/configuring-edi-batches.md) </span></span>  
 [<span data-ttu-id="562fe-159">作成する方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="562fe-159">How to Create a Receive Location</span></span>](../core/how-to-create-a-receive-location.md)