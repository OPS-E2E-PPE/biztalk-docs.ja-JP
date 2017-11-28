---
title: "動的なメッセージの種類の探索とスキーマの解決 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77e9a8949787fcd3c7e942c406c9f31470894a8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a><span data-ttu-id="241a9-102">動的なメッセージの種類の探索とスキーマの解決</span><span class="sxs-lookup"><span data-stu-id="241a9-102">Dynamic Message Type Discovery and Schema Resolution</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="241a9-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT 逆アセンブラおよびアセンブラの両方での動的なメッセージの型の検出とスキーマの解決を有効にします。</span><span class="sxs-lookup"><span data-stu-id="241a9-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] enables dynamic message type discovery and schema resolution in both the SWIFT disassembler and assembler.</span></span>  
  
## <a name="swift-disassembler"></a><span data-ttu-id="241a9-104">SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="241a9-104">SWIFT Disassembler</span></span>  
 <span data-ttu-id="241a9-105">SWIFT 逆アセンブラー (逆アセンブラー) を動的に受信したメッセージのメッセージの種類を検出して、メッセージを解析して必要な適切なスキーマを読み込む権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="241a9-105">The SWIFT disassembler (DASM) has the ability to dynamically discover the message type of a received message and load the appropriate schema needed to parse the message.</span></span> <span data-ttu-id="241a9-106">この機能の最大のメリットは、すべて SWIFT メッセージの種類の SWIFT メッセージの処理に SWIFT の逆アセンブラーを使用して 1 つのパイプラインを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="241a9-106">The greatest benefit of this feature is that you can configure a single pipeline using the SWIFT disassembler to process SWIFT messages of any SWIFT message type.</span></span> <span data-ttu-id="241a9-107">ネイティブの BizTalk フラット ファイル逆アセンブラーとは異なり、SWIFT の逆アセンブラーは必要ありません A4SWIFT が発生する可能性のあるメッセージの種類ごとに個別の受信パイプラインをビルドします。</span><span class="sxs-lookup"><span data-stu-id="241a9-107">Unlike the native BizTalk flat-file disassembler, the SWIFT disassembler does not require that you build a separate receive pipeline for each message type that A4SWIFT might encounter.</span></span>  
  
 <span data-ttu-id="241a9-108">ほとんどの場合、システムを受信するすべてのメッセージで始まります構造的に同種の見出しのデータと仮定した場合、動的なメッセージの種類の探索を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="241a9-108">You can use dynamic message type discovery if you assume that, in most cases, all messages that a system receives will begin with structurally homogeneous header data.</span></span> <span data-ttu-id="241a9-109">ヘッダー内では、データは、送信メッセージのメッセージの種類が表示されるフィールドです。</span><span class="sxs-lookup"><span data-stu-id="241a9-109">Within the header data are fields that reveal the message type of the message.</span></span> <span data-ttu-id="241a9-110">SWIFT のメッセージのヘッダーのデータで構成されます SWIFT メッセージ ブロック 1、2、3、ブロック (アプリケーション ヘッダーと呼ばれます) 2 に含まれるメッセージの種類の情報。</span><span class="sxs-lookup"><span data-stu-id="241a9-110">For SWIFT messages, header data consists of SWIFT message blocks 1, 2, and 3, with message type information contained in block 2 (known as the Application Header).</span></span>  
  
 <span data-ttu-id="241a9-111">SWIFT 逆アセンブラー コンポーネントは、プロパティの設定のいずれかを必要とせずすべて「単一」(非バッチ) SWIFT からメッセージ ボックスを処理できます。</span><span class="sxs-lookup"><span data-stu-id="241a9-111">The SWIFT DASM component can process all "single" (non-batched) SWIFT Messages out of the box without requiring any of the properties to be set.</span></span> <span data-ttu-id="241a9-112">既定では、SWIFT インターチェンジのスキーマと SWIFT ヘッダー スキーマ設定されていません。ただし、SWIFT 逆アセンブラー コンポーネントはスキーマを使用、SWIFT ヘッダー Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll 内に存在を動的に SWIFT メッセージの種類を検出し、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="241a9-112">By default, the SWIFT Interchange Schema and SWIFT Header schema are not set; however, the SWIFT DASM component will use the SWIFT Header schema present in Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll to detect the SWIFT Message Type dynamically and process the messages.</span></span> <span data-ttu-id="241a9-113">また、BRE および XML の検証は既定で有効に処理されるすべてのメッセージが完全に検証するためです。</span><span class="sxs-lookup"><span data-stu-id="241a9-113">Also, BRE and XML Validation are enabled by default so any message that is processed will be completely validated.</span></span> <span data-ttu-id="241a9-114">RuntimeSchemas.dll に SWIFT ヘッダーをポイントする SWIFT ヘッダー スキーマ プロパティを設定が上記と同じ動作にも発生します。</span><span class="sxs-lookup"><span data-stu-id="241a9-114">Setting the SWIFT Header schema property to point to the SWIFT Header in RuntimeSchemas.dll will also result in the same behavior as above.</span></span>  
  
 <span data-ttu-id="241a9-115">SWIFT の逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティが「なし」(既定) に設定されている場合、逆アセンブラーは動的に解決し、次の手順を実行することによって、適切なスキーマを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="241a9-115">When the SWIFT Header Schema configuration property for the SWIFT disassembler is set to "None" (the default), the disassembler dynamically resolves and loads the appropriate schema by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="241a9-116">(SWIFT ヘッダー スキーマ構成のプロパティで指定)、ユーザーが指定したヘッダー スキーマを使用して、受信メッセージの先頭 (ヘッダー) を解析します。</span><span class="sxs-lookup"><span data-stu-id="241a9-116">Uses the user-specified header schema (specified by the SWIFT Header Schema configuration property) to parse the beginning (header) of the receive message.</span></span>  
  
