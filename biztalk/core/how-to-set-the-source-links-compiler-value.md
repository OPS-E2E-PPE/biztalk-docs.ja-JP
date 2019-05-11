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
ms.openlocfilehash: cb6d3a08cf1cc4f22ea339d74a1b7ca2de081a37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334218"
---
# <a name="how-to-set-the-source-links-compiler-value"></a><span data-ttu-id="47fe6-102">送信元リンクのコンパイラ値を設定する方法</span><span class="sxs-lookup"><span data-stu-id="47fe6-102">How to Set the Source Links Compiler Value</span></span>
<span data-ttu-id="47fe6-103">使用することができます、**ソース リンク**値が送信元ノードから取得され、送信先ノードに適用する方法を指定するリンクのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="47fe6-103">You can use the **Source Links** property of a link to specify how a value is retrieved from the source node and applied to the destination node.</span></span> <span data-ttu-id="47fe6-104">このトピックでは、使用可能な選択肢とそれらの間で選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47fe6-104">This topic explains the available choices and how to choose among them.</span></span>  
  
### <a name="to-set-the-source-links-link-property"></a><span data-ttu-id="47fe6-105">送信元のリンクのリンクのプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="47fe6-105">To set the Source Links link property</span></span>  
  
1. <span data-ttu-id="47fe6-106">BizTalk マッパーのグリッド ページで、リンクをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="47fe6-106">In BizTalk Mapper, in a grid page, click a link to select it.</span></span>  
  
    <span data-ttu-id="47fe6-107">グリッド ページ内の選択したリンクのエンドポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="47fe6-107">The endpoints of a selected link in the grid page are highlighted.</span></span>  
  
2. <span data-ttu-id="47fe6-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ソース リンク**プロパティを次の選択肢のいずれか。</span><span class="sxs-lookup"><span data-stu-id="47fe6-108">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, set the **Source Links** property to one of the following choices:</span></span>  
  
   -   <span data-ttu-id="47fe6-109">**名前をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="47fe6-109">**Copy Name.**</span></span> <span data-ttu-id="47fe6-110">送信元スキーマ ノードの名前は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="47fe6-110">The name of the node in the source schema is used as the value of the linked node in the destination schema.</span></span>  
  
   -   <span data-ttu-id="47fe6-111">**テキスト値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="47fe6-111">**Copy Text Value.**</span></span> <span data-ttu-id="47fe6-112">(要素データまたは属性値) の送信元スキーマ内のノードに対応する値は、送信先スキーマのリンク先ノードの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="47fe6-112">The value corresponding to the node in the source schema (element data or an attribute value) is used as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="47fe6-113">このオプションは、既定値です。</span><span class="sxs-lookup"><span data-stu-id="47fe6-113">This choice is the default.</span></span> <span data-ttu-id="47fe6-114">たとえば、 `<Node>Hello<Name>Chris</Name>Barry</Node>` 「こんにちは」になります。</span><span class="sxs-lookup"><span data-stu-id="47fe6-114">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello".</span></span>  
  
   -   <span data-ttu-id="47fe6-115">**テキストとサブコンテンツの値をコピーします。**</span><span class="sxs-lookup"><span data-stu-id="47fe6-115">**Copy Text and Subcontent Value.**</span></span> <span data-ttu-id="47fe6-116">レコード ノードとそのすべての子ノードとその子ノードの値に対応する値をソース スキーマ (要素データおよび属性値) は、送信先スキーマのリンク先ノードの値として結合されます。</span><span class="sxs-lookup"><span data-stu-id="47fe6-116">The value corresponding to the record node, and the value of all its child nodes, and their child nodes, in the source schema (element data and attribute values) are combined as the value of the linked node in the destination schema.</span></span> <span data-ttu-id="47fe6-117">たとえば、 `<Node>Hello<Name>Chris</Name>Barry</Node>` "こんにちは Chris Barry"になります。</span><span class="sxs-lookup"><span data-stu-id="47fe6-117">For example, `<Node>Hello<Name>Chris</Name>Barry</Node>` would result in "Hello Chris Barry".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fe6-118">参照</span><span class="sxs-lookup"><span data-stu-id="47fe6-118">See Also</span></span>  
 <span data-ttu-id="47fe6-119">[リンクを使用してレコードを指定して、フィールド マッピング](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="47fe6-119">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="47fe6-120">コンパイラ ディレクティブおよびリンク</span><span class="sxs-lookup"><span data-stu-id="47fe6-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)