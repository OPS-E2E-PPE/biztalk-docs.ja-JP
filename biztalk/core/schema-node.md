---
title: スキーマ ノードの |Microsoft ドキュメント
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
ms.openlocfilehash: dd892e825194afea880d3bde153f472051ce9102
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972232"
---
# <a name="schema-node"></a><span data-ttu-id="d597c-102">[スキーマ] ノード</span><span class="sxs-lookup"><span data-stu-id="d597c-102">Schema Node</span></span>

## <a name="overview"></a><span data-ttu-id="d597c-103">概要</span><span class="sxs-lookup"><span data-stu-id="d597c-103">Overview</span></span>
<span data-ttu-id="d597c-104">BizTalk エディターで、スキーマ階層の最上位は常に、**スキーマ**ノードで、名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d597c-104">In BizTalk Editor, the top of the schema hierarchy is always the **Schema** node, which cannot be renamed.</span></span> <span data-ttu-id="d597c-105">**スキーマ**ノードに対応、**スキーマ**XML スキーマ定義 (XSD) 言語表記のスキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="d597c-105">The **Schema** node corresponds to the **schema** element in the XML Schema definition (XSD) language representation of the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d597c-106">BizTalk エディターで、**スキーマ**ノードは、文字列で表される\<スキーマ\>スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="d597c-106">In BizTalk Editor, the **Schema** node is represented with the string \<Schema\> in the schema tree view.</span></span>  
  
 <span data-ttu-id="d597c-107">一般のプロパティ、**スキーマ**の属性に対応しているノード、**スキーマ**スキーマの XSD 表記内の要素。</span><span class="sxs-lookup"><span data-stu-id="d597c-107">In general, the properties of the **Schema** node correspond to the attributes of the **schema** element in the XSD representation of the schema.</span></span> <span data-ttu-id="d597c-108">ノードのプロパティに関する概要については、次を参照してください。[ノードのプロパティ](../core/node-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="d597c-108">For general information about node properties, see [Node Properties](../core/node-properties.md).</span></span> <span data-ttu-id="d597c-109">プロパティに関するリファレンス情報について、**スキーマ** ノードを参照してください、**スキーマ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d597c-109">For reference information about the properties of the **Schema** node, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="d597c-110">BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードおよび**ルート**ノードが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d597c-110">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="d597c-111">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="d597c-111">XSD representation</span></span>  
 <span data-ttu-id="d597c-112">例を次に、太字に対応するスキーマの XSD 表記内の行で、 **\<スキーマ\>** スキーマのツリー ビュー内のノードです。</span><span class="sxs-lookup"><span data-stu-id="d597c-112">The following example shows, in bold type, the lines in the XSD representation of the schema that correspond to the **\<Schema\>** node in the tree view of the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d597c-113">参照</span><span class="sxs-lookup"><span data-stu-id="d597c-113">See Also</span></span>  
 <span data-ttu-id="d597c-114">[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="d597c-114">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="d597c-115">[ノードのプロパティ](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d597c-115">[Node Properties](../core/node-properties.md) </span></span>  
 [<span data-ttu-id="d597c-116">ノードのプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="d597c-116">Set Node Properties</span></span>](../core/how-to-set-node-properties.md)