2.  <span data-ttu-id="241a9-117">A4SWIFT_MessageType 昇格させたプロパティ フィールドの結果として得られる「ヘッダー XML」を検査します。</span><span class="sxs-lookup"><span data-stu-id="241a9-117">Inspects the resulting "header XML" for the A4SWIFT_MessageType promoted property field.</span></span> <span data-ttu-id="241a9-118">このフィールドが存在する場合は"メッセージの種類として"フィールドの値を使用し、手順 4. に進みます。</span><span class="sxs-lookup"><span data-stu-id="241a9-118">If this field exists, it uses the field value as the "message type" and proceeds to Step 4.</span></span> <span data-ttu-id="241a9-119">フィールドが存在しない場合は、手順 3. に進みます。</span><span class="sxs-lookup"><span data-stu-id="241a9-119">If the field does not exist, it proceeds to Step 3.</span></span>  
  
3.  <span data-ttu-id="241a9-120">XML A4SWIFT_MessageType2 昇格させたプロパティ フィールドのヘッダーを検査 (逆アセンブラーが A4SWIFT_MessageType フィールドを検索していないかどうかを想定)。</span><span class="sxs-lookup"><span data-stu-id="241a9-120">Inspects the header XML for the A4SWIFT_MessageType2 promoted property field (expected if the disassembler does not find the A4SWIFT_MessageType field).</span></span> <span data-ttu-id="241a9-121">"メッセージの種類として"A4SWIFT_MessageType2 フィールドの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="241a9-121">Uses the A4SWIFT_MessageType2 field value as the "message type".</span></span>  
  
4.  <span data-ttu-id="241a9-122">手順 2 または 3 で識別される「メッセージ型」が「574」の場合は、SWIFT の逆アセンブラーは「574」が (つまり、逆アセンブラーのプロパティ) デュアル型メッセージの一覧の構成プロパティで指定されたメッセージの種類の一覧の場合は、メッセージの種類をチェックします。</span><span class="sxs-lookup"><span data-stu-id="241a9-122">If the "message type" identified in Step 2 or 3 is "574", the SWIFT disassembler checks if the message type "574" is in the list of message types specified in the Dual Type Message List configuration property (which is a property of the disassembler).</span></span> <span data-ttu-id="241a9-123">場合は、手順 5. に進みます。</span><span class="sxs-lookup"><span data-stu-id="241a9-123">If yes, it proceeds to Step 5.</span></span> <span data-ttu-id="241a9-124">ない場合は、手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="241a9-124">If no, proceeds to Step 6.</span></span>  
  
