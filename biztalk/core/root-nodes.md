---
title: "ルート ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="root-nodes"></a><span data-ttu-id="2aa7e-102">ルート ノード</span><span class="sxs-lookup"><span data-stu-id="2aa7e-102">Root Nodes</span></span>
<span data-ttu-id="2aa7e-103">BizTalk エディターでの子ノード、**スキーマ**ノードと呼ばれる**ルート**ノード。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-103">In BizTalk Editor, child nodes of the **Schema** node are known as **Root** nodes.</span></span> <span data-ttu-id="2aa7e-104">**ルート**ノードは、特殊な種類の**レコード**ノード、通常よりも、いくつかのプロパティがあると**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-104">**Root** nodes are a special type of **Record** node, and have a few more properties than regular **Record** nodes.</span></span> <span data-ttu-id="2aa7e-105">**ルート**ノードが、スキーマによって示されるドキュメントの種類を表し、必要に応じて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-105">The **Root** node represents the type of document described by the schema, and can be renamed as appropriate.</span></span> <span data-ttu-id="2aa7e-106">たとえば、名前を変更できます、**ルート**ノードが purchaseOrder、orderAcknowledgment、shipnotice など、スキーマを表すメッセージの種類を説明するようにします。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-106">For example, you can rename the **Root** node so that it describes the type of message that the schema represents, such as purchaseOrder, orderAcknowledgment, or shipNotice.</span></span>  
  
 <span data-ttu-id="2aa7e-107">BizTalk エディターで、新しい XML スキーマを作成するときに、**スキーマ**ノードおよび**ルート**ノードが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-107">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span> <span data-ttu-id="2aa7e-108">追加作成することができます**ルート**ノードの子として、**スキーマ**ノードです。 これにより、単一の XML スキーマ定義 (XSD) 言語表記でスキーマのライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-108">You can create additional **Root** nodes as children of the **Schema** node; this enables you to create a library of schemas within a single XML Schema definition (XSD) language representation.</span></span> <span data-ttu-id="2aa7e-109">たとえば、スキーマのライブラリを作成して、注文書の送信やさまざまなルート ノードの名前付け (purchaseOrder、orderAcknowledgment、shipNotice など) に関連するメッセージのスキーマを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-109">For example, you can create a library of schemas to describe the various schemas of messages related to sending purchase orders, naming the various root nodes purchaseOrder, orderAcknowledgment, and shipNotice.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="2aa7e-110">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="2aa7e-110">XSD representation</span></span>  
 <span data-ttu-id="2aa7e-111">次の例に対応するスキーマの XSD 表記で、行を示しています、**ルート**スキーマのツリー ビュー内のノードです。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-111">The following example shows the lines in the XSD representation of the schema that correspond to the **Root** node in the tree view of the schema.</span></span>  
  
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
  
 <span data-ttu-id="2aa7e-112">**ルート**ノード BizTalk エディターでは対象のメッセージの対応する XML インスタンス内の主な要素を表します。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-112">**Root** nodes in BizTalk Editor represent the main element in a corresponding XML instance of the message in question.</span></span> <span data-ttu-id="2aa7e-113">たとえば場合、**ルート**特定のスキーマのノードの名前が purchaseOrder に、対応する XSD 表記は、次の大まかな構造です。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-113">For example, if the **Root** node of a particular schema is renamed to purchaseOrder, the corresponding XSD representation has the following high-level structure.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="2aa7e-114">対応する XML インスタンス メッセージには、次の基本構造が必要です。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-114">A corresponding XML instance message must have the following basic structure.</span></span>  
  
```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  
  
> [!NOTE]
>  <span data-ttu-id="2aa7e-115">ルート ノードがない可能性があります**フィールド**属性。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="2aa7e-116">**フィールド**に属性が追加されている、**ルート**ノードは、スキーマには保存されません。</span><span class="sxs-lookup"><span data-stu-id="2aa7e-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa7e-117">参照</span><span class="sxs-lookup"><span data-stu-id="2aa7e-117">See Also</span></span>  
-  [<span data-ttu-id="2aa7e-118">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="2aa7e-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="2aa7e-119">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="2aa7e-119">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="2aa7e-120">**レコード ノードのプロパティ**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa7e-120">**Record Node Properties**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="2aa7e-121">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="2aa7e-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)