---
title: パイプライン コンポーネントの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 9b493758-6b0f-4223-94bb-8f077ee735a9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9ba18aed137380f6b3d491ad52cfcee94bf111a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286778"
---
# <a name="types-of-pipeline-components"></a><span data-ttu-id="dda4f-102">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="dda4f-102">Types of Pipeline Components</span></span>
<span data-ttu-id="dda4f-103">3 種類のパイプライン コンポーネントに付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: 全般、アセンブル、および逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="dda4f-103">Three types of pipeline components are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: general, assembling, and disassembling.</span></span> <span data-ttu-id="dda4f-104">3 種類のパイプライン コンポーネントには、いずれもプローブ機能を実装できます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-104">Any of these three types can also implement probing functionality.</span></span> <span data-ttu-id="dda4f-105">このトピックでは、各コンポーネントの概要と、一般的にどのようなステージで使用されるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dda4f-105">This topic describes each type of component and the stages in which each component is generally used.</span></span>  
  
## <a name="general"></a><span data-ttu-id="dda4f-106">全般</span><span class="sxs-lookup"><span data-stu-id="dda4f-106">General</span></span>  
 <span data-ttu-id="dda4f-107">全般コンポーネントは、1 つのメッセージを受け取って、そのメッセージを処理し、0 個または 1 個のメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="dda4f-107">General components take one message, process the message, and produce zero or one message.</span></span>  
  
 <span data-ttu-id="dda4f-108">MIME/SMIME デコーダー、MIME/SMIME エンコーダー、パーティの解決、および検証コンポーネントは、全般コンポーネントに属します。</span><span class="sxs-lookup"><span data-stu-id="dda4f-108">The MIME/SMIME Decoder, MIME/SMIME Encoder, Party Resolution, and Validator components are the included general components.</span></span> <span data-ttu-id="dda4f-109">メッセージを送信する前にメッセージのサイズを圧縮したり、処理対象となる他の情報を待機する間にメッセージを利用したりする場合は、カスタムの全般コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-109">You may need to create custom general components to compress the size of a message before sending, or to consume a message while waiting for additional information to process it.</span></span>  
  
 <span data-ttu-id="dda4f-110">全般コンポーネントは、デコード、エンコード、プリアセンブル、パーティの解決、検証のいずれかのステージに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-110">General components should be placed in the Decode, Encode, Pre-assemble, ResolveParty, or Validate stages.</span></span>  
  
 <span data-ttu-id="dda4f-111">全般パイプライン コンポーネントの開発方法の詳細については、次を参照してください。[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="dda4f-111">For information about developing general pipeline components, see [Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md).</span></span>  
  
## <a name="assembling"></a><span data-ttu-id="dda4f-112">アセンブル</span><span class="sxs-lookup"><span data-stu-id="dda4f-112">Assembling</span></span>  
 <span data-ttu-id="dda4f-113">アセンブラー コンポーネントには、送信メッセージを準備するための、さまざまな役割があります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-113">Assembling components have numerous responsibilities to prepare the message to be sent.</span></span> <span data-ttu-id="dda4f-114">その 1 つに、XML メッセージを、スキーマとして設定されたアセンブラーの種類とプロパティに基づいて、適切なネイティブ形式 (XML または非 XML) に変換する機能があります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-114">First, the component converts the XML message to the appropriate XML or non-XML native format of the message, based on the type of assembler and properties set in the schema.</span></span> <span data-ttu-id="dda4f-115">また、メッセージをエンベロープとしてアセンブルおよびラップする (つまり、ヘッダーやトレーラーをメッセージに付加する) 機能もあります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-115">In addition, assembling components assemble and wrap the message in an envelope, or add a header or trailer (or both) to the message.</span></span> <span data-ttu-id="dda4f-116">アセンブル中、いくつかのプロパティが、メッセージ コンテキストからドキュメント本体またはエンベロープに移動されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-116">During assembly, some properties are moved from the message context to the body of the document or to the envelope.</span></span>  
  
 <span data-ttu-id="dda4f-117">BizTalk Framework アセンブラー、フラット ファイル アセンブラー、および XML アセンブラー コンポーネントは、既定のアセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="dda4f-117">The BizTalk Framework Assembler, Flat File Assembler, and XML Assembler components are the default assembling components.</span></span>  
  
 <span data-ttu-id="dda4f-118">アセンブラー コンポーネントは、送信パイプラインのアセンブル ステージに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-118">Assembling components should be placed in the Assemble stage of send pipelines.</span></span>  
  
 <span data-ttu-id="dda4f-119">アセンブラー パイプライン コンポーネントの開発方法の詳細については、次を参照してください。 [、アセンブル パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="dda4f-119">For information about developing assembling pipeline components, see [Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md).</span></span>  
  
## <a name="disassembling"></a><span data-ttu-id="dda4f-120">逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="dda4f-120">Disassembling</span></span>  
 <span data-ttu-id="dda4f-121">逆アセンブラー コンポーネントは、エンベロープおよびドキュメント スキーマに従って、メッセージを個別のドキュメントに分割し、BizTalk Serverで使用できるようにするための、さまざまな準備作業を行います。</span><span class="sxs-lookup"><span data-stu-id="dda4f-121">Disassembling components complete many tasks to prepare the message to be split up into individual documents according to envelope and document schemas for use within BizTalk Server.</span></span> <span data-ttu-id="dda4f-122">逆アセンブラー コンポーネントは、まず、非 XML 形式のメッセージを、BizTalk Server が認識できる XML 表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="dda4f-122">First, the disassembling component may convert non-XML messages into their XML representation, which is required for processing by BizTalk Server.</span></span> <span data-ttu-id="dda4f-123">次に、このメッセージは、それぞれ別々のオーケストレーションに送信可能な単位へと逆アセンブルされます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-123">Next, the message is disassembled into singular messages that can be sent to separate orchestrations.</span></span> <span data-ttu-id="dda4f-124">メッセージの逆アセンブル時に、エンベロープが取り除かれ、エンベロープおよびメッセージ スキーマに従ってメッセージが個別のドキュメントに分割され、さらに、エンベロープから各メッセージ コンテキストへとプロパティが移動されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-124">The message is disassembled by removing the envelope, splitting the message up into individual documents according to envelope and message schemas, and then moving properties from the envelope to the individual message contexts.</span></span> <span data-ttu-id="dda4f-125">次に、いくつかのプロパティがメッセージの本文からヘッダーへと昇格されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-125">Additionally, some properties may be promoted from the body of the message to the header.</span></span> <span data-ttu-id="dda4f-126">昇格されるプロパティは、スキーマによって決まります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-126">The promoted properties are determined by the schema.</span></span>  
  
 <span data-ttu-id="dda4f-127">逆アセンブラー コンポーネントでは、必ず、メッセージの種類を示すプロパティが設定されます。このプロパティが設定されることによって初めて、メッセージを適切にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-127">The disassembling component must also set the message type property, which is used for routing messages appropriately.</span></span> <span data-ttu-id="dda4f-128">メッセージの種類を示すプロパティとは、メッセージ本文の Namespace#RootElement のことです。</span><span class="sxs-lookup"><span data-stu-id="dda4f-128">The message type property is the Namespace#RootElement of the message body.</span></span> <span data-ttu-id="dda4f-129">コンテンツの種類や文字セットなど、その他のプロパティは、コンテキスト プロパティの一部として設定されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-129">Other properties, such as the content type and character set are set as part of the context property.</span></span>  
  
 <span data-ttu-id="dda4f-130">BizTalk Framework 逆アセンブラー、フラット ファイル逆アセンブラー、および XML 逆アセンブラー コンポーネントは、BizTalk Server の既定の逆アセンブラー コンポーネントになります。</span><span class="sxs-lookup"><span data-stu-id="dda4f-130">The BizTalk Framework Disassembler, Flat File Disassembler, and XML Disassembler components are the default disassembling components included with BizTalk Server.</span></span>  
  
 <span data-ttu-id="dda4f-131">逆アセンブラー コンポーネントは、受信パイプラインの逆アセンブル ステージで使用されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-131">Disassembling components should be used in the Disassemble stage of receive pipelines.</span></span>  
  
 <span data-ttu-id="dda4f-132">逆アセンブラー パイプライン コンポーネントの開発方法の詳細については、次を参照してください。[逆アセンブル パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="dda4f-132">For information about developing disassembling pipeline components, see [Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md).</span></span>  
  
## <a name="probing"></a><span data-ttu-id="dda4f-133">プローブ</span><span class="sxs-lookup"><span data-stu-id="dda4f-133">Probing</span></span>  
 <span data-ttu-id="dda4f-134">プローブ コンポーネントは、メッセージが認識可能な形式になっているかどうかを、メッセージの先頭部分を見ることによってチェックします。</span><span class="sxs-lookup"><span data-stu-id="dda4f-134">A probing component checks the first portion of the message to see if it is in a format that the component understands.</span></span> <span data-ttu-id="dda4f-135">既知の形式であった場合は、メッセージ全体が対応するコンポーネントに渡され、処理されます。</span><span class="sxs-lookup"><span data-stu-id="dda4f-135">If the format is known, the whole message is given to this component for processing.</span></span>  
  
 <span data-ttu-id="dda4f-136">調査の開発については、パイプライン コンポーネントを参照してください[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="dda4f-136">For information about developing probing pipeline components, see [Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda4f-137">参照</span><span class="sxs-lookup"><span data-stu-id="dda4f-137">See Also</span></span>  
 <span data-ttu-id="dda4f-138">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="dda4f-138">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="dda4f-139">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="dda4f-139">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="dda4f-140">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="dda4f-140">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="dda4f-141">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="dda4f-141">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="dda4f-142">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="dda4f-142">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)