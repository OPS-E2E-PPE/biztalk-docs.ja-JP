---
title: スキーマ ノードの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14658eb48e4031345ec8ce3e9618ef601f5f5ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396936"
---
# <a name="schema-node"></a><span data-ttu-id="4728d-102">スキーマ ノード</span><span class="sxs-lookup"><span data-stu-id="4728d-102">Schema Node</span></span>

## <a name="overview"></a><span data-ttu-id="4728d-103">概要</span><span class="sxs-lookup"><span data-stu-id="4728d-103">Overview</span></span>
<span data-ttu-id="4728d-104">BizTalk エディターでは、スキーマ階層の最上位は常に、**スキーマ**ノードで、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4728d-104">In BizTalk Editor, the top of the schema hierarchy is always the **Schema** node, which cannot be renamed.</span></span> <span data-ttu-id="4728d-105">**スキーマ**ノードに対応、**スキーマ**スキーマの XML スキーマ定義 (XSD) 言語表記での要素。</span><span class="sxs-lookup"><span data-stu-id="4728d-105">The **Schema** node corresponds to the **schema** element in the XML Schema definition (XSD) language representation of the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4728d-106">BizTalk エディターで、**スキーマ**ノードが文字列で表される\<スキーマ\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="4728d-106">In BizTalk Editor, the **Schema** node is represented with the string \<Schema\> in the schema tree view.</span></span>  
  
 <span data-ttu-id="4728d-107">一般のプロパティ、**スキーマ**ノードの属性に対応、**スキーマ**要素は、スキーマの XSD 表記でします。</span><span class="sxs-lookup"><span data-stu-id="4728d-107">In general, the properties of the **Schema** node correspond to the attributes of the **schema** element in the XSD representation of the schema.</span></span> <span data-ttu-id="4728d-108">ノードのプロパティの詳細については、次を参照してください。[ノード プロパティ](../core/node-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="4728d-108">For general information about node properties, see [Node Properties](../core/node-properties.md).</span></span> <span data-ttu-id="4728d-109">プロパティの参照情報について、**スキーマ**ノードを参照してください、**スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4728d-109">For reference information about the properties of the **Schema** node, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="4728d-110">BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードと 1 つ**ルート**ノードが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4728d-110">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="4728d-111">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="4728d-111">XSD representation</span></span>  
 <span data-ttu-id="4728d-112">太字に対応するスキーマの XSD 表記での行で、次の例は、 **\<スキーマ\>** スキーマのツリー ビューでノード。</span><span class="sxs-lookup"><span data-stu-id="4728d-112">The following example shows, in bold type, the lines in the XSD representation of the schema that correspond to the **\<Schema\>** node in the tree view of the schema.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4728d-113">参照</span><span class="sxs-lookup"><span data-stu-id="4728d-113">See Also</span></span>  
 <span data-ttu-id="4728d-114">[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="4728d-114">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="4728d-115">[ノードのプロパティ](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4728d-115">[Node Properties](../core/node-properties.md) </span></span>  
 [<span data-ttu-id="4728d-116">ノードのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="4728d-116">Set Node Properties</span></span>](../core/how-to-set-node-properties.md)