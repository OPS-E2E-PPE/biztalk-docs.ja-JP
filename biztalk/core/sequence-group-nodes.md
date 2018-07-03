---
title: シーケンス グループ ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c113d0cfd0f6055d55b0329bba3c1ec60bf835e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019744"
---
# <a name="sequence-group-nodes"></a><span data-ttu-id="e7759-102">[シーケンス グループ] ノード</span><span class="sxs-lookup"><span data-stu-id="e7759-102">Sequence Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="e7759-103">概要</span><span class="sxs-lookup"><span data-stu-id="e7759-103">Overview</span></span>
<span data-ttu-id="e7759-104">BizTalk エディターでは、挿入できる、**シーケンス グループ**をする必要があります内に表示される同じ順序で、インスタンス メッセージ内に表示される他のノードを含むノード、**シーケンス グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="e7759-104">In BizTalk Editor, you can insert a **Sequence Group** node to contain other nodes that must appear in an instance message in the same order in which they appear within the **Sequence Group** node.</span></span> <span data-ttu-id="e7759-105">取り込むノードは、XML 要素に対応するノードであることが必要です。ただし、XML 属性に対応するノードではありません。</span><span class="sxs-lookup"><span data-stu-id="e7759-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  

> [!NOTE]
>  <span data-ttu-id="e7759-106">BizTalk エディターで、**シーケンス グループ**ノードが既定では、文字列で表される\<シーケンス\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="e7759-106">In BizTalk Editor, the **Sequence Group** node is represented by default with the string \<Sequence\> in the schema tree view.</span></span> <span data-ttu-id="e7759-107">参照を設定した場合、**シーケンス グループ**x などのノードとして表されます\<グループ: x\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="e7759-107">If you set a reference to a **Sequence Group** node, such as x, it is represented as \<Group:x\> in the schema tree view.</span></span>  

 <span data-ttu-id="e7759-108">追加することも、**シーケンス グループ**グローバル要素グループを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e7759-108">You may want to add a **Sequence Group** to declare a global element group.</span></span>  

 <span data-ttu-id="e7759-109">このような場合は、次の例に示す XML のスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7759-109">You may need to create a schema for XML as follows.</span></span>  

```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  

```  

 <span data-ttu-id="e7759-110">GroupItem1 と GroupItem2 は両方の場合に存在するので、Record1 および Record2 の両方の子であるグローバル シーケンス グループを宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="e7759-110">Because GroupItem1 and GroupItem2 exist in both cases, you may declare a global sequence group that is a child of both Record1 and Record2.</span></span> <span data-ttu-id="e7759-111">グローバル シーケンス グループを宣言する方法の詳しい手順については、「[別のノードまたは種類への参照の作成](../core/how-to-create-references-to-another-node-or-type.md)です。</span><span class="sxs-lookup"><span data-stu-id="e7759-111">For step-by-step instructions about how to declare a global sequence group, see [Creating References to Another Node or Type](../core/how-to-create-references-to-another-node-or-type.md).</span></span>  

 <span data-ttu-id="e7759-112">ユーザー グループを非表示を変更できる、**グループの選択**ノードまたは**すべてのグループ**ノード (とは限りませんため、**シーケンス グループ**ノード) を変更して、 **Group Order Type**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e7759-112">A user can change the hidden group to be a **Choice Group** node or an **All Group** node (so it is not necessarily a **Sequence Group** node) by changing the **Group Order Type** property.</span></span> <span data-ttu-id="e7759-113">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e7759-113">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="xsd-representation"></a><span data-ttu-id="e7759-114">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="e7759-114">XSD representation</span></span>  
 <span data-ttu-id="e7759-115">ときに、**シーケンス グループ**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、 **の選択**、または**すべて**内の要素、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="e7759-115">When a **Sequence Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="e7759-116">次の例は、新しい**シーケンス グループ**太字の末尾に挿入でのノード、**シーケンス**内の要素を**レコード**ノード (ノードを明確にすると、id) です。</span><span class="sxs-lookup"><span data-stu-id="e7759-116">The following example shows a new **Sequence Group** node, in bold type, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="e7759-117">参照</span><span class="sxs-lookup"><span data-stu-id="e7759-117">See Also</span></span>  
- [<span data-ttu-id="e7759-118">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="e7759-118">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="e7759-119">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e7759-119">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="e7759-120">**シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e7759-120">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="e7759-121">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="e7759-121">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
