---
title: ノード名プロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: c1d39c71a425e20c5a9228e418cfa86acb579fa5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972800"
---
# <a name="node-name-property"></a><span data-ttu-id="e0460-102">"ノード名" プロパティ</span><span class="sxs-lookup"><span data-stu-id="e0460-102">Node Name Property</span></span>
<span data-ttu-id="e0460-103">BizTalk エディターでノードをスキーマ ツリーに挿入すると、ノードの名前が変更されるノードと名前が変更されないノードがあります。</span><span class="sxs-lookup"><span data-stu-id="e0460-103">As you use BizTalk Editor to insert nodes into the schema tree, some nodes are meant to be renamed and others are not.</span></span> <span data-ttu-id="e0460-104">基本的に、できるし、名前を変更する必要があります**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="e0460-104">Essentially, you can and should rename **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes.</span></span> <span data-ttu-id="e0460-105">これらのノードに名前を指定すると、その名前は、スキーマで定義されるメッセージの XML 要素および XML 属性の名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0460-105">The names that you give to these nodes will become the names of the XML elements and attributes in the message that the schema defines.</span></span>  
  
 <span data-ttu-id="e0460-106">スキーマ ツリーで名前を変更することはできません、ノードが XML タグの形式で表示します。小により (\<) より大きいと (\>) 記号です。</span><span class="sxs-lookup"><span data-stu-id="e0460-106">In the schema tree, the nodes that you cannot rename are shown in the form of XML tags; that is, with the less than (\<) and greater than (\>) signs.</span></span> <span data-ttu-id="e0460-107">たとえば、**スキーマ**ノード、**選択肢グループ**ノード、**すべての要素**ノード、および**すべての属性**ノードは、スキーマで表されます名前を持つツリー\<スキーマ\>、\<選択肢\>、\<任意\>、および\<AnyAttribute\>、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="e0460-107">For example, the **Schema** node, **Choice Group** nodes, **Any Element** nodes, and **Any Attribute** nodes are represented in the schema tree with the names \<Schema\>, \<Choice\>, \<Any\>, and \<AnyAttribute\>, respectively.</span></span> <span data-ttu-id="e0460-108">**ノード名**このようなノードのプロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="e0460-108">The **Node Name** property for such nodes is read-only.</span></span>  
  
 <span data-ttu-id="e0460-109">内で、指定された**レコード**ノード、2 つを持つことはできません**フィールド属性**と同じ名前のノードです。</span><span class="sxs-lookup"><span data-stu-id="e0460-109">Within a given **Record** node, you cannot have two **Field Attribute** nodes with the same name.</span></span> <span data-ttu-id="e0460-110">1 つ以上ありますただし、**フィールド要素**ノードまたは**レコード**同じの子ノードと同じ名前を持つノード**レコード**限り、それらはすべて同じデータ型のノード(で指定されたとおり、**データ型**プロパティ**フィールド要素**ノード、または**Data Structure Type**の**レコード**ノード)。</span><span class="sxs-lookup"><span data-stu-id="e0460-110">However, you can have more than one **Field Element** node or **Record** node with the same name as child nodes of the same **Record** node, as long as they all have the same data type (as specified by their **Data Type** property for **Field Element** nodes or their **Data Structure Type** for **Record** nodes).</span></span>  
  
 <span data-ttu-id="e0460-111">名前を指定するときに**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード内で属性またはその要素の役割のわかりやすい名前を使用します。スキーマによって定義されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e0460-111">When you give names to **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, use names that are descriptive of the role of that element or attribute within the message being defined by the schema.</span></span> <span data-ttu-id="e0460-112">たとえば、FirstName は都合の良い選択肢の名前、**フィールド要素**アドレス構造内の他のユーザー名を格納するために使用するノードです。</span><span class="sxs-lookup"><span data-stu-id="e0460-112">For example, FirstName is probably a good choice for the name of a **Field Element** node that will be used to store the first name of someone in an address structure.</span></span> <span data-ttu-id="e0460-113">名 (ファースト ネーム) が James の XML インスタンス メッセージの場合、対応する要素は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e0460-113">In an XML instance message where the first name James occurs, the corresponding element would look like the following.</span></span>  
  
```  
    <FirstName>James</FirstName>  
```  
  
 <span data-ttu-id="e0460-114">名前を変更するときに**レコード**ノード、**フィールド要素**ノード、および**フィールド属性**ノード、する必要がありますいないすべての文字がノード名に許可されていることに注意してくださかった。</span><span class="sxs-lookup"><span data-stu-id="e0460-114">When you are renaming **Record** nodes, **Field Element** nodes, and **Field Attribute** nodes, you should be aware that not all characters are allowed in node names.</span></span> <span data-ttu-id="e0460-115">使用できない文字に関する情報は、次を参照してください。[がノード名の文字エン コード](../core/which-node-name-characters-get-encoded.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0460-115">For information about these disallowed characters, see [Which Node Name Characters Get Encoded](../core/which-node-name-characters-get-encoded.md).</span></span> <span data-ttu-id="e0460-116">BizTalk エディターでは、使用できない文字をエンコードすることによって使用可能にできますが、このような文字はできるだけ使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0460-116">Although BizTalk Editor allows you to use disallowed characters by encoding them, it is often simpler to avoid such characters altogether.</span></span> <span data-ttu-id="e0460-117">使用できない文字をエンコードする方法については、「[どのノード名の文字エン コード](../core/how-node-name-characters-get-encoded.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0460-117">For information about how disallowed characters are encoded, see [How Node Name Characters Get Encoded](../core/how-node-name-characters-get-encoded.md).</span></span>  
  
 <span data-ttu-id="e0460-118">ノード名で使用できない文字だけでなく、スキーマ ツリーのルート ノードの名前として c# 予約語を使用する必要があります、スキーマの XSD 表記でエンコードされている場合を除き、(有効なを指定しない限り**RootNodeTypeName**プロパティの値) またはスキーマ ファイル名。</span><span class="sxs-lookup"><span data-stu-id="e0460-118">In addition to the characters that are disallowed in node names, unless they are encoded in the XSD representation of the schema, you should not use C# reserved words as the names of any root nodes in the schema tree (unless you provide a valid **RootNode TypeName** property value) or as schema file names.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0460-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0460-119">In This Section</span></span>  
  
-   [<span data-ttu-id="e0460-120">ノード名における文字エンコード</span><span class="sxs-lookup"><span data-stu-id="e0460-120">Which Node Name Characters Get Encoded</span></span>](../core/which-node-name-characters-get-encoded.md)  
  
-   [<span data-ttu-id="e0460-121">ノード名の文字エンコードの方法</span><span class="sxs-lookup"><span data-stu-id="e0460-121">How Node Name Characters Get Encoded</span></span>](../core/how-node-name-characters-get-encoded.md)