---
title: "等価のノードとその子ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05c5603cf1882aa7b262ecc5393a9d91dc93da10
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="equivalent-nodes-and-their-child-nodes"></a><span data-ttu-id="c937f-102">等価のノードとその子ノード</span><span class="sxs-lookup"><span data-stu-id="c937f-102">Equivalent Nodes and Their Child Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="c937f-103">概要</span><span class="sxs-lookup"><span data-stu-id="c937f-103">Overview</span></span>
<span data-ttu-id="c937f-104">**\<等価\>**ノードとその子で使用、スキーマ ツリーを複雑なデータの種類のポリモーフィズムの出現を表示します。</span><span class="sxs-lookup"><span data-stu-id="c937f-104">The **\<Equivalent\>** node and its children are used in the schema tree to display occurrences of complex data type polymorphism.</span></span> <span data-ttu-id="c937f-105">ある複合データ型から別の複合データ型を派生させた場合、XSD における多態性により、ベースとなる複合データ型が指定されているインスタンス メッセージ内の対応位置には、この 2 つのデータ型のどちらでも出現できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c937f-105">When you derive one complex data type from another complex data type, polymorphism within XSD allows either of these data types to occur in instance messages in locations for which the base complex data type has been specified.</span></span> <span data-ttu-id="c937f-106">スキーマの検証中に特定の場所に複数の複合データ型の 1 つは許可されているという事実によって表される暗黙的に関連付けられている基本の複雑なデータ型の名前、**基本**の属性**拡張子**または**制限**派生複合データ型の要素。</span><span class="sxs-lookup"><span data-stu-id="c937f-106">During schema validation, the fact that one of multiple possible complex data types is allowed at a particular location is represented implicitly by the base complex data type name associated with the **base** attribute of the **extension** or **restriction** elements of the derived complex data types.</span></span> <span data-ttu-id="c937f-107">スキーマ ツリーで、この多態性をより明確にする、 **\<等価\>**ノードとその子ノードが明示的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c937f-107">To make this polymorphism more obvious in the schema tree, the **\<Equivalent\>** node and its child nodes are displayed explicitly.</span></span>  
  
 <span data-ttu-id="c937f-108">**\<等価\>**発生インスタンス内の位置で発生する可能性があります複数の複合データ型があることを示す、ベース複合データ型の子ノードとしてノードが表示されますメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c937f-108">The **\<Equivalent\>** node is displayed as a child node of occurrences of the base complex data type, indicating that there are multiple complex data types that could occur at that position in an instance message.</span></span> <span data-ttu-id="c937f-109">子ノード、 **\<等価\>**ノードの値として表示されます、**名前**の対応する属性**complexType**山かっこ内に表示される、ポリモーフィズムの XSD 表記内の要素 (\<名前\>)。</span><span class="sxs-lookup"><span data-stu-id="c937f-109">The child nodes of the **\<Equivalent\>** node are displayed as the value of the **name** attribute of the corresponding **complexType** element in the XSD representation of the polymorphism, displayed within angle brackets (\<name\>).</span></span>  
  
 <span data-ttu-id="c937f-110">**\<等価\>**ノードとその子の各それらに関連付けられている 2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="c937f-110">The **\<Equivalent\>** node and its children each have only two properties associated with them:</span></span>  
  
-   <span data-ttu-id="c937f-111">**\<等価\>**ノード:**ノード名**と**基本データ型**</span><span class="sxs-lookup"><span data-stu-id="c937f-111">**\<Equivalent\>** node: **Node Name** and **Base Type**</span></span>
  
-   <span data-ttu-id="c937f-112">子ノード:**ノード名**と**派生型**</span><span class="sxs-lookup"><span data-stu-id="c937f-112">Child nodes: **Node Name** and **Derivation Type**</span></span>

<span data-ttu-id="c937f-113">これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c937f-113">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="c937f-114">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="c937f-114">XSD representation</span></span>  
 <span data-ttu-id="c937f-115">直接の XSD 表記ではありません、 **\<等価\>**ノードとその子。</span><span class="sxs-lookup"><span data-stu-id="c937f-115">There is no direct XSD representation of the **\<Equivalent\>** node and its children.</span></span> <span data-ttu-id="c937f-116">このノードは、スキーマ ツリー内で複合データ型の多態性を一見してわかるようにするために使用されるノードです。</span><span class="sxs-lookup"><span data-stu-id="c937f-116">This node is used within the schema tree to make complex data type polymorphism more visible and obvious.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c937f-117">参照</span><span class="sxs-lookup"><span data-stu-id="c937f-117">See Also</span></span>  
-  [<span data-ttu-id="c937f-118">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="c937f-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="c937f-119">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="c937f-119">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="c937f-120">**シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="c937f-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="c937f-121">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="c937f-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)