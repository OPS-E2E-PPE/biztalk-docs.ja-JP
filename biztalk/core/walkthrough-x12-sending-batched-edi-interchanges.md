---
title: 'チュートリアル (X12): バッチ EDI インターチェンジの送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b80ea79b-6112-49bd-90e8-9a0a0e604df8
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ce491b5cf9ff3d1c142599edee4e6c5f6a324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22292034"
---
# <a name="walkthrough-x12-sending-batched-edi-interchanges"></a><span data-ttu-id="6af2a-102">チュートリアル (X12): バッチ EDI インターチェンジの送信</span><span class="sxs-lookup"><span data-stu-id="6af2a-102">Walkthrough (X12): Sending Batched EDI Interchanges</span></span>
<span data-ttu-id="6af2a-103">このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して二者間で複数の EDI インターチェンジをバッチとしてまとめて送信するためのソリューションを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-103">This walkthrough provides a set of step-by-step procedures that creates a solution for sending batched EDI interchanges from one party to another using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6af2a-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="6af2a-104">Prerequisites</span></span>  
 <span data-ttu-id="6af2a-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="how-the-solution-sends-batched-edi-interchanges"></a><span data-ttu-id="6af2a-106">ソリューションがバッチ EDI インターチェンジを送信する方法</span><span class="sxs-lookup"><span data-stu-id="6af2a-106">How the Solution Sends Batched EDI Interchanges</span></span>  
 <span data-ttu-id="6af2a-107">このソリューションは次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-107">The solution will do the following:</span></span>  
  
1.  <span data-ttu-id="6af2a-108">受信場所から EDI インターチェンジを受信する、**パーティ A**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-108">The receive location receives an EDI interchange from a **Party A**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-109">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="6af2a-109">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="6af2a-110">受信パイプラインが、インターチェンジの EDI 形式を内部 XML 形式に変換し、</span><span class="sxs-lookup"><span data-stu-id="6af2a-110">The receive pipeline converts the EDI format of the interchange to internal XML format.</span></span> <span data-ttu-id="6af2a-111">インターチェンジがバッチ処理されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-111">The receive pipeline determines that the interchange is to be batched.</span></span> <span data-ttu-id="6af2a-112">その結果、BatchMarkerReceivePipeline コンポーネントが `EDI.ToBeBatched==True` プロパティと `EDI.BatchId` プロパティを昇格させ、</span><span class="sxs-lookup"><span data-stu-id="6af2a-112">As a result, the BatchMarkerReceivePipeline component promotes the `EDI.ToBeBatched==True` and `EDI.BatchId` properties.</span></span> <span data-ttu-id="6af2a-113">インターチェンジを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-113">It then drops the interchange into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="6af2a-114">受信されたインターチェンジをバッチ処理オーケストレーションがメッセージ ボックスから取り出します。このオーケストレーションは、`EDI.ToBeBatched==True` および `EDI.BatchId==%BatchID%` に基づいてメッセージをサブスクライブしているからです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-114">The Batching Orchestration retrieves the received interchange from the MessageBox, because it subscribes to the message based upon `EDI.ToBeBatched==True` and `EDI.BatchId==%BatchID%`.</span></span>  
  
4.  <span data-ttu-id="6af2a-115">受信場所が、最初のインターチェンジと同じ送信元から 2 つ目の EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-115">The receive location receives a second EDI interchange from the same party that sent the first interchange.</span></span>  
  
5.  <span data-ttu-id="6af2a-116">受信場所が、手順 2. と同様にインターチェンジを処理した後で、インターチェンジを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-116">The receive location processes the interchange as in step 2, and then drops the interchange into the MessageBox.</span></span>  
  
6.  <span data-ttu-id="6af2a-117">バッチ処理オーケストレーションが手順 3. と同様にインターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-117">The Batching Orchestration retrieves the interchange as in step 3.</span></span>  
  
