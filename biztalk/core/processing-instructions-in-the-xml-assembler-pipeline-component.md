---
title: 手順については、XML アセンブラー パイプライン コンポーネントでの処理 |Microsoft Docs
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
ms.openlocfilehash: df3b56a3703e56dd4b3f474b4846999bae9858f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016108"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="05fbd-102">手順については、XML アセンブラー パイプライン コンポーネントでの処理</span><span class="sxs-lookup"><span data-stu-id="05fbd-102">Processing Instructions in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="05fbd-103">処理命令は、XML ドキュメントを処理するアプリケーションに対する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="05fbd-103">Processing instructions provide information to the application that processes an XML document.</span></span> <span data-ttu-id="05fbd-104">この情報には、ドキュメントの処理方法や表示方法などの命令が含まれます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-104">Such information may include instructions about how to process the document, how to display it, and so on.</span></span>  
  
 <span data-ttu-id="05fbd-105">処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="05fbd-105">Processing instructions are added to an XML document by the **Add processing instructions** property (or the equivalent **XMLNorm.ProcessingInstructionOption** property on the message context).</span></span> <span data-ttu-id="05fbd-106">処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="05fbd-106">Processing instruction text is specified with the **Add processing instructions text** property (or the equivalent **XMLNorm.ProcessingInstruction** property on the message context).</span></span>  
  
 <span data-ttu-id="05fbd-107">**処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明されている 3 つの値。</span><span class="sxs-lookup"><span data-stu-id="05fbd-107">The **Add processing instructions** property (or **XMLNorm.ProcessingInstructionOption** property) has three possible values, which are described in the following table.</span></span>  
  
|<span data-ttu-id="05fbd-108">値</span><span class="sxs-lookup"><span data-stu-id="05fbd-108">Value</span></span>|<span data-ttu-id="05fbd-109">値</span><span class="sxs-lookup"><span data-stu-id="05fbd-109">Value</span></span>|<span data-ttu-id="05fbd-110">説明</span><span class="sxs-lookup"><span data-stu-id="05fbd-110">Description</span></span>|  
|-----------|-----------|-----------------|  
|<span data-ttu-id="05fbd-111">追加</span><span class="sxs-lookup"><span data-stu-id="05fbd-111">Append</span></span>|<span data-ttu-id="05fbd-112">0</span><span class="sxs-lookup"><span data-stu-id="05fbd-112">0</span></span>|<span data-ttu-id="05fbd-113">XML アセンブラーからの新しい処理命令は、ドキュメントの最初の処理命令に追加されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-113">New processing instructions from the XML Assembler are appended to the processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="05fbd-114">新規作成します。</span><span class="sxs-lookup"><span data-stu-id="05fbd-114">Create new</span></span>|<span data-ttu-id="05fbd-115">1</span><span class="sxs-lookup"><span data-stu-id="05fbd-115">1</span></span>|<span data-ttu-id="05fbd-116">XML アセンブラーからの新しい処理命令は、ドキュメントの最初の既存の処理命令を上書きします。</span><span class="sxs-lookup"><span data-stu-id="05fbd-116">New processing instructions from the XML Assembler overwrite existing processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="05fbd-117">Ignore</span><span class="sxs-lookup"><span data-stu-id="05fbd-117">Ignore</span></span>|<span data-ttu-id="05fbd-118">2</span><span class="sxs-lookup"><span data-stu-id="05fbd-118">2</span></span>|<span data-ttu-id="05fbd-119">ドキュメントの最初の処理命令は、削除されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-119">Processing instructions at the beginning of the document are removed.</span></span>|  
  
 <span data-ttu-id="05fbd-120">メッセージ コンテキストで指定される処理命令 (またはメッセージ コンテキスト プロパティ) のペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-120">The pair of processing instructions (or message context properties) specified on a message context take precedence over the property pair specified in Pipeline Designer.</span></span> <span data-ttu-id="05fbd-121">たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定されて**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-121">For example, if **XMLNorm.ProcessingInstructionOption** is specified as **Create new** (1) and **XMLNorm.ProcessingInstruction** is not specified, an empty processing instruction will replace an existing processing instruction.</span></span>  
  
 <span data-ttu-id="05fbd-122">別の例として場合**XMLNorm.ProcessingInstruction**が指定されて、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれもが使用されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-122">As another example, if **XMLNorm.ProcessingInstruction** is specified but **XMLNorm.ProcessingInstructionOption** is not, none of the properties from the message context are used.</span></span> <span data-ttu-id="05fbd-123">この場合、パイプライン デザイナーからの処理命令が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-123">In this case, the processing instructions from Pipeline Designer are used.</span></span>  
  
 <span data-ttu-id="05fbd-124">既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。</span><span class="sxs-lookup"><span data-stu-id="05fbd-124">By default, **Add processing instructions** is set to **Append**, and **Add processing instructions text** is empty.</span></span>  
  
## <a name="processing-properties-and-envelopes"></a><span data-ttu-id="05fbd-125">プロパティおよびエンベロープの処理</span><span class="sxs-lookup"><span data-stu-id="05fbd-125">Processing Properties and Envelopes</span></span>  
 <span data-ttu-id="05fbd-126">処理命令はエンベロープ用に維持されないので、フラット ファイル アセンブラー設定の次の組み合わせは、処理命令を持つ最も外側にあるエンベロープのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="05fbd-126">Because processing instructions are not preserved for the envelopes, the following combination of flat file assembler settings results in only the outermost envelope having the processing instruction:</span></span>  
  
- <span data-ttu-id="05fbd-127">**処理命令スコープ**プロパティが「エンベロープ」に設定</span><span class="sxs-lookup"><span data-stu-id="05fbd-127">**Processing instruction scope** property set to "Envelope."</span></span>  
  
- <span data-ttu-id="05fbd-128">**処理命令の追加**プロパティを「追加」「に設定</span><span class="sxs-lookup"><span data-stu-id="05fbd-128">**Add processing instructions** property set to "Append."</span></span>  
  
  <span data-ttu-id="05fbd-129">アセンブラーので指定される処理命令はエンベロープを使用して、**追加処理命令テキストの**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="05fbd-129">The envelope would use the processing instruction specified in the assembler's **Add Processing instructions text** property.</span></span>  
  
  <span data-ttu-id="05fbd-130">いずれか、外部または内部エンベロープを着信メッセージで指定されている既存の処理手順については出力メッセージに存在できません。</span><span class="sxs-lookup"><span data-stu-id="05fbd-130">Any existing processing instructions in either the outer or inner envelope(s), as specified in the incoming message, will not be present in the output message(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05fbd-131">参照</span><span class="sxs-lookup"><span data-stu-id="05fbd-131">See Also</span></span>  
 <span data-ttu-id="05fbd-132">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="05fbd-132">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="05fbd-133">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="05fbd-133">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="05fbd-134">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="05fbd-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)