---
title: 既定のパイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a49e806bf8d38c7b2018f583e443589065be71a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389711"
---
# <a name="default-pipelines"></a><span data-ttu-id="c5612-102">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="c5612-102">Default Pipelines</span></span>
<span data-ttu-id="c5612-103">ときに既定のパイプラインを作成し、既定で展開新しいアプリケーションを作成し、すべての BizTalk プロジェクトに対して、\References フォルダーの Microsoft.BizTalk.DefaultPipelines アセンブリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5612-103">When you create a new application, the default pipelines are created and deployed by default and appear in the Microsoft.BizTalk.DefaultPipelines assembly in the \References folder for every BizTalk project.</span></span> <span data-ttu-id="c5612-104">パイプライン デザイナーで、既定のパイプラインを変更できません。</span><span class="sxs-lookup"><span data-stu-id="c5612-104">The default pipelines cannot be modified in Pipeline Designer.</span></span> <span data-ttu-id="c5612-105">これらのパイプラインは、送信ポートを構成するときに選択するか、BizTalk エクスプ ローラーで受信場所。</span><span class="sxs-lookup"><span data-stu-id="c5612-105">These pipelines can be selected when configuring a send port or receive location in BizTalk Explorer.</span></span> <span data-ttu-id="c5612-106">このトピックでは、既定のパイプラインとそれらを使用する場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5612-106">This topic describes the default pipelines and when to use them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5612-107">XML 受信パイプラインおよび XML 送信パイプラインは 4 ギガバイトを超える XML ドキュメントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c5612-107">The XML receive and XML send pipelines do not support XML documents larger than 4 gigabytes.</span></span>  
  
## <a name="passthrureceive-pipeline"></a><span data-ttu-id="c5612-108">PassThruReceive パイプライン</span><span class="sxs-lookup"><span data-stu-id="c5612-108">PassThruReceive pipeline</span></span>  
 <span data-ttu-id="c5612-109">パススルー受信パイプラインには、コンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="c5612-109">The pass-through receive pipeline has no components.</span></span> <span data-ttu-id="c5612-110">メッセージ ペイロードの処理が必要ないときに単純なパススルー シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5612-110">It is used for simple pass-through scenarios when no message payload processing is necessary.</span></span> <span data-ttu-id="c5612-111">このパイプラインは通常、ソースと、メッセージの送信先が既知であり、メッセージ エンコーディング、または逆アセンブル、検証は必要ないときに使用します。</span><span class="sxs-lookup"><span data-stu-id="c5612-111">This pipeline is generally used when the source and the destination of the message are known, and the message requires no validation, encoding, or disassembling.</span></span> <span data-ttu-id="c5612-112">このパイプラインは、パススルー送信パイプラインと組み合わせてよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5612-112">This pipeline is commonly used in conjunction with the pass-through send pipeline.</span></span>  
  
 <span data-ttu-id="c5612-113">逆アセンブラーを含まないために、オーケストレーションにメッセージをルーティングするパススルー受信パイプラインを使用できません。</span><span class="sxs-lookup"><span data-stu-id="c5612-113">Because it does not contain a disassembler, the pass-through receive pipeline cannot be used to route messages to orchestrations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5612-114">パススルー受信パイプラインは、プロパティの昇格をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c5612-114">The pass-through receive pipeline does not support property promotion.</span></span>  
  
## <a name="passthrutransmit-pipeline"></a><span data-ttu-id="c5612-115">PassThruTransmit パイプライン</span><span class="sxs-lookup"><span data-stu-id="c5612-115">PassThruTransmit pipeline</span></span>  
 <span data-ttu-id="c5612-116">パススルー送信パイプラインには、コンポーネントがありません。</span><span class="sxs-lookup"><span data-stu-id="c5612-116">The pass-through-send pipeline has no components.</span></span> <span data-ttu-id="c5612-117">このパイプラインは通常、変換先にメッセージを送信する前に必要なドキュメントの処理がないときに使用します。</span><span class="sxs-lookup"><span data-stu-id="c5612-117">This pipeline is generally used when no document processing is necessary before sending the message to a destination.</span></span>  
  
