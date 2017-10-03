---
title: "すべての要素または属性の任意のノードを挿入する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913d7d0c68d61df1c457dd22500a9e4a8d90ec68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a><span data-ttu-id="9c4f2-102">すべての要素または属性の任意のノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="9c4f2-102">How to Insert an Any Element or Any Attribute Node</span></span>
<span data-ttu-id="9c4f2-103">BizTalk エディターには、すべてのノードの 2 種類がサポートしています: **Any 要素**と**すべての属性**です。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-103">BizTalk Editor supports two types of any nodes: **Any Element** and **Any Attribute**.</span></span> <span data-ttu-id="9c4f2-104">これらのノードを使用すると、インスタンス メッセージ内の特定の位置にどのような要素または属性が出現するかわからないときに、それらの要素や属性のための場所をスキーマ内で確保できます。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-104">These nodes allow you to create locations within your schema that correspond to locations within the corresponding instance messages where you do not know what elements or attributes will appear.</span></span> <span data-ttu-id="9c4f2-105">これらのノードがインスタンス メッセージの処理時にどのように解釈されるかについては、Web 上で XSD (XML Schema Definition) 言語に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-105">For detailed information about how these nodes are interpreted when processing instance messages, refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="9c4f2-106">この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a><span data-ttu-id="9c4f2-107">すべての要素ノードまたはすべての属性ノードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-107">Insert an Any Element node or an Any Attribute node</span></span>  
  
1.  <span data-ttu-id="9c4f2-108">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、 **Any 要素**ノードまたは**すべての属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-108">In the schema tree view, select the **Record** node into which you want to insert the **Any Element** node or the **Any Attribute** node.</span></span>  
  
2.  <span data-ttu-id="9c4f2-109">**BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、順にクリック**すべての要素**または**すべての属性** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-109">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Any Element** or **Any Attribute**, as appropriate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c4f2-110">設定、 **Process Contents**プロパティを**Lax**の**Any 要素**または**すべての属性**ノードが正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-110">Setting the **Process Contents** property to **Lax** for **Any Element** or **Any Attribute** nodes may not work correctly.</span></span> <span data-ttu-id="9c4f2-111">検証に合格する**Any 要素**または**すべての属性**ノード、プロパティを設定します**Skip**です。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-111">To pass validation on **Any Element** or **Any Attribute** nodes, set the property to **Skip**.</span></span>  <span data-ttu-id="9c4f2-112">このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-112">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
>
>  <span data-ttu-id="9c4f2-113">含むマップを作成する**Any 要素**または**すべての属性**ノード、いずれかを使用する必要があります、[一括コピー](mass-copy-functoid.md) functoid または[スクリプト](scripting-functoid.md)functoid (インライン XSLT またはインライン XSLT 呼び出しテンプレート) をこのようなノードのマッピングを実行または単にそれらのノードをマップされません。</span><span class="sxs-lookup"><span data-stu-id="9c4f2-113">To create a map that contains **Any Element** or **Any Attribute** nodes, you must use either the [Mass Copy](mass-copy-functoid.md) functoid or the [Scripting](scripting-functoid.md) functoid (with Inline XSLT or Inline XSLT Call Template) to perform the mapping for such nodes, or simply not map those nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4f2-114">参照</span><span class="sxs-lookup"><span data-stu-id="9c4f2-114">See Also</span></span>  
-  [<span data-ttu-id="9c4f2-115">スキーマにノードを挿入</span><span class="sxs-lookup"><span data-stu-id="9c4f2-115">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)
- <span data-ttu-id="9c4f2-116">**Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9c4f2-116">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>