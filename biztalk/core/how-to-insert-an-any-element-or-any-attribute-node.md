---
title: すべての要素または属性の任意のノードを挿入する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bce55126fe800841aef325f22de0afe62e03cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021077"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a><span data-ttu-id="be888-102">すべての要素または属性の任意のノードを挿入する方法</span><span class="sxs-lookup"><span data-stu-id="be888-102">How to Insert an Any Element or Any Attribute Node</span></span>
<span data-ttu-id="be888-103">BizTalk エディターは、2 種類のすべてのノードをサポートしています: **Any 要素**と**すべての属性**します。</span><span class="sxs-lookup"><span data-stu-id="be888-103">BizTalk Editor supports two types of any nodes: **Any Element** and **Any Attribute**.</span></span> <span data-ttu-id="be888-104">これらのノードを使用すると、インスタンス メッセージ内の特定の位置にどのような要素または属性が出現するかわからないときに、それらの要素や属性のための場所をスキーマ内で確保できます。</span><span class="sxs-lookup"><span data-stu-id="be888-104">These nodes allow you to create locations within your schema that correspond to locations within the corresponding instance messages where you do not know what elements or attributes will appear.</span></span> <span data-ttu-id="be888-105">これらのノードがインスタンス メッセージの処理時にどのように解釈されるかについては、Web 上で XSD (XML Schema Definition) 言語に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be888-105">For detailed information about how these nodes are interpreted when processing instance messages, refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="be888-106">この情報へのリンクを参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="be888-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a><span data-ttu-id="be888-107">Any 要素ノードまたはすべての属性ノードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="be888-107">Insert an Any Element node or an Any Attribute node</span></span>  

1.  <span data-ttu-id="be888-108">スキーマ ツリー ビューで、選択、**レコード**ノードを挿入する、 **Any 要素**ノードまたは**すべての属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="be888-108">In the schema tree view, select the **Record** node into which you want to insert the **Any Element** node or the **Any Attribute** node.</span></span>  

2.  <span data-ttu-id="be888-109">**BizTalk**メニューで、**スキーマ ノードの挿入**、順にクリックします**Any 要素**または**すべての属性**必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="be888-109">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Any Element** or **Any Attribute**, as appropriate.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="be888-110">設定、 **Process Contents**プロパティを**Lax**の**Any 要素**または**すべての属性**ノードが正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be888-110">Setting the **Process Contents** property to **Lax** for **Any Element** or **Any Attribute** nodes may not work correctly.</span></span> <span data-ttu-id="be888-111">検証に合格する**Any 要素**または**すべての属性**ノードにプロパティを設定する**スキップ**します。</span><span class="sxs-lookup"><span data-stu-id="be888-111">To pass validation on **Any Element** or **Any Attribute** nodes, set the property to **Skip**.</span></span>  <span data-ttu-id="be888-112">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="be888-112">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
>  <span data-ttu-id="be888-113">含むマップを作成する**Any 要素**または**すべての属性**ノード、いずれかを使用する必要があります、[一括コピー](mass-copy-functoid.md) functoid、または[Scripting](scripting-functoid.md)(インライン XSLT またはインライン XSLT 呼び出しテンプレートで) 使用する functoid をこのようなノードのマッピングを実行または単にそれらのノードをマップできません。</span><span class="sxs-lookup"><span data-stu-id="be888-113">To create a map that contains **Any Element** or **Any Attribute** nodes, you must use either the [Mass Copy](mass-copy-functoid.md) functoid or the [Scripting](scripting-functoid.md) functoid (with Inline XSLT or Inline XSLT Call Template) to perform the mapping for such nodes, or simply not map those nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="be888-114">参照</span><span class="sxs-lookup"><span data-stu-id="be888-114">See Also</span></span>  
- [<span data-ttu-id="be888-115">スキーマへのノードの挿入</span><span class="sxs-lookup"><span data-stu-id="be888-115">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)
- <span data-ttu-id="be888-116">**Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="be888-116">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
