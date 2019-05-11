---
title: EnvelopeProcessing (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, envelopes
- flat files, processing
- examples, flat files
- examples, messages
- examples, envelopes
- envelopes, messages
- flat files, examples
- envelopes, examples
ms.assetid: b4cd979b-c7b4-446c-be29-c9f3169afa1f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304a19f0ab775438f01df107baf860962cf89166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349235"
---
# <a name="envelopeprocessing-biztalk-server-sample"></a><span data-ttu-id="56888-102">EnvelopeProcessing (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="56888-102">EnvelopeProcessing (BizTalk Server Sample)</span></span>
<span data-ttu-id="56888-103">EnvelopeProcessing サンプルは、メッセージのメッセージのエンベロープを処理する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプライン。</span><span class="sxs-lookup"><span data-stu-id="56888-103">The EnvelopeProcessing sample demonstrates how to process messages and message envelopes in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines.</span></span> <span data-ttu-id="56888-104">さらに、XML メッセージにフラット ファイル メッセージを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="56888-104">Further, it shows how to process flat file messages into XML messages.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="56888-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="56888-105">What This Sample Does</span></span>  
 <span data-ttu-id="56888-106">このサンプルでは、受信場所として、EnvInput フォルダを構成します。</span><span class="sxs-lookup"><span data-stu-id="56888-106">This sample configures the folder EnvInput as a receive location.</span></span> <span data-ttu-id="56888-107">サンプル ファイル EnvelopeProcessing_in.txt、このフォルダーにファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の手順を使用してこのファイル内のメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="56888-107">When you place a file, such as the sample file EnvelopeProcessing_in.txt, in this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the messages in this file using the following steps:</span></span>  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="56888-108">受信場所フォルダ EnvInput からメッセージ ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="56888-108">retrieves the message file from the receive location folder EnvInput.</span></span>  

2. <span data-ttu-id="56888-109">受信パイプラインで、フラット ファイル逆アセンブラー パイプライン コンポーネントは、フラット ファイル メッセージからヘッダーおよびトレーラを削除し、個々 のメッセージに解析します。</span><span class="sxs-lookup"><span data-stu-id="56888-109">In the receive pipeline, the Flat File Disassembler pipeline component removes the header and trailer from the flat file messages, and parses them into individual messages.</span></span>  

3. <span data-ttu-id="56888-110">メッセージ ボックス データベースでは、メッセージは、サブスクリプション フィルターを使用して、送信ポートにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="56888-110">In the MessageBox database, the messages are routed to the send port using subscription filters.</span></span>  

4. <span data-ttu-id="56888-111">送信ポートの送信パイプラインでは、XML アセンブラー パイプライン コンポーネントは、メッセージを XML エンベロープでラップし、送信アダプタ フォルダ EnvOutput に配置します。</span><span class="sxs-lookup"><span data-stu-id="56888-111">In the send pipeline of the send port, XML Assembler pipeline component wraps the messages in XML envelopes and then places them into the send adapter folder EnvOutput.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="56888-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="56888-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="56888-113">このサンプルのデザインは、2 つの基本的な要件に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56888-113">The design of this sample had to accommodate two basic requirements:</span></span>  

- <span data-ttu-id="56888-114">受信して、1 つまたは複数の注文書を含むフラット ファイル メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="56888-114">Receive and process a flat file message containing one or more purchase orders.</span></span>  

- <span data-ttu-id="56888-115">バックエンド処理システムによって 1 つ購入順序と送信者情報ピックアップ ディレクトリを含む 1 つの XML メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="56888-115">Send one XML message containing one purchase order and sender information to a directory for pickup by a back-end processing system.</span></span>  

  <span data-ttu-id="56888-116">これらの要件を満たすには、フラットファイルおよび XML スキーマとカスタム パイプラインの組み合わせが使用されました。</span><span class="sxs-lookup"><span data-stu-id="56888-116">To meet these requirements, a combination of flat file/XML schemas and custom pipelines were used.</span></span> <span data-ttu-id="56888-117">これらおよび他のデザイン要素は、次の表にまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="56888-117">These and other design elements are summarized in the following table.</span></span>  

|<span data-ttu-id="56888-118">デザイン要素</span><span class="sxs-lookup"><span data-stu-id="56888-118">Design element</span></span>|<span data-ttu-id="56888-119">選択理由</span><span class="sxs-lookup"><span data-stu-id="56888-119">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="56888-120">カスタム受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="56888-120">Custom receive pipeline</span></span>|<span data-ttu-id="56888-121">-受信した注文書の注文メッセージを変換するのに、フラット ファイル逆アセンブラーとフラット ファイル スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-121">-   Uses the Flat File Disassembler and flat file schemas to translate inbound purchase order messages.</span></span>|  
|<span data-ttu-id="56888-122">メッセージのヘッダー、ボディ、およびトレーラ用フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="56888-122">Flat file schemas for message header, body, and trailer</span></span>|<span data-ttu-id="56888-123">-すべての同じレコードとフィールドの特性 (構造体を含む) として定義 XML スキーマとすべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。</span><span class="sxs-lookup"><span data-stu-id="56888-123">-   Defines all of the same record and field characteristics (including structure) as XML schemas and provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span><br /><span data-ttu-id="56888-124">ヘッダー、本文、およびトレーラーのスキーマは、本文を処理するための個々 のチャンクに分割に使用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-124">-   Header, body, and trailer schemas are used to split the body into discrete chunks for processing.</span></span>|  
|<span data-ttu-id="56888-125">エンベロープ スキーマ</span><span class="sxs-lookup"><span data-stu-id="56888-125">Envelope schema</span></span>|<span data-ttu-id="56888-126">-ヘッダーからの情報の個別の注文をラップするために使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-126">-   Used to wrap individual purchase orders with information from the header.</span></span>|  
|<span data-ttu-id="56888-127">サブスクリプション フィルター</span><span class="sxs-lookup"><span data-stu-id="56888-127">Subscription filter</span></span>|<span data-ttu-id="56888-128">-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。</span><span class="sxs-lookup"><span data-stu-id="56888-128">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="56888-129">カスタム送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="56888-129">Custom send pipeline</span></span>|<span data-ttu-id="56888-130">-インスタンス メッセージを XML 形式に変換するのに XML アセンブラおよびエンベロープとボディ スキーマの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-130">-   Uses the XML Assembler and a combination of envelope and body schemas to translate the instance messages into XML format.</span></span>|  

 <span data-ttu-id="56888-131">このサンプルのデザインに次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-131">The following considerations apply to the design of this sample.</span></span>  

-   <span data-ttu-id="56888-132">フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。</span><span class="sxs-lookup"><span data-stu-id="56888-132">The flat file schema (PO.xsd) contains extended annotations describing the structure of the purchase order flat file.</span></span> <span data-ttu-id="56888-133">これらのファイルを手動で作成できますが、多くは、フラット ファイル ウィザードを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="56888-133">These files can be created by hand, but many can be generated by using the Flat File Wizard.</span></span>  

-   <span data-ttu-id="56888-134">注文書 (PO.xsd) フラット ファイルのスキーマは、Unqualified の elementFormDefault 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-134">The purchase order (PO.xsd) flat file schema uses an elementFormDefault value of Unqualified.</span></span> <span data-ttu-id="56888-135">正しい結果が生成されますが、追加の予期しない xmlns 修飾します。</span><span class="sxs-lookup"><span data-stu-id="56888-135">This produces correct results but with additional and unexpected xmlns qualifications.</span></span> <span data-ttu-id="56888-136">この問題を回避するために、Qualified の elementFormDefault を使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-136">Use an elementFormDefault of Qualified to avoid this issue.</span></span>  

-   <span data-ttu-id="56888-137">ヘッダーおよびトレーラ フラット ファイル スキーマは、先頭および末尾のメッセージからのデータを個別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-137">Header and trailer flat file schemas are used to separate heading and trailing data from the message.</span></span> <span data-ttu-id="56888-138">フラット ファイル逆アセンブラーのヘッダー、ドキュメント、およびトレーラーのスキーマをヘッダー プロパティを設定した注文書、およびトレーラのスキーマをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="56888-138">The Flat File Disassembler header, document, and trailer schema properties were set to the header, purchase order, and trailer schema respectively.</span></span>  

-   <span data-ttu-id="56888-139">XML エンベロープ スキーマは、1 つの XML メッセージを生成するためにヘッダーと注文書の注文から要素を結合します。</span><span class="sxs-lookup"><span data-stu-id="56888-139">The XML envelope schema combines elements from the header and purchase order to produce a single XML message.</span></span> <span data-ttu-id="56888-140">ヘッダー スキーマでは、ソース フィールドを昇格 SourceParty フィールドに、 **BTS.bts_system_properties**名前空間。 エンベロープ スキーマに、送信メッセージに降格する原因となる、同じ値を昇格させます。</span><span class="sxs-lookup"><span data-stu-id="56888-140">The header schema promotes the Source field into the SourceParty field in the **BTS.bts_system_properties** namespace; the envelope schema promotes this same value, causing it to be demoted into the outbound message.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="56888-141">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="56888-141">Where to Find This Sample</span></span>  
 <span data-ttu-id="56888-142">`<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span><span class="sxs-lookup"><span data-stu-id="56888-142">`<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span></span>  

 <span data-ttu-id="56888-143">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="56888-143">The following table shows the files in this sample and describes their purpose.</span></span>  


|                      <span data-ttu-id="56888-144">ファイル</span><span class="sxs-lookup"><span data-stu-id="56888-144">File(s)</span></span>                      |                                                                                               <span data-ttu-id="56888-145">説明</span><span class="sxs-lookup"><span data-stu-id="56888-145">Description</span></span>                                                                                               |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    <span data-ttu-id="56888-146">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="56888-146">Cleanup.bat</span></span>                    |    <span data-ttu-id="56888-147">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-147">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="56888-148">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="56888-148">Removes send and receive ports.</span></span> <span data-ttu-id="56888-149">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="56888-149">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>     |
| <span data-ttu-id="56888-150">EnvelopeProcessing.btproj、EnvelopeProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="56888-150">EnvelopeProcessing.btproj, EnvelopeProcessing.sln</span></span> |                                                                               <span data-ttu-id="56888-151">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="56888-151">Project and solution files for this sample.</span></span>                                                                               |
|             <span data-ttu-id="56888-152">EnvelopeProcessing_in.txt</span><span class="sxs-lookup"><span data-stu-id="56888-152">EnvelopeProcessing_in.txt</span></span>             |                                                                                           <span data-ttu-id="56888-153">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="56888-153">Sample input file.</span></span>                                                                                            |
|          <span data-ttu-id="56888-154">Header.xsd、PO.xsd、Trailer.xsd</span><span class="sxs-lookup"><span data-stu-id="56888-154">Header.xsd, PO.xsd, Trailer.xsd</span></span>          |                                                                      <span data-ttu-id="56888-155">フラット スキーマは、ヘッダー、本文、およびトレーラーをそれぞれファイルします。</span><span class="sxs-lookup"><span data-stu-id="56888-155">Schema for flat file header, body, and trailer, respectively.</span></span>                                                                      |
|                  <span data-ttu-id="56888-156">XmlEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="56888-156">XmlEnvelope.xsd</span></span>                  |                                                                                    <span data-ttu-id="56888-157">送信 XML エンベロープ用スキーマです。</span><span class="sxs-lookup"><span data-stu-id="56888-157">Schema for outbound XML envelope.</span></span>                                                                                    |
|    <span data-ttu-id="56888-158">EnvReceivePipeline.btp, EnvSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="56888-158">EnvReceivePipeline.btp, EnvSendPipeline.btp</span></span>    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="56888-159">受信し、それぞれのフラット ファイル逆アセンブラーおよび XML アセンブラー パイプライン コンポーネントでは、パイプライン ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="56888-159">receive and send pipeline files with the Flat File Disassembler and XML Assembler pipeline components, respectively.</span></span> |
|           <span data-ttu-id="56888-160">EnvelopeProcessingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="56888-160">EnvelopeProcessingBinding.xml</span></span>           |                                                                             <span data-ttu-id="56888-161">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-161">Used for automated setup such as port binding.</span></span>                                                                              |
|                     <span data-ttu-id="56888-162">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="56888-162">Setup.bat</span></span>                     |                                                                                <span data-ttu-id="56888-163">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="56888-163">Used to build and initialize this sample.</span></span>                                                                                |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="56888-164">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="56888-164">How to Use This Sample</span></span>  
 <span data-ttu-id="56888-165">このサンプルを独自のフラット ファイル処理ソリューションの基礎として使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-165">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="56888-166">多くの独自の要件に合わせて、このサンプルで使用されるデザイン要素を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="56888-166">You can extend many of the design elements used in this sample to fit your own requirements.</span></span> <span data-ttu-id="56888-167">いくつかの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56888-167">Some examples are as follows:</span></span>  

-   <span data-ttu-id="56888-168">書き込む XML バージョンに加えて、各注文書のフラット ファイルのバージョンのサンプルを強化します。</span><span class="sxs-lookup"><span data-stu-id="56888-168">Enhance the sample to write a flat file version of each purchase order in addition to the XML version.</span></span> <span data-ttu-id="56888-169">新しいカスタム送信パイプラインを作成して、フラット ファイル アセンブラーを使用して、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="56888-169">You can do this by creating a new custom send pipeline and using the Flat File Assembler.</span></span> <span data-ttu-id="56888-170">フラット ファイル アセンブラー、フラット ファイルのヘッダーを指定、発注書、およびトレーラのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="56888-170">On the Flat File Assembler, specify the flat file header, purchase order, and trailer schemas.</span></span> <span data-ttu-id="56888-171">送信ポートで使用する場合は、ヘッダーおよびトレーラの情報を個別の注文を生成します。</span><span class="sxs-lookup"><span data-stu-id="56888-171">When used in a send port, it produces individual purchase orders with header/trailer information.</span></span>  

-   <span data-ttu-id="56888-172">詳細については、注文のエンベロープを強化します。</span><span class="sxs-lookup"><span data-stu-id="56888-172">Enhance the envelope with more information from the purchase order.</span></span> <span data-ttu-id="56888-173">送信メッセージに追加情報を記述するには、「出荷先」名またはクイック昇格を使用して他のフィールドを昇格、封筒にフィールドを追加および同じフィールドをエンベロープ フィールドを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="56888-173">To write additional information into the outbound message, promote the "ship to" name or other fields using Quick Promote, add fields to the envelope, and then promote the envelope fields to the same field.</span></span> <span data-ttu-id="56888-174">アセンブラーを通じて、メッセージが処理されるときに昇格させたプロパティが降格し、送信メッセージにコピーします。</span><span class="sxs-lookup"><span data-stu-id="56888-174">When the message is processed through the assembler, promoted properties are demoted and copied into the outbound message.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="56888-175">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="56888-175">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a><span data-ttu-id="56888-176">ビルドして初期化 EnvelopeProcessing サンプル</span><span class="sxs-lookup"><span data-stu-id="56888-176">To build and initialize the EnvelopeProcessing sample</span></span>  

1. <span data-ttu-id="56888-177">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="56888-177">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="56888-178">*\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing</span><span class="sxs-lookup"><span data-stu-id="56888-178">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing</span></span>  

2. <span data-ttu-id="56888-179">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="56888-179">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="56888-180">フォルダーには、入力 (EnvInput) とこのサンプルの出力 (EnvOutput) フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="56888-180">Creates the input (EnvInput) and output (EnvOutput) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="56888-181">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span><span class="sxs-lookup"><span data-stu-id="56888-181">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\\</span></span>  

   - <span data-ttu-id="56888-182">コンパイルし、このサンプルの Visual Studio プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="56888-182">Compiles and deploys the Visual Studio project for this sample.</span></span>  

   - <span data-ttu-id="56888-183">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="56888-183">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

      <span data-ttu-id="56888-184">このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56888-184">This sample displays the following warnings when creating and binding ports:</span></span>  

     ```  
     Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
     Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
     ```  

      <span data-ttu-id="56888-185">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="56888-185">You can safely ignore these warnings.</span></span> <span data-ttu-id="56888-186">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="56888-186">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="56888-187">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="56888-187">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="56888-188">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56888-188">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="56888-189">開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56888-189">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="56888-190">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-190">Use this key pair to sign the resulting assembly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="56888-191">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="56888-191">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="56888-192">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="56888-192">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="56888-193">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="56888-193">Running This Sample</span></span>  

#### <a name="to-run-the-envelopeprocessing-sample"></a><span data-ttu-id="56888-194">EnvelopeProcessing サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="56888-194">To run the EnvelopeProcessing sample</span></span>  

1.  <span data-ttu-id="56888-195">EnvelopeProcessing_in.txt ファイルのコピーを EnvInput フォルダに配置します。</span><span class="sxs-lookup"><span data-stu-id="56888-195">Put a copy of the file EnvelopeProcessing_in.txt into the folder EnvInput.</span></span>  

2.  <span data-ttu-id="56888-196">EnvOutput フォルダーに作成された 3 つの .xml ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="56888-196">Observe the three .xml files created in the folder EnvOutput.</span></span> <span data-ttu-id="56888-197">これらの .xml ファイルの名前は、そのメッセージ ID Guid に基づいています。</span><span class="sxs-lookup"><span data-stu-id="56888-197">The names of these .xml files are based on their message ID GUIDs.</span></span> <span data-ttu-id="56888-198">入力ファイルから抽出され、エンベロープでラップされたメッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56888-198">They contain the messages extracted from the input file and wrapped in envelopes.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="56888-199">クラスまたはメソッドのこのサンプルで使用</span><span class="sxs-lookup"><span data-stu-id="56888-199">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="56888-200">Setup.bat および Cleanup.bat の構成スクリプトは、次の管理用の Windows Management Instrumentation (WMI) スクリプトに依存します。</span><span class="sxs-lookup"><span data-stu-id="56888-200">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  

- <span data-ttu-id="56888-201">Start Send Port\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="56888-201">Start Send Port\StartSendPort.vbs</span></span>  

- <span data-ttu-id="56888-202">Enable Receive Location\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="56888-202">Enable Receive Location\EnableRecLoc</span></span>  

- <span data-ttu-id="56888-203">Remove Send Port\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="56888-203">Remove Send Port\RemoveSendPort</span></span>  

  <span data-ttu-id="56888-204">セットアップとクリーンアップ バッチ ファイルは、次のような BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="56888-204">The setup and cleanup batch files use BTSTask as follows:</span></span>  

- <span data-ttu-id="56888-205">**BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには</span><span class="sxs-lookup"><span data-stu-id="56888-205">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  

- <span data-ttu-id="56888-206">**BTSTask RemoveApp** FlatFileReceiveApplication を削除するには</span><span class="sxs-lookup"><span data-stu-id="56888-206">**BTSTask RemoveApp** to remove the FlatFileReceiveApplication</span></span>  

## <a name="see-also"></a><span data-ttu-id="56888-207">参照</span><span class="sxs-lookup"><span data-stu-id="56888-207">See Also</span></span>  
 [<span data-ttu-id="56888-208">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="56888-208">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)