7.  <span data-ttu-id="6af2a-118">リリース条件 (インターチェンジと照合される条件の定義) が満たされると、バッチ処理オーケストレーションは、すべてのインターチェンジが含まれるインターチェンジをアセンブルし、次にコンテキスト プロパティ `EDI.ToBeBatched==False`、`EDI.BatchName`、および `EDI.DestinationPartyName` を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-118">After the release criteria is met (release criteria defines how the interchanges have to be matched), the Batching Orchestration assembles the interchange containing all the interchanges, and then promotes the `EDI.ToBeBatched==False`, `EDI.BatchName` and `EDI.DestinationPartyName` context properties.</span></span> <span data-ttu-id="6af2a-119">その後で、バッチ インターチェンジを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-119">It drops the batched interchange into the MessageBox.</span></span>  
  
8.  <span data-ttu-id="6af2a-120">送信ポートが、コンテキスト プロパティ `EDI.ToBeBatched`==False、`EDI.BatchName`、および `EDI.DestinationPartyName` をサブスクライブしてこのバッチ インターチェンジを取得します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-120">The send port picks up the batched interchange by subscribing on the context properties `EDI.ToBeBatched`==False, `EDI.BatchName` and `EDI.DestinationPartyName`.</span></span>  
  
9. <span data-ttu-id="6af2a-121">送信パイプラインが、バッチ インターチェンジのエンベロープに追加のプロパティを適用し、送信先パーティをインターチェンジを送信**パーティ B**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-121">The send pipeline applies additional properties to the envelope of the batched interchange, and then sends the interchange to destination party, **Party B**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-122">詳細については、次を参照してください。[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-122">For more information, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
 <span data-ttu-id="6af2a-123">次の図では、このソリューションのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="6af2a-123">The following figure shows the architecture for this solution.</span></span>  
  
 <span data-ttu-id="6af2a-124">![バッチ EDI インターチェンジの送信](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")</span><span class="sxs-lookup"><span data-stu-id="6af2a-124">![Sending batched EDI interchanges](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")</span></span>  
  
## <a name="the-functionality-in-this-solution"></a><span data-ttu-id="6af2a-125">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="6af2a-125">The Functionality in this Solution</span></span>  
 <span data-ttu-id="6af2a-126">このチュートリアルを実行するために、以下の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-126">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  
  
-   <span data-ttu-id="6af2a-127">このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="6af2a-127">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-128">HIPAA および EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成によく似ています。</span><span class="sxs-lookup"><span data-stu-id="6af2a-128">The configuration used for HIPAA and for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  
  
-   <span data-ttu-id="6af2a-129">最初に受信したインターチェンジ、または送信されたバッチ インターチェンジへの応答として、技術確認または機能確認は返されません。</span><span class="sxs-lookup"><span data-stu-id="6af2a-129">Technical or functional acknowledgments will not be returned in response to the interchange originally received or any batched interchange that is sent.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-130">EDI 受信確認の生成方法の詳細については、次を参照してください。[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認をバックアップ](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-130">For information about generating EDI acknowledgments, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  
  
-   <span data-ttu-id="6af2a-131">このソリューションでは、一方向受信ポートと静的な一方向送信ポート。</span><span class="sxs-lookup"><span data-stu-id="6af2a-131">This solution uses a one-way receive port and a static one-way send port.</span></span> <span data-ttu-id="6af2a-132">これらのポートは、FILE トランスポートの種類で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-132">These ports will be configured with the FILE transport type.</span></span>  
  
-   <span data-ttu-id="6af2a-133">EDI レポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-133">EDI reporting will be enabled.</span></span>  
  
-   <span data-ttu-id="6af2a-134">インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-134">Transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="6af2a-135">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="6af2a-135">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="6af2a-136">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-136">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="6af2a-137">BizTalk プロジェクトに必要なメッセージ スキーマを追加してビルドおよび展開し、メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-137">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the messages.</span></span>  
  
-   <span data-ttu-id="6af2a-138">SQL アダプタのポーリング間隔を更新、 **BatchControlMessageReccvLoc**受信場所をクリックしたときに、バッチ処理オーケストレーションがすぐにアクティブにできるように、**開始** ボタンをクリックしてバッチ処理オーケストレーション インスタンスをアクティブ化するコントロール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-138">Update the polling interval for the SQL adapter in the **BatchControlMessageReccvLoc** receive location, so that the batching orchestration will be promptly activated when you click the **Start** button to send the control message that will activate a batching orchestration instance.</span></span>  
  
-   <span data-ttu-id="6af2a-139">EDI X12 でエンコードされた .txt 形式の入力メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって受信するための受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-139">Create a receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI X12-encoded .txt input messages from a party.</span></span>  
  
-   <span data-ttu-id="6af2a-140">パーティ A とパーティ B の両方に対してパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-140">Create a party (trading partner) for both Party A and Party B.</span></span>  
  
-   <span data-ttu-id="6af2a-141">両方の取引先それぞれにビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-141">Create a business profile each for both the trading partners.</span></span>  
  
-   <span data-ttu-id="6af2a-142">受信するメッセージの EDI プロパティを構成して、2 つのプロファイル間のアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-142">Create an agreement between the two profiles by configuring the EDI properties for the message to be received.</span></span> <span data-ttu-id="6af2a-143">送信されるバッチ メッセージの EDI プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-143">Configure the EDI properties for the batched message to be sent.</span></span> <span data-ttu-id="6af2a-144">このソリューションでは、850 インターチェンジを 2 つ受信したらパーティ B にバッチを 1 つ送信するように、アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-144">For this solution, configure the agreements such that BizTalk Server will send a batch to Party B whenever two 850 interchanges are received.</span></span>  
  
-   <span data-ttu-id="6af2a-145">バッチ EDI インターチェンジを取引先に送信するための送信ポートを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-145">Create a send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send the batched EDI interchange to the trading partner.</span></span> <span data-ttu-id="6af2a-146">この送信ポートは、静的な一方向の送信ポートとなります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-146">This send port will be a static one-way send port.</span></span>  
  
-   <span data-ttu-id="6af2a-147">インターチェンジを処理してバッチとしてまとめるためのアグリーメントに、この送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-147">Associate the send port with the agreement that processes the interchanges and batches them.</span></span>  
  
-   <span data-ttu-id="6af2a-148">受信場所に関連付けられたローカル フォルダーに 2 つのテスト EDI インターチェンジをドロップして、送信ポートに関連付けられたフォルダーにバッチ インターチェンジがドロップされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-148">Drop two test EDI interchanges into the local folder associated with the receive location, and verifying that BizTalk Server has dropped a batched interchange into the folder associated with the send port.</span></span>  
  
### <a name="configuring-the-walkthrough"></a><span data-ttu-id="6af2a-149">チュートリアルの構成</span><span class="sxs-lookup"><span data-stu-id="6af2a-149">Configuring the Walkthrough</span></span>  
 <span data-ttu-id="6af2a-150">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-150">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="6af2a-151">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-151">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="6af2a-152">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-152">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-153">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6af2a-153">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="6af2a-154">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-154">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="6af2a-155">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-155">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="6af2a-156">[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401 に移動し、テスト メッセージに対応するスキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-156">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401, and then double-click the schema corresponding to your test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-157">EDI スキーマが \XSD_Schema\EDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe** \XSD_Schema\EDI フォルダーに既定のフォルダーにして、スキーマ内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-157">If the EDI schemas have not been unzipped into the \XSD_Schema\EDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the \XSD_Schema\EDI folder to unzip the schemas into the default folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-158">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用される 850 サンプル メッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-158">For a test message, you can use the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="6af2a-159">このファイルは、の SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial\\です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-159">This file is SamplePO.txt in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\.</span></span> <span data-ttu-id="6af2a-160">この場合、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI にあるスキーマ x12_00401_850.xsd located in を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-160">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.</span></span>  
  
3.  <span data-ttu-id="6af2a-161">アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-161">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-update-the-polling-interval"></a><span data-ttu-id="6af2a-162">ポーリング間隔を更新するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-162">To update the polling interval</span></span>  
  
1.  <span data-ttu-id="6af2a-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、開く、 **BizTalk グループ**、**アプリケーション**、 **BizTalk EDI アプリケーション**ノード、および**受信場所**ノード。</span><span class="sxs-lookup"><span data-stu-id="6af2a-163">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, open the **BizTalk Group**, **Applications**, **BizTalk EDI Application** nodes, and **Receive Locations** nodes.</span></span> <span data-ttu-id="6af2a-164">下にある、**受信場所** ノードを右クリックして**BatchControlMessageRecvLoc**、順にクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-164">Under the **Receive Locations** node, right-click **BatchControlMessageRecvLoc**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6af2a-165">SQL トランスポートの種類をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-165">For the SQL transport type, click **Configure**.</span></span>  
  
3.  <span data-ttu-id="6af2a-166">**SQL トランスポートのプロパティ** ダイアログ ボックスで、値を小さくするポーリング間隔を設定します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-166">In the **SQL Transport Properties** dialog box, set the polling interval to a smaller value.</span></span> <span data-ttu-id="6af2a-167">たとえば、変更することができます**ポーリング単位**に**秒**分、5 秒間に、ポーリング間隔を変更する代わりにします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-167">For example, you can change **Polling Unit of Measure** to **Seconds**, instead of minutes, to change the polling interval to 5 seconds.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-168">ポーリング間隔を変更すると、バッチ処理オーケストレーションが正しくアクティブ化されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-168">Changing the polling interval ensures that the batching orchestration will be promptly activated.</span></span>  
  
4.  <span data-ttu-id="6af2a-169">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-169">Click **OK**, and then click **OK** again.</span></span>  
  
##### <a name="to-create-a-one-way-receive-port-to-receive-the-edi-messages-to-be-batched"></a><span data-ttu-id="6af2a-170">バッチ処理される EDI メッセージを受信するための一方向の受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-170">To create a one-way receive port to receive the EDI messages to be batched</span></span>  
  
1.  <span data-ttu-id="6af2a-171">バッチ処理される EDI メッセージを受信するためのローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-171">Create a local folder to receive the EDI messages to be batched.</span></span>  
  
2.  <span data-ttu-id="6af2a-172">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="6af2a-172">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
3.  <span data-ttu-id="6af2a-173">受信ポートの名前を指定し、をクリックして**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-173">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
4.  <span data-ttu-id="6af2a-174">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-174">Click **New**.</span></span>  
  
5.  <span data-ttu-id="6af2a-175">名前、受信場所は、select**ファイル**の**型**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-175">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="6af2a-176">用のフォルダーを入力**受信フォルダー**、およびマスクを**ファイル マスク**など **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-176">Enter a folder for **Receive folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  
  
7.  <span data-ttu-id="6af2a-177">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-177">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="6af2a-178">**受信パイプライン** **EdiReceive**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-178">For **Receive pipeline**, select **EdiReceive**.</span></span>  
  
9. <span data-ttu-id="6af2a-179">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-179">Click **OK**, and then click **OK** again.</span></span>  
  
10. <span data-ttu-id="6af2a-180">コンソール ツリーでクリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-180">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="6af2a-181">**受信場所** ウィンドウで、右クリックし、受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-181">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a><span data-ttu-id="6af2a-182">パーティ A のパーティおよびビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-182">To create a party and a business profile for Party A</span></span>  
  
1.  <span data-ttu-id="6af2a-183">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-183">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="6af2a-184">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-184">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-185">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6af2a-185">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6af2a-186">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-186">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="6af2a-187">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="6af2a-187">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="6af2a-188">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-188">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="6af2a-189">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**PartyA_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="6af2a-189">In the **Profile Properties** dialog box, on the **General** page, enter **PartyA_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-190">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-190">When you create a party, a profile is also created.</span></span> <span data-ttu-id="6af2a-191">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-191">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="6af2a-192">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-192">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="6af2a-193">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-193">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a><span data-ttu-id="6af2a-194">パーティ B のパーティおよびビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-194">To create a party and a business profile for Party B</span></span>  
  
1.  <span data-ttu-id="6af2a-195">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-195">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="6af2a-196">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-196">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-197">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6af2a-197">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6af2a-198">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-198">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="6af2a-199">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="6af2a-199">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="6af2a-200">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-200">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="6af2a-201">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力 **「partyb_profile」** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="6af2a-201">In the **Profile Properties** dialog box, on the **General** page, enter **PartyB_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-202">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-202">When you create a party, a profile is also created.</span></span> <span data-ttu-id="6af2a-203">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-203">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="6af2a-204">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-204">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="6af2a-205">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-205">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="6af2a-206">2 つのビジネス プロファイル間のアグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-206">To create an agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="6af2a-207">右クリック**PartyA_Profile**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-207">Right-click **PartyA_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="6af2a-208">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-208">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="6af2a-209">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-209">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="6af2a-210">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、**パーティ b**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-210">In the **Second Partner** section, from the **Name** drop-down list, select **PartyB**.</span></span>  
  
5.  <span data-ttu-id="6af2a-211">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **「partyb_profile」** です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-211">In the **Second Partner** section, from the **Profile** drop-down list, select **PartyB_Profile**.</span></span>  
  
     <span data-ttu-id="6af2a-212">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-212">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
6.  <span data-ttu-id="6af2a-213">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-213">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="6af2a-214">次のタスクを実行、**パーティ パーティ b]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-214">Perform the following tasks on the **PartyA->PartyB** tab.</span></span>  
  
    1.  <span data-ttu-id="6af2a-215">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-215">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6af2a-216"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-216"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="6af2a-217">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-217">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="6af2a-218">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-218">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="6af2a-219">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-219">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6af2a-220">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**THEM**、 **ISA7**に**ZZ**、および**ISA8**に**米国**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-220">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  
  
    2.  <span data-ttu-id="6af2a-221">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**重複している isa13 を確認**オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="6af2a-221">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6af2a-222">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-222">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    3.  <span data-ttu-id="6af2a-223">**文字セットと区切り記号**ページで、**インターチェンジの設定** セクションで、選択、 **CR LF**オプション。</span><span class="sxs-lookup"><span data-stu-id="6af2a-223">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  
  
    4.  <span data-ttu-id="6af2a-224">**バッチ構成**ページで、**インターチェンジの設定**セクションで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-224">On the **Batch Configuration** page under the **Interchange Settings** section, do the following:</span></span>  
  
        1.  <span data-ttu-id="6af2a-225">をクリックして**新しいバッチ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-225">Click **New Batch**.</span></span>  
  
        2.  <span data-ttu-id="6af2a-226">下にある、**識別** セクションの**バッチ名**、テキスト入力`Batch1`です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-226">Under the **Identification** section, for **Batch Name** text, enter `Batch1`.</span></span>  
  
        3.  <span data-ttu-id="6af2a-227">下にある、**フィルター**セクションで、をクリックして、**フィルター** 、ボタンをクリックし、[、**バッチ フィルター** ] ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-227">Under the **Filter** section, click the **Filter** button, and in the **Batch Filter** dialog box, do the following:</span></span>  
  
            1.  <span data-ttu-id="6af2a-228">下の空のセルをクリックして、**プロパティ**列と select **BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-228">Click the empty cell under the **Property** column and select **BTS.ReceivePortName**.</span></span>  
  
            2.  <span data-ttu-id="6af2a-229">下の空のセルをクリックして、**演算子**列と select  **==** です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-229">Click the empty cell under the **Operator** column and select **==**.</span></span>  
  
            3.  <span data-ttu-id="6af2a-230">下の空のセルをクリックして、**値**列と以前に作成した受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-230">Click the empty cell under the **Value** column and enter the name of the receive port you created earlier.</span></span>  
  
            4.  <span data-ttu-id="6af2a-231">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-231">Click **OK**.</span></span>  
  
        4.  <span data-ttu-id="6af2a-232">下にある、**リリース** セクションで、選択、**セットのトランザクションの最大数**ドロップダウンの選択 からのオプション**インターチェンジ**、し、テキスト ボックスに入力の数バッチ処理インターチェンジです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-232">Under the **Release** section, select the **Maximum number of transaction sets in** option, from the drop-down select **Interchange**, and in the text box enter the number of interchanges that will be batched.</span></span> <span data-ttu-id="6af2a-233">2 つのインターチェンジでは、このソリューションでバッチするよう、テキスト ボックスに次のように入力します。`2`です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-233">In this solution, you will be batching two interchanges, so in the text box, enter `2`.</span></span>  
  
        5.  <span data-ttu-id="6af2a-234">下にある、**アクティベーション**セクションで、**をすぐに開始**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-234">Under the **Activation** section, select **Start immediately**.</span></span>  
  
    5.  <span data-ttu-id="6af2a-235">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-235">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="6af2a-236">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6af2a-236">Use this</span></span>|<span data-ttu-id="6af2a-237">目的</span><span class="sxs-lookup"><span data-stu-id="6af2a-237">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="6af2a-238">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="6af2a-238">**Default**</span></span>|<span data-ttu-id="6af2a-239">選択**既定**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-239">Select **Default**.</span></span> <span data-ttu-id="6af2a-240">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="6af2a-240">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="6af2a-241">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="6af2a-241">**Transaction Type**</span></span>|<span data-ttu-id="6af2a-242">テスト メッセージのメッセージの種類を選択して**850 - 注文**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-242">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="6af2a-243">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="6af2a-243">**Version/Release**</span></span>|<span data-ttu-id="6af2a-244">EDI のバージョンを入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-244">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="6af2a-245">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="6af2a-245">**Target namespace**</span></span>|<span data-ttu-id="6af2a-246">選択**http://schemas.microsoft.com/BizTalk/Edi/X12/2006**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-246">Select **http://schemas.microsoft.com/BizTalk/Edi/X12/2006**.</span></span>|  
        |<span data-ttu-id="6af2a-247">**GS1**</span><span class="sxs-lookup"><span data-stu-id="6af2a-247">**GS1**</span></span>|<span data-ttu-id="6af2a-248">テスト メッセージのメッセージの種類が選択されていることを確認**PO - 注文書 (850)** です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-248">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>|  
        |<span data-ttu-id="6af2a-249">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="6af2a-249">**GS2**</span></span>|<span data-ttu-id="6af2a-250">たとえば、アプリケーション送信者の値を入力**Purchasing**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-250">Enter a value for the Application sender, for example, **Purchasing**.</span></span>|  
        |<span data-ttu-id="6af2a-251">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="6af2a-251">**GS3**</span></span>|<span data-ttu-id="6af2a-252">たとえば、アプリケーション受信者の値を入力**OrderControl**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-252">Enter a value for the Application receiver, for example, **OrderControl**.</span></span>|  
        |<span data-ttu-id="6af2a-253">**GS4**</span><span class="sxs-lookup"><span data-stu-id="6af2a-253">**GS4**</span></span>|<span data-ttu-id="6af2a-254">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-254">Select the date format that you want.</span></span> <span data-ttu-id="6af2a-255">**注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-255">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="6af2a-256">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="6af2a-256">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="6af2a-257">**GS5**</span><span class="sxs-lookup"><span data-stu-id="6af2a-257">**GS5**</span></span>|<span data-ttu-id="6af2a-258">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-258">Select the time format that you want.</span></span>|  
        |<span data-ttu-id="6af2a-259">**GS7**</span><span class="sxs-lookup"><span data-stu-id="6af2a-259">**GS7**</span></span>|<span data-ttu-id="6af2a-260">選択**X の間に認可 Standards Committee X12**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-260">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="6af2a-261">**GS8**</span><span class="sxs-lookup"><span data-stu-id="6af2a-261">**GS8**</span></span>|<span data-ttu-id="6af2a-262">EDI のバージョンが入力されていることを確認**00401**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-262">Verify that the EDI version has been entered, **00401**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6af2a-263">GS01、GS02、GS03、GS04、GS05、GS07、および入力した値に基づいて、送信する受信確認の GS08 の値が設定されます**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-263"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="6af2a-264">送信パイプラインは、トランザクション セットの種類、X12 バージョン、およびターゲットの名前空間と、メッセージ ヘッダー内の対応する値との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-264">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="6af2a-265">成功すると、その値が使用 GS に関連付けられている、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**値。</span><span class="sxs-lookup"><span data-stu-id="6af2a-265">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
8.  <span data-ttu-id="6af2a-266">次のタスクを実行、**パーティ b には、パーティが]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-266">Perform the following tasks on the **PartyB->PartyA** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-267">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-267">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="6af2a-268">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-268">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    1.  <span data-ttu-id="6af2a-269">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-269">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6af2a-270">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**米国**、 **ISA7**に**ZZ**、および**ISA8**に**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-270">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  
  
