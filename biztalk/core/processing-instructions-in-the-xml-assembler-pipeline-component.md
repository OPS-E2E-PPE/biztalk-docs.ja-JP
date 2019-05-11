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
ms.openlocfilehash: 3366ed738020ebf90fadfb104f860f0cdb952168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396988"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="159f8-102">手順については、XML アセンブラー パイプライン コンポーネントでの処理</span><span class="sxs-lookup"><span data-stu-id="159f8-102">Processing Instructions in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="159f8-103">処理命令は、XML ドキュメントを処理するアプリケーションに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="159f8-103">Processing instructions provide information to the application that processes an XML document.</span></span> <span data-ttu-id="159f8-104">このような情報は、ドキュメントを処理する方法に関する指示を含めることができ、それを表示する方法。</span><span class="sxs-lookup"><span data-stu-id="159f8-104">Such information may include instructions about how to process the document, how to display it, and so on.</span></span>  
  
 <span data-ttu-id="159f8-105">処理命令は、XML ドキュメントに追加、**処理命令の追加**プロパティ (または同等の**XMLNorm.ProcessingInstructionOption**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="159f8-105">Processing instructions are added to an XML document by the **Add processing instructions** property (or the equivalent **XMLNorm.ProcessingInstructionOption** property on the message context).</span></span> <span data-ttu-id="159f8-106">処理命令テキストを指定した、**処理命令テキストの追加**プロパティ (または同等の**XMLNorm.ProcessingInstruction**メッセージ コンテキストのプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="159f8-106">Processing instruction text is specified with the **Add processing instructions text** property (or the equivalent **XMLNorm.ProcessingInstruction** property on the message context).</span></span>  
  
 <span data-ttu-id="159f8-107">**処理命令の追加**プロパティ (または**XMLNorm.ProcessingInstructionOption**プロパティ) は、次の表で説明されている 3 つの値。</span><span class="sxs-lookup"><span data-stu-id="159f8-107">The **Add processing instructions** property (or **XMLNorm.ProcessingInstructionOption** property) has three possible values, which are described in the following table.</span></span>  
  
|<span data-ttu-id="159f8-108">値</span><span class="sxs-lookup"><span data-stu-id="159f8-108">Value</span></span>|<span data-ttu-id="159f8-109">値</span><span class="sxs-lookup"><span data-stu-id="159f8-109">Value</span></span>|<span data-ttu-id="159f8-110">説明</span><span class="sxs-lookup"><span data-stu-id="159f8-110">Description</span></span>|  
|-----------|-----------|-----------------|  
|<span data-ttu-id="159f8-111">追加</span><span class="sxs-lookup"><span data-stu-id="159f8-111">Append</span></span>|<span data-ttu-id="159f8-112">0</span><span class="sxs-lookup"><span data-stu-id="159f8-112">0</span></span>|<span data-ttu-id="159f8-113">XML アセンブラーからの新しい処理命令は、ドキュメントの先頭にある処理命令に付加されます。</span><span class="sxs-lookup"><span data-stu-id="159f8-113">New processing instructions from the XML Assembler are appended to the processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="159f8-114">新規作成します。</span><span class="sxs-lookup"><span data-stu-id="159f8-114">Create new</span></span>|<span data-ttu-id="159f8-115">1</span><span class="sxs-lookup"><span data-stu-id="159f8-115">1</span></span>|<span data-ttu-id="159f8-116">XML アセンブラーからの新しい処理命令は、ドキュメントの先頭にある既存の処理命令を上書きします。</span><span class="sxs-lookup"><span data-stu-id="159f8-116">New processing instructions from the XML Assembler overwrite existing processing instructions at the beginning of the document.</span></span>|  
|<span data-ttu-id="159f8-117">Ignore</span><span class="sxs-lookup"><span data-stu-id="159f8-117">Ignore</span></span>|<span data-ttu-id="159f8-118">2</span><span class="sxs-lookup"><span data-stu-id="159f8-118">2</span></span>|<span data-ttu-id="159f8-119">ドキュメントの先頭にある処理命令が削除されます。</span><span class="sxs-lookup"><span data-stu-id="159f8-119">Processing instructions at the beginning of the document are removed.</span></span>|  
  
 <span data-ttu-id="159f8-120">処理命令 (またはメッセージ コンテキストのプロパティ) のメッセージ コンテキストで指定されたペアは、パイプライン デザイナーで指定されるプロパティ ペアよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="159f8-120">The pair of processing instructions (or message context properties) specified on a message context take precedence over the property pair specified in Pipeline Designer.</span></span> <span data-ttu-id="159f8-121">たとえば場合、 **XMLNorm.ProcessingInstructionOption**として指定されて**新規作成**(1) と**XMLNorm.ProcessingInstruction**が指定されていない空の処理命令は、既存の処理命令が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="159f8-121">For example, if **XMLNorm.ProcessingInstructionOption** is specified as **Create new** (1) and **XMLNorm.ProcessingInstruction** is not specified, an empty processing instruction will replace an existing processing instruction.</span></span>  
  
 <span data-ttu-id="159f8-122">別の例として場合**XMLNorm.ProcessingInstruction**が指定されて、 **XMLNorm.ProcessingInstructionOption**は、メッセージ コンテキストからプロパティのいずれもが使用されます。</span><span class="sxs-lookup"><span data-stu-id="159f8-122">As another example, if **XMLNorm.ProcessingInstruction** is specified but **XMLNorm.ProcessingInstructionOption** is not, none of the properties from the message context are used.</span></span> <span data-ttu-id="159f8-123">この場合、パイプライン デザイナーからの処理命令が使用されます。</span><span class="sxs-lookup"><span data-stu-id="159f8-123">In this case, the processing instructions from Pipeline Designer are used.</span></span>  
  
 <span data-ttu-id="159f8-124">既定では、**処理命令の追加**に設定されている**Append**、および**処理命令テキストの追加**が空です。</span><span class="sxs-lookup"><span data-stu-id="159f8-124">By default, **Add processing instructions** is set to **Append**, and **Add processing instructions text** is empty.</span></span>  
  
## <a name="processing-properties-and-envelopes"></a><span data-ttu-id="159f8-125">プロパティおよびエンベロープの処理</span><span class="sxs-lookup"><span data-stu-id="159f8-125">Processing Properties and Envelopes</span></span>  
 <span data-ttu-id="159f8-126">処理命令はエンベロープ用保持されず、ため、処理命令を持つ最も外側にあるエンベロープのみにフラット ファイル アセンブラー設定の次の組み合わせが発生します。</span><span class="sxs-lookup"><span data-stu-id="159f8-126">Because processing instructions are not preserved for the envelopes, the following combination of flat file assembler settings results in only the outermost envelope having the processing instruction:</span></span>  
  
- <span data-ttu-id="159f8-127">**処理命令スコープ**プロパティが「エンベロープ」に設定</span><span class="sxs-lookup"><span data-stu-id="159f8-127">**Processing instruction scope** property set to "Envelope."</span></span>  
  
- <span data-ttu-id="159f8-128">**処理命令の追加**プロパティを「追加」「に設定</span><span class="sxs-lookup"><span data-stu-id="159f8-128">**Add processing instructions** property set to "Append."</span></span>  
  
  <span data-ttu-id="159f8-129">アセンブラーので指定される処理命令はエンベロープを使用して、**追加処理命令テキストの**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="159f8-129">The envelope would use the processing instruction specified in the assembler's **Add Processing instructions text** property.</span></span>  
  
  <span data-ttu-id="159f8-130">いずれか、外部または内部エンベロープを着信メッセージで指定されている既存の処理手順については出力メッセージに存在できません。</span><span class="sxs-lookup"><span data-stu-id="159f8-130">Any existing processing instructions in either the outer or inner envelope(s), as specified in the incoming message, will not be present in the output message(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159f8-131">参照</span><span class="sxs-lookup"><span data-stu-id="159f8-131">See Also</span></span>  
 <span data-ttu-id="159f8-132">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="159f8-132">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="159f8-133">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="159f8-133">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="159f8-134">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="159f8-134">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)