## <a name="xmlreceive-pipeline"></a><span data-ttu-id="c5612-118">XMLReceive パイプライン</span><span class="sxs-lookup"><span data-stu-id="c5612-118">XMLReceive pipeline</span></span>  
 <span data-ttu-id="c5612-119">XML 受信パイプラインは、次のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c5612-119">The XML receive pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="c5612-120">**デコードします。**</span><span class="sxs-lookup"><span data-stu-id="c5612-120">**Decode.**</span></span> <span data-ttu-id="c5612-121">空</span><span class="sxs-lookup"><span data-stu-id="c5612-121">Empty</span></span>  
  
-   <span data-ttu-id="c5612-122">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="c5612-122">**Disassemble.**</span></span> <span data-ttu-id="c5612-123">XML 逆アセンブラー コンポーネントが含まれています</span><span class="sxs-lookup"><span data-stu-id="c5612-123">Contains the XML Disassembler component</span></span>  
  
-   <span data-ttu-id="c5612-124">**検証します。**</span><span class="sxs-lookup"><span data-stu-id="c5612-124">**Validate.**</span></span> <span data-ttu-id="c5612-125">空</span><span class="sxs-lookup"><span data-stu-id="c5612-125">Empty</span></span>  
  
-   <span data-ttu-id="c5612-126">**パーティの解決。**</span><span class="sxs-lookup"><span data-stu-id="c5612-126">**ResolveParty.**</span></span> <span data-ttu-id="c5612-127">証明書のサブジェクトまたは送信元セキュリティ ID をパーティ ID に解決されるパーティの解決コンポーネントを実行します</span><span class="sxs-lookup"><span data-stu-id="c5612-127">Runs the Party Resolution component, which resolves the certificate subject or the source security ID to the party ID.</span></span>  
  
## <a name="xmltransmit-pipeline"></a><span data-ttu-id="c5612-128">XMLTransmit パイプライン</span><span class="sxs-lookup"><span data-stu-id="c5612-128">XMLTransmit pipeline</span></span>  
 <span data-ttu-id="c5612-129">XML 送信パイプラインは、次のステージで構成されます。</span><span class="sxs-lookup"><span data-stu-id="c5612-129">The XML send pipeline consists of the following stages:</span></span>  
  
-   <span data-ttu-id="c5612-130">**プリアセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="c5612-130">**Pre-assemble.**</span></span> <span data-ttu-id="c5612-131">空</span><span class="sxs-lookup"><span data-stu-id="c5612-131">Empty</span></span>  
  
-   <span data-ttu-id="c5612-132">**アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="c5612-132">**Assemble.**</span></span> <span data-ttu-id="c5612-133">XML アセンブラー コンポーネントが含まれています</span><span class="sxs-lookup"><span data-stu-id="c5612-133">Contains the XML Assembler component</span></span>  
  
-   <span data-ttu-id="c5612-134">**エンコードします。**</span><span class="sxs-lookup"><span data-stu-id="c5612-134">**Encode.**</span></span> <span data-ttu-id="c5612-135">空</span><span class="sxs-lookup"><span data-stu-id="c5612-135">Empty</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5612-136">参照</span><span class="sxs-lookup"><span data-stu-id="c5612-136">See Also</span></span>  
 <span data-ttu-id="c5612-137">[パイプラインの種類](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="c5612-137">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="c5612-138">[パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c5612-138">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="c5612-139">[パイプライン テンプレート](../core/pipeline-templates.md) </span><span class="sxs-lookup"><span data-stu-id="c5612-139">[Pipeline Templates](../core/pipeline-templates.md) </span></span>  
 <span data-ttu-id="c5612-140">[パイプライン コンポーネント](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="c5612-140">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="c5612-141">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="c5612-141">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)