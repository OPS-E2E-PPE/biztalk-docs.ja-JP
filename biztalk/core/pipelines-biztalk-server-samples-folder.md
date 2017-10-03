---
title: "パイプライン (BizTalk Server Samples フォルダ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- SDK examples
- examples, pipelines
ms.assetid: d1b6d984-ac0d-4149-99fd-93d3b6ed316c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ec02e774255a9574301a0a59f33fb989b8d0f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="pipelines-biztalk-server-samples-folder"></a><span data-ttu-id="1ccc5-102">パイプライン (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1ccc5-102">Pipelines (BizTalk Server Samples Folder)</span></span>
<span data-ttu-id="1ccc5-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のソフトウェア開発キット (SDK) には、パイプラインのサンプルがいくつか付属しています。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes several pipeline samples in its software development kit (SDK).</span></span> <span data-ttu-id="1ccc5-104">このセクションでは、各パイプライン サンプルが示す機能、サンプルをビルドして実行する方法、および予測される実行結果について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-104">This section provides detailed information about the functionality that each pipeline sample demonstrates, instructions for building and running the sample, and the results you can expect.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ccc5-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ccc5-105">In This Section</span></span>  
  
-   <span data-ttu-id="1ccc5-106">[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-106">[Aggregator (BizTalk Server Sample)](../core/aggregator-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-107">オーケストレーションとパイプラインを使用したメッセージ集計機能を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-107">Demonstrates message aggregation functionality using orchestrations and pipelines.</span></span>  
  
-   <span data-ttu-id="1ccc5-108">[任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)](../core/arbitrary-xpath-property-handler-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-108">[Arbitrary XPath Property Handler (BizTalk Server Sample)](../core/arbitrary-xpath-property-handler-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-109">BizTalk Server に送信される XML ドキュメント上で特定のプロパティを昇格させるためのカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-109">Demonstrates how to write a custom pipeline component to promote specific properties on an XML document submitted to BizTalk Server.</span></span> <span data-ttu-id="1ccc5-110">プロパティの昇格は、XPath 式を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-110">Property promotion is accomplished using an XPath expression.</span></span>  
  
-   [<span data-ttu-id="1ccc5-111">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1ccc5-111">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)  
  
    -   <span data-ttu-id="1ccc5-112">[FlatFileReceive (BizTalk Server サンプル)](../core/flatfilereceive-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-112">[FlatFileReceive (BizTalk Server Sample)](../core/flatfilereceive-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-113">BizTalk Server パイプラインを使用して、区切りフラット ファイル メッセージを同等の XML メッセージに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-113">Demonstrates how to process delimited flat file messages into the equivalent XML messages using BizTalk Server pipelines.</span></span>  
  
    -   <span data-ttu-id="1ccc5-114">[EnvelopeProcessing (BizTalk Server サンプル)](../core/envelopeprocessing-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-114">[EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-115">BizTalk Server パイプラインを使用して、フラット ファイル メッセージをエンベロープ付きの XML メッセージに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-115">Demonstrates how to process flat file messages into XML messages with envelopes using BizTalk Server pipelines.</span></span>  
  
    -   <span data-ttu-id="1ccc5-116">[FlatFileSend (BizTalk Server サンプル)](../core/flatfilesend-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-116">[FlatFileSend (BizTalk Server Sample)](../core/flatfilesend-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-117">BizTalk Server パイプラインを使用して、XML メッセージを同等の位置指定フラット ファイル メッセージに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-117">Demonstrates how to process XML messages into the equivalent positional flat file messages using BizTalk Server pipelines.</span></span>  
  
-   <span data-ttu-id="1ccc5-118">[メッセージ プロセッサ (BizTalk Server サンプル) で構成される](../core/composed-message-processor-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-118">[Composed Message Processor (BizTalk Server Sample)](../core/composed-message-processor-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-119">構成済みメッセージ処理を使用して集計したメッセージからの個別のアイテムを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-119">Demonstrates how to process individual line items from aggregated messages using composed message processing.</span></span>  
  
-   <span data-ttu-id="1ccc5-120">[CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-120">[CustomComponent (BizTalk Server Sample)](../core/customcomponent-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-121">ストリーム送信されたメッセージを変更するカスタム パイプライン コンポーネントを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-121">Demonstrates how to create and use a custom pipeline component that modifies a streamed message.</span></span>  
  
-   <span data-ttu-id="1ccc5-122">[カスタム パーティの解決 (BizTalk Server サンプル)](../core/custom-party-resolution-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-122">[Custom Party Resolution (BizTalk Server Sample)](../core/custom-party-resolution-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-123">カスタム パーティを解決するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-123">Demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  
  
-   <span data-ttu-id="1ccc5-124">[MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-124">[MIME (BizTalk Server Sample)](../core/mime-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-125">BizTalk パイプラインを使用してメッセージを MIME でエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-125">Demonstrates how messages can be MIME-encoded using BizTalk pipelines.</span></span>  
  
-   <span data-ttu-id="1ccc5-126">[スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)](../core/schema-resolver-component-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-126">[Schema Resolver Component (BizTalk Server Sample)](../core/schema-resolver-component-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] フラット ファイル逆アセンブラ コンポーネントの機能を拡張する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-127">Demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  
  
-   <span data-ttu-id="1ccc5-128">[XSLT 変換コンポーネント (BizTalk Server サンプル)](../core/xslt-transform-component-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-128">[XSLT Transform Component (BizTalk Server Sample)](../core/xslt-transform-component-biztalk-server-sample.md).</span></span> <span data-ttu-id="1ccc5-129">XSLT を使用して XML メッセージを変換するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ccc5-129">Demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>