---
title: AS2 送信コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 352cde6b72aecaf0baa9c53d1f67b63f3da215c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359003"
---
# <a name="as2-send-components"></a><span data-ttu-id="aa2cd-102">AS2 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aa2cd-102">AS2 Send Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="aa2cd-103">いくつかのコンポーネントを使用して、AS2 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-103">uses several components to send AS2 messages.</span></span>  
  
## <a name="as2-send-pipelines"></a><span data-ttu-id="aa2cd-104">AS2 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="aa2cd-104">AS2 Send Pipelines</span></span>  
 <span data-ttu-id="aa2cd-105">ほとんどの AS2 送信処理は、次の AS2 送信パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-105">Most AS2 send processing is performed in the following AS2 send pipelines.</span></span> <span data-ttu-id="aa2cd-106">これらのパイプラインがインストールされている`Microsoft.BizTalk.Edi.EdiIntPipelines.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components にします。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-106">These pipelines are installed in `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa2cd-107">AS2 送信パイプラインは、32 ビットの BizTalk ホスト プロセスでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-107">The AS2 Send pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="aa2cd-108">**AS2EDISend パイプライン**</span><span class="sxs-lookup"><span data-stu-id="aa2cd-108">**AS2EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="aa2cd-109">このパイプラインは、生成し、AS2 経由で EDI メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-109">This pipeline generates and sends EDI messages over AS2.</span></span> <span data-ttu-id="aa2cd-110">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-110">The pipeline consists of the following pipeline components:</span></span>  
  
- <span data-ttu-id="aa2cd-111">EDI アセンブラー</span><span class="sxs-lookup"><span data-stu-id="aa2cd-111">EDI Assembler</span></span>  
  
- <span data-ttu-id="aa2cd-112">AS2 エンコーダー</span><span class="sxs-lookup"><span data-stu-id="aa2cd-112">AS2 Encoder</span></span>  
  
  <span data-ttu-id="aa2cd-113">このパイプラインは、MDN は EDI アセンブラーによって処理される必要がないために生成し、AS2 経由で Mdn を送信するのには使用されません。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-113">This pipeline is not used to generate and send MDNs over AS2, because the MDN does not need to be processed by the EDI Assembler.</span></span> <span data-ttu-id="aa2cd-114">AS2SendPipeline を使用すると、Mdn を送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-114">Use the AS2SendPipeline to send MDNs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa2cd-115">オーケストレーションからの AS2EDISend パイプラインの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-115">Running the AS2EDISend pipeline from an orchestration is not supported.</span></span>  
  
 <span data-ttu-id="aa2cd-116">**AS2Send パイプライン**</span><span class="sxs-lookup"><span data-stu-id="aa2cd-116">**AS2Send Pipeline**</span></span>  
  
 <span data-ttu-id="aa2cd-117">このパイプラインは、メッセージが EDI でエンコードされていないときに、AS2 経由でメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-117">This pipeline sends messages over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="aa2cd-118">また、AS2 経由で Mdn を送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-118">It also sends MDNs over AS2.</span></span> <span data-ttu-id="aa2cd-119">パイプラインは、次のパイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-119">The pipeline consists of the following pipeline components:</span></span>  
  
- <span data-ttu-id="aa2cd-120">AS2 エンコーダー。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-120">AS2 Encoder.</span></span>  
  
  <span data-ttu-id="aa2cd-121">AS2 経由で送信するメッセージが EDI でも XML メッセージの場合は、これらのメッセージを処理するためにカスタマイズされた AS2Send パイプラインを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-121">If the messages to be sent over AS2 are neither EDI nor XML messages, you can create a customized AS2Send pipeline to handle these messages.</span></span> <span data-ttu-id="aa2cd-122">このパイプラインには、カスタマイズされたアセンブラーの中間 XML では、BizTalk Server はメッセージを ediint/as2 にエンコードする前に他の形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-122">This pipeline must have a customized assembler to convert the intermediate XML in BizTalk Server into the other format before encoding the message in EDIINT/AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa2cd-123">オーケストレーションからの AS2Send パイプラインを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-123">Running the AS2Send pipeline from an orchestration is not supported.</span></span>  
  
## <a name="as2-send-pipeline-components"></a><span data-ttu-id="aa2cd-124">AS2 送信パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aa2cd-124">AS2 Send Pipeline Components</span></span>  
 <span data-ttu-id="aa2cd-125">AS2 送信パイプラインは、次のパイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-125">The AS2 send pipelines use the following pipeline components.</span></span> <span data-ttu-id="aa2cd-126">これらのコンポーネントがインストールされている`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx \pipeline Components に\\します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-126">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="aa2cd-127">**EDI アセンブラー**</span><span class="sxs-lookup"><span data-stu-id="aa2cd-127">**EDI Assembler**</span></span>  
  
 <span data-ttu-id="aa2cd-128">EDIINT 送信パイプラインでは、EDI アセンブラーは EDI インターチェンジをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-128">In the EDIINT send pipelines, the EDI Assembler serializes the EDI interchange.</span></span>  
  
 <span data-ttu-id="aa2cd-129">**AS2 エンコーダー**</span><span class="sxs-lookup"><span data-stu-id="aa2cd-129">**AS2 Encoder**</span></span>  
  
 <span data-ttu-id="aa2cd-130">AS2 エンコーダーは、AS2 送信パイプラインのエンコード ステージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-130">The AS2 Encoder is included in the encode stage of the AS2 send pipelines.</span></span> <span data-ttu-id="aa2cd-131">S/MIME エンコード AS2 および MDN メッセージに機能を提供するのに、BizTalk の S/MIME パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-131">It uses the BizTalk S/MIME pipeline component to provide S/MIME encoding functionality to AS2 and MDN messages.</span></span> <span data-ttu-id="aa2cd-132">AS2 エンコーダーは、次を行います。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-132">The AS2 Encoder does the following:</span></span>  
  
