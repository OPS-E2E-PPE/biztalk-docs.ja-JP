---
title: フィールド要素 ノードとします。フィールド属性 ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1fffbca-8886-42c0-9214-cd0c5314850c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50bb60f66b6de00510e973357bec43d0af506f4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345582"
---
# <a name="field-element-nodes-vs-field-attribute-nodes"></a><span data-ttu-id="1415a-102">フィールド要素 ノードとします。フィールド属性 ノード</span><span class="sxs-lookup"><span data-stu-id="1415a-102">Field Element Nodes vs. Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="1415a-103">概要</span><span class="sxs-lookup"><span data-stu-id="1415a-103">Overview</span></span>
<span data-ttu-id="1415a-104">フラット ファイル スキーマが使用されるコントロールにフラット ファイル逆アセンブラーが受信フラット ファイル インスタンス メッセージが、同等の XML 形式に変換されますが送信フラット ファイル アセンブラーで使用方法の XML メッセージに変換されます、対応します。フラット ファイル インスタンス メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1415a-104">Flat file schemas are used by the flat file disassembler to control how inbound flat file instance messages are translated into their equivalent XML form, and are used by the flat file assembler to control how outbound XML messages are translated into their equivalent flat file instance messages.</span></span> <span data-ttu-id="1415a-105">いずれかを使用するこのようなスキーマを作成するときに、**フィールド要素**ノードまたは**フィールド属性**ノード具体的には配置を制御するスキーマ内でかどうか、フラット ファイル インスタンスの特定のフィールドメッセージは、XML 要素をまたは同等の XML 形式のメッセージ内の XML 属性に対応しています。</span><span class="sxs-lookup"><span data-stu-id="1415a-105">When constructing such schemas, you use either a **Field Element** node or a **Field Attribute** node in particular positions within the schema to control whether a particular field in the flat file instance message corresponds to an XML element or to an XML attribute in the equivalent XML form of the message.</span></span>  

## <a name="example"></a><span data-ttu-id="1415a-106">例</span><span class="sxs-lookup"><span data-stu-id="1415a-106">Example</span></span>  
 <span data-ttu-id="1415a-107">左揃え、アスタリスクが埋め込まれたフィールドの値ではたとえば、"`red*****`"フラット ファイル インスタンス メッセージに変換できる同等の XML 表現、スキーマ内のフィールドは、かどうかに応じて 2 つの異なる方法で、**フィールド要素**ノードまたは**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-107">For example, the left-aligned, asterisk-padded field value "`red*****`" in a flat file instance message can be translated into its equivalent XML representation in two different ways depending upon whether that field in the schema is a **Field Element** node or a **Field Attribute** node.</span></span> <span data-ttu-id="1415a-108">ときにそのフィールドは、スキーマ内に表されます、**フィールド要素**ノードとその**ノード名**プロパティが"color"、および格納オブジェクトに設定**レコード**ノードがその**ノード名**プロパティが"shirt"、同等の XML は (太字で表示)、フラット ファイル フィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="1415a-108">When that field is represented in the schema by a **Field Element** node with its **Node Name** property set to "color", and the containing **Record** node has its **Node Name** property set to "shirt", the XML equivalent of the flat file field is (shown in bold type).</span></span>  

```  
<shirt>  
    <color>red</color>  
</shirt>  
```  

 <span data-ttu-id="1415a-109">同じフラット ファイル フィールドは、スキーマ内に表されます、**フィールド属性**ノードでその**ノード名**プロパティには、色、および格納している設定**レコード**ノードがその**ノード名**プロパティは (太字で表示)、フラット ファイル フィールドに相当する XML のシャツに設定します。</span><span class="sxs-lookup"><span data-stu-id="1415a-109">When that same flat file field is represented in the schema by a **Field Attribute** node with its **Node Name** property set to color, and the containing **Record** node has its **Node Name** property set to shirt, the XML equivalent of the flat file field is (shown in bold type):</span></span>  

```  
<color shirt="red"/>  
```  

> [!NOTE]
>  <span data-ttu-id="1415a-110">フラット ファイル スキーマがさらに制限がある内を指定された**レコード**ノードの下位**フィールド属性**ノードは、下位のより前に、でなければなりません**レコード**ノードまたは**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-110">Flat file schemas have a further restriction that within a given **Record** node, subordinate **Field Attribute** nodes must come before subordinate **Record** nodes or **Field Element** nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1415a-111">参照</span><span class="sxs-lookup"><span data-stu-id="1415a-111">See Also</span></span>  
- [<span data-ttu-id="1415a-112">フィールドに関する注意</span><span class="sxs-lookup"><span data-stu-id="1415a-112">Field Considerations</span></span>](../core/field-considerations.md)
- <span data-ttu-id="1415a-113">**ノード名**プロパティ [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1415a-113">**Node Name** property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