9. <span data-ttu-id="6af2a-271">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-271">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="6af2a-272">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-272">Click **OK**.</span></span> <span data-ttu-id="6af2a-273">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="6af2a-273">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="6af2a-274">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-274">The newly added agreement is enabled by default.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a><span data-ttu-id="6af2a-275">バッチ EDI インターチェンジを送信するための静的な一方向の送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="6af2a-275">To create a static one-way send port to send the batched EDI interchange</span></span>  
  
1.  <span data-ttu-id="6af2a-276">バッチ EDI メッセージの送信先ローカル フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-276">Create a local folder to send the batched EDI message to.</span></span>  
  
2.  <span data-ttu-id="6af2a-277">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="6af2a-277">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
3.  <span data-ttu-id="6af2a-278">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="6af2a-278">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
4.  <span data-ttu-id="6af2a-279">**トランスポート**セクションで、**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-279">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="6af2a-280">用のフォルダーを入力**コピー先フォルダー**、および**ファイル名**など **%MessageID%.txt**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-280">Enter a folder for **Destination folder**, and a **File name**, such as **%MessageID%.txt**.</span></span>  
  
6.  <span data-ttu-id="6af2a-281">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-281">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="6af2a-282">**送信パイプライン** **EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-282">In **Send pipeline**, select **EdiSend**.</span></span>  
  