5.  <span data-ttu-id="241a9-125">ヘッダー XML A4SWIFT_SecondaryMessageType 昇格させたプロパティ フィールドを検査します。</span><span class="sxs-lookup"><span data-stu-id="241a9-125">Inspects header XML for the A4SWIFT_SecondaryMessageType promoted property field.</span></span> <span data-ttu-id="241a9-126">このフィールドが存在する場合、逆アセンブラーは"メッセージのサブ種類として"フィールドの値 (たとえば、"IRSLST") を使用して、「メッセージの種類」、"574_IRSLST"などに追加します。</span><span class="sxs-lookup"><span data-stu-id="241a9-126">If this field exists, the disassembler uses the field value (for example, "IRSLST") as the "message sub-type" and appends it to the "message type", for example, "574_IRSLST".</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="241a9-127">手順 5. の説明は、SWIFT の逆アセンブラー実際の実行内容のメッセージのサブ型に評価する簡略化バージョンです。</span><span class="sxs-lookup"><span data-stu-id="241a9-127">The explanation given for Step 5 is a simplification of what the SWIFT disassembler actually does to evaluate message sub-type.</span></span> <span data-ttu-id="241a9-128">実際には、SWIFT 逆アセンブラは、次のアルゴリズムおよびを判別メッセージの種類、サブタイプがある場合は、そのサブ型は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="241a9-128">In actuality, the SWIFT disassembler uses the following algorithm to determine if a message type has sub-types, and if so, what that sub-type is as follows.</span></span>  
  
    ```  
    Given MT type number nxx ...  
    if nxx is in the Dual-Type list {  
      if field 119 exists AND field 119 is NOT null/empty {  
        if n == 1 {  
          if field 119 == "STP" {  
            Use MTnxxPLUS schema  
          } else if field 119 == "REMIT" {  
            Use MTnxx schema  
          } else {  
            Use MTnxx_<field 119> schema  
          }   
        } else {  
          // n != 1  
          Use MTnxx_<field 119> schema  
        }  
      } else {  
        // field 119 does not exist or 119 does exist but is null/empty  
        Use MTnxx schema  
      }  
    } else {  
      // nxx is not a dual-type message  
      Use MTnxx schema  
    }  
    ```  
  
6.  <span data-ttu-id="241a9-129">逆アセンブラーは今すぐ、メッセージの種類を認識し、インターチェンジのスキーマ名をプレフィックスとサフィックス ("MT"プレフィックス"MT574_IRSLST"を作成する) などの名前付けいくつかの固定スキーマを連結して形成できます。</span><span class="sxs-lookup"><span data-stu-id="241a9-129">The disassembler now knows the message type, and it can form the interchange schema name by concatenating some fixed schema naming prefixes and suffixes (such as "MT" in the prefix to make "MT574_IRSLST").</span></span>  
  
7.  <span data-ttu-id="241a9-130">(名) をインターチェンジのスキーマを読み込み、メッセージ全体を解析**先頭から開始**、読み込まれたスキーマを使用して (つまり、逆アセンブラーが 2 回の見出しのデータを解析しますヘッダー スキーマを使用すると、を使ってもう一度。インターチェンジのスキーマの先頭)。</span><span class="sxs-lookup"><span data-stu-id="241a9-130">Loads the interchange schema (by name) and parses the entire message, **starting from the beginning**, using the loaded schema (this means that the disassembler parses the header data twice: once using the header schema, and again using the beginning of the interchange schema).</span></span> <span data-ttu-id="241a9-131">インターチェンジのスキーマは、ヘッダーを含むメッセージ全体を解析できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="241a9-131">The interchange schema must be able to parse the entire message, including the header.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="241a9-132">逆アセンブラーは、A4SWIFT SWIFT メッセージのすべてのスキーマを使用して SWIFT インターチェンジ全体を解析することができます (SWIFT ブロック 1、2、3、4、および 5)。</span><span class="sxs-lookup"><span data-stu-id="241a9-132">The disassembler can use all A4SWIFT SWIFT message schemas to parse the entire SWIFT interchange (SWIFT blocks 1, 2, 3, 4, and 5).</span></span> <span data-ttu-id="241a9-133">逆アセンブラーでは、既定 SWIFT ヘッダーのスキーマを使用して、ブロック 1、2、3 のみを解析します。</span><span class="sxs-lookup"><span data-stu-id="241a9-133">The disassembler uses the default SWIFT header schema to parse blocks 1, 2, and 3 only.</span></span> <span data-ttu-id="241a9-134">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="241a9-134">See below for details.</span></span>  
  
 <span data-ttu-id="241a9-135">上記で説明した、スキーマ解決アルゴリズムを意味する動的なメッセージ型探索が機能するためには、SWIFT ヘッダー スキーマ含める必要があります (、A4SWIFT で定義されている次の昇格させたプロパティを使用して、逆アセンブラーが昇格されるフィールドプロパティ スキーマ、Microsoft.Solutions.A4SWIFT.Property.PropertySchema):</span><span class="sxs-lookup"><span data-stu-id="241a9-135">The schema resolution algorithm described above implies that in order for dynamic message type discovery to work, the SWIFT Header Schema must contain fields that the disassembler has promoted using the following promoted properties (defined in the A4SWIFT Property Schema, Microsoft.Solutions.A4SWIFT.Property.PropertySchema):</span></span>  
  
