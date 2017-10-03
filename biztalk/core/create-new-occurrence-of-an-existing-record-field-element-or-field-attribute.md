---
title: "既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="42c87-102">既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="42c87-102">How to Create a New Occurrence of an Existing Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="42c87-103">既存の新しいインスタンスを作成する**レコード**、**フィールド要素**、または**フィールド属性**ノードすべてに任意のインスタンスに対して行った変更が反映されるようインスタンス。</span><span class="sxs-lookup"><span data-stu-id="42c87-103">You can create new instances of an existing **Record**, **Field Element**, or **Field Attribute** node such that subsequent modifications to any instance are reflected in all instances.</span></span>  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="42c87-104">既存の[レコード] ノード、[フィールド要素] ノード、または[フィールド属性] ノードの新しいインスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="42c87-104">To create a new instance of an existing Record, Field Element, or Field Attribute node</span></span>  
  
1.  <span data-ttu-id="42c87-105">元の選択**レコード**、**フィールド要素**、または**フィールド属性**ノード、ことを確認、 **Base Data Type**プロパティが正しく設定その**Data Structure Type** (**レコード**ノード) またはその**データ型**(**フィールド要素**と**フィールド属性**ノード) プロパティ、カスタム データ型の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="42c87-105">Select the original **Record**, **Field Element**, or **Field Attribute** node, make sure its **Base Data Type** property is set correctly, and then in its **Data Structure Type** (**Record** nodes) or its **Data Type** (**Field Element** and **Field Attribute** nodes) property, type a custom data type name.</span></span>  
  
2.  <span data-ttu-id="42c87-106">新しい挿入**レコード**、**フィールド要素**、または**フィールド属性**ノードとカスタム データを次のプロパティのいずれかのセットは、手順 1. で入力した名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="42c87-106">Insert the new **Record**, **Field Element**, or **Field Attribute** node and set one of the following properties to the custom data type name you typed in step 1.</span></span>  
  
    -   <span data-ttu-id="42c87-107">Data Structure Type (**レコード**ノード)</span><span class="sxs-lookup"><span data-stu-id="42c87-107">Data Structure Type (**Record** nodes)</span></span>  
  
    -   <span data-ttu-id="42c87-108">データ型 (**フィールド要素**と**フィールド属性**ノード)</span><span class="sxs-lookup"><span data-stu-id="42c87-108">Data Type (**Field Element** and **Field Attribute** nodes)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42c87-109">場合、新しい**レコード**または**フィールド要素**ノードは、元のノードの兄弟、新しいノードに、元のノードと同じ名前を付けると、同じスコープ内で重複するノードについて確認するメッセージ ボックスが表示されます同じ名前です。</span><span class="sxs-lookup"><span data-stu-id="42c87-109">If a new **Record** or **Field Element** node is a sibling of the original node, and you give the new node the same name as the original node, you will see a message box asking about duplicate nodes in the same scope with the same name.</span></span> <span data-ttu-id="42c87-110">クリックすると**はい**手順 2. でカスタム データ型の名前を選択すると、同じ処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="42c87-110">Clicking **Yes** performs the same action as choosing the custom data type name in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42c87-111">既存の新しいインスタンスを作成した**レコード**、**フィールド要素**、または**フィールド属性**ノード。</span><span class="sxs-lookup"><span data-stu-id="42c87-111">You have created a new instance of the existing **Record**, **Field Element**, or **Field Attribute** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42c87-112">一部のプロパティの**レコード**、**フィールド要素**、または**フィールド属性**ノード インスタンスが同じままになります (1 つのインスタンスへの変更がすべてのインスタンスへの変更)、およびその他のプロパティは、インスタンスごとに個別に設定できます。</span><span class="sxs-lookup"><span data-stu-id="42c87-112">Some properties of **Record**, **Field Element**, or **Field Attribute** node instances remain identical (a change to one instance is a change to all instances), and other properties can be set independently for each instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c87-113">参照</span><span class="sxs-lookup"><span data-stu-id="42c87-113">See Also</span></span>  
 [<span data-ttu-id="42c87-114">スキーマにノードを挿入</span><span class="sxs-lookup"><span data-stu-id="42c87-114">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)