---
title: パイプライン コンポーネントの種類 |Microsoft Docs
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
ms.openlocfilehash: c6b8ad31d2e135aec1283b5057e6b39de45ad422
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379921"
---
# <a name="types-of-pipeline-components"></a><span data-ttu-id="f24b7-102">パイプライン コンポーネントの種類</span><span class="sxs-lookup"><span data-stu-id="f24b7-102">Types of Pipeline Components</span></span>
<span data-ttu-id="f24b7-103">3 種類のパイプライン コンポーネントが付属[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: 全般、アセンブル、および逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="f24b7-103">Three types of pipeline components are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]: general, assembling, and disassembling.</span></span> <span data-ttu-id="f24b7-104">プローブ機能を実装これら 3 種類のいずれかのこともできます。</span><span class="sxs-lookup"><span data-stu-id="f24b7-104">Any of these three types can also implement probing functionality.</span></span> <span data-ttu-id="f24b7-105">このトピックでは、コンポーネントと各コンポーネントが一般的に使用されているステージの各型について説明します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-105">This topic describes each type of component and the stages in which each component is generally used.</span></span>  
  
## <a name="general"></a><span data-ttu-id="f24b7-106">全般</span><span class="sxs-lookup"><span data-stu-id="f24b7-106">General</span></span>  
 <span data-ttu-id="f24b7-107">全般コンポーネント 1 つのメッセージを取得するには、メッセージを処理および 0 個または 1 つのメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-107">General components take one message, process the message, and produce zero or one message.</span></span>  
  
 <span data-ttu-id="f24b7-108">MIME/SMIME デコーダー、MIME/SMIME エンコーダー、パーティの解決、および検証コンポーネントは、含まれる一般的なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f24b7-108">The MIME/SMIME Decoder, MIME/SMIME Encoder, Party Resolution, and Validator components are the included general components.</span></span> <span data-ttu-id="f24b7-109">送信する前に、メッセージのサイズを圧縮するか、それを処理する追加情報を待機中にメッセージを使用するカスタムの一般的なコンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-109">You may need to create custom general components to compress the size of a message before sending, or to consume a message while waiting for additional information to process it.</span></span>  
  
 <span data-ttu-id="f24b7-110">全般コンポーネントにする必要があります、デコード、配置のエンコード、プリアセンブル、パーティの解決、または段階を検証します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-110">General components should be placed in the Decode, Encode, Pre-assemble, ResolveParty, or Validate stages.</span></span>  
  
 <span data-ttu-id="f24b7-111">全般パイプライン コンポーネントの開発方法の詳細については、次を参照してください。[全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-111">For information about developing general pipeline components, see [Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md).</span></span>  
  
## <a name="assembling"></a><span data-ttu-id="f24b7-112">アセンブル</span><span class="sxs-lookup"><span data-stu-id="f24b7-112">Assembling</span></span>  
 <span data-ttu-id="f24b7-113">アセンブラー コンポーネントでは、送信されるメッセージを準備するさまざまな役割があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-113">Assembling components have numerous responsibilities to prepare the message to be sent.</span></span> <span data-ttu-id="f24b7-114">最初に、コンポーネントは、アセンブラーとスキーマの設定のプロパティの種類に基づいて、メッセージの適切な XML インデックスまたは非 XML ネイティブ形式を XML メッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-114">First, the component converts the XML message to the appropriate XML or non-XML native format of the message, based on the type of assembler and properties set in the schema.</span></span> <span data-ttu-id="f24b7-115">さらに、アセンブラー コンポーネント、アセンブルしたり、メッセージをエンベロープにラップし、メッセージにヘッダーまたはトレーラー (またはその両方) を追加またはします。</span><span class="sxs-lookup"><span data-stu-id="f24b7-115">In addition, assembling components assemble and wrap the message in an envelope, or add a header or trailer (or both) to the message.</span></span> <span data-ttu-id="f24b7-116">アセンブリの中にいくつかのプロパティは、ドキュメントの本文に、またはエンベロープにメッセージ コンテキストから移動されます。</span><span class="sxs-lookup"><span data-stu-id="f24b7-116">During assembly, some properties are moved from the message context to the body of the document or to the envelope.</span></span>  
  
 <span data-ttu-id="f24b7-117">BizTalk Framework アセンブラー、フラット ファイル アセンブラー、および XML アセンブラー コンポーネントは、既定のアセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f24b7-117">The BizTalk Framework Assembler, Flat File Assembler, and XML Assembler components are the default assembling components.</span></span>  
  
 <span data-ttu-id="f24b7-118">アセンブラー コンポーネントは、送信パイプラインのアセンブル ステージに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-118">Assembling components should be placed in the Assemble stage of send pipelines.</span></span>  
  
 <span data-ttu-id="f24b7-119">アセンブラー パイプライン コンポーネントの開発方法の詳細については、次を参照してください。[アセンブル パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-119">For information about developing assembling pipeline components, see [Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md).</span></span>  
  
## <a name="disassembling"></a><span data-ttu-id="f24b7-120">逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="f24b7-120">Disassembling</span></span>  
 <span data-ttu-id="f24b7-121">逆アセンブラー コンポーネントは、メッセージをエンベロープに従って個別のドキュメントに分割することを準備する多くのタスクを完了し、BizTalk Server 内のドキュメント スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-121">Disassembling components complete many tasks to prepare the message to be split up into individual documents according to envelope and document schemas for use within BizTalk Server.</span></span> <span data-ttu-id="f24b7-122">最初に、逆アセンブラー コンポーネントは、BizTalk Server で処理するために必要なは、その XML 表現に XML 以外のメッセージを変換することがあります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-122">First, the disassembling component may convert non-XML messages into their XML representation, which is required for processing by BizTalk Server.</span></span> <span data-ttu-id="f24b7-123">次に、メッセージは個別のオーケストレーションに送信できる単一のメッセージに逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="f24b7-123">Next, the message is disassembled into singular messages that can be sent to separate orchestrations.</span></span> <span data-ttu-id="f24b7-124">メッセージは、エンベロープを削除するメッセージをエンベロープおよびメッセージのスキーマに従って個別のドキュメントに分割、エンベロープからプロパティを個別のメッセージ コンテキストに移動して逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="f24b7-124">The message is disassembled by removing the envelope, splitting the message up into individual documents according to envelope and message schemas, and then moving properties from the envelope to the individual message contexts.</span></span> <span data-ttu-id="f24b7-125">さらに、いくつかのプロパティは、ヘッダーに、メッセージの本文から昇格させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-125">Additionally, some properties may be promoted from the body of the message to the header.</span></span> <span data-ttu-id="f24b7-126">昇格させたプロパティは、スキーマによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="f24b7-126">The promoted properties are determined by the schema.</span></span>  
  
 <span data-ttu-id="f24b7-127">逆アセンブラー コンポーネントは、メッセージのルーティングを適切に使用されるメッセージ型のプロパティを設定も必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-127">The disassembling component must also set the message type property, which is used for routing messages appropriately.</span></span> <span data-ttu-id="f24b7-128">メッセージの種類プロパティは、メッセージ本文の Namespace #RootElement です。</span><span class="sxs-lookup"><span data-stu-id="f24b7-128">The message type property is the Namespace#RootElement of the message body.</span></span> <span data-ttu-id="f24b7-129">コンテンツの種類と文字セットなどの他のプロパティは、コンテキスト プロパティの一部として設定されます。</span><span class="sxs-lookup"><span data-stu-id="f24b7-129">Other properties, such as the content type and character set are set as part of the context property.</span></span>  
  
 <span data-ttu-id="f24b7-130">BizTalk Framework 逆アセンブラー、フラット ファイル逆アセンブラー、および XML 逆アセンブラー コンポーネントは、逆アセンブラー コンポーネントが BizTalk Server に含まれている既定値です。</span><span class="sxs-lookup"><span data-stu-id="f24b7-130">The BizTalk Framework Disassembler, Flat File Disassembler, and XML Disassembler components are the default disassembling components included with BizTalk Server.</span></span>  
  
 <span data-ttu-id="f24b7-131">逆アセンブラー コンポーネントは、受信パイプラインの逆アセンブル ステージで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f24b7-131">Disassembling components should be used in the Disassemble stage of receive pipelines.</span></span>  
  
 <span data-ttu-id="f24b7-132">逆アセンブラー パイプライン コンポーネントの開発方法の詳細については、次を参照してください。[逆アセンブル パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-132">For information about developing disassembling pipeline components, see [Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md).</span></span>  
  
## <a name="probing"></a><span data-ttu-id="f24b7-133">プローブ</span><span class="sxs-lookup"><span data-stu-id="f24b7-133">Probing</span></span>  
 <span data-ttu-id="f24b7-134">プローブ コンポーネントは、コンポーネントで認識される形式であるかを確認するメッセージの最初の部分を確認します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-134">A probing component checks the first portion of the message to see if it is in a format that the component understands.</span></span> <span data-ttu-id="f24b7-135">形式がわかっている場合は、メッセージ全体が処理するためには、このコンポーネントに付与されます。</span><span class="sxs-lookup"><span data-stu-id="f24b7-135">If the format is known, the whole message is given to this component for processing.</span></span>  
  
 <span data-ttu-id="f24b7-136">プローブの開発については、パイプライン コンポーネントを参照してください[プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="f24b7-136">For information about developing probing pipeline components, see [Developing a Probing Pipeline Component](../core/developing-a-probing-pipeline-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f24b7-137">参照</span><span class="sxs-lookup"><span data-stu-id="f24b7-137">See Also</span></span>  
 <span data-ttu-id="f24b7-138">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="f24b7-138">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="f24b7-139">[既定のパイプライン](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="f24b7-139">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="f24b7-140">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="f24b7-140">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="f24b7-141">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="f24b7-141">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="f24b7-142">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="f24b7-142">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)