-   <span data-ttu-id="241a9-136">**A4SWIFT_MessageType**</span><span class="sxs-lookup"><span data-stu-id="241a9-136">**A4SWIFT_MessageType**</span></span>  
  
-   <span data-ttu-id="241a9-137">**A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**を使用)</span><span class="sxs-lookup"><span data-stu-id="241a9-137">**A4SWIFT_MessageType2** (optional if **A4SWIFT_MessageTypes** is used)</span></span>  
  
-   <span data-ttu-id="241a9-138">**A4SWIFT_SecondaryMessageType** (省略可能)</span><span class="sxs-lookup"><span data-stu-id="241a9-138">**A4SWIFT_SecondaryMessageType** (optional)</span></span>  
  
 <span data-ttu-id="241a9-139">これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="241a9-139">For more information about these and other promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="241a9-140">SWIFT ヘッダー スキーマを設定すると**なし**、完全なインターチェンジのスキーマを指定する必要があります、 **SWIFT インターチェンジ スキーマ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="241a9-140">If you set the SWIFT Header Schema to **None**, you should specify a complete interchange schema for the **SWIFT Interchange Schema** property.</span></span> <span data-ttu-id="241a9-141">ここでは、逆アセンブラーは指定されたインターチェンジのスキーマを使用して、A4SWIFT を受信するすべてのメッセージを解析します。</span><span class="sxs-lookup"><span data-stu-id="241a9-141">In this case, the disassembler uses the specified interchange schema to parse all messages that A4SWIFT receives.</span></span> <span data-ttu-id="241a9-142">つまり、動的スキーマの解決を無効にし、型が指定されたインターチェンジ スキーマに一致するメッセージのみを受信するパイプラインを構成します。</span><span class="sxs-lookup"><span data-stu-id="241a9-142">That is, you disable dynamic schema resolution and configure the pipeline to receive only messages whose type matches the specified interchange schema.</span></span>  
  
 <span data-ttu-id="241a9-143">A4SWIFT は、SWIFT の標準ヘッダー データを解析することができますを動的スキーマの解決を容易にするために必要な昇格させたプロパティを持つ既定 SWIFT ヘッダー スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="241a9-143">A4SWIFT installs a default SWIFT header schema (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) that can parse SWIFT standard header data and has the necessary promoted properties to facilitate dynamic schema resolution.</span></span>  
  
 <span data-ttu-id="241a9-144">既定 SWIFT ヘッダーのスキーマには、次の昇格させたフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="241a9-144">The default SWIFT header schema has the following promoted fields:</span></span>  
  
-   <span data-ttu-id="241a9-145">**SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="241a9-145">**SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**.</span></span> <span data-ttu-id="241a9-146">逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="241a9-146">The disassembler promotes this using the **A4SWIFT_MessageType** property.</span></span>  
  
-   <span data-ttu-id="241a9-147">**SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="241a9-147">**SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**.</span></span> <span data-ttu-id="241a9-148">逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType2**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="241a9-148">The disassembler promotes this using the **A4SWIFT_MessageType2** property.</span></span>  
  
