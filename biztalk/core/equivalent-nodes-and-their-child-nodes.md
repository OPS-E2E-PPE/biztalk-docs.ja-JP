---
title: 等価のノードとその子ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a85c6a1-6121-4849-b958-7c4bd1c7c552
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38e472edca428ea010c0fa6200886c5b7e8b41d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349285"
---
# <a name="equivalent-nodes-and-their-child-nodes"></a><span data-ttu-id="858db-102">等価のノードとその子ノード</span><span class="sxs-lookup"><span data-stu-id="858db-102">Equivalent Nodes and Their Child Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="858db-103">概要</span><span class="sxs-lookup"><span data-stu-id="858db-103">Overview</span></span>
<span data-ttu-id="858db-104">**\<同等\>** ノードとその子を使ってスキーマ ツリーで複雑なデータの種類のポリモーフィズムの出現回数を表示します。</span><span class="sxs-lookup"><span data-stu-id="858db-104">The **\<Equivalent\>** node and its children are used in the schema tree to display occurrences of complex data type polymorphism.</span></span> <span data-ttu-id="858db-105">1 つの複合データ型を別の複合データ型から派生する基本の複雑なデータ型が指定されている場所のインスタンス メッセージで発生するこれらのデータ型のいずれかの XSD における多態性が許可されます。</span><span class="sxs-lookup"><span data-stu-id="858db-105">When you derive one complex data type from another complex data type, polymorphism within XSD allows either of these data types to occur in instance messages in locations for which the base complex data type has been specified.</span></span> <span data-ttu-id="858db-106">スキーマの検証中に特定の場所で複数の複雑なデータ型のいずれかが許可されているという事実によって表される暗黙的に関連付けられている基本の複雑なデータ型の名前、**基本**属性、の**拡張子**または**制限**派生複合データ型の要素。</span><span class="sxs-lookup"><span data-stu-id="858db-106">During schema validation, the fact that one of multiple possible complex data types is allowed at a particular location is represented implicitly by the base complex data type name associated with the **base** attribute of the **extension** or **restriction** elements of the derived complex data types.</span></span> <span data-ttu-id="858db-107">スキーマ ツリーで、このポリモーフィズムをより明確に、 **\<同等\>** ノードとその子ノードが明示的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="858db-107">To make this polymorphism more obvious in the schema tree, the **\<Equivalent\>** node and its child nodes are displayed explicitly.</span></span>  

 <span data-ttu-id="858db-108">**\<同等\>** ノードが出現するインスタンスでは、その位置で発生する可能性が複数の複合データ型があることを示す、基本の複雑なデータ型の子ノードとして表示されますメッセージ。</span><span class="sxs-lookup"><span data-stu-id="858db-108">The **\<Equivalent\>** node is displayed as a child node of occurrences of the base complex data type, indicating that there are multiple complex data types that could occur at that position in an instance message.</span></span> <span data-ttu-id="858db-109">子ノード、 **\<同等\>** ノードは、の値として表示されます、**名前**属性に対応する**complexType**山かっこ内に表示される、ポリモーフィズムの XSD 表記内の要素 (\<名前\>)。</span><span class="sxs-lookup"><span data-stu-id="858db-109">The child nodes of the **\<Equivalent\>** node are displayed as the value of the **name** attribute of the corresponding **complexType** element in the XSD representation of the polymorphism, displayed within angle brackets (\<name\>).</span></span>  

 <span data-ttu-id="858db-110">**\<同等\>** ノードとその子はそれらに関連付けられている 2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="858db-110">The **\<Equivalent\>** node and its children each have only two properties associated with them:</span></span>  

-   <span data-ttu-id="858db-111">**\<等価\>** ノード。**ノード名**と**基本データ型**</span><span class="sxs-lookup"><span data-stu-id="858db-111">**\<Equivalent\>** node: **Node Name** and **Base Type**</span></span>

-   <span data-ttu-id="858db-112">子ノード:**ノード名**と**派生型**</span><span class="sxs-lookup"><span data-stu-id="858db-112">Child nodes: **Node Name** and **Derivation Type**</span></span>

<span data-ttu-id="858db-113">これらのプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="858db-113">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="xsd-representation"></a><span data-ttu-id="858db-114">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="858db-114">XSD representation</span></span>  
 <span data-ttu-id="858db-115">直接表す XSD 表記ではありません、 **\<同等\>** ノードとその子。</span><span class="sxs-lookup"><span data-stu-id="858db-115">There is no direct XSD representation of the **\<Equivalent\>** node and its children.</span></span> <span data-ttu-id="858db-116">このノードは、複雑なにスキーマ ツリー内で使用されるデータ型のポリモーフィズム性を一見して明らかです。</span><span class="sxs-lookup"><span data-stu-id="858db-116">This node is used within the schema tree to make complex data type polymorphism more visible and obvious.</span></span>  

## <a name="see-also"></a><span data-ttu-id="858db-117">参照</span><span class="sxs-lookup"><span data-stu-id="858db-117">See Also</span></span>  
- [<span data-ttu-id="858db-118">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="858db-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="858db-119">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="858db-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="858db-120">**シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="858db-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="858db-121">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="858db-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