8.  <span data-ttu-id="6af2a-283">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-283">In the console tree, select **Filters**.</span></span> <span data-ttu-id="6af2a-284">**フィルター**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-284">On the **Filters** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="6af2a-285">グリッドの最初の行で次のように選択します。 **EDI です。DestinationPartyName**の**プロパティ**、  **==** の**演算子**用にバッチを送信するパーティの選択された名前**値**、および**と**の**Group by**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-285">On the first line of the grid, select **EDI.DestinationPartyName** for **Property**, **==** for **Operator**, the name you selected for the party to send the batch to for **Value**, and **And** for **Group by**.</span></span>  
  
    2.  <span data-ttu-id="6af2a-286">2 番目の行に次のように選択します。 **EDI です。ToBeBatched**の**プロパティ**、  **==** の**演算子**、および**False**の**値**、および**と**の**Group by**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-286">On the second line, select **EDI.ToBeBatched** for **Property**, **==** for **Operator**, and **False** for **Value**, and **And** for **Group by**.</span></span>  
  
    3.  <span data-ttu-id="6af2a-287">3 番目の行に次のように選択します。 **EDI です。BatchName**の**プロパティ**、  **==** の**演算子**、および名前のバッチの**値**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-287">On the third line, select **EDI.BatchName** for **Property**, **==** for **Operator**, and the name of the batch for **Value**.</span></span>  
  
