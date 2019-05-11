---
title: ノード名プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95d9e5bf-7439-4ef4-ad14-e8d3e8eff911
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57d4c558e509cdcd8540795756a3891a286c3fc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263381"
---
# <a name="node-name-property"></a><span data-ttu-id="2c859-102">ノード名プロパティ</span><span class="sxs-lookup"><span data-stu-id="2c859-102">Node Name Property</span></span>
<span data-ttu-id="2c859-103">BizTalk エディターを使用して、スキーマ ツリーにノードを挿入するにはいくつかのノードの名前を変更するものし、されないものもあります。</span><span class="sxs-lookup"><span data-stu-id="2c859-103">As you use BizTalk Editor to insert nodes into the schema tree, some nodes are meant to be renamed and others are not.</span></span> <span data-ttu-id="2c859-104">基本的に、できるし、名前を変更する必要があります**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="2c859-104">Essentially, you can and should rename **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes.</span></span> <span data-ttu-id="2c859-105">これらのノードに付ける名前は、XML 要素と、スキーマによって定義されるメッセージ内の属性の名前になります。</span><span class="sxs-lookup"><span data-stu-id="2c859-105">The names that you give to these nodes will become the names of the XML elements and attributes in the message that the schema defines.</span></span>  
  
 <span data-ttu-id="2c859-106">名前を変更できないノードは、スキーマ ツリーの場合、XML タグの形式で、表示します。以下により (\<) よりも大きいと (\>) 記号。</span><span class="sxs-lookup"><span data-stu-id="2c859-106">In the schema tree, the nodes that you cannot rename are shown in the form of XML tags; that is, with the less than (\<) and greater than (\>) signs.</span></span> <span data-ttu-id="2c859-107">たとえば、**スキーマ**ノード、**グループの選択**ノード、**すべての要素**ノード、および**すべての属性**ノードは、スキーマで表されます名前を持つツリー\<スキーマ\>、\<選択肢\>、\<任意\>、および\<AnyAttribute\>、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="2c859-107">For example, the **Schema** node, **Choice Group** nodes, **Any Element** nodes, and **Any Attribute** nodes are represented in the schema tree with the names \<Schema\>, \<Choice\>, \<Any\>, and \<AnyAttribute\>, respectively.</span></span> <span data-ttu-id="2c859-108">**ノード名**このようなノードのプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="2c859-108">The **Node Name** property for such nodes is read-only.</span></span>  
  
 <span data-ttu-id="2c859-109">内で、指定された**レコード**ノード、2 つを含めることはできません**フィールド属性**と同じ名前のノード。</span><span class="sxs-lookup"><span data-stu-id="2c859-109">Within a given **Record** node, you cannot have two **Field Attribute** nodes with the same name.</span></span> <span data-ttu-id="2c859-110">1 つ以上がただし、**フィールド要素**ノードまたは**レコード**同じの子ノードと同じ名前を持つノード**レコード**ノードで、これらのすべてが同じデータ型である場合に限り(で指定されたとおり、**データ型**プロパティ**フィールド要素**ノード、または**Data Structure Type**の**レコード**ノードの場合)。</span><span class="sxs-lookup"><span data-stu-id="2c859-110">However, you can have more than one **Field Element** node or **Record** node with the same name as child nodes of the same **Record** node, as long as they all have the same data type (as specified by their **Data Type** property for **Field Element** nodes or their **Data Structure Type** for **Record** nodes).</span></span>  
  
 <span data-ttu-id="2c859-111">名前を付ける場合**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード内の属性またはその要素のロールのわかりやすい名前を使用します。スキーマによって定義されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="2c859-111">When you give names to **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, use names that are descriptive of the role of that element or attribute within the message being defined by the schema.</span></span> <span data-ttu-id="2c859-112">たとえば、FirstName は最適の名前、**フィールド要素**ノード アドレス構造に他のユーザー名を格納するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c859-112">For example, FirstName is probably a good choice for the name of a **Field Element** node that will be used to store the first name of someone in an address structure.</span></span> <span data-ttu-id="2c859-113">James 名が発生した XML インスタンス メッセージ内の対応する要素は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2c859-113">In an XML instance message where the first name James occurs, the corresponding element would look like the following.</span></span>  
  
```  
    <FirstName>James</FirstName>  
```  
  
 <span data-ttu-id="2c859-114">名前を変更するときに**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード、おく必要があるすべての文字がノード名に許可されることに注意してくださかった。</span><span class="sxs-lookup"><span data-stu-id="2c859-114">When you are renaming **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, you should be aware that not all characters are allowed in node names.</span></span> <span data-ttu-id="2c859-115">使用できない文字については、次を参照してください。[がノード名における文字エン](../core/which-node-name-characters-get-encoded.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c859-115">For information about these disallowed characters, see [Which Node Name Characters Get Encoded](../core/which-node-name-characters-get-encoded.md).</span></span> <span data-ttu-id="2c859-116">BizTalk エディターには、エンコードすることによって許可されない文字を使用することができますが、このような文字を完全に回避するために簡単ですが多くの場合です。</span><span class="sxs-lookup"><span data-stu-id="2c859-116">Although BizTalk Editor allows you to use disallowed characters by encoding them, it is often simpler to avoid such characters altogether.</span></span> <span data-ttu-id="2c859-117">使用できない文字をエンコードする方法については、「[どのノード名における文字エン](../core/how-node-name-characters-get-encoded.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c859-117">For information about how disallowed characters are encoded, see [How Node Name Characters Get Encoded](../core/how-node-name-characters-get-encoded.md).</span></span>  
  
 <span data-ttu-id="2c859-118">ノード名に禁止されている文字だけでなく、スキーマの XSD 表記でエンコードされている場合を除き、使用しないようにするC#スキーマ ツリーのルート ノードの名前として予約語 (有効なを指定しない限り**RootNode TypeName**プロパティの値) またはスキーマ ファイル名。</span><span class="sxs-lookup"><span data-stu-id="2c859-118">In addition to the characters that are disallowed in node names, unless they are encoded in the XSD representation of the schema, you should not use C# reserved words as the names of any root nodes in the schema tree (unless you provide a valid **RootNode TypeName** property value) or as schema file names.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c859-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2c859-119">In This Section</span></span>  
  
-   [<span data-ttu-id="2c859-120">ノード名における文字エンコード</span><span class="sxs-lookup"><span data-stu-id="2c859-120">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)  
  
-   [<span data-ttu-id="2c859-121">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="2c859-121">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)