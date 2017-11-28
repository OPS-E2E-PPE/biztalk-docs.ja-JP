---
title: "ソースを設定する方法は、コンパイラの値をリンク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edd1d73-78d1-468d-806a-3f6f258ee375
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a7adf74d0b186f338220a383da6b6831013312
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="c07fd-102">送信元リンクのコンパイラ値を設定する方法</span><span class="sxs-lookup"><span data-stu-id="c07fd-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="c07fd-103">使用することができます、**送信元のリンク**値を送信元ノードから取得され、移行先ノードに適用する方法を指定するリンクのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c07fd-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="c07fd-104">このトピックでは、利用可能な選択肢と具体的な選択方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c07fd-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="c07fd-105">[送信元のリンク] プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="c07fd-105">To set the Source Links link property</span></span>  
  
1.  <span data-ttu-id="c07fd-106">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="c07fd-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
     <span data-ttu-id="c07fd-107">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="c07fd-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2.  <span data-ttu-id="c07fd-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、設定、**送信元のリンク**プロパティに、次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="c07fd-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
    -   <span data-ttu-id="c07fd-109">**名前をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="c07fd-109">**Copy Name.**</span></span> <span data-ttu-id="c07fd-110">: 送信元スキーマにおけるノード名は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c07fd-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
    -   <span data-ttu-id="c07fd-111">**テキスト値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="c07fd-111">**Copy Text Value.**</span></span> <span data-ttu-id="c07fd-112">: 送信元スキーマのノードに対応する値 (要素データまたは属性データ) は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c07fd-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="c07fd-113">これは既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="c07fd-113">This choice is the default.</span></span> <span data-ttu-id="c07fd-114">たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello" のようになります。</span><span class="sxs-lookup"><span data-stu-id="c07fd-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
    -   <span data-ttu-id="c07fd-115">**テキストとサブコンテンツの値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="c07fd-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="c07fd-116">送信元スキーマの [レコード] ノードに対応する値と、そのすべての子孫ノードの値 (要素データおよび属性値) が結合され、送信先スキーマのリンク先ノードの値となります。</span><span class="sxs-lookup"><span data-stu-id="c07fd-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="c07fd-117">たとえば、`<Node>Hello<Name>Chris</Name>Barry</Node>` は "Hello Chris Barry" のようになります。</span><span class="sxs-lookup"><span data-stu-id="c07fd-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c07fd-118">参照</span><span class="sxs-lookup"><span data-stu-id="c07fd-118">See Also</span></span>  
 <span data-ttu-id="c07fd-119">[リンクを使用してレコードを指定してフィールドのマッピング](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="c07fd-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="c07fd-120">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="c07fd-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)