9. <span data-ttu-id="6af2a-288">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-288">Click **OK**.</span></span>  
  
10. <span data-ttu-id="6af2a-289">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-289">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="6af2a-290">**送信ポート** ウィンドウは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-290">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-associate-the-send-port-with-the-agreement-created-for-batching"></a><span data-ttu-id="6af2a-291">バッチ処理用に作成したアグリーメントに送信ポートを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="6af2a-291">To associate the send port with the agreement created for batching</span></span>  
  
1.  <span data-ttu-id="6af2a-292">以前に作成したアグリーメントを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-292">Right-click the agreement you created earlier and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6af2a-293">**アグリーメントのプロパティ** ダイアログ ボックスで、**パーティ パーティ b->**   タブで、をクリックして**送信ポート**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-293">In the **Agreement Properties** dialog box, on the **PartyA->PartyB** tab, click **Send Ports** in the left pane.</span></span>  
  
3.  <span data-ttu-id="6af2a-294">**送信ポート**ページで、**インターチェンジの設定**セクションで、先ほど作成した送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-294">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that you created earlier.</span></span> <span data-ttu-id="6af2a-295">**送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-295">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port.</span></span>  
  
4.  <span data-ttu-id="6af2a-296">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-296">Click **OK**.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="6af2a-297">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="6af2a-297">Testing the Walkthrough</span></span>  
 <span data-ttu-id="6af2a-298">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-298">This section provides information on how to test the walkthrough.</span></span>  
  
