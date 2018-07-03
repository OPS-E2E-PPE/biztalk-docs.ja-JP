---
title: ソースを設定する方法は、コンパイラの値をリンク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ad777bc5b4df2717d20fd95aa60fdf5d59d1f6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975171"
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="0240e-102">送信元リンクのコンパイラ値を設定する方法</span><span class="sxs-lookup"><span data-stu-id="0240e-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="0240e-103">使用することができます、**ソース リンク**値が送信元ノードから取得され、送信先ノードに適用する方法を指定するリンクのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="0240e-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="0240e-104">このトピックでは、利用可能な選択肢と具体的な選択方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0240e-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="0240e-105">[送信元のリンク] プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="0240e-105">To set the Source Links link property</span></span>  
  
1. <span data-ttu-id="0240e-106">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="0240e-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="0240e-107">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0240e-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="0240e-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ソース リンク**プロパティを次の選択肢のいずれか。</span><span class="sxs-lookup"><span data-stu-id="0240e-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="0240e-109">**名前をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="0240e-109">**Copy Name.**</span></span> <span data-ttu-id="0240e-110">: 送信元スキーマにおけるノード名は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0240e-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
   -   <span data-ttu-id="0240e-111">**テキスト値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="0240e-111">**Copy Text Value.**</span></span> <span data-ttu-id="0240e-112">: 送信元スキーマのノードに対応する値 (要素データまたは属性データ) は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0240e-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="0240e-113">これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="0240e-113">This choice is the default.</span></span> <span data-ttu-id="0240e-114">たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello" のようになります。</span><span class="sxs-lookup"><span data-stu-id="0240e-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
   -   <span data-ttu-id="0240e-115">**テキストとサブコンテンツの値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="0240e-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="0240e-116">送信元スキーマの [レコード] ノードに対応する値と、そのすべての子孫ノードの値 (要素データおよび属性値) が結合され、送信先スキーマのリンク先ノードの値となります。</span><span class="sxs-lookup"><span data-stu-id="0240e-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="0240e-117">たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello Chris Barry" のようになります。</span><span class="sxs-lookup"><span data-stu-id="0240e-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0240e-118">参照</span><span class="sxs-lookup"><span data-stu-id="0240e-118">See Also</span></span>  
 <span data-ttu-id="0240e-119">[リンクを使用してレコードを指定して、フィールド マッピング](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0240e-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="0240e-120">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="0240e-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)