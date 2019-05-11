---
title: EDI 送信コンポーネント |Microsoft Docs
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
ms.openlocfilehash: 9afcc401b800fab7b549ac9bc4c53ae7502b8caa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350272"
---
# <a name="edi-send-components"></a><span data-ttu-id="d4537-102">EDI 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4537-102">EDI Send Components</span></span>
<span data-ttu-id="d4537-103">このトピックでは、EDI/AS2 メッセージ以外の EDI メッセージを処理するパイプラインおよびパイプライン コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d4537-103">The pipeline and pipeline components described in this topic process EDI messages that are not EDI/AS2 messages.</span></span> <span data-ttu-id="d4537-104">EDI および AS2 または EDI および AS2 メッセージの送信方法の詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4537-104">For information about the sending of EDI/AS2 or non-EDI/AS2 messages, see [AS2 Send Components](../core/as2-send-components.md).</span></span> <span data-ttu-id="d4537-105">AS2 送信コンポーネントが EDI AS2 の処理だけでなく処理を実行することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4537-105">Note that AS2 send components perform EDI processing in addition to AS2 processing.</span></span>  
  
## <a name="edi-send-pipeline"></a><span data-ttu-id="d4537-106">EDI 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d4537-106">EDI Send Pipeline</span></span>  
 <span data-ttu-id="d4537-107">EDI 送信処理は、次の EDISend パイプラインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4537-107">EDI send processing is performed in the following EDISend pipeline.</span></span> <span data-ttu-id="d4537-108">このパイプラインがインストールされている`Microsoft.BizTalk.Edi.EdiPipelines.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d4537-108">This pipeline is installed in `Microsoft.BizTalk.Edi.EdiPipelines.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
 <span data-ttu-id="d4537-109">**EDISend パイプライン**</span><span class="sxs-lookup"><span data-stu-id="d4537-109">**EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="d4537-110">このパイプラインは、生成し、EDI メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d4537-110">This pipeline generates and sends EDI messages.</span></span> <span data-ttu-id="d4537-111">HTTP 経由で受信した AS2 でエンコードされた EDI メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="d4537-111">It does not process AS2-encoded EDI messages received over HTTP.</span></span> <span data-ttu-id="d4537-112">AS2 でエンコードされた EDI メッセージの処理は、AS2 パイプラインによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4537-112">Processing of AS2-encoded EDI messages is performed by an AS2 pipeline.</span></span> <span data-ttu-id="d4537-113">AS2 送信パイプラインに EDI パイプラインと EDI メッセージを処理するのにのと同じコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4537-113">The AS2 send pipelines use the same components to process EDI messages as the EDI pipeline uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4537-114">オーケストレーションからの EDISend パイプラインの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d4537-114">Running the EDISend pipeline from an orchestration is not supported.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4537-115">AS2EDISend パイプラインでは、生成し、AS2 トランスポート経由で EDI メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d4537-115">The AS2EDISend pipeline generates and sends EDI messages over AS2 transport.</span></span> <span data-ttu-id="d4537-116">詳細については、次を参照してください。 [AS2 送信コンポーネント](../core/as2-send-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4537-116">For more information, see [AS2 Send Components](../core/as2-send-components.md).</span></span>  
  
 <span data-ttu-id="d4537-117">パイプラインは、EDI アセンブラー パイプライン コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d4537-117">The pipeline consists of the EDI Assembler pipeline component:</span></span>  
  
## <a name="edi-send-pipeline-component"></a><span data-ttu-id="d4537-118">EDI 送信パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4537-118">EDI Send Pipeline Component</span></span>  
 <span data-ttu-id="d4537-119">EDISend パイプラインは、EDI アセンブラー パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4537-119">The EDISend pipeline uses the EDI Assembler pipeline component.</span></span> <span data-ttu-id="d4537-120">このコンポーネントがインストールされている`Microsoft.BizTalk.Edi.PipelineComponents.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]パイプライン コンポーネント\\します。</span><span class="sxs-lookup"><span data-stu-id="d4537-120">This component is installed in `Microsoft.BizTalk.Edi.PipelineComponents.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="d4537-121">EDI アセンブラーは、EDISend パイプラインで EDI エンコード インターチェンジの処理の大部分を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4537-121">The EDI Assembler performs most processing of EDI-encoded interchanges in the EDISend Pipeline.</span></span> <span data-ttu-id="d4537-122">EDI アセンブラーが EDI メッセージを処理する方法については、次を参照してください。 [、EDI アセンブラーのしくみ](../core/how-the-edi-assembler-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="d4537-122">For information about how the EDI Assembler processes EDI messages, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>