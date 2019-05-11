---
title: XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定 |Microsoft Docs
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
ms.openlocfilehash: 2c6662f65c82a79fb174fe3b97c10fc24351255b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246400"
---
# <a name="xml-information-set-elements-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="aa818-102">XML 情報は、XML アセンブラー パイプライン コンポーネントで要素を設定</span><span class="sxs-lookup"><span data-stu-id="aa818-102">XML Information Set Elements in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="aa818-103">XML アセンブラー コンポーネントは、次のように XML 情報セットの要素を処理します。</span><span class="sxs-lookup"><span data-stu-id="aa818-103">The XML Assembler component handles XML information set elements as follows.</span></span>  
  
|<span data-ttu-id="aa818-104">要素</span><span class="sxs-lookup"><span data-stu-id="aa818-104">Element</span></span>|<span data-ttu-id="aa818-105">説明</span><span class="sxs-lookup"><span data-stu-id="aa818-105">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa818-106">comment</span><span class="sxs-lookup"><span data-stu-id="aa818-106">comment</span></span>|<span data-ttu-id="aa818-107">コメントは、タグと終了、ドキュメント内の XML タグの間で保持されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-107">Comments are preserved between opening and closing XML tags in the document.</span></span>|  
|<span data-ttu-id="aa818-108">CDATA</span><span class="sxs-lookup"><span data-stu-id="aa818-108">CDATA</span></span>|<span data-ttu-id="aa818-109">CDATA はドキュメント内の XML タグを開いたり閉じたり間保持されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-109">CDATA is preserved between opening and closing XML tags in the document.</span></span> <span data-ttu-id="aa818-110">CDATA の値がないプロパティの昇格に使用または識別フィールド。</span><span class="sxs-lookup"><span data-stu-id="aa818-110">CDATA values are not used for property promotion or distinguished fields.</span></span>|  
|<span data-ttu-id="aa818-111">処理命令</span><span class="sxs-lookup"><span data-stu-id="aa818-111">processing instructions</span></span>|<span data-ttu-id="aa818-112">それらの値に基づいて、ドキュメントの XML タグが処理される前に置かれた処理命令 (詳細については、次を参照してください。 [XML アセンブラー パイプライン コンポーネントにおける処理命令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md))。</span><span class="sxs-lookup"><span data-stu-id="aa818-112">Processing instructions located before the document XML tag are handled based on their value (for more information, see [Processing Instructions in the XML Assembler Pipeline Component](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)).</span></span> <span data-ttu-id="aa818-113">処理命令の開始タグと終了タグは保持されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-113">Processing instructions between document open and close tags are preserved.</span></span> <span data-ttu-id="aa818-114">すべての命令は、前に、またはエンベロープの後に、XML 終了タグの後の処理命令は無視されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-114">Processing instructions after the closing XML tag are ignored, as are any instructions before, in, or after the envelope.</span></span>|  
|<span data-ttu-id="aa818-115">XML 宣言</span><span class="sxs-lookup"><span data-stu-id="aa818-115">XML declaration</span></span>|<span data-ttu-id="aa818-116">XML 宣言文字列など`<?xml version='1.0'? encoding='UTF-8'>`、XML アセンブラー パイプライン コンポーネントによって保持される場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa818-116">The XML declaration string, such as `<?xml version='1.0'? encoding='UTF-8'>`, may be preserved by the XML Assembler pipeline component.</span></span> <span data-ttu-id="aa818-117">これによって制御されますが、 **XML 宣言の追加**プロパティ、またはそれと同等のメッセージ コンテキスト**XMLNorm.AddXMLDeclaration**します。</span><span class="sxs-lookup"><span data-stu-id="aa818-117">This is controlled by the **Add XML declaration** property, or its equivalent on the message context, **XMLNorm.AddXMLDeclaration**.</span></span><br /><br /> <span data-ttu-id="aa818-118">このオプション設定されている場合**True** XML 宣言は、ドキュメントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-118">If this option is set to **True** then the XML declaration will be added to the document.</span></span> <span data-ttu-id="aa818-119">既に XML 宣言が存在する場合は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="aa818-119">If the XML declaration already existed, it will be overwritten.</span></span><br /><br /> <span data-ttu-id="aa818-120">このオプション設定されている場合**False**XML 宣言が追加されないことや、既存の XML 宣言は削除されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-120">If this option is set to **False**, no XML declaration will be added and any existing XML declaration will be removed.</span></span> <span data-ttu-id="aa818-121">メッセージのコンテキストでこのプロパティの値は、パイプライン デザイナーで指定された値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="aa818-121">The value of this property in the message context takes precedence over the value specified in Pipeline Designer.</span></span><br /><br /> <span data-ttu-id="aa818-122">既定値:**True** (常には、XML 宣言を追加)</span><span class="sxs-lookup"><span data-stu-id="aa818-122">Default value: **True** (the XML declaration is always added)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa818-123">参照</span><span class="sxs-lookup"><span data-stu-id="aa818-123">See Also</span></span>  
 <span data-ttu-id="aa818-124">[XML アセンブラー パイプライン コンポーネント](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="aa818-124">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="aa818-125">[XML アセンブラー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="aa818-125">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="aa818-126">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="aa818-126">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)