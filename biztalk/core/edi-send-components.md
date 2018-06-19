---
title: EDI 送信コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce270db-a573-48b3-be15-0178a5b7785b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5520a0c1dd0a6ef7e42818314a9f87733aebcb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239930"
---
# <a name="edi-send-components"></a><span data-ttu-id="474be-102">EDI 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="474be-102">EDI Send Components</span></span>
<span data-ttu-id="474be-103">このトピックでは、EDI/AS2 メッセージ以外の EDI メッセージを処理するパイプラインおよびパイプライン コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="474be-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="474be-104">EDI および AS2 の EDI および AS2 メッセージを送信する方法については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="474be-104">For information about the sending of EDI/AS2 or non-EDI/AS2 messages, see [AS2 Send Components](../core/as2-send-components.md).</span></span> <span data-ttu-id="474be-105">AS2 の送信コンポーネントは、AS2 の処理だけでなく、EDI の処理も実行します。</span><span class="sxs-lookup"><span data-stu-id="474be-105">Note that AS2 send components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-send-pipeline"></a><span data-ttu-id="474be-106">EDI 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="474be-106">EDI Send Pipeline</span></span>  
 <span data-ttu-id="474be-107">EDI 送信処理は、次の EDISend パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="474be-107">EDI send processing is performed in the following EDISend pipeline.</span></span> <span data-ttu-id="474be-108">このパイプラインは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] の `Microsoft.BizTalk.Edi.EdiPipelines.dll` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="474be-108">This pipeline is installed in `Microsoft.BizTalk.Edi.EdiPipelines.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="474be-109">**EDISend パイプライン**</span><span class="sxs-lookup"><span data-stu-id="474be-109">**EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="474be-110">このパイプラインでは、EDI メッセージを生成し、送信します。</span><span class="sxs-lookup"><span data-stu-id="474be-110">This pipeline generates and sends EDI messages.</span></span> <span data-ttu-id="474be-111">HTTP 経由で受信した AS2 でエンコードされた EDI メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="474be-111">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="474be-112">AS2 でエンコードされた EDI メッセージの処理は、AS2 パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="474be-112">Processing of AS2-encoded EDI messages is performed by an AS2 pipeline.</span></span> <span data-ttu-id="474be-113">AS2 送信パイプラインでは、EDI メッセージの処理に EDI パイプラインと同じコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="474be-113">The AS2 send pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="474be-114">オーケストレーションからの EDISend パイプラインの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="474be-114">Running the EDISend pipeline from an orchestration is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="474be-115">AS2EDISend パイプラインでは、EDI メッセージを生成し、AS2 トランスポート経由で送信します。</span><span class="sxs-lookup"><span data-stu-id="474be-115">The AS2EDISend pipeline generates and sends EDI messages over AS2 transport.</span></span> <span data-ttu-id="474be-116">詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="474be-116">For more information, see [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
 <span data-ttu-id="474be-117">このパイプラインは、EDI アセンブラー パイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="474be-117">The pipeline consists of the EDI Assembler pipeline component:</span></span>  
  
## <a name="edi-send-pipeline-component"></a><span data-ttu-id="474be-118">EDI 送信パイプラインのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="474be-118">EDI Send Pipeline Component</span></span>  
 <span data-ttu-id="474be-119">EDISend パイプラインでは、EDI アセンブラー パイプライン コンポーネントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="474be-119">The EDISend pipeline uses the EDI Assembler pipeline component.</span></span> <span data-ttu-id="474be-120">このコンポーネントがインストールされている`Microsoft.BizTalk.Edi.PipelineComponents.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]パイプライン コンポーネント\\です。</span><span class="sxs-lookup"><span data-stu-id="474be-120">This component is installed in `Microsoft.BizTalk.Edi.PipelineComponents.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="474be-121">EDI アセンブラーは、EDISend パイプラインにおいて、EDI エンコード インターチェンジの処理の大部分を担当します。</span><span class="sxs-lookup"><span data-stu-id="474be-121">The EDI Assembler performs most processing of EDI-encoded interchanges in the EDISend Pipeline.</span></span> <span data-ttu-id="474be-122">EDI アセンブラーが EDI メッセージを処理する方法については、次を参照してください。 [「EDI アセンブラーの動作](../core/how-the-edi-assembler-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="474be-122">For information about how the EDI Assembler processes EDI messages, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>