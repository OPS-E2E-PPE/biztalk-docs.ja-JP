---
title: "既定のパイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, PassThruTransmit
- pipelines, PassThruReceive
- pipelines, XMLTransmit
- pipelines, StsReceive
- pipelines, StsSend
- pipelines, StsFileReceive
- Microsoft.BizTalk.KwTpm.StsDefaultPipelines.EnvSchema XML envelope
- pipelines, XMLReceive
- pipelines, backward compatibility
- Microsoft.BizTalk.DefaultPipelines assembly
- pipelines, default
ms.assetid: 7d82bb2c-c7f1-44a1-9e1b-89b0bb806845
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ceb3f06f2e2b57ec37bc4a95a385574de594940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="default-pipelines"></a><span data-ttu-id="830e5-102">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="830e5-102">Default Pipelines</span></span>
<span data-ttu-id="830e5-103">新しいアプリケーションを作成すると、既定のパイプラインが作成および展開され、各 BizTalk プロジェクトに対して、\References フォルダーの Microsoft.BizTalk.DefaultPipelines アセンブリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-103">When you create a new application, the default pipelines are created and deployed by default and appear in the Microsoft.BizTalk.DefaultPipelines assembly in the \References folder for every BizTalk project.</span></span> <span data-ttu-id="830e5-104">パイプライン デザイナーでは、既定のパイプラインを変更できません。</span><span class="sxs-lookup"><span data-stu-id="830e5-104">The default pipelines cannot be modified in Pipeline Designer.</span></span> <span data-ttu-id="830e5-105">これらのパイプラインは、送信ポートまたは受信場所を BizTalk エクスプローラーで構成するときに選択できます。</span><span class="sxs-lookup"><span data-stu-id="830e5-105">These pipelines can be selected when configuring a send port or receive location in BizTalk Explorer.</span></span> <span data-ttu-id="830e5-106">ここでは、既定のパイプラインの概要および使用時期について説明します。</span><span class="sxs-lookup"><span data-stu-id="830e5-106">This topic describes the default pipelines and when to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="830e5-107">XML 受信パイプラインおよび送信パイプラインは、4 GB を超える XML ドキュメントをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="830e5-107">The XML receive and XML send pipelines do not support XML documents larger than 4 gigabytes.</span></span>  
  
## <a name="passthrureceive-pipeline"></a><span data-ttu-id="830e5-108">PassThruReceive パイプライン</span><span class="sxs-lookup"><span data-stu-id="830e5-108">PassThruReceive pipeline</span></span>  
 <span data-ttu-id="830e5-109">パススルー受信パイプラインはコンポーネントを持っていません。</span><span class="sxs-lookup"><span data-stu-id="830e5-109">The pass-through receive pipeline has no components.</span></span> <span data-ttu-id="830e5-110">このパイプラインは、メッセージ ペイロード処理を必要としないシンプル パススルー シナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-110">It is used for simple pass-through scenarios when no message payload processing is necessary.</span></span> <span data-ttu-id="830e5-111">一般に、メッセージの送信元と送信先が既知であり、メッセージが検証、エンコーディング、または逆アセンブルを必要としない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-111">This pipeline is generally used when the source and the destination of the message are known, and the message requires no validation, encoding, or disassembling.</span></span> <span data-ttu-id="830e5-112">通常は、パススルー送信パイプラインと一緒に使用されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-112">This pipeline is commonly used in conjunction with the pass-through send pipeline.</span></span>  
  
 <span data-ttu-id="830e5-113">パススルー受信パイプラインには逆アセンブラーが含まれていないので、メッセージのオーケストレーションへのルーティングに使用できません。</span><span class="sxs-lookup"><span data-stu-id="830e5-113">Because it does not contain a disassembler, the pass-through receive pipeline cannot be used to route messages to orchestrations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="830e5-114">パススルー受信パイプラインは、プロパティの昇格をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="830e5-114">The pass-through receive pipeline does not support property promotion.</span></span>  
  
