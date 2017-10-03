---
title: "フィールド要素 ノードとフィールド属性 ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d90f622e20bbdbace6804b2418cb68fd2ad60da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a><span data-ttu-id="26b8e-102">[フィールド要素] ノードと[フィールド属性] ノード</span><span class="sxs-lookup"><span data-stu-id="26b8e-102">Field Element Nodes vs. Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="26b8e-103">概要</span><span class="sxs-lookup"><span data-stu-id="26b8e-103">Overview</span></span>
<span data-ttu-id="26b8e-104">フラット ファイル スキーマは、フラット ファイル逆アセンブラーが受信フラット ファイル インスタンス メッセージを、それと等価な XML 形式に変換するとき、および、フラット ファイル アセンブラーが送信 XML メッセージを、それと等価なフラット ファイル インスタンス メッセージに変換するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="26b8e-104">Flat file schemas are used by the flat file disassembler to control how inbound flat file instance messages are translated into their equivalent XML form, and are used by the flat file assembler to control how outbound XML messages are translated into their equivalent flat file instance messages.</span></span> <span data-ttu-id="26b8e-105">いずれかを使用するこのようなスキーマを構築するときに、**フィールド要素**ノードまたは**フィールド属性**ノード具体的には配置を制御スキーマ内で、フラット ファイル インスタンスの特定のフィールドかどうかメッセージは、XML 要素をまたは同等の XML 形式のメッセージ内の XML 属性に対応しています。</span><span class="sxs-lookup"><span data-stu-id="26b8e-105">When constructing such schemas, you use either a **Field Element** node or a **Field Attribute** node in particular positions within the schema to control whether a particular field in the flat file instance message corresponds to an XML element or to an XML attribute in the equivalent XML form of the message.</span></span>  

## <a name="example"></a><span data-ttu-id="26b8e-106">例</span><span class="sxs-lookup"><span data-stu-id="26b8e-106">Example</span></span>  
 <span data-ttu-id="26b8e-107">たとえば、左揃え、アスタリスクが埋め込まれたフィールド値"`red*****`"フラット ファイル インスタンス メッセージ変換できるを同等の XML 表現にスキーマ内のフィールドがかどうかに応じて 2 つの異なる方法で、**フィールド要素**ノードまたは**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="26b8e-107">For example, the left-aligned, asterisk-padded field value "`red*****`" in a flat file instance message can be translated into its equivalent XML representation in two different ways depending upon whether that field in the schema is a **Field Element** node or a **Field Attribute** node.</span></span> <span data-ttu-id="26b8e-108">により、スキーマでそのフィールドを表現するときに、**フィールド要素**ノードをその**ノード名**プロパティ"color"と、親に設定する**レコード**ノードがその**ノード名**プロパティが"shirt"、同等の XML は、(太字で表示)、フラット ファイル フィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="26b8e-108">When that field is represented in the schema by a **Field Element** node with its **Node Name** property set to "color", and the containing **Record** node has its **Node Name** property set to "shirt", the XML equivalent of the flat file field is (shown in bold type).</span></span>  
  
```  
<shirt>  
    <color>red</color>  
</shirt>  
```  
  
 <span data-ttu-id="26b8e-109">により、スキーマで同じフラット ファイル フィールドを表現するときに、**フィールド属性**ノードをその**ノード名**プロパティを設定する色、および含まれている**レコード**ノードには、**ノード名**プロパティが (太字で表示)、フラット ファイル フィールドの同等の XML のシャツに設定します。</span><span class="sxs-lookup"><span data-stu-id="26b8e-109">When that same flat file field is represented in the schema by a **Field Attribute** node with its **Node Name** property set to color, and the containing **Record** node has its **Node Name** property set to shirt, the XML equivalent of the flat file field is (shown in bold type):</span></span>  
  
```  
<color shirt="red"/>  
```  
  
> [!NOTE]
>  <span data-ttu-id="26b8e-110">フラット ファイル スキーマがさらに制限がある内を指定された**レコード**ノードで下位**フィールド属性**ノードで下位図形の前になければなりません**レコード**ノードまたは**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="26b8e-110">Flat file schemas have a further restriction that within a given **Record** node, subordinate **Field Attribute** nodes must come before subordinate **Record** nodes or **Field Element** nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b8e-111">参照</span><span class="sxs-lookup"><span data-stu-id="26b8e-111">See Also</span></span>  
-  [<span data-ttu-id="26b8e-112">フィールドに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="26b8e-112">Field Considerations</span></span>](../core/field-considerations.md)
-  <span data-ttu-id="26b8e-113">**ノード名**プロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="26b8e-113">**Node Name** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>