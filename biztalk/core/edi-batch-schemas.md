---
title: EDI のバッチ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26da8036-8fe0-481e-b1e9-7f2e5b090768
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c03f9a6136a925419166fa4db8b919b9ec8eb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389244"
---
# <a name="edi-batch-schemas"></a><span data-ttu-id="2c0a4-102">EDI のバッチ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c0a4-102">EDI Batch Schemas</span></span>
<span data-ttu-id="2c0a4-103">保存されたインターチェンジが BizTalk Server で処理される際には、以下の 3 つ以上のスキーマが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-103">When BizTalk Server processes a preserved interchange, it uses at least three schemas:</span></span>  

- <span data-ttu-id="2c0a4-104">保存されたバッチ インターチェンジ (BaseArtifacts.dll に配置された X12_BatchSchema または Edifact_BatchSchema) のルート ノードを検証するためのバッチ スキーマ (インターチェンジ XML スキーマ)。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-104">The batch schemas (Interchange XML schemas) to validate the root node of the preserved batched interchange (X12_BatchSchema or Edifact_BatchSchema deployed in BaseArtifacts.dll)</span></span>  

- <span data-ttu-id="2c0a4-105">インターチェンジ、グループ、およびトランザクション セットのヘッダーとトレーラー (BaseArtifacts.dll に配置された X12ServiceSchema または EdifactServiceSchema) を検証するためのエンベロープ サービス スキーマ。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-105">The envelope service schemas to validate the interchange, gorup, and transaction set headers and trailers (X12ServiceSchema or EdifactServiceSchema deployed in BaseArtifacts.dll).</span></span> <span data-ttu-id="2c0a4-106">詳細については、次を参照してください。 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-106">For more information, see [EDI Service and Control Schemas](../core/edi-service-and-control-schemas.md).</span></span>  

- <span data-ttu-id="2c0a4-107">(プロジェクト内に配置された) バッチ インターチェンジ内にある各ドキュメントの種類のドキュメント スキーマ。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-107">Document schemas for each document type in the batched interchange (deployed in your project).</span></span> <span data-ttu-id="2c0a4-108">詳細については、次を参照してください。 [EDI ドキュメント スキーマ](../core/edi-document-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-108">For more information, see [EDI Document Schemas](../core/edi-document-schemas.md).</span></span>  

  <span data-ttu-id="2c0a4-109">バッチ スキーマは、保存中の受信および送信の各バッチ インターチェンジを検証するために、実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-109">Batch schemas are used at runtime to validate inbound and outbound batched interchanges that are being preserved.</span></span> <span data-ttu-id="2c0a4-110">また、バッチ スキーマは、メッセージ インスタンスを検証および生成するために、デザイン時にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-110">Batch schemas are also used at design time to validate and generate message instances.</span></span>  

## <a name="batch-schemas-used-at-runtime"></a><span data-ttu-id="2c0a4-111">実行時に使用されるバッチ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c0a4-111">Batch Schemas Used at Runtime</span></span>  
 <span data-ttu-id="2c0a4-112">バッチ スキーマの 2 つの標準的なバージョンが存在します。使用される X12_BatchSchema.xsd X12 エンコードと EDIFACT エンコードに使用される EDIFACT_BatchSchema.xsd です。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-112">Two canonical versions of the batch schemas exist: X12_BatchSchema.xsd for X12 encoding and EDIFACT_BatchSchema.xsd for EDIFACT encoding.</span></span> <span data-ttu-id="2c0a4-113">これらのスキーマは、制御セグメントを含むテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-113">These schemas are templates that include the control segment.</span></span> <span data-ttu-id="2c0a4-114">これらのスキーマは、次のルート名および名前空間を保持します。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-114">These schemas have the following root names and namespaces:</span></span>  


|       <span data-ttu-id="2c0a4-115">スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c0a4-115">Schema</span></span>        |       <span data-ttu-id="2c0a4-116">ルート ノード</span><span class="sxs-lookup"><span data-stu-id="2c0a4-116">Root Node</span></span>       |                    <span data-ttu-id="2c0a4-117">Namespace</span><span class="sxs-lookup"><span data-stu-id="2c0a4-117">Namespace</span></span>                     |
|---------------------|-----------------------|--------------------------------------------------|
|   <span data-ttu-id="2c0a4-118">X12_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="2c0a4-118">X12_BatchSchema</span></span>   |   <span data-ttu-id="2c0a4-119">X12InterchangeXML</span><span class="sxs-lookup"><span data-stu-id="2c0a4-119">X12InterchangeXML</span></span>   | http://schemas.microsoft.com/Edi/X12_BatchSchema |
| <span data-ttu-id="2c0a4-120">Edifact_BatchSchema</span><span class="sxs-lookup"><span data-stu-id="2c0a4-120">Edifact_BatchSchema</span></span> | <span data-ttu-id="2c0a4-121">EdifactInterchangeXML</span><span class="sxs-lookup"><span data-stu-id="2c0a4-121">EdifactInterchangeXML</span></span> |     http://schemas.microsoft.com/Edi/Edifact     |

 <span data-ttu-id="2c0a4-122">受信パイプラインによって生成された XML インスタンス ドキュメントの種類は定数である (\<エンコード\>_BatchSchema.xml) この標準のスキーマを参照します。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-122">The document type on the XML instance generated by the receive pipeline will be a constant (\<Encoding\>_BatchSchema.xml) and will reference this canonical schema.</span></span> <span data-ttu-id="2c0a4-123">このインスタンスはオーケストレーションのマップで使用できますが、使用前にドキュメントの種類と名前空間を変更して、必要な実際のスキーマをマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-123">You can use this instance in a map in an orchestration; however, before doing so you have to change the document type and namespace to map to the actual schema required.</span></span>  

 <span data-ttu-id="2c0a4-124">バッチ スキーマは BaseArtifacts.dll に配置されるので、プロジェクトのデザイン時に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-124">You do not need to specify the batch schema at design time in the project, because it is deployed in BaseArtifacts.dll.</span></span>  

## <a name="batch-schemas-in-the-schema-store"></a><span data-ttu-id="2c0a4-125">スキーマ ストア内のバッチ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2c0a4-125">Batch Schemas in the Schema Store</span></span>  
 <span data-ttu-id="2c0a4-126">保存されたバッチを BizTalk Server で処理する際に実行時に使用されるバッチ スキーマは、BaseArtifacts.dll アセンブリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-126">The batch schemas that BizTalk Server uses at runtime to process preserved batches are deployed in the BaseArtifacts.dll assembly.</span></span> <span data-ttu-id="2c0a4-127">これらは、自動的にランタイム処理で利用できます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-127">These are automatically available for run-time processing.</span></span> <span data-ttu-id="2c0a4-128">Edifact_BatchSchema および X12_BatchSchema は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI の BizTalk スキーマ ストアでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-128">Edifact_BatchSchema and X12_BatchSchema are also available in the BizTalk schema store at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="2c0a4-129">インターチェンジの生成または検証するデザイン時にのみ使用これらの各スキーマは。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-129">Each of these schemas is only used at design time to validate or generate the interchange.</span></span> <span data-ttu-id="2c0a4-130">いずれのスキーマも、受信パイプラインまたは送信パイプラインでの実行時の検証には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2c0a4-130">Neither schema is required for validation in the receive pipeline or send pipeline at runtime.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2c0a4-131">参照</span><span class="sxs-lookup"><span data-stu-id="2c0a4-131">See Also</span></span>  
 <span data-ttu-id="2c0a4-132">[EDI スキーマ](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="2c0a4-132">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="2c0a4-133">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="2c0a4-133">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)