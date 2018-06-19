---
title: 'チュートリアル (X12): バッチ EDI インターチェンジの受信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f6e6e96-39ec-469d-a845-1bfdce6cc0bf
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95c4bb48805eb0d2b349a8802c0bc8af1d12925a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975727"
---
# <a name="walkthrough-x12-receiving-batched-edi-interchanges"></a><span data-ttu-id="0c9e5-102">チュートリアル (X12): バッチ EDI インターチェンジの受信</span><span class="sxs-lookup"><span data-stu-id="0c9e5-102">Walkthrough (X12): Receiving Batched EDI Interchanges</span></span>
<span data-ttu-id="0c9e5-103">このチュートリアルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して EDI バッチの受信用のソリューションを作成する一連の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-103">This walkthrough provides a set of step-by-step procedures that creates a solution for receiving EDI batches using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0c9e5-104">このソリューションでは、バッチ EDI インターチェンジを受信する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-104">This solution demonstrates two ways to receive a batched EDI interchange:</span></span>  
  
-   <span data-ttu-id="0c9e5-105">その構成トランザクション バッチに分割して次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-105">By splitting the batch into its constituent transaction sets.</span></span>  
  
-   <span data-ttu-id="0c9e5-106">トランザクションを分割することがなく、1 つのドキュメント インターチェンジを処理することで、インターチェンジを保存することにより次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-106">By preserving the interchange by processing the interchange as one document without splitting the transaction sets.</span></span>  
  
 <span data-ttu-id="0c9e5-107">このチュートリアルでは、分割とバッチを保存の両方を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-107">This walkthrough demonstrates how to configure both splitting and preserving batches.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c9e5-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="0c9e5-108">Prerequisites</span></span>  
 <span data-ttu-id="0c9e5-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="how-the-solution-splits-received-edi-batches"></a><span data-ttu-id="0c9e5-110">ソリューションにより受信した EDI バッチを分割する方法</span><span class="sxs-lookup"><span data-stu-id="0c9e5-110">How the Solution Splits Received EDI Batches</span></span>  
 <span data-ttu-id="0c9e5-111">バッチ化されたインターチェンジを構成トランザクション セットに分割するようにソリューションを構成すると、このソリューションは次の動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-111">When you configure the solution to split the batched interchange into its constituent transaction sets, the solution will do the following:</span></span>  
  
1.  <span data-ttu-id="0c9e5-112">受信場所は、パーティから複数のトランザクション セットを含むバッチ EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-112">The receive location receives a batched EDI interchange containing multiple transaction sets from a party.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-113">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-113">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="0c9e5-114">受信パイプラインは、受信したインターチェンジを構成トランザクション セットに分割し、トランザクション セットを内部 XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-114">The receive pipeline splits the received interchange into its constituent transaction sets, converting the transaction sets into internal XML format.</span></span>  
  
3.  <span data-ttu-id="0c9e5-115">受信パイプラインは、インターチェンジ ヘッダーとグループ ヘッダー全体を、インターチェンジから分割された各トランザクション セットのコンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-115">The receive pipeline promotes the entire interchange and group headers into the context of each transaction set split from the interchange.</span></span> <span data-ttu-id="0c9e5-116">また、ISA6、GS1、GS2 などの特定のインターチェンジおよびグループ ヘッダーを昇格させ、これらのフィールドをルーティングに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-116">It also promotes certain specific interchange and group headers, such as ISA6, GS1, and GS2, so that these fields can be used for routing.</span></span>  
  
4.  <span data-ttu-id="0c9e5-117">受信パイプラインは、各トランザクション セット XML ファイルを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-117">The receive pipeline drops each transaction set XML file into the MessageBox.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-118">このソリューションでは、バッチには同じメッセージの種類の複数のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-118">In this solution, the batch contains multiple instances of the same message type.</span></span>  
  
5.  <span data-ttu-id="0c9e5-119">送信ポートは、適切なコンテキスト プロパティをサブスクライブすることで各トランザクション セットを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-119">The send port picks up each transaction set by subscribing on an appropriate context property.</span></span>  
  
