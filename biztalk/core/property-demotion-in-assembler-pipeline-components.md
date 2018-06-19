---
title: アセンブラー パイプライン コンポーネントでプロパティの降格 |Microsoft ドキュメント
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
ms.openlocfilehash: af634d302f01b18c91ebdbb7533673e8b9c545c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268834"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a><span data-ttu-id="e2972-102">アセンブラー パイプライン コンポーネントでプロパティの降格</span><span class="sxs-lookup"><span data-stu-id="e2972-102">Property Demotion in Assembler Pipeline Components</span></span>
<span data-ttu-id="e2972-103">プロパティの降格を使用して、メッセージ コンテキストのプロパティ値をメッセージ コンテキストまたはメッセージのヘッダーやトレーラーにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="e2972-103">You can use property demotion to copy a property value from the message context into the message content or to its header or trailer.</span></span> <span data-ttu-id="e2972-104">プロパティの降格を行うには、ドキュメントで指定した XPath 式、またはヘッダーやトレーラー スキーマで指定した XPath 式を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2972-104">You accomplish property demotion by using an XPath expression specified in the document or in the header and trailer schema.</span></span>  
  
 <span data-ttu-id="e2972-105">コンテキスト プロパティの日付データを結果のドキュメントに書き込む場合、BizTalk Server では、日付データがすべて UTC 形式であることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="e2972-105">When writing datetime data from the context property into the resulting document, BizTalk Server assumes that all datetime data is in UTC format.</span></span>  
  
 <span data-ttu-id="e2972-106">プロパティをデータに書き込むために使用される形式は、次の表の XSD データ型によって決まります。</span><span class="sxs-lookup"><span data-stu-id="e2972-106">The format used to write properties into the data is determined by the XSD data type as shown in the following table.</span></span>  
  
|<span data-ttu-id="e2972-107">データ型</span><span class="sxs-lookup"><span data-stu-id="e2972-107">Data type</span></span>|<span data-ttu-id="e2972-108">Format</span><span class="sxs-lookup"><span data-stu-id="e2972-108">Format</span></span>|  
|---------------|------------|  
|<span data-ttu-id="e2972-109">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="e2972-109">xs:datetime</span></span>|<span data-ttu-id="e2972-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="e2972-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span></span>|  
|<span data-ttu-id="e2972-111">xs:date</span><span class="sxs-lookup"><span data-stu-id="e2972-111">xs:date</span></span>|<span data-ttu-id="e2972-112">yyyy-MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="e2972-112">yyyy-MM-ddZ</span></span>|  
|<span data-ttu-id="e2972-113">xs:gDay</span><span class="sxs-lookup"><span data-stu-id="e2972-113">xs:gDay</span></span>|<span data-ttu-id="e2972-114">---ddZ</span><span class="sxs-lookup"><span data-stu-id="e2972-114">---ddZ</span></span>|  
|<span data-ttu-id="e2972-115">xs:gMonth</span><span class="sxs-lookup"><span data-stu-id="e2972-115">xs:gMonth</span></span>|<span data-ttu-id="e2972-116">--MM — Z</span><span class="sxs-lookup"><span data-stu-id="e2972-116">--MM—Z</span></span>|  
|<span data-ttu-id="e2972-117">xs:gMonthDay</span><span class="sxs-lookup"><span data-stu-id="e2972-117">xs:gMonthDay</span></span>|<span data-ttu-id="e2972-118">--MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="e2972-118">--MM-ddZ</span></span>|  
|<span data-ttu-id="e2972-119">xs:gYear</span><span class="sxs-lookup"><span data-stu-id="e2972-119">xs:gYear</span></span>|<span data-ttu-id="e2972-120">yyyyZ</span><span class="sxs-lookup"><span data-stu-id="e2972-120">yyyyZ</span></span>|  
|<span data-ttu-id="e2972-121">xs:gYearMonth</span><span class="sxs-lookup"><span data-stu-id="e2972-121">xs:gYearMonth</span></span>|<span data-ttu-id="e2972-122">yyyy-MMZ</span><span class="sxs-lookup"><span data-stu-id="e2972-122">yyyy-MMZ</span></span>|  
|<span data-ttu-id="e2972-123">xs:time</span><span class="sxs-lookup"><span data-stu-id="e2972-123">xs:time</span></span>|<span data-ttu-id="e2972-124">HH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="e2972-124">HH:mm:ss.fffffffZ</span></span>|  
  
