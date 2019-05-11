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
ms.openlocfilehash: a183aa499b5acb56813fcb0433d2fd57258a777d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324839"
---
# <a name="microsoftbiztalkdefaultpipelines-reference"></a><span data-ttu-id="8413c-102">Microsoft.BizTalk.DefaultPipelines の参照</span><span class="sxs-lookup"><span data-stu-id="8413c-102">Microsoft.BizTalk.DefaultPipelines Reference</span></span>
<span data-ttu-id="8413c-103">**Microsoft.BizTalk.DefaultPipelines**名前空間には、次のパイプラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8413c-103">The **Microsoft.BizTalk.DefaultPipelines** namespace contains the following pipelines:</span></span>  
  
- <span data-ttu-id="8413c-104">[Xmlreceive]</span><span class="sxs-lookup"><span data-stu-id="8413c-104">XMLReceive</span></span>  
  
- <span data-ttu-id="8413c-105">PassThruReceive</span><span class="sxs-lookup"><span data-stu-id="8413c-105">PassThruReceive</span></span>  
  
- <span data-ttu-id="8413c-106">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="8413c-106">XMLTransmit</span></span>  
  
- <span data-ttu-id="8413c-107">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="8413c-107">PassThruTransmit</span></span>  
  
  <span data-ttu-id="8413c-108">パイプラインを定義し、受信または送信されたメッセージの処理の 1 つ以上のステージをリンクするソフトウェア コンポーネントとは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8413c-108">A pipeline is a software component that defines and links one or more stages for processing messages received or sent by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8413c-109">各ステージには、エンコードまたはデコード、逆アセンブルまたはアセンブル、および復号化または暗号化などの関数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8413c-109">The stages include functions such as encoding or decoding, disassembling or assembling, and decrypting or encrypting.</span></span> <span data-ttu-id="8413c-110">これらの関数は、特定の順序で実装されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-110">These functions are implemented in a specific order.</span></span> <span data-ttu-id="8413c-111">パイプライン デザイナーを使用して、作成する受信パイプラインと送信されます。</span><span class="sxs-lookup"><span data-stu-id="8413c-111">You can use Pipeline Designer to create receive and send pipelines.</span></span>  
  
  <span data-ttu-id="8413c-112">BizTalk プロジェクトに含まれる既定のパイプライン参照を使用してドキュメントのすべての種類を処理できる、 **PassThruReceive**と**PassThruTransmit**パイプライン。</span><span class="sxs-lookup"><span data-stu-id="8413c-112">The default pipeline references included in a BizTalk project can process all types of documents using the **PassThruReceive** and **PassThruTransmit** pipelines.</span></span>  
  
  <span data-ttu-id="8413c-113">次の表は、既定のパイプラインの既定のコンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="8413c-113">The following lists show the default components in the default pipelines.</span></span> <span data-ttu-id="8413c-114">これらのリストには、各パイプラインにおけるコンポーネントの既定の順序も示します。</span><span class="sxs-lookup"><span data-stu-id="8413c-114">These lists also indicate the default order of the components in each pipeline.</span></span> <span data-ttu-id="8413c-115">追加し、必要に応じて、コンポーネントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="8413c-115">You can add and delete components if necessary.</span></span>  
  
  <span data-ttu-id="8413c-116">既定の XMLReceive パイプラインに既定のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8413c-116">The default components in the default XMLReceive pipeline are:</span></span>  
  
- <span data-ttu-id="8413c-117">復号化</span><span class="sxs-lookup"><span data-stu-id="8413c-117">Decrypter</span></span>  
  
- <span data-ttu-id="8413c-118">デコーダー</span><span class="sxs-lookup"><span data-stu-id="8413c-118">Decoder</span></span>  
  
- <span data-ttu-id="8413c-119">逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="8413c-119">Disassembler</span></span>  
  
- <span data-ttu-id="8413c-120">検証ツール</span><span class="sxs-lookup"><span data-stu-id="8413c-120">Validator</span></span>  
  
- <span data-ttu-id="8413c-121">パーティの解決</span><span class="sxs-lookup"><span data-stu-id="8413c-121">Party Resolution</span></span>  
  
  <span data-ttu-id="8413c-122">既定の XMLTransmit パイプラインで既定のコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8413c-122">The default components in the default XMLTransmit pipeline are:</span></span>  
  
- <span data-ttu-id="8413c-123">アセンブラー</span><span class="sxs-lookup"><span data-stu-id="8413c-123">Assembler</span></span>  
  
- <span data-ttu-id="8413c-124">エンコーダー</span><span class="sxs-lookup"><span data-stu-id="8413c-124">Encoder</span></span>  
  
- <span data-ttu-id="8413c-125">盗み見</span><span class="sxs-lookup"><span data-stu-id="8413c-125">Encrypter</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8413c-126">参照</span><span class="sxs-lookup"><span data-stu-id="8413c-126">See Also</span></span>  
 <span data-ttu-id="8413c-127">[パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8413c-127">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="8413c-128">BizTalk プロジェクト内の BizTalk 名前空間参照について</span><span class="sxs-lookup"><span data-stu-id="8413c-128">About BizTalk Namespace References Included in BizTalk Projects</span></span>](../core/about-biztalk-namespace-references-included-in-biztalk-projects.md)