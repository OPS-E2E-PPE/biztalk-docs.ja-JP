---
title: パイプライン (BizTalk Server Samples フォルダ) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- SDK examples
- examples, pipelines
ms.assetid: d1b6d984-ac0d-4149-99fd-93d3b6ed316c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21ea7a91815576c736ca150465191b2aa83d4c74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395748"
---
# <a name="pipelines-biztalk-server-samples-folder"></a><span data-ttu-id="cfdf0-102">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="cfdf0-102">Pipelines (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="cfdf0-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK) のいくつかのパイプラインのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several pipeline samples in its software development kit (SDK).</span></span> <span data-ttu-id="cfdf0-104">このセクションでは、機能の詳細について、各パイプライン サンプル説明を構築して、サンプルと予想される結果を実行する手順。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-104">This section provides detailed information about the functionality that each pipeline sample demonstrates, instructions for building and running the sample, and the results you can expect.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="cfdf0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cfdf0-105">In This Section</span></span>  

- <span data-ttu-id="cfdf0-106">[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-106">[Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-107">オーケストレーションとパイプラインを使用したメッセージ集計機能を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-107">Demonstrates message aggregation functionality using orchestrations and pipelines.</span></span>  

- <span data-ttu-id="cfdf0-108">[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](../core/arbitrary-xpath-property-handler-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-108">[Arbitrary XPath Property Handler (BizTalk Server Sample)](../core/arbitrary-xpath-property-handler-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-109">BizTalk Server に送信された XML ドキュメントの特定のプロパティを昇格させるためのカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-109">Demonstrates how to write a custom pipeline component to promote specific properties on an XML document submitted to BizTalk Server.</span></span> <span data-ttu-id="cfdf0-110">プロパティの昇格は、XPath 式を使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-110">Property promotion is accomplished using an XPath expression.</span></span>  

- [<span data-ttu-id="cfdf0-111">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="cfdf0-111">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)  

  -   <span data-ttu-id="cfdf0-112">[FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-112">[FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-113">BizTalk Server パイプラインを使用して同等の XML メッセージに区切られたフラット ファイル メッセージを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-113">Demonstrates how to process delimited flat file messages into the equivalent XML messages using BizTalk Server pipelines.</span></span>  

  -   <span data-ttu-id="cfdf0-114">[EnvelopeProcessing (BizTalk Server サンプル)](../core/envelopeprocessing-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-114">[EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-115">BizTalk Server パイプラインを使用してエンベロープを XML メッセージをフラット ファイル メッセージに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-115">Demonstrates how to process flat file messages into XML messages with envelopes using BizTalk Server pipelines.</span></span>  

  -   <span data-ttu-id="cfdf0-116">[FlatFileSend (BizTalk Server サンプル)](../core/flatfilesend-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-116">[FlatFileSend (BizTalk Server Sample)](../core/flatfilesend-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-117">BizTalk Server パイプラインを使用して同等の位置指定フラット ファイル メッセージに XML メッセージを変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-117">Demonstrates how to process XML messages into the equivalent positional flat file messages using BizTalk Server pipelines.</span></span>  

- <span data-ttu-id="cfdf0-118">[メッセージ プロセッサ (BizTalk Server サンプル) で構成される](../core/composed-message-processor-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-118">[Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-119">構成済みメッセージ処理を使用して集計したメッセージからの個別のアイテムを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-119">Demonstrates how to process individual line items from aggregated messages using composed message processing.</span></span>  

- <span data-ttu-id="cfdf0-120">[CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-120">[CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-121">作成およびストリーミングされたメッセージを変更するカスタム パイプライン コンポーネントを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-121">Demonstrates how to create and use a custom pipeline component that modifies a streamed message.</span></span>  

- <span data-ttu-id="cfdf0-122">[カスタム パーティの解決 (BizTalk Server サンプル)](../core/custom-party-resolution-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-122">[Custom Party Resolution (BizTalk Server Sample)](../core/custom-party-resolution-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-123">カスタム パーティを解決するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-123">Demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  

- <span data-ttu-id="cfdf0-124">[MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-124">[MIME (BizTalk Server Sample)](../core/mime-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-125">どのメッセージを示します MIME でエンコードされた BizTalk パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-125">Demonstrates how messages can be MIME-encoded using BizTalk pipelines.</span></span>  

- <span data-ttu-id="cfdf0-126">[スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)](../core/schema-resolver-component-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-126">[Schema Resolver Component (BizTalk Server Sample)](../core/schema-resolver-component-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-127">機能を拡張する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フラット ファイル逆アセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-127">Demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  

- <span data-ttu-id="cfdf0-128">[XSLT 変換コンポーネント (BizTalk Server サンプル)](../core/xslt-transform-component-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-128">[XSLT Transform Component (BizTalk Server Sample)](../core/xslt-transform-component-biztalk-server-sample.md).</span></span> <span data-ttu-id="cfdf0-129">XSLT を使用して XML メッセージを変換するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cfdf0-129">Demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>