-   <span data-ttu-id="aa2cd-133">AS2 または HTTP ヘッダーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-133">Applies AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="aa2cd-134">有効になっている場合、送信メッセージに署名</span><span class="sxs-lookup"><span data-stu-id="aa2cd-134">Signs outgoing messages, if enabled</span></span>  
  
-   <span data-ttu-id="aa2cd-135">(Edi/as2、MDN ではない) を有効になっている場合、送信メッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-135">Encrypts outgoing messages, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="aa2cd-136">(Edi/as2、MDN ではない) を有効になっている場合、メッセージを圧縮します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-136">Compresses the message, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="aa2cd-137">ペイロードをワイヤ形式に保存する場合、**送信のデコードされた AS2 メッセージに対して有効な NRR**プロパティが選択されているし、メッセージをワイヤ形式に保存する場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**プロパティが選択されています。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-137">Stores the payload in wire format if the **NRR enabled for outbound decoded AS2 messages** property is selected, and stores the message in wire format if the **NRR enabled for outbound encoded AS2 messages** property is selected</span></span>  
  
-   <span data-ttu-id="aa2cd-138">MIC 値を計算し、データ ストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-138">Computes the MIC value and stores it in the data store</span></span>  
  
-   <span data-ttu-id="aa2cd-139">更新し、受信の否認不可データベース内のレコードを関連付けています</span><span class="sxs-lookup"><span data-stu-id="aa2cd-139">Updates and correlates records in the non-repudiation receipt database</span></span>  
  
-   <span data-ttu-id="aa2cd-140">MDN メッセージの場合は、as2receive AS2 デコーダーによって生成された MDN をルーティングするパススルー パイプラインとして機能は受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-140">For MDN messages, acts as a passthrough pipeline, routing the MDN generated by the AS2 Decoder in the AS2Receive receive pipeline.</span></span> <span data-ttu-id="aa2cd-141">構成設定で必要な場合、AS2 エンコーダーが MDN に署名します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-141">If required by the configuration settings, the AS2 Encoder will sign the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aa2cd-142">AS2 メッセージでは 8 ビット エンコードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-142">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="aa2cd-143">Base64 エンコードは、AS2 メッセージと MDN の署名にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-143">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="aa2cd-144">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="aa2cd-144">HTTP Adapter</span></span>  
 <span data-ttu-id="aa2cd-145">EDIINT AS2 処理の使用するために使用される送信ポート、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP アダプター。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-145">The send ports used for EDIINT AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="aa2cd-146">HTTP アダプターが一方向の両方で構成されていると、送信請求-応答送信します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-146">The HTTP Adapter is configured in both one-way and solicit-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="aa2cd-147">否認不可データベース</span><span class="sxs-lookup"><span data-stu-id="aa2cd-147">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="aa2cd-148">は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) を使用して次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-148">uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa2cd-149">EdiMessageContent テーブルは、非否認不可ストレージ アグリーメントのプロパティのいずれかがチェックされている場合にのみ BizTalkDTADb データベースに存在します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-149">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties are checked.</span></span>  
  
-   <span data-ttu-id="aa2cd-150">署名付き MDN を否認不可記録を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-150">Provide a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="aa2cd-151">受信 MDN と送信メッセージを関連付け</span><span class="sxs-lookup"><span data-stu-id="aa2cd-151">Correlate an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="aa2cd-152">さまざまな状態の変化を経由してメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-152">Store messages through various state changes</span></span>  
  
-   <span data-ttu-id="aa2cd-153">エラー コードを HTTP 応答および MDN と関連付ける</span><span class="sxs-lookup"><span data-stu-id="aa2cd-153">Associate error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="aa2cd-154">フィルター条件に基づくレコードの表示</span><span class="sxs-lookup"><span data-stu-id="aa2cd-154">Display records based on filter criteria</span></span>  
  
-   <span data-ttu-id="aa2cd-155">マークされたレコードのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="aa2cd-155">Archive marked records</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa2cd-156">認証と否認不可データベースに格納されたメッセージの整合性を確保するには、元の AS2 メッセージと Mdn の両方のデータベースに格納されるすべてのメッセージにデジタル署名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa2cd-156">To ensure authentication and integrity of messages stored in the non-repudiation database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="aa2cd-157">詳細については、表示のセクション 9.1 [RFC 1430 の「Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)」](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span><span class="sxs-lookup"><span data-stu-id="aa2cd-157">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2cd-158">参照</span><span class="sxs-lookup"><span data-stu-id="aa2cd-158">See Also</span></span>  
 [<span data-ttu-id="aa2cd-159">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="aa2cd-159">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)