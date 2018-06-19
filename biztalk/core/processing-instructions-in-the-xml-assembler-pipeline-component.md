---
title: XML アセンブラー パイプライン コンポーネントで処理命令 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85ac6045084c0aea672b0c1e9d6dfb1b4a742d55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265154"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="ab03f-102">XML アセンブラー パイプライン コンポーネントで処理命令</span><span class="sxs-lookup"><span data-stu-id="ab03f-102">Processing Instructions in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="ab03f-103">処理命令は、XML ドキュメントを処理するアプリケーションに対する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab03f-103">Processing instructions provide information to the application that processes an XML document.</span></span> <span data-ttu-id="ab03f-104">この情報には、ドキュメントの処理方法や表示方法などの命令が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-104">Such information may include instructions about how to process the document, how to display it, and so on.</span></span>  
  
 <span data-ttu-id="ab03f-105">処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="ab03f-105">Processing instructions are added to an XML document by the **Add processing instructions** property (or the equivalent **XMLNorm.ProcessingInstructionOption** property on the message context).</span></span> <span data-ttu-id="ab03f-106">処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="ab03f-106">Processing instruction text is specified with the **Add processing instructions text** property (or the equivalent **XMLNorm.ProcessingInstruction** property on the message context).</span></span>  
  
 <span data-ttu-id="ab03f-107">**処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明される 3 つの値。</span><span class="sxs-lookup"><span data-stu-id="ab03f-107">The **Add processing instructions** property (or **XMLNorm.ProcessingInstructionOption** property) has three possible values, which are described in the following table.</span></span>  
  
|<span data-ttu-id="ab03f-108">値</span><span class="sxs-lookup"><span data-stu-id="ab03f-108">Value</span></span>|<span data-ttu-id="ab03f-109">値</span><span class="sxs-lookup"><span data-stu-id="ab03f-109">Value</span></span>|<span data-ttu-id="ab03f-110">Description</span><span class="sxs-lookup"><span data-stu-id="ab03f-110">Description</span></span>|  
|-----------|-----------|-----------------|  
|<span data-ttu-id="ab03f-111">追加</span><span class="sxs-lookup"><span data-stu-id="ab03f-111">Append</span></span>|<span data-ttu-id="ab03f-112">0</span><span class="sxs-lookup"><span data-stu-id="ab03f-112">0</span></span>|<span data-ttu-id="ab03f-113">XML アセンブラーからの新しい処理命令は、ドキュメントの最初の処理命令に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-113">New processing instructions from the XML Assembler are appended to the processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="ab03f-114">[新規作成]</span><span class="sxs-lookup"><span data-stu-id="ab03f-114">Create new</span></span>|<span data-ttu-id="ab03f-115">1</span><span class="sxs-lookup"><span data-stu-id="ab03f-115">1</span></span>|<span data-ttu-id="ab03f-116">XML アセンブラーからの新しい処理命令は、ドキュメントの最初の既存の処理命令を上書きします。</span><span class="sxs-lookup"><span data-stu-id="ab03f-116">New processing instructions from the XML Assembler overwrite existing processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="ab03f-117">Ignore</span><span class="sxs-lookup"><span data-stu-id="ab03f-117">Ignore</span></span>|<span data-ttu-id="ab03f-118">2</span><span class="sxs-lookup"><span data-stu-id="ab03f-118">2</span></span>|<span data-ttu-id="ab03f-119">ドキュメントの最初の処理命令は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-119">Processing instructions at the beginning of the document are removed.</span></span>|  
  
 <span data-ttu-id="ab03f-120">メッセージ コンテキストで指定される処理命令 (またはメッセージ コンテキスト プロパティ) のペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-120">The pair of processing instructions (or message context properties) specified on a message context take precedence over the property pair specified in Pipeline Designer.</span></span> <span data-ttu-id="ab03f-121">たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定された**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-121">For example, if **XMLNorm.ProcessingInstructionOption** is specified as **Create new** (1) and **XMLNorm.ProcessingInstruction** is not specified, an empty processing instruction will replace an existing processing instruction.</span></span>  
  
 <span data-ttu-id="ab03f-122">別の例として場合**XMLNorm.ProcessingInstruction**が指定されているが、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれも使用します。</span><span class="sxs-lookup"><span data-stu-id="ab03f-122">As another example, if **XMLNorm.ProcessingInstruction** is specified but **XMLNorm.ProcessingInstructionOption** is not, none of the properties from the message context are used.</span></span> <span data-ttu-id="ab03f-123">この場合、パイプライン デザイナーからの処理命令が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-123">In this case, the processing instructions from Pipeline Designer are used.</span></span>  
  
 <span data-ttu-id="ab03f-124">既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。</span><span class="sxs-lookup"><span data-stu-id="ab03f-124">By default, **Add processing instructions** is set to **Append**, and **Add processing instructions text** is empty.</span></span>  
  
## <a name="processing-properties-and-envelopes"></a><span data-ttu-id="ab03f-125">プロパティおよびエンベロープの処理</span><span class="sxs-lookup"><span data-stu-id="ab03f-125">Processing Properties and Envelopes</span></span>  
 <span data-ttu-id="ab03f-126">処理命令はエンベロープ用に維持されないので、フラット ファイル アセンブラー設定の次の組み合わせは、処理命令を持つ最も外側にあるエンベロープのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ab03f-126">Because processing instructions are not preserved for the envelopes, the following combination of flat file assembler settings results in only the outermost envelope having the processing instruction:</span></span>  
  
-   <span data-ttu-id="ab03f-127">**処理命令スコープ**プロパティ「封筒」に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab03f-127">**Processing instruction scope** property set to "Envelope."</span></span>  
  
-   <span data-ttu-id="ab03f-128">**処理命令の追加**プロパティを「追加」に設定</span><span class="sxs-lookup"><span data-stu-id="ab03f-128">**Add processing instructions** property set to "Append."</span></span>  
  
 <span data-ttu-id="ab03f-129">エンベロープは、アセンブラーで指定される処理命令を使用して**追加処理命令テキストの**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ab03f-129">The envelope would use the processing instruction specified in the assembler's **Add Processing instructions text** property.</span></span>  
  
 <span data-ttu-id="ab03f-130">いずれか、外部または内部エンベロープを受信メッセージで指定されている、既存の処理命令は出力メッセージに存在できません。</span><span class="sxs-lookup"><span data-stu-id="ab03f-130">Any existing processing instructions in either the outer or inner envelope(s), as specified in the incoming message, will not be present in the output message(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab03f-131">参照</span><span class="sxs-lookup"><span data-stu-id="ab03f-131">See Also</span></span>  
 <span data-ttu-id="ab03f-132">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ab03f-132">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="ab03f-133">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="ab03f-133">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="ab03f-134">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="ab03f-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)