-   <span data-ttu-id="241a9-149">**SWIFTHeader/UserHeaderBlock/ValidationFlag_119**です。</span><span class="sxs-lookup"><span data-stu-id="241a9-149">**SWIFTHeader/UserHeaderBlock/ValidationFlag_119**.</span></span> <span data-ttu-id="241a9-150">逆アセンブラーを推進これを使用して、 **A4SWIFT_MessageType**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="241a9-150">The disassembler promotes this using the **A4SWIFT_MessageType** property.</span></span>  
  
 <span data-ttu-id="241a9-151">逆アセンブラーを使用して**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**に SWIFT ヘッダー スキーマと SWIFT インターチェンジのスキーマの両方の構成プロパティを設定した場合、ヘッダー スキーマとして既定では"None"です。</span><span class="sxs-lookup"><span data-stu-id="241a9-151">The disassembler uses **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** by default as the header schema if you set both SWIFT Header Schema and SWIFT Interchange Schema configuration properties to "None".</span></span>  
  
## <a name="swift-assembler"></a><span data-ttu-id="241a9-152">SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="241a9-152">SWIFT Assembler</span></span>  
 <span data-ttu-id="241a9-153">SWIFT 逆アセンブラーのようには、SWIFT、アセンブラーを動的に送信メッセージのメッセージの種類を検出して、メッセージをシリアル化するために必要な適切なスキーマを読み込む権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="241a9-153">Like the SWIFT disassembler, the SWIFT assembler has the ability to dynamically discover the message type of an outbound message and load the appropriate schema needed to serialize the message.</span></span> <span data-ttu-id="241a9-154">この機能では、SWIFT アセンブラーを使用して、SWIFT メッセージの種類の SWIFT のメッセージを処理する 1 つのパイプラインを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="241a9-154">This feature enables you to configure a single pipeline using the SWIFT assembler to process SWIFT messages of any SWIFT message type.</span></span> <span data-ttu-id="241a9-155">ネイティブの BizTalk フラット ファイル アセンブラーとは異なり、SWIFT アセンブラーは必要ありません A4SWIFT が発生する可能性のあるメッセージの種類ごとに個別の送信パイプラインを構築します。</span><span class="sxs-lookup"><span data-stu-id="241a9-155">Unlike the native BizTalk flat-file assembler, the SWIFT assembler does not require you to build a separate send pipeline for each message type that A4SWIFT might encounter.</span></span>  
  
 <span data-ttu-id="241a9-156">SWIFT アセンブラーで動的スキーマ解決は、アセンブラーは、ジョブに SWIFT のフラット ファイル形式の XML をシリアル化のために SWIFT の逆アセンブラーでより単純です。</span><span class="sxs-lookup"><span data-stu-id="241a9-156">Dynamic schema resolution in the SWIFT assembler is much simpler than in the SWIFT disassembler because the assembler does the job of serializing XML back into SWIFT flat-file format.</span></span> <span data-ttu-id="241a9-157">XML を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SWIFT アセンブラーへのシリアル化には、メッセージ型とスキーマについてには、シリアル化のための適切なスキーマを読み込むには、直接使用できる、SWIFT アセンブラーが含まれていますを提供します。</span><span class="sxs-lookup"><span data-stu-id="241a9-157">The XML that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] gives to the SWIFT assembler for serialization contains the message type and schema information, which the SWIFT assembler can use directly to load the appropriate schema for serialization.</span></span> <span data-ttu-id="241a9-158">そのため、SWIFT アセンブラーにはヘッダーとインターチェンジのスキーマのどの構成機能がありません: 指定されたスキーマを常に使用がシリアル化する XML のです。</span><span class="sxs-lookup"><span data-stu-id="241a9-158">As such, the SWIFT assembler does not have any configurability for header and interchange schemas: it always uses the schema specified in the XML that it will serialize.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241a9-159">参照</span><span class="sxs-lookup"><span data-stu-id="241a9-159">See Also</span></span>  
 [<span data-ttu-id="241a9-160">SWIFT 逆アセンブラおよびアセンブラの操作</span><span class="sxs-lookup"><span data-stu-id="241a9-160">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)