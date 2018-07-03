---
title: Microsoft.BizTalk.DefaultPipelines の参照 |Microsoft Docs
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
- pipelines
- PassThruTransmit pipelines
- XMLReceive pipelines
- pipelines, XMLTransmit
- Pipeline Designer
- pipelines, XMLReceive
- pipelines, about pipelines
- PassThruReceive pipelines
- XMLTransmit pipelines
- namespaces, Microsoft.BizTalk.DefaultPipelines namespace
- Microsoft.BizTalk.DefaultPipelines namespace
ms.assetid: a54f8813-9c6f-4afe-8c76-2db3fa478947
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de2ec54b34a4e6d92f471db7fe9ad5dbc7933014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022056"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a><span data-ttu-id="b240e-102">Microsoft.BizTalk.DefaultPipelines の参照</span><span class="sxs-lookup"><span data-stu-id="b240e-102">Microsoft.BizTalk.DefaultPipelines Reference</span></span>
<span data-ttu-id="b240e-103">**Microsoft.BizTalk.DefaultPipelines**名前空間には、次のパイプラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b240e-103">The **Microsoft.BizTalk.DefaultPipelines** namespace contains the following pipelines:</span></span>  
  
- <span data-ttu-id="b240e-104">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="b240e-104">XMLReceive</span></span>  
  
- <span data-ttu-id="b240e-105">PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="b240e-105">PassThruReceive</span></span>  
  
- <span data-ttu-id="b240e-106">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="b240e-106">XMLTransmit</span></span>  
  
- <span data-ttu-id="b240e-107">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="b240e-107">PassThruTransmit</span></span>  
  
  <span data-ttu-id="b240e-108">パイプラインとは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送受信されるメッセージを処理するために 1 つ以上のステージを定義およびリンクする、ソフトウェア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b240e-108">A pipeline is a software component that defines and links one or more stages for processing messages received or sent by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b240e-109">ステージは、エンコードやデコード、アセンブルや逆アセンブル、暗号化や復号化などの機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="b240e-109">The stages include functions such as encoding or decoding, disassembling or assembling, and decrypting or encrypting.</span></span> <span data-ttu-id="b240e-110">これらの機能は、特定の順序で実装されます。</span><span class="sxs-lookup"><span data-stu-id="b240e-110">These functions are implemented in a specific order.</span></span> <span data-ttu-id="b240e-111">パイプライン デザイナーを使用して、受信および送信パイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b240e-111">You can use Pipeline Designer to create receive and send pipelines.</span></span>  
  
  <span data-ttu-id="b240e-112">BizTalk プロジェクトに含まれる既定のパイプライン参照を使用してドキュメントのすべての種類を処理できる、 **PassThruReceive**と**PassThruTransmit**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="b240e-112">The default pipeline references included in a BizTalk project can process all types of documents using the **PassThruReceive** and **PassThruTransmit** pipelines.</span></span>  
  
  <span data-ttu-id="b240e-113">既定のパイプラインに含まれる既定のコンポーネントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b240e-113">The following lists show the default components in the default pipelines.</span></span> <span data-ttu-id="b240e-114">これらは、各パイプラインにおけるコンポーネントの既定の順序も示しています。</span><span class="sxs-lookup"><span data-stu-id="b240e-114">These lists also indicate the default order of the components in each pipeline.</span></span> <span data-ttu-id="b240e-115">コンポーネントは必要に応じて追加したり削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="b240e-115">You can add and delete components if necessary.</span></span>  
  
  <span data-ttu-id="b240e-116">既定の XMLReceive パイプラインに含まれる既定のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b240e-116">The default components in the default XMLReceive pipeline are:</span></span>  
  
- <span data-ttu-id="b240e-117">復号化</span><span class="sxs-lookup"><span data-stu-id="b240e-117">Decrypter</span></span>  
  
- <span data-ttu-id="b240e-118">デコーダー</span><span class="sxs-lookup"><span data-stu-id="b240e-118">Decoder</span></span>  
  
- <span data-ttu-id="b240e-119">逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="b240e-119">Disassembler</span></span>  
  
- <span data-ttu-id="b240e-120">検証ツール</span><span class="sxs-lookup"><span data-stu-id="b240e-120">Validator</span></span>  
  
- <span data-ttu-id="b240e-121">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="b240e-121">Party Resolution</span></span>  
  
  <span data-ttu-id="b240e-122">既定の XMLTransmit パイプラインに含まれる既定のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b240e-122">The default components in the default XMLTransmit pipeline are:</span></span>  
  
- <span data-ttu-id="b240e-123">アセンブラー</span><span class="sxs-lookup"><span data-stu-id="b240e-123">Assembler</span></span>  
  
- <span data-ttu-id="b240e-124">エンコーダー</span><span class="sxs-lookup"><span data-stu-id="b240e-124">Encoder</span></span>  
  
- <span data-ttu-id="b240e-125">暗号化</span><span class="sxs-lookup"><span data-stu-id="b240e-125">Encrypter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b240e-126">参照</span><span class="sxs-lookup"><span data-stu-id="b240e-126">See Also</span></span>  
 <span data-ttu-id="b240e-127">[パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b240e-127">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="b240e-128">BizTalk プロジェクト内の BizTalk 名前空間参照について</span><span class="sxs-lookup"><span data-stu-id="b240e-128">About BizTalk Namespace References Included in BizTalk Projects</span></span>](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)