## <a name="property-demotion-and-envelopes"></a><span data-ttu-id="e2972-125">プロパティの降格とエンベロープ</span><span class="sxs-lookup"><span data-stu-id="e2972-125">Property Demotion and Envelopes</span></span>  
 <span data-ttu-id="e2972-126">エンベロープ内のファイルをアセンブルするときに、システム名前空間の 1 つ以上、またはユーザーの名前空間の 1 つから値を降格すると役に立つことが多くあります。</span><span class="sxs-lookup"><span data-stu-id="e2972-126">It is often useful to demote values from one or more of the system namespaces -- or one of your own namespaces -- when assembling files within an envelope.</span></span> <span data-ttu-id="e2972-127">一般的には次のようなシナリオが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e2972-127">Some common scenarios include:</span></span>  
  
-   <span data-ttu-id="e2972-128">バックエンド システムでデータのソースを追跡できるよう、システムに送信された元のファイル名を送信メッセージに含める場合。</span><span class="sxs-lookup"><span data-stu-id="e2972-128">You want to include the original file name submitted to the system in outbound messages so back-end systems can track the origin of data.</span></span>  
  
-   <span data-ttu-id="e2972-129">メッセージ本文のデータをヘッダーに書き込む場合。</span><span class="sxs-lookup"><span data-stu-id="e2972-129">You want to write data from the body message to the header.</span></span> <span data-ttu-id="e2972-130">たとえば注文書の処理では、出荷先名をエンベロープに書き込むと下流のシステムで役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="e2972-130">For example, for a purchase order it might be useful to write the ship to name to the envelope for down-stream systems.</span></span>  
  
-   <span data-ttu-id="e2972-131">カスタム コードを記述せずに、多数の異なるフィールドを結合してヘッダーに含める場合。</span><span class="sxs-lookup"><span data-stu-id="e2972-131">You want to combine many different fields into the header without writing custom code.</span></span> <span data-ttu-id="e2972-132">XML アセンブラーやフラット ファイル アセンブラーのプロパティの降格で、この処理を実現できます。</span><span class="sxs-lookup"><span data-stu-id="e2972-132">Property demotion in the Xml assembler or flat file assembler can do the job.</span></span>  
  
 <span data-ttu-id="e2972-133">重要な点としては、XML アセンブラー コンポーネントとフラット ファイル アセンブラー コンポーネントのどちらを使用しても、エンベロープとドキュメント本文用に使用するスキーマを指定できることです。</span><span class="sxs-lookup"><span data-stu-id="e2972-133">It is important to remember that the XML and flat file assembler components both allow you to specify which schema to use for the envelope and document body.</span></span> <span data-ttu-id="e2972-134">逆アセンブラーで使用されるスキーマと同じスキーマを選択したり、異なるフィールドで新しいエンベロープ スキーマを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2972-134">You can choose the same schemas used in disassembly or create a new envelope schema with different fields.</span></span>  
  
 <span data-ttu-id="e2972-135">これらの概念の例は、次を参照してください。 [EnvelopeProcessing (BizTalk Server サンプル)](../core/envelopeprocessing-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2972-135">For an example of these concepts, see [EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2972-136">参照</span><span class="sxs-lookup"><span data-stu-id="e2972-136">See Also</span></span>  
 <span data-ttu-id="e2972-137">[フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e2972-137">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="e2972-138">フラット ファイル アセンブラー パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e2972-138">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)