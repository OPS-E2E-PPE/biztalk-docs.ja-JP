---
title: アセンブラー パイプライン コンポーネントでプロパティの降格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b114d4a66b4fcb0139403fc22dcacc5c8ec1675
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398487"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a><span data-ttu-id="d2960-102">アセンブラー パイプライン コンポーネントでプロパティの降格</span><span class="sxs-lookup"><span data-stu-id="d2960-102">Property Demotion in Assembler Pipeline Components</span></span>
<span data-ttu-id="d2960-103">プロパティの降格を使用して、メッセージ コンテキストのプロパティ値をメッセージ コンテキストまたはメッセージのヘッダーやトレーラーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="d2960-103">You can use property demotion to copy a property value from the message context into the message content or to its header or trailer.</span></span> <span data-ttu-id="d2960-104">プロパティの降格を行うには、ドキュメントで指定した XPath 式、またはヘッダーやトレーラー スキーマで指定した XPath 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2960-104">You accomplish property demotion by using an XPath expression specified in the document or in the header and trailer schema.</span></span>  
  
 <span data-ttu-id="d2960-105">コンテキスト プロパティの日付データを結果のドキュメントに書き込む場合、BizTalk Server では、日付データがすべて UTC 形式であることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="d2960-105">When writing datetime data from the context property into the resulting document, BizTalk Server assumes that all datetime data is in UTC format.</span></span>  
  
 <span data-ttu-id="d2960-106">プロパティをデータに書き込むために使用される形式は、次の表の XSD データ型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="d2960-106">The format used to write properties into the data is determined by the XSD data type as shown in the following table.</span></span>  
  
|<span data-ttu-id="d2960-107">データ型</span><span class="sxs-lookup"><span data-stu-id="d2960-107">Data type</span></span>|<span data-ttu-id="d2960-108">[形式]</span><span class="sxs-lookup"><span data-stu-id="d2960-108">Format</span></span>|  
|---------------|------------|  
|<span data-ttu-id="d2960-109">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="d2960-109">xs:datetime</span></span>|<span data-ttu-id="d2960-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="d2960-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span></span>|  
|<span data-ttu-id="d2960-111">xs:date</span><span class="sxs-lookup"><span data-stu-id="d2960-111">xs:date</span></span>|<span data-ttu-id="d2960-112">yyyy-MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="d2960-112">yyyy-MM-ddZ</span></span>|  
|<span data-ttu-id="d2960-113">xs:gDay</span><span class="sxs-lookup"><span data-stu-id="d2960-113">xs:gDay</span></span>|<span data-ttu-id="d2960-114">---ddZ</span><span class="sxs-lookup"><span data-stu-id="d2960-114">---ddZ</span></span>|  
|<span data-ttu-id="d2960-115">xs:gMonth</span><span class="sxs-lookup"><span data-stu-id="d2960-115">xs:gMonth</span></span>|<span data-ttu-id="d2960-116">-MM: Z</span><span class="sxs-lookup"><span data-stu-id="d2960-116">--MM—Z</span></span>|  
|<span data-ttu-id="d2960-117">xs:gMonthDay</span><span class="sxs-lookup"><span data-stu-id="d2960-117">xs:gMonthDay</span></span>|<span data-ttu-id="d2960-118">--MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="d2960-118">--MM-ddZ</span></span>|  
|<span data-ttu-id="d2960-119">xs:gYear</span><span class="sxs-lookup"><span data-stu-id="d2960-119">xs:gYear</span></span>|<span data-ttu-id="d2960-120">yyyyZ</span><span class="sxs-lookup"><span data-stu-id="d2960-120">yyyyZ</span></span>|  
|<span data-ttu-id="d2960-121">xs:gYearMonth</span><span class="sxs-lookup"><span data-stu-id="d2960-121">xs:gYearMonth</span></span>|<span data-ttu-id="d2960-122">yyyy-MMZ</span><span class="sxs-lookup"><span data-stu-id="d2960-122">yyyy-MMZ</span></span>|  
|<span data-ttu-id="d2960-123">xs:time</span><span class="sxs-lookup"><span data-stu-id="d2960-123">xs:time</span></span>|<span data-ttu-id="d2960-124">HH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="d2960-124">HH:mm:ss.fffffffZ</span></span>|  
  
## <a name="property-demotion-and-envelopes"></a><span data-ttu-id="d2960-125">プロパティの降格とエンベロープ</span><span class="sxs-lookup"><span data-stu-id="d2960-125">Property Demotion and Envelopes</span></span>  
 <span data-ttu-id="d2960-126">エンベロープ内のファイルをアセンブルするときに、システム名前空間の 1 つ以上、またはユーザーの名前空間の 1 つから値を降格すると役に立つことが多くあります。</span><span class="sxs-lookup"><span data-stu-id="d2960-126">It is often useful to demote values from one or more of the system namespaces -- or one of your own namespaces -- when assembling files within an envelope.</span></span> <span data-ttu-id="d2960-127">一般的には次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="d2960-127">Some common scenarios include:</span></span>  
  
- <span data-ttu-id="d2960-128">バックエンド システムでデータのソースを追跡できるよう、システムに送信された元のファイル名を送信メッセージに含める場合。</span><span class="sxs-lookup"><span data-stu-id="d2960-128">You want to include the original file name submitted to the system in outbound messages so back-end systems can track the origin of data.</span></span>  
  
- <span data-ttu-id="d2960-129">メッセージ本文のデータをヘッダーに書き込む場合。</span><span class="sxs-lookup"><span data-stu-id="d2960-129">You want to write data from the body message to the header.</span></span> <span data-ttu-id="d2960-130">たとえば注文書の処理では、出荷先名をエンベロープに書き込むと下流のシステムで役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="d2960-130">For example, for a purchase order it might be useful to write the ship to name to the envelope for down-stream systems.</span></span>  
  
- <span data-ttu-id="d2960-131">カスタム コードを記述せずに、多数の異なるフィールドを結合してヘッダーに含める場合。</span><span class="sxs-lookup"><span data-stu-id="d2960-131">You want to combine many different fields into the header without writing custom code.</span></span> <span data-ttu-id="d2960-132">XML アセンブラーやフラット ファイル アセンブラーのプロパティの降格で、この処理を実現できます。</span><span class="sxs-lookup"><span data-stu-id="d2960-132">Property demotion in the Xml assembler or flat file assembler can do the job.</span></span>  
  
  <span data-ttu-id="d2960-133">重要な点としては、XML アセンブラー コンポーネントとフラット ファイル アセンブラー コンポーネントのどちらを使用しても、エンベロープとドキュメント本文用に使用するスキーマを指定できることです。</span><span class="sxs-lookup"><span data-stu-id="d2960-133">It is important to remember that the XML and flat file assembler components both allow you to specify which schema to use for the envelope and document body.</span></span> <span data-ttu-id="d2960-134">逆アセンブラーで使用されるスキーマと同じスキーマを選択したり、異なるフィールドで新しいエンベロープ スキーマを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d2960-134">You can choose the same schemas used in disassembly or create a new envelope schema with different fields.</span></span>  
  
  <span data-ttu-id="d2960-135">これらの概念の例は、次を参照してください。 [EnvelopeProcessing (BizTalk Server サンプル)](../core/envelopeprocessing-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="d2960-135">For an example of these concepts, see [EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2960-136">参照</span><span class="sxs-lookup"><span data-stu-id="d2960-136">See Also</span></span>  
 <span data-ttu-id="d2960-137">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="d2960-137">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="d2960-138">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d2960-138">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)