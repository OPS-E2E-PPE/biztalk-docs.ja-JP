---
title: XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], processing instructions
- Add XML declaration property
- XMLNorm.AddXMLDeclaration property
- pipeline components, XML Assembler
- XML Assembler [pipeline component], XML information set
ms.assetid: 5a262763-838e-476b-8117-30c94bc1d64a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194b85c88f63036cd74fcd9838aa99e73de6556
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289522"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="1a9fb-102">XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定</span><span class="sxs-lookup"><span data-stu-id="1a9fb-102">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="1a9fb-103">XML アセンブラー コンポーネントでは、各種の XML 要素が次のように扱われます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-103">The XML Assembler component handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="1a9fb-104">要素</span><span class="sxs-lookup"><span data-stu-id="1a9fb-104">Element</span></span>|<span data-ttu-id="1a9fb-105">Description</span><span class="sxs-lookup"><span data-stu-id="1a9fb-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a9fb-106">comment</span><span class="sxs-lookup"><span data-stu-id="1a9fb-106">comment</span></span>|<span data-ttu-id="1a9fb-107">開始タグと終了タグ間のコメントが維持されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-107">Comments are preserved between opening and closing XML tags in the document.</span></span>|  
|<span data-ttu-id="1a9fb-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="1a9fb-108">CDATA</span></span>|<span data-ttu-id="1a9fb-109">開始タグと終了タグ間の CDATA が維持されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-109">CDATA is preserved between opening and closing XML tags in the document.</span></span> <span data-ttu-id="1a9fb-110">プロパティ昇格や識別フィールドについては、CDATA の値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-110">CDATA values are not used for property promotion or distinguished fields.</span></span>|  
|<span data-ttu-id="1a9fb-111">処理命令</span><span class="sxs-lookup"><span data-stu-id="1a9fb-111">processing instructions</span></span>|<span data-ttu-id="1a9fb-112">処理命令、ドキュメントの XML タグが処理される前に置かれた値に基づいて (詳細については、次を参照してください。 [XML アセンブラー パイプライン コンポーネントにおける処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-112">Processing instructions located before the document XML tag are handled based on their value (for more information, see [Processing Instructions in the XML Assembler Pipeline Component](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)).</span></span> <span data-ttu-id="1a9fb-113">開始タグと終了タグの間にある処理命令が維持されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-113">Processing instructions between document open and close tags are preserved.</span></span> <span data-ttu-id="1a9fb-114">エンベロープの前、エンベロープ内、エンベロープの後のいずれの場合も、終了タグの後にある処理命令は無視されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-114">Processing instructions after the closing XML tag are ignored, as are any instructions before, in, or after the envelope.</span></span>|  
|<span data-ttu-id="1a9fb-115">XML 宣言</span><span class="sxs-lookup"><span data-stu-id="1a9fb-115">XML declaration</span></span>|<span data-ttu-id="1a9fb-116">XML 宣言文字列 (`<?xml version='1.0'? encoding='UTF-8'>` など) が XML アセンブラー パイプライン コンポーネントによって維持されるかどうかは、場合によって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-116">The XML declaration string, such as `<?xml version='1.0'? encoding='UTF-8'>`, may be preserved by the XML Assembler pipeline component.</span></span> <span data-ttu-id="1a9fb-117">によって制御されます、 **XML 宣言の追加**プロパティ、またはそれと同等のメッセージ コンテキスト**XMLNorm.AddXMLDeclaration**です。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-117">This is controlled by the **Add XML declaration** property, or its equivalent on the message context, **XMLNorm.AddXMLDeclaration**.</span></span><br /><br /> <span data-ttu-id="1a9fb-118">このオプションが設定されている場合**True** XML 宣言は、ドキュメントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-118">If this option is set to **True** then the XML declaration will be added to the document.</span></span> <span data-ttu-id="1a9fb-119">既に XML 宣言が存在した場合、既存の XML 宣言は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-119">If the XML declaration already existed, it will be overwritten.</span></span><br /><br /> <span data-ttu-id="1a9fb-120">このオプションが設定されている場合**False**XML 宣言が追加されないこと、および既存の XML 宣言は削除されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-120">If this option is set to **False**, no XML declaration will be added and any existing XML declaration will be removed.</span></span> <span data-ttu-id="1a9fb-121">メッセージ コンテキストでは、このプロパティ値は、パイプライン デザイナーで指定されたプロパティ値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="1a9fb-121">The value of this property in the message context takes precedence over the value specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="1a9fb-122">既定値: **True** (常には、XML 宣言を追加)</span><span class="sxs-lookup"><span data-stu-id="1a9fb-122">Default value: **True** (the XML declaration is always added)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a9fb-123">参照</span><span class="sxs-lookup"><span data-stu-id="1a9fb-123">See Also</span></span>  
 <span data-ttu-id="1a9fb-124">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="1a9fb-124">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="1a9fb-125">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="1a9fb-125">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="1a9fb-126">パイプライン AssemblerDisassembler (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1a9fb-126">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)