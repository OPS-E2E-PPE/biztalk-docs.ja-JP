---
title: パイプライン デザイナーを使用してパイプラインを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b693a4e8df20a7f39f81fb820810c1191ef637
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238050"
---
# <a name="creating-pipelines-using-pipeline-designer"></a><span data-ttu-id="852c1-102">パイプライン デザイナーを使用してパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="852c1-102">Creating Pipelines Using Pipeline Designer</span></span>
<span data-ttu-id="852c1-103">Microsoft BizTalk Server は、主に XML ドキュメント形式を処理します。</span><span class="sxs-lookup"><span data-stu-id="852c1-103">Microsoft BizTalk Server works mainly with the XML document format.</span></span> <span data-ttu-id="852c1-104">BizTalk Server の機能を最大限に活用してメッセージを処理するには、多くの場合、ネイティブ形式から XML 表現へ変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="852c1-104">For a message to take full advantage of BizTalk Server processing, it must often be transformed from its native format into its XML representation.</span></span> <span data-ttu-id="852c1-105">BizTalk Server パイプラインでは、受信メッセージおよび送信メッセージに対して、データの暗号化や復号化、プロパティの昇格などのデータ自身に対する操作だけでなく、ネイティブ形式から XML 表現への変換といったメッセージ変換も行います。</span><span class="sxs-lookup"><span data-stu-id="852c1-105">BizTalk Server pipelines perform this transformation, as well as other data-specific actions (such as data encryption or decryption, property promotion, and so on) on incoming and outgoing messages.</span></span> <span data-ttu-id="852c1-106">このセクションでは、パイプラインおよびパイプライン デザイナーに関する概要とタスク固有の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="852c1-106">This section provides conceptual and task-specific information about pipelines and Pipeline Designer.</span></span>  
  
 <span data-ttu-id="852c1-107">パイプラインは、アダプターで受信したメッセージをサーバーで処理するための準備をしたり、サーバーで処理したメッセージを送信するための準備をする役割を担っています。</span><span class="sxs-lookup"><span data-stu-id="852c1-107">The purpose of a pipeline is to prepare a message for processing by the server after being received by an adapter or to prepare a message for sending after being processed by the server.</span></span>  
  
 <span data-ttu-id="852c1-108">通常、パイプラインは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="852c1-108">Pipelines commonly perform:</span></span>  
  
-   <span data-ttu-id="852c1-109">さまざまな形式から XML 形式へのデータの正規化</span><span class="sxs-lookup"><span data-stu-id="852c1-109">Data normalization from various formats to XML.</span></span>  
  
-   <span data-ttu-id="852c1-110">XML 形式からさまざまな形式へのデータ変換</span><span class="sxs-lookup"><span data-stu-id="852c1-110">Data transformation from XML to various formats.</span></span>  
  
-   <span data-ttu-id="852c1-111">プロパティの昇格および降格</span><span class="sxs-lookup"><span data-stu-id="852c1-111">Property promotion and demotion.</span></span>  
  
-   <span data-ttu-id="852c1-112">ドキュメントの逆アセンブリおよびアセンブリ</span><span class="sxs-lookup"><span data-stu-id="852c1-112">Document disassembly and assembly.</span></span>  
  
-   <span data-ttu-id="852c1-113">ドキュメントのデコードおよびエンコード</span><span class="sxs-lookup"><span data-stu-id="852c1-113">Document decoding and encoding.</span></span>  
  
-   <span data-ttu-id="852c1-114">ドキュメントの復号化および暗号化</span><span class="sxs-lookup"><span data-stu-id="852c1-114">Document decryption and encryption.</span></span>  
  
-   <span data-ttu-id="852c1-115">ドキュメントの署名およびデジタル署名の確認</span><span class="sxs-lookup"><span data-stu-id="852c1-115">Document signing and digital signature verification.</span></span>  
  
 <span data-ttu-id="852c1-116">パイプラインでのメッセージ処理を含むワークフローを次に示します。</span><span class="sxs-lookup"><span data-stu-id="852c1-116">The following figure shows the workflow involved in processing a message by using pipelines.</span></span>  
  
 <span data-ttu-id="852c1-117">![メッセージを処理するためのワークフローのダイアグラム。] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span><span class="sxs-lookup"><span data-stu-id="852c1-117">![Diagram of workflow for processing a message.](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")</span></span>  
<span data-ttu-id="852c1-118">メッセージ処理ワークフロー</span><span class="sxs-lookup"><span data-stu-id="852c1-118">Depicts the message processing workflow.</span></span>  
  
 <span data-ttu-id="852c1-119">図に示すように、メッセージは、アダプターから受信パイプラインに渡されます。この受信パイプラインで、メッセージが XML に変換されます。</span><span class="sxs-lookup"><span data-stu-id="852c1-119">As shown in the figure, the message is passed from the adapter to the receive pipeline where it is transformed to XML.</span></span> <span data-ttu-id="852c1-120">この後、メッセージはオーケストレーションで使用可能になります。また、メッセージを送信パイプラインに渡してから、送信アダプターに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="852c1-120">The message can then be used by orchestrations, or passed to a send pipeline, and then to a send adapter.</span></span>  
  
 <span data-ttu-id="852c1-121">パイプライン デザイナーのキーボード ショートカットの使用方法の詳細については、次を参照してください。[パイプライン デザイナーのキーボード ショートカット](../core/pipeline-designer-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="852c1-121">For information about using the keyboard shortcuts for Pipeline Designer, see [Pipeline Designer Keyboard Shortcuts](../core/pipeline-designer-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="852c1-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="852c1-122">In This Section</span></span>  
  
-   [<span data-ttu-id="852c1-123">パイプライン、ステージ、およびコンポーネントについて</span><span class="sxs-lookup"><span data-stu-id="852c1-123">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)  
  
-   [<span data-ttu-id="852c1-124">パイプライン デザイナーの使用</span><span class="sxs-lookup"><span data-stu-id="852c1-124">Using Pipeline Designer</span></span>](../core/using-pipeline-designer.md)  
  
-   [<span data-ttu-id="852c1-125">パイプライン デザイナーでパイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="852c1-125">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [<span data-ttu-id="852c1-126">ネイティブ パイプライン コンポーネントの構成</span><span class="sxs-lookup"><span data-stu-id="852c1-126">Configuring Native Pipeline Components</span></span>](../core/configuring-native-pipeline-components.md)  
  
-   [<span data-ttu-id="852c1-127">パイプラインを展開する方法</span><span class="sxs-lookup"><span data-stu-id="852c1-127">How to Deploy Pipelines</span></span>](../core/how-to-deploy-pipelines.md)  
  
-   [<span data-ttu-id="852c1-128">パイプラインをセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="852c1-128">How to Secure Pipelines</span></span>](../core/how-to-secure-pipelines.md)