## <a name="passthrutransmit-pipeline"></a><span data-ttu-id="830e5-115">PassThruTransmit パイプライン</span><span class="sxs-lookup"><span data-stu-id="830e5-115">PassThruTransmit pipeline</span></span>  
 <span data-ttu-id="830e5-116">パススルー送信パイプラインはコンポーネントを持っていません。</span><span class="sxs-lookup"><span data-stu-id="830e5-116">The pass-through-send pipeline has no components.</span></span> <span data-ttu-id="830e5-117">このパイプラインは、一般に、メッセージを送信先に送信する前のドキュメント処理を必要としない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-117">This pipeline is generally used when no document processing is necessary before sending the message to a destination.</span></span>  
  
## <a name="xmlreceive-pipeline"></a><span data-ttu-id="830e5-118">XMLReceive パイプライン</span><span class="sxs-lookup"><span data-stu-id="830e5-118">XMLReceive pipeline</span></span>  
 <span data-ttu-id="830e5-119">XML 受信パイプラインは、次のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-119">The XML receive pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="830e5-120">**デコードします。**</span><span class="sxs-lookup"><span data-stu-id="830e5-120">**Decode.**</span></span> <span data-ttu-id="830e5-121">空</span><span class="sxs-lookup"><span data-stu-id="830e5-121">Empty</span></span>  
  
-   <span data-ttu-id="830e5-122">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="830e5-122">**Disassemble.**</span></span> <span data-ttu-id="830e5-123">XML 逆アセンブラー コンポーネントを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="830e5-123">Contains the XML Disassembler component</span></span>  
  
-   <span data-ttu-id="830e5-124">**検証します。**</span><span class="sxs-lookup"><span data-stu-id="830e5-124">**Validate.**</span></span> <span data-ttu-id="830e5-125">空</span><span class="sxs-lookup"><span data-stu-id="830e5-125">Empty</span></span>  
  
-   <span data-ttu-id="830e5-126">**パーティの解決。**</span><span class="sxs-lookup"><span data-stu-id="830e5-126">**ResolveParty.**</span></span> <span data-ttu-id="830e5-127">証明書サブジェクトまたは送信元セキュリティ ID をパーティ ID に解決する、パーティの解決パイプライン コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="830e5-127">Runs the Party Resolution component, which resolves the certificate subject or the source security ID to the party ID.</span></span>  
  
## <a name="xmltransmit-pipeline"></a><span data-ttu-id="830e5-128">XMLTransmit パイプライン</span><span class="sxs-lookup"><span data-stu-id="830e5-128">XMLTransmit pipeline</span></span>  
 <span data-ttu-id="830e5-129">XML 送信パイプラインは、次のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="830e5-129">The XML send pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="830e5-130">**プリアセンブルです。**</span><span class="sxs-lookup"><span data-stu-id="830e5-130">**Pre-assemble.**</span></span> <span data-ttu-id="830e5-131">空</span><span class="sxs-lookup"><span data-stu-id="830e5-131">Empty</span></span>  
  
-   <span data-ttu-id="830e5-132">**編成します。**</span><span class="sxs-lookup"><span data-stu-id="830e5-132">**Assemble.**</span></span> <span data-ttu-id="830e5-133">XML アセンブラー コンポーネントを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="830e5-133">Contains the XML Assembler component</span></span>  
  
-   <span data-ttu-id="830e5-134">**エンコードします。**</span><span class="sxs-lookup"><span data-stu-id="830e5-134">**Encode.**</span></span> <span data-ttu-id="830e5-135">空</span><span class="sxs-lookup"><span data-stu-id="830e5-135">Empty</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830e5-136">参照</span><span class="sxs-lookup"><span data-stu-id="830e5-136">See Also</span></span>  
 <span data-ttu-id="830e5-137">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="830e5-137">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="830e5-138">[パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="830e5-138">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="830e5-139">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="830e5-139">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="830e5-140">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="830e5-140">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="830e5-141">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="830e5-141">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)