6.  <span data-ttu-id="0c9e5-120">送信パイプラインは、各トランザクション セットを EDI インターチェンジに組み込んだ後、インターチェンジを送信先に送信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-120">The send pipeline builds each transaction set into an EDI interchange, and then sends the interchange to the destination.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-121">方法の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、バッチ内のトランザクション セットを分割を参照してください[バッチ EDI インターチェンジを分割](../core/splitting-a-batched-edi-interchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-121">For more information on how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] splits the transaction sets in a batch, see [Splitting a Batched EDI Interchange](../core/splitting-a-batched-edi-interchange.md).</span></span>  
  
 <span data-ttu-id="0c9e5-122">次の図に、バッチ化されたインターチェンジでトランザクション セットを分割するように構成した場合の、ソリューションのアーキテクチャとメッセージ フローを示します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-122">The following figure shows the architecture and message flow of the solution when it is configured to split the transaction sets in the batched interchange.</span></span>  
  
 <span data-ttu-id="0c9e5-123">![分割バッチ EDI インターチェンジ](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")</span><span class="sxs-lookup"><span data-stu-id="0c9e5-123">![Splitting batched EDI interchanges](../core/media/ef386df6-e195-45d9-abff-4d0bd3a82a4f.gif "ef386df6-e195-45d9-abff-4d0bd3a82a4f")</span></span>  
  
## <a name="how-the-solution-preserves-received-edi-batches"></a><span data-ttu-id="0c9e5-124">ソリューションにより受信した EDI バッチを保存する方法</span><span class="sxs-lookup"><span data-stu-id="0c9e5-124">How the Solution Preserves Received EDI Batches</span></span>  
 <span data-ttu-id="0c9e5-125">バッチ化されたインターチェンジを保存するようにソリューションを構成すると、このソリューションは次の動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-125">When you configure the solution to preserve the batched interchange, the solution will do the following:</span></span>  
  
1.  <span data-ttu-id="0c9e5-126">受信場所は、パーティからの複数のトランザクション セットを含むバッチ EDI インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-126">The receive location receives a batched EDI interchange containing multiple transaction sets from the party.</span></span>  
  
2.  <span data-ttu-id="0c9e5-127">受信パイプラインは、トランザクション セットを分割せずにインターチェンジを処理し、2 つのトランザクション セットを 1 つの単位として内部 XML 形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-127">The receive pipeline process the interchange without splitting the transaction sets, converting the two transaction sets as a unit into internal XML format.</span></span>  
  
3.  <span data-ttu-id="0c9e5-128">受信パイプラインは、インターチェンジがバッチでなかった場合と同じプロパティを昇格させます。ただし、生成する XML に予約タグを適用する場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-128">The receive pipeline promotes the same properties as if the interchange were not a batch, with the exception that it will applied a reserved tag to the XML that it generates.</span></span> <span data-ttu-id="0c9e5-129">このタグは、 \<X12InterchangeXml\> X12 でエンコードされた EDI インターチェンジまたは\<EdifactInterchangeXml\> EDIFACT でエンコードされた EDI インターチェンジの場合。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-129">This tag is \<X12InterchangeXml\> for an X12-encoded EDI interchange or \<EdifactInterchangeXml\> for an EDIFACT-encoded EDI interchange.</span></span> <span data-ttu-id="0c9e5-130">EDI 受信パイプラインは、インターチェンジを保存されたインターチェンジとして識別するために、コンテキスト プロパティ `ReuseEnvelope` も適用します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-130">The EDI receive pipeline also applies the context property `ReuseEnvelope` to identify the interchange as preserved.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-131">EDI 送信パイプラインを使用して、 \<X12InterchangeXml\>または\<EdifactInterchangeXml\>保存されたバッチとしてメッセージを識別するタグです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-131">The EDI send pipeline uses the \<X12InterchangeXml\> or \<EdifactInterchangeXml\> tag to identify the message as a preserved batch.</span></span> <span data-ttu-id="0c9e5-132">`ReuseEnvelope` コンテキスト プロパティにより、保存されたすべてのバッチ化されたインターチェンジをサブスクライブする送信ポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-132">The `ReuseEnvelope` context property enables you to create a send port that subscribes to all batched interchanges that are preserved.</span></span>  
  
4.  <span data-ttu-id="0c9e5-133">受信パイプラインは、メッセージ XML ファイルを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-133">The receive pipeline drops the message XML file into the MessageBox.</span></span>  
  
5.  <span data-ttu-id="0c9e5-134">送信ポートは、適切なコンテキスト プロパティでサブスクライブすることでインターチェンジを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-134">The send port picks up the interchange by subscribing on an appropriate context property.</span></span>  
  
6.  <span data-ttu-id="0c9e5-135">送信パイプラインは、XML ファイル内の 2 つのトランザクション セットを 1 つのバッチ EDI インターチェンジに組み込んだ後、インターチェンジを送信先に送信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-135">The send pipeline builds the two transaction sets in the XML file into a batched EDI interchange, and then sends the interchange to the destination.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-136">方法の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]保存されたバッチの処理を参照してください[、受信したバッチ EDI インターチェンジを保持する](../core/preserving-a-received-batched-edi-interchange.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-136">For more information on how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes a preserved batch, see [Preserving a Received Batched EDI Interchange](../core/preserving-a-received-batched-edi-interchange.md).</span></span>  
  
## <a name="functionality-in-this-solution"></a><span data-ttu-id="0c9e5-137">このソリューションの機能</span><span class="sxs-lookup"><span data-stu-id="0c9e5-137">Functionality in this Solution</span></span>  
 <span data-ttu-id="0c9e5-138">このチュートリアルを実行するために、以下の機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-138">For the purposes of this walkthrough, the following functionality will be enabled:</span></span>  
  
-   <span data-ttu-id="0c9e5-139">このソリューションは、EDIFACT エンコードではなく X12 エンコードを使用するインターチェンジを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-139">The solution is designed for interchanges using X12 encoding, not EDIFACT encoding.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-140">HIPAA および EDIFACT エンコードに使用される構成は、X12 エンコードに使用される構成によく似ています。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-140">The configuration used for HIPAA and for EDIFACT encoding is closely parallel to that used for X12 encoding.</span></span>  
  
-   <span data-ttu-id="0c9e5-141">最初に受信したインターチェンジ、または送信されたバッチ インターチェンジへの応答として、技術確認または機能確認は返されません。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-141">Technical or functional acknowledgments will not be returned in response to the interchange originally received or any batched interchange that is sent.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-142">EDI 受信確認の生成方法の詳細については、次を参照してください。[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認をバックアップ](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-142">For information about generating EDI acknowledgments, see [Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).</span></span>  
  
-   <span data-ttu-id="0c9e5-143">このソリューションでは、一方向受信ポートと静的な一方向送信ポート。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-143">This solution uses a one-way receive port and a static one-way send port.</span></span> <span data-ttu-id="0c9e5-144">これらのポートは、FILE トランスポートの種類で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-144">These ports will be configured with the FILE transport type.</span></span>  
  
-   <span data-ttu-id="0c9e5-145">EDI レポートが有効になります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-145">EDI reporting will be enabled.</span></span>  
  
-   <span data-ttu-id="0c9e5-146">インターチェンジの状態レポートに表示するトランザクション セットが保存されます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-146">Transaction sets will be saved for viewing from the interchange status report.</span></span>  
  
-   <span data-ttu-id="0c9e5-147">テストを実行するために、ソリューションは送信ポートを使用して、分割されたインターチェンジまたは保存されたバッチをローカル フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-147">For testing purposes, the solution uses a send ports to send the split interchanges or the preserved batch to a local folder.</span></span>  
  
## <a name="configuring-and-testing-the-walkthrough"></a><span data-ttu-id="0c9e5-148">チュートリアルの構成とテスト</span><span class="sxs-lookup"><span data-stu-id="0c9e5-148">Configuring and Testing the Walkthrough</span></span>  
 <span data-ttu-id="0c9e5-149">このソリューションに必要な手順は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-149">The procedures required for this solution include the following:</span></span>  
  
-   <span data-ttu-id="0c9e5-150">BizTalk プロジェクトに必要なメッセージ スキーマを追加してビルドおよび展開し、メッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するときにそのスキーマを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-150">Add the required message schema(s) to a BizTalk project, and then build and deploy the project, making the schema(s) available for use by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in processing the messages.</span></span>  
  
-   <span data-ttu-id="0c9e5-151">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信ポートを作成して、EDI X12 エンコード .txt バッチ入力メッセージをパーティから受信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-151">Create a receive port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive the EDI X12-encoded .txt batched input message from a party.</span></span>  
  
-   <span data-ttu-id="0c9e5-152">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の送信ポートを作成し、バッチで受信した各トランザクション セットからインターチェンジを作成する (バッチを分割する場合) か、受信バッチ内のトランザクション セットから 1 つのインターチェンジを作成します (バッチを保存する場合)。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-152">Create a send port for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to build an interchange out of each transaction sets received in the batch (if splitting the batch), or to build a single interchange from the transaction sets in the received batch (if preserving the batch).</span></span> <span data-ttu-id="0c9e5-153">次に、送信ポートは送信先パーティに 1 つまたは複数のインターチェンジを送信します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-153">The send port then sends the interchange or interchanges to the destination party.</span></span> <span data-ttu-id="0c9e5-154">この送信ポートは、静的な一方向の送信ポートとなります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-154">This send port will be a static one-way send port.</span></span>  
  
-   <span data-ttu-id="0c9e5-155">パーティ A とパーティ B の両方に対してパーティ (取引先) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-155">Create a party (trading partner) for both Party A and Party B.</span></span>  
  
-   <span data-ttu-id="0c9e5-156">両方の取引先それぞれにビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-156">Create a business profile each for both the trading partners.</span></span>  
  
-   <span data-ttu-id="0c9e5-157">分割するか、インターチェンジの保存、メッセージを受信する EDI のプロパティを構成することによって、2 つのプロファイル間のアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-157">Create an agreement between the two profiles by configuring the EDI properties to receive the message by splitting or preserving the interchange.</span></span>  
  
-   <span data-ttu-id="0c9e5-158">バッチ EDI インターチェンジを受信場所に関連付けられているローカル フォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-158">Drop one batched EDI interchange into the local folder associated with the receive location.</span></span> <span data-ttu-id="0c9e5-159">次に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信バッチの個別のインターチェンジ (バッチを分割する場合) または保存された 1 つのバッチ インターチェンジ (バッチを保存する場合) を、送信ポートに関連付けられているフォルダーにドロップしたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-159">You can then verify that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has dropped the separate interchanges from the received batch (if splitting the batch) or the single preserved batched interchange (if preserving the batch) into the folder associated with the send port.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-160">バッチ インターチェンジの送信チュートリアルの手順を実行した場合、そのソリューションの出力をこのソリューションの入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-160">If you have performed the steps in the sending batched interchanges walkthrough, you can use the output from that solution as the input for this solution.</span></span> <span data-ttu-id="0c9e5-161">そのソリューションからの出力は、2 つの 850 メッセージのバッチです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-161">The output from that solution is a batch of two 850 messages.</span></span> <span data-ttu-id="0c9e5-162">詳細については、次を参照してください。[チュートリアル (X12): バッチ EDI インターチェンジの送信](../core/walkthrough-x12-sending-batched-edi-interchanges.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-162">For more information, see [Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md).</span></span>  
  
 <span data-ttu-id="0c9e5-163">ここでは、チュートリアルを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-163">This section describes the procedures to configure the walkthrough.</span></span>  
  
##### <a name="to-deploy-the-message-schema"></a><span data-ttu-id="0c9e5-164">メッセージ スキーマを展開するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-164">To deploy the message schema</span></span>  
  
1.  <span data-ttu-id="0c9e5-165">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk プロジェクトを作成するか、開きます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-165">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create or open a BizTalk project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-166">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-166">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="0c9e5-167">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-167">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
2.  <span data-ttu-id="0c9e5-168">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-168">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="0c9e5-169">移動**\<ドライブ\>: \Program Files\Microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**、テスト メッセージに対応するスキーマをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-169">Move to **\<drive\>:\Program Files\Microsoft BizTalk Server 2009\XSD_Schema\EDI\X12\00401**, and then double-click the schema corresponding to your test message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-170">EDI スキーマは、XSD_SchemaEDI フォルダーに展開されていないが、実行、 **MicrosoftEdiXSDTemplates.exe**スキーマを既定のフォルダーに解凍する XSD_SchemaEDI フォルダー内のファイルです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-170">If the EDI schemas have not been unzipped into the XSD_SchemaEDI folders, execute the **MicrosoftEdiXSDTemplates.exe** file in the XSD_SchemaEDI folder to unzip the schemas into the default folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-171">テスト メッセージには、バッチ インターチェンジの送信チュートリアルでソリューションによって生成されたバッチ インターチェンジを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-171">For a test message, you can use the batched interchange generated by the solution in the sending batched interchanges walkthrough.</span></span> <span data-ttu-id="0c9e5-172">そのソリューションからの出力は、EDI インターフェイス開発チュートリアルに使用した 850 サンプル メッセージの 2 つのインスタンスのバッチです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-172">The output from that solution is a batch of two instances of the 850 sample message used for the EDI Interface Developer tutorial.</span></span> <span data-ttu-id="0c9e5-173">これを行う場合にある x12_00401_850.xsd というスキーマを使用する必要があります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI インターフェイス開発者 TutorialInbound_EDI です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-173">If you do so, you must use the schema x12_00401_850.xsd located in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDKEDI Interface Developer TutorialInbound_EDI.</span></span>  
  
3.  <span data-ttu-id="0c9e5-174">アセンブリ キー ファイルを設定し、アセンブリをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-174">Set the assembly key file, and then build and deploy the assembly.</span></span>  
  
##### <a name="to-create-a-one-way-receive-port-to-receive-the-batched-edi-messages"></a><span data-ttu-id="0c9e5-175">一方向の受信ポートを作成してバッチ処理された EDI メッセージを受信するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-175">To create a one-way receive port to receive the batched EDI messages</span></span>  
  
1.  <span data-ttu-id="0c9e5-176">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**受信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**一方向受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-176">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Receive Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
2.  <span data-ttu-id="0c9e5-177">受信ポートの名前を指定し、をクリックして**受信場所**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-177">Name the receive port, and then click **Receive Locations** in the console tree.</span></span>  
  
3.  <span data-ttu-id="0c9e5-178">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-178">Click **New**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-179">名前、受信場所は、select**ファイル**の**型**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-179">Name the receive location, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="0c9e5-180">用のフォルダーを入力**受信フォルダー**、およびマスクを**ファイル マスク**など **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-180">Enter a folder for **Receive folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  
  
6.  <span data-ttu-id="0c9e5-181">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-181">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0c9e5-182">**受信パイプライン** **EdiReceive**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-182">For **Receive pipeline**, select **EdiReceive**.</span></span>  
  
8.  <span data-ttu-id="0c9e5-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-183">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0c9e5-184">コンソール ツリーでクリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-184">In the console tree, click **Receive Locations**.</span></span> <span data-ttu-id="0c9e5-185">**受信場所** ウィンドウで、右クリックし、受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-185">In the **Receive Locations** pane, right-click your receive location, and then click **Enable**.</span></span>  
  
##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a><span data-ttu-id="0c9e5-186">バッチ EDI インターチェンジを送信するための静的な一方向の送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-186">To create a static one-way send port to send the batched EDI interchange</span></span>  
  
1.  <span data-ttu-id="0c9e5-187">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、**送信ポート**ノードの下、 **BizTalk アプリケーション 1**に**新規**をクリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-187">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send Ports** node under the **BizTalk Application 1** node, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
2.  <span data-ttu-id="0c9e5-188">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-188">In the **Send Port Properties** dialog box, name the send port.</span></span>  
  
3.  <span data-ttu-id="0c9e5-189">**トランスポート**セクションで、**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-189">In the **Transport** section, select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-190">用のフォルダーを入力**コピー先フォルダー**、およびマスクを**ファイル マスク**など **\*.txt**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-190">Enter a folder for **Destination folder**, and a mask for **File Mask**, such as **\*.txt**.</span></span>  
  
5.  <span data-ttu-id="0c9e5-191">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-191">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="0c9e5-192">**送信パイプライン** **EdiSend**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-192">In **Send pipeline**, select **EdiSend**.</span></span>  
  
7.  <span data-ttu-id="0c9e5-193">コンソール ツリーで、次のように選択します。**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-193">In the console tree, select **Filters**.</span></span> <span data-ttu-id="0c9e5-194">**フィルター**  ページで、バッチ内のメッセージをサブスクライブするフィルター式を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-194">On the **Filters** page, enter a filter expression that will subscribe to the messages in the batch.</span></span> <span data-ttu-id="0c9e5-195">たとえば、選択**BTS です。ReceivePortName**の**プロパティ**、  **==** の**演算子**用に作成した受信ポートの名前と**値**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-195">For example, select **BTS.ReceivePortName** for **Property**, **==** for **Operator**, and the name of the receive port that you just created for **Value**.</span></span>  
  
8.  <span data-ttu-id="0c9e5-196">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-196">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0c9e5-197">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-197">In the console tree, click **Send Ports**.</span></span> <span data-ttu-id="0c9e5-198">**送信ポート** ウィンドウは、送信ポートを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-198">In the **Send Ports** pane, right-click your send port, and then click **Start**.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a><span data-ttu-id="0c9e5-199">パーティ A のパーティおよびビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-199">To create a party and a business profile for Party A</span></span>  
  
1.  <span data-ttu-id="0c9e5-200">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-200">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0c9e5-201">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-201">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-202">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c9e5-202">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0c9e5-203">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-203">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0c9e5-204">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-204">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0c9e5-205">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-205">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-206">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力**PartyA_Profile**で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-206">In the **Profile Properties** dialog box, on the **General** page, enter **PartyA_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-207">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-207">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0c9e5-208">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-208">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0c9e5-209">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-209">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0c9e5-210">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-210">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a><span data-ttu-id="0c9e5-211">パーティ B のパーティおよびビジネス プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-211">To create a party and a business profile for Party B</span></span>  
  
1.  <span data-ttu-id="0c9e5-212">右クリックし、**パーティ**内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-212">Right-click the **Parties** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0c9e5-213">パーティの名前を入力、**名前**テキスト ボックスに入力し**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-213">Enter a name for the party in the **Name** text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-214">選択して、**ローカルの BizTalk は、このパーティからメッセージを送信するパーティまたはサポートが受信したメッセージを処理** チェック ボックスを指定できますをホストしている同じ組織のパーティの作成中であること[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c9e5-214">By selecting the **Local BizTalk processes messages received by the Party OR supports sending messages from this party** check box, you can specify that the party being created is for the same organization that is also hosting [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0c9e5-215">その指定に基づいて、アグリーメントを作成するときに一部のプロパティが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-215">Based on that, some properties will be enabled or disabled when you create an agreement.</span></span> <span data-ttu-id="0c9e5-216">ただし、このチュートリアルでは、このチェック ボックスはオンのままでかまいません。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-216">However, for this walkthrough, you can leave this check box selected.</span></span>  
  
3.  <span data-ttu-id="0c9e5-217">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-217">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-218">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力 **「partyb_profile」** で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-218">In the **Profile Properties** dialog box, on the **General** page, enter **PartyB_Profile** in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-219">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-219">When you create a party, a profile is also created.</span></span> <span data-ttu-id="0c9e5-220">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-220">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="0c9e5-221">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-221">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="0c9e5-222">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-222">In the **General** page, specify a name for the profile.</span></span>  
  
##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a><span data-ttu-id="0c9e5-223">2 つのビジネス プロファイル間のアグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-223">To create an agreement between the two business profiles</span></span>  
  
1.  <span data-ttu-id="0c9e5-224">右クリック**PartyA_Profile**、 をポイント**新規**、クリックして**アグリーメント**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-224">Right-click **PartyA_Profile**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="0c9e5-225">**全般プロパティ** ページの**名前**テキスト ボックスに、アグリーメントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-225">In the **General Properties** page, for the **Name** text box, enter a name for the agreement.</span></span>  
  
3.  <span data-ttu-id="0c9e5-226">**プロトコル**ドロップダウン リストで、 **X12**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-226">From the **Protocol** drop-down list, select **X12**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-227">**2 番目のパートナー**  セクションから、**名前**ドロップダウン リストで、**パーティ b**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-227">In the **Second Partner** section, from the **Name** drop-down list, select **PartyB**.</span></span>  
  
5.  <span data-ttu-id="0c9e5-228">**2 番目のパートナー**  セクションから、**プロファイル**ドロップダウン リストで、 **「partyb_profile」** です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-228">In the **Second Partner** section, from the **Profile** drop-down list, select **PartyB_Profile**.</span></span>  
  
     <span data-ttu-id="0c9e5-229">2 つの新しいタブの追加を取得 の横に表示されます、**全般**タブです。各タブに 1 つの一方向のアグリーメントを構成するようになっており、一方向の各アグリーメントが 1 つの完全なメッセージ トランザクション (メッセージの送信と受信確認の送信を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-229">You will notice that two new tabs get added next to the **General** tab. Each tab is for configuring a one-way agreement and each one-way agreement represents one complete transaction of message (including message transfer and acknowledgement transfer).</span></span>  
  
6.  <span data-ttu-id="0c9e5-230">**全般** タブで、**全般プロパティ** ページの 、**共通のホスト設定**セクションで、**レポートをオンに**、し、選択**reporting 用メッセージ ペイロードを格納**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-230">In the **General** tab, on the **General Properties** page, in the **Common Host Settings** section, select **Turn ON reporting**, and then select **Store message payload for reporting**.</span></span>  
  
7.  <span data-ttu-id="0c9e5-231">次のタスクを実行、**パーティ パーティ b]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-231">Perform the following tasks on the **PartyA->PartyB** tab.</span></span>  
  
    1.  <span data-ttu-id="0c9e5-232">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-232">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0c9e5-233"> では、アグリーメントの解決を実行するために、送信者と受信者の修飾子フィールドおよび ID フィールドを必ず指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-233"> requires the qualifier and identifier fields for sender and receiver in order to perform agreement resolution.</span></span> <span data-ttu-id="0c9e5-234">値と照合**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**とアグリーメントのプロパティで、インターチェンジ ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-234">It will match the values of **ISA5**, **ISA6**, **ISA7**, and **ISA8** in the interchange header with those in the properties of an agreement.</span></span> <span data-ttu-id="0c9e5-235">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信者の修飾子および識別子を照合して (受信者の修飾子および識別子は不要)、アグリーメントを解決します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-235">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also resolve the agreement by matching the sender qualifier and identifier (without the receiver qualifier and identifier).</span></span> <span data-ttu-id="0c9e5-236">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、アグリーメントを解決できない場合、フォールバック アグリーメントのプロパティが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-236">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot resolve the agreement, it will use the fallback agreement properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0c9e5-237">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**THEM**、 **ISA7**に**ZZ**、および**ISA8**に**米国**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-237">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **THEM**, **ISA7** to **ZZ**, and **ISA8** to **US**.</span></span>  
  
    2.  <span data-ttu-id="0c9e5-238">**検証**ページで、、**インターチェンジの設定**セクションで、確認してください**重複している isa13 を確認**オプションがオフになっています。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-238">On the **Validation** page under the **Interchange Settings** section, make sure **Check for duplicate ISA13** option is unchecked.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0c9e5-239">オフにすると、**重複している isa13 を確認して**プロパティでは、同じメッセージの複数のインスタンスを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-239">Clearing the **Check for duplicate ISA13** property enables you to receive multiple instances of the same message.</span></span>  
  
    3.  <span data-ttu-id="0c9e5-240">**文字セットと区切り記号**ページで、**インターチェンジの設定** セクションで、選択、 **CR LF**オプション。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-240">On the **Charset and Separators** page under the **Interchange Settings** section, select the **CR LF** option.</span></span>  
  
    4.  <span data-ttu-id="0c9e5-241">**ローカル ホスト設定**ページで、**インターチェンジの設定**セクションで、**受信メッセージ処理オプション**ボックスで、選択、**分割トランザクション セットとしてインターチェンジ - エラーのトランザクション セットを中断**オプション。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-241">On the **Local Host Settings** page under the **Interchange Settings** section, in the **Inbound Message Processing Option** box, select the **Split Interchange as Transaction Sets - suspend Transaction Sets on Error** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0c9e5-242">最初に、このソリューションでは、このオプションを選択してインターチェンジを分割します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-242">To start with, in this solution, we will split the interchange by selecting this option.</span></span> <span data-ttu-id="0c9e5-243">後の一部として[チュートリアルをテスト](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc)次の手順でソリューションを構成してインターチェンジを保存します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-243">Later, as part of [To test the walkthrough](../core/walkthrough-x12-receiving-batched-edi-interchanges.md#BKMK_Proc) procedure below, we will configure the solution to preserve the interchange.</span></span>  
  
    5.  <span data-ttu-id="0c9e5-244">**送信ポート**ページで、**インターチェンジの設定**セクションで、先ほど作成した送信ポートを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-244">On the **Send Ports** page under the **Interchange Settings** section, associate the send port that you created earlier.</span></span> <span data-ttu-id="0c9e5-245">**送信ポート**グリッド 、**名前**列は、空のセルをクリックし、ドロップダウン リストから送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-245">In the **Send ports** grid, under the **Name** column, click an empty cell, and from the drop-down list, select the send port.</span></span>  
  
    6.  <span data-ttu-id="0c9e5-246">**エンベロープ**ページで、**トランザクション セットの設定**セクションで、グリッドの最初の行のすべての列の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-246">On the **Envelopes** page under the **Transaction Set Settings** section, enter values for all columns in the first line of the grid.</span></span>  
  
        |<span data-ttu-id="0c9e5-247">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c9e5-247">Use this</span></span>|<span data-ttu-id="0c9e5-248">目的</span><span class="sxs-lookup"><span data-stu-id="0c9e5-248">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="0c9e5-249">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-249">**Default**</span></span>|<span data-ttu-id="0c9e5-250">選択**既定**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-250">Select **Default**.</span></span> <span data-ttu-id="0c9e5-251">**注:** 、既定の値は、この行を選択すると**GS1**、 **GS2**、 **GS3**、 **GS7**、および**GS8**が使用される場合でもの値は、**トランザクションの種類**、**バージョン/リリース**、および**ターゲットの名前空間**の一致するものではありません、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-251">**Note:**  When you select this row as the default, the values for **GS1**, **GS2**, **GS3**, **GS7**, and **GS8** are used even if the values for **Transaction Type**, **Version/Release**, and **Target namespace** are not a match for the message.</span></span>|  
        |<span data-ttu-id="0c9e5-252">**トランザクションの種類**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-252">**Transaction Type**</span></span>|<span data-ttu-id="0c9e5-253">テスト メッセージのメッセージの種類を選択して**850 - 注文**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-253">Select the message type of your test message, **850 - Purchase Order**.</span></span>|  
        |<span data-ttu-id="0c9e5-254">**バージョン/リリース**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-254">**Version/Release**</span></span>|<span data-ttu-id="0c9e5-255">EDI のバージョンを入力**00401**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-255">Enter the EDI version, **00401**.</span></span>|  
        |<span data-ttu-id="0c9e5-256">**ターゲットの名前空間**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-256">**Target namespace**</span></span>|<span data-ttu-id="0c9e5-257">選択**http://schemas.microsoft.com/Edi/X12**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-257">Select **http://schemas.microsoft.com/Edi/X12**.</span></span>|  
        |<span data-ttu-id="0c9e5-258">**GS1**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-258">**GS1**</span></span>|<span data-ttu-id="0c9e5-259">テスト メッセージのメッセージの種類が選択されていることを確認**PO - 注文書 (850)** です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-259">Verify that the message type of the test message is selected, **PO - Purchase Order (850)**.</span></span>|  
        |<span data-ttu-id="0c9e5-260">**[GS2]**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-260">**GS2**</span></span>|<span data-ttu-id="0c9e5-261">たとえば、アプリケーション送信者の値を入力**Purchasing**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-261">Enter a value for the Application sender, for example, **Purchasing**.</span></span>|  
        |<span data-ttu-id="0c9e5-262">**[GS3]**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-262">**GS3**</span></span>|<span data-ttu-id="0c9e5-263">たとえば、アプリケーション受信者の値を入力**OrderControl**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-263">Enter a value for the Application receiver, for example, **OrderControl**.</span></span>|  
        |<span data-ttu-id="0c9e5-264">**GS4**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-264">**GS4**</span></span>|<span data-ttu-id="0c9e5-265">日付の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-265">Select the date format that you want.</span></span> <span data-ttu-id="0c9e5-266">**注:** ドロップダウン リストで、値を選択し、だけでなく、既定値を表示するフィールドをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-266">**Note:**  You have to select the value in the drop-down list, not just click in the field to display the default.</span></span> <span data-ttu-id="0c9e5-267">ドロップダウン リストから値を選択せずにフィールドをクリックしても、値は実際に選択されません。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-267">If you click in the field without selecting the value from the drop-down list, the value will not actually be selected.</span></span>|  
        |<span data-ttu-id="0c9e5-268">**GS5**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-268">**GS5**</span></span>|<span data-ttu-id="0c9e5-269">時刻の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-269">Select the time format that you want.</span></span>|  
        |<span data-ttu-id="0c9e5-270">**GS7**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-270">**GS7**</span></span>|<span data-ttu-id="0c9e5-271">選択**X の間に認可 Standards Committee X12**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-271">Select **X - Accredited Standards Committee X12**.</span></span>|  
        |<span data-ttu-id="0c9e5-272">**GS8**</span><span class="sxs-lookup"><span data-stu-id="0c9e5-272">**GS8**</span></span>|<span data-ttu-id="0c9e5-273">EDI のバージョンが入力されていることを確認**00401**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-273">Verify that the EDI version has been entered, **00401**.</span></span>|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0c9e5-274">GS01、GS02、GS03、GS04、GS05、GS07、および入力した値に基づいて、送信する受信確認の GS08 の値が設定されます**トランザクション タイプ**、**バージョン/リリース**、および**ターゲット名前空間**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-274"> will set the values for GS01, GS02, GS03, GS04, GS05, GS07, and GS08 of the outbound acknowledgments based on the values entered for **Transaction Type**, **Version/Release**, and **Target namespace**.</span></span> <span data-ttu-id="0c9e5-275">送信パイプラインは、トランザクション セットの種類、X12 バージョン、およびターゲットの名前空間と、メッセージ ヘッダー内の対応する値との照合を試みます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-275">The send pipeline attempts to match the transaction set type, the X12 version, and the target namespace with the corresponding values in the header of the message.</span></span> <span data-ttu-id="0c9e5-276">成功すると、その値が使用 GS に関連付けられている、**トランザクション タイプ**、**バージョン/リリース**、および**ターゲットの名前空間**値。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-276">If successful, it uses the GS values associated with the **Transaction Type**, **Version/Release**, and **Target namespace** values.</span></span>  
  
8.  <span data-ttu-id="0c9e5-277">次のタスクを実行、**パーティ b には、パーティが]-> [** タブです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-277">Perform the following tasks on the **PartyB->PartyA** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-278">このチュートリアルでは、必要な値をタブに指定し、アグリーメントを正常に作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-278">In this walkthrough, we specify the required value in the tab so that an agreement can be successfully created.</span></span> <span data-ttu-id="0c9e5-279">アグリーメントを正常に作成する両方の一方向アグリーメント タブの値に対して定義されている必要があります**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-279">To successfully create an agreement, both one-way agreement tabs must have values defined for **ISA5**, **ISA6**, **ISA7**, and **ISA8**.</span></span>  
  
    1.  <span data-ttu-id="0c9e5-280">**識別子**ページで、**インターチェンジの設定**セクションで、修飾子と識別子のフィールドの値を入力 (**ISA5**、 **ISA6**、 **ISA7**、および**ISA8**) テスト メッセージのヘッダー フィールドの値に対応します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-280">On the **Identifiers** page under the **Interchange Settings** section, enter values for the qualifier and identifier fields (**ISA5**, **ISA6**, **ISA7**, and **ISA8**) that correspond to the values for those header fields in your test message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0c9e5-281">テスト メッセージとして「EDI インターフェイス開発チュートリアル」の SamplePO.txt ファイルを使用する場合は、設定**ISA5**に**ZZ**、 **ISA6**に**米国**、 **ISA7**に**ZZ**、および**ISA8**に**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-281">If you are using the SamplePO.txt file from the “EDI Interface Developer Tutorial” as your test message, set **ISA5** to **ZZ**, **ISA6** to **US**, **ISA7** to **ZZ**, and **ISA8** to **THEM**.</span></span>  
  
9. <span data-ttu-id="0c9e5-282">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-282">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="0c9e5-283">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-283">Click **OK**.</span></span> <span data-ttu-id="0c9e5-284">新しく追加したアグリーメントが一覧表示、**契約**のセクションで、**パーティとビジネス プロファイル**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-284">The newly added agreement is listed in the **Agreements** section of the **Parties and Business Profiles** pane.</span></span> <span data-ttu-id="0c9e5-285">新しく追加したアグリーメントは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-285">The newly added agreement is enabled by default.</span></span>  
  
### <a name="testing-the-walkthrough"></a><span data-ttu-id="0c9e5-286">チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="0c9e5-286">Testing the Walkthrough</span></span>  
 <span data-ttu-id="0c9e5-287">ここでは、チュートリアルをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-287">This section provides information on how to test the walkthrough.</span></span>  
  
####  <a name="BKMK_Proc"></a><span data-ttu-id="0c9e5-288">このチュートリアルをテストするには</span><span class="sxs-lookup"><span data-stu-id="0c9e5-288">To test the walkthrough</span></span>  
  
1.  <span data-ttu-id="0c9e5-289">Windows エクスプローラーで、受信場所に関連付けられているローカル フォルダーを開き、テスト バッチ EDI インターチェンジをフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-289">In Windows Explorer, open the local folder associated with the receive location, and drop a test batched EDI interchange into the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c9e5-290">テスト メッセージには、バッチ インターチェンジの送信チュートリアルでソリューションによって生成されたバッチ インターチェンジ出力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-290">For a test message, you can use the batched interchange output generated by the solution in the sending batched interchanges walkthrough.</span></span> <span data-ttu-id="0c9e5-291">このサンプル メッセージには、2 つのトランザクション セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-291">This sample message would contain two transaction sets.</span></span>  
  
2.  <span data-ttu-id="0c9e5-292">作成した送信ポートに関連付けられているフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-292">Open the folder that you associated with the send port that you created above.</span></span> <span data-ttu-id="0c9e5-293">フォルダーに 2 つの新しいファイルが含まれ、各ファイルがテスト バッチ メッセージのトランザクション セットの 1 つを含む 850 インターチェンジであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-293">Verify that the folder contains two new files, and that each file is an 850 interchange containing one of the transaction sets in the test batched message.</span></span>  
  
3.  <span data-ttu-id="0c9e5-294">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノード、先ほど作成したアグリーメントの一部である 2 つのビジネス プロファイルのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-294">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Parties** node, click any of the two business profiles that are part of the agreement created earlier.</span></span> <span data-ttu-id="0c9e5-295">**契約**セクションで、アグリーメントを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-295">In the **Agreements** section, right-click the agreement, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0c9e5-296">**アグリーメントのプロパティ**ダイアログ ボックスの**ローカル ホスト設定**ページで、**インターチェンジの設定**セクションで、**メッセージの受信処理オプション**ボックスで、いずれかを選択**インターチェンジの保存 - エラーでインターチェンジを中断**または**インターチェンジの保存 - エラーのトランザクション セットを中断** をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-296">In the **Agreement Properties** dialog box, on the **Local Host Settings** page under the **Interchange Settings** section, in the **Inbound Message Processing Option** box, select either **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="0c9e5-297">をクリックして**ホスト インスタンス**下にある、**プラットフォームの設定** ノードを右クリックして**BizTalkServerApplication**、順にクリック**再起動**。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-297">Click **Host Instances** under the **Platform Settings** node, right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
6.  <span data-ttu-id="0c9e5-298">Windows エクスプローラーで、受信場所に関連付けられているローカル フォルダーを開き、再度同じテスト バッチ EDI インターチェンジをフォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-298">In Windows Explorer, open the local folder associated with the receive location, and once again drop the same test batched EDI interchange into the folder.</span></span>  
  
7.  <span data-ttu-id="0c9e5-299">Windows エクスプローラーで、前に作成した送信ポートに関連付けたフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-299">In Windows Explorer, open the folder that you associated with the send port that you created above.</span></span> <span data-ttu-id="0c9e5-300">フォルダーに 1 つの新しいファイルのみが含まれ、そのファイルがテスト バッチ メッセージに存在した 2 つの 850 トランザクション セットを含むインターチェンジであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c9e5-300">Verify that the folder now contains only one new file, and that the file is an interchange containing the two 850 transaction sets that were in the test batched message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c9e5-301">参照</span><span class="sxs-lookup"><span data-stu-id="0c9e5-301">See Also</span></span>  
 <span data-ttu-id="0c9e5-302">[開発および BizTalk Server EDI ソリューションを構成します。](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-302">[Developing and Configuring BizTalk Server EDI Solutions](../core/developing-and-configuring-biztalk-server-edi-solutions.md) </span></span>  
 <span data-ttu-id="0c9e5-303">[バッチ EDI インターチェンジの分割](../core/splitting-a-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-303">[Splitting a Batched EDI Interchange](../core/splitting-a-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="0c9e5-304">[HIPAA サブドキュメントの分割](../core/splitting-hipaa-subdocuments.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-304">[Splitting HIPAA Subdocuments](../core/splitting-hipaa-subdocuments.md) </span></span>  
 <span data-ttu-id="0c9e5-305">[バッチ EDI インターチェンジを受信した保持](../core/preserving-a-received-batched-edi-interchange.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-305">[Preserving a Received Batched EDI Interchange](../core/preserving-a-received-batched-edi-interchange.md) </span></span>  
 <span data-ttu-id="0c9e5-306">[チュートリアル (X12): バッチ EDI インターチェンジの送信](../core/walkthrough-x12-sending-batched-edi-interchanges.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-306">[Walkthrough (X12): Sending Batched EDI Interchanges](../core/walkthrough-x12-sending-batched-edi-interchanges.md) </span></span>  
 <span data-ttu-id="0c9e5-307">[チュートリアル (X12): EDI インターチェンジの受信と送信、受信確認](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span><span class="sxs-lookup"><span data-stu-id="0c9e5-307">[Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md) </span></span>  
 [<span data-ttu-id="0c9e5-308">チュートリアル (X12): EDI インターチェンジの送信</span><span class="sxs-lookup"><span data-stu-id="0c9e5-308">Walkthrough (X12): Sending EDI Interchanges</span></span>](../core/walkthrough-x12-sending-edi-interchanges.md)