##### <a name="to-test-the-walkthrough"></a><span data-ttu-id="6af2a-299">チュートリアルをテストするには</span><span class="sxs-lookup"><span data-stu-id="6af2a-299">To test the walkthrough</span></span>  
  
1.  <span data-ttu-id="6af2a-300">Windows エクスプローラーで、受信場所に関連付けられているローカル フォルダーを開き、テスト EDI インターチェンジをそのフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-300">In Windows Explorer, open the local folder associated with the receive location, and drop a test EDI interchange into the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af2a-301">テスト メッセージには、EDI インターフェイス開発チュートリアルで使用される 850 サンプル メッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-301">For a test message, you can use the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="6af2a-302">このファイルは、の SamplePO.txt [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial\\です。</span><span class="sxs-lookup"><span data-stu-id="6af2a-302">This file is SamplePO.txt in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\.</span></span> <span data-ttu-id="6af2a-303">この場合、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI にあるスキーマ x12_00401_850.xsd located in を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6af2a-303">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.</span></span>  
  
2.  <span data-ttu-id="6af2a-304">テスト EDI インターチェンジのコピーを、このフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="6af2a-304">Drop a second copy of the test EDI interchange into the folder.</span></span>  
  
3.  <span data-ttu-id="6af2a-305">インターチェンジ用の送信ポートに関連付けられたフォルダーを開き、バッチ インターチェンジを開きます。</span><span class="sxs-lookup"><span data-stu-id="6af2a-305">Open the folder that you associated with the send port for interchanges, and open the batched interchange.</span></span> <span data-ttu-id="6af2a-306">インターチェンジに 1 組の ISA ヘッダーと GS ヘッダー、および 2 組のトランザクションが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6af2a-306">Verify that the interchange contains one set of ISA and GS headers, and two transaction sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af2a-307">参照</span><span class="sxs-lookup"><span data-stu-id="6af2a-307">See Also</span></span>  
 <span data-ttu-id="6af2a-308">[開発および BizTalk Server EDI ソリューションを構成します。](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="6af2a-308">[Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span></span>  
 <span data-ttu-id="6af2a-309">[送信バッチの構成](../core/configuring-an-outgoing-batch.md) </span><span class="sxs-lookup"><span data-stu-id="6af2a-309">[Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md) </span></span>  
 <span data-ttu-id="6af2a-310">[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="6af2a-310">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="6af2a-311">[バッチ EDI インターチェンジをアセンブル](../core/assembling-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="6af2a-311">[Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="6af2a-312">[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span><span class="sxs-lookup"><span data-stu-id="6af2a-312">[Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span></span>  
 [<span data-ttu-id="6af2a-313">EDI インターチェンジの送信チュートリアル (X12):</span><span class="sxs-lookup"><span data-stu-id="6af2a-313">Walkthrough (X12): Sending EDI Interchanges</span></span>](../core/walkthrough-x12-sending-edi-interchanges.md)