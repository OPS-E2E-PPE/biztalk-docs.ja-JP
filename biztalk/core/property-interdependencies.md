---
title: プロパティの相互依存性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed5b75e-db1c-43d4-a287-fc4cd1c529f5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15e1a02d82d294c63a33c0682e77585a7934b8ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268458"
---
# <a name="property-interdependencies"></a><span data-ttu-id="072b7-102">プロパティの相互依存性</span><span class="sxs-lookup"><span data-stu-id="072b7-102">Property Interdependencies</span></span>

## <a name="overview"></a><span data-ttu-id="072b7-103">概要</span><span class="sxs-lookup"><span data-stu-id="072b7-103">Overview</span></span>
<span data-ttu-id="072b7-104">BizTalk エディター ([!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウ) でプロパティの値を操作していると、プロパティとプロパティの間にはさまざまな依存関係があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="072b7-104">As you use BizTalk Editor, and specifically the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, to change the values of properties, you will notice that there are extensive interdependencies between properties.</span></span> <span data-ttu-id="072b7-105">あるプロパティに対して特定の設定を行うと、他のプロパティが自動的にクリアされたり、有効と無効が切り替わったり、あるいは、[プロパティ] ウィンドウから消えてしまうこともあります。</span><span class="sxs-lookup"><span data-stu-id="072b7-105">Sometimes a particular setting for one property will cause other properties to be automatically cleared, become enabled or disabled, or even appear or disappear entirely from the Properties window.</span></span> <span data-ttu-id="072b7-106">こうした相互依存は広範囲に及ぶため、ここですべてを説明することはできません。</span><span class="sxs-lookup"><span data-stu-id="072b7-106">These interdependencies are too numerous to cover.</span></span> 

<span data-ttu-id="072b7-107">このセクションでは、一般的な例をいくつか示して、相互依存の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="072b7-107">However, the following list provides some common examples to give you an idea of how they work:</span></span>  
  
-   <span data-ttu-id="072b7-108">プロパティを設定するときに、**フィールド要素**ノードまたは**フィールド属性**対象のデータ型はから派生している単純型の新しいカテゴリ全体、制限メカニズムを使用してノードプロパティが使用可能になります:**制限**です。</span><span class="sxs-lookup"><span data-stu-id="072b7-108">When setting the properties of a **Field Element** node or **Field Attribute** node for which a data type is being derived from a simple type by using the restriction mechanism, an entire new category of properties becomes available: **Restriction**.</span></span> <span data-ttu-id="072b7-109">さらに、この新しいカテゴリのプロパティは、基本データ型が文字列型であるか数値型であるかに応じて、有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="072b7-109">Further, the properties in this new category are enabled or disabled based on whether the base data type is of a string type or a numeric type.</span></span> <span data-ttu-id="072b7-110">この形式の単純型の派生の詳細については、次を参照してください。[単純型の派生を使用して制約メカニズム](../core/simple-type-derivation-using-the-restriction-mechanism.md)です。</span><span class="sxs-lookup"><span data-stu-id="072b7-110">For more information about this form of simple type derivation, see [Simple Type Derivation Using the Restriction Mechanism](../core/simple-type-derivation-using-the-restriction-mechanism.md).</span></span>  
  
-   <span data-ttu-id="072b7-111">プロパティを設定するときに、**フィールド要素**ノードまたは**フィールド属性**対象のデータ型はから派生している単純型リストまたはユニオンのメカニズムのいずれかを使用して、ノード、**ベースデータ型**プロパティがいずれかに変更された、**項目の種類**プロパティまたは**Member Types**プロパティ、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="072b7-111">When setting the properties of a **Field Element** node or **Field Attribute** node for which a data type is being derived from a simple type by using either the list or union mechanism, the **Base Data Type** property is changed to either the **Item Type** property or the **Member Types** property, respectively.</span></span> <span data-ttu-id="072b7-112">後者の場合、対応するドロップダウン リストには、チェック ボックスが追加され、複数の型から選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="072b7-112">In the latter case, the corresponding drop-down list is modified to include check boxes, allowing multiple types to be selected.</span></span> <span data-ttu-id="072b7-113">これらの形式の単純型の派生の詳細については、次を参照してください。[単純型の派生を使用してリスト メカニズム](../core/simple-type-derivation-using-the-list-mechanism.md)と[単純型の派生メカニズムを使用して、共用体](../core/simple-type-derivation-using-the-union-mechanism.md)です。</span><span class="sxs-lookup"><span data-stu-id="072b7-113">For more information about these forms of simple type derivation, see [Simple Type Derivation Using the List Mechanism](../core/simple-type-derivation-using-the-list-mechanism.md) and [Simple Type Derivation Using the Union Mechanism](../core/simple-type-derivation-using-the-union-mechanism.md).</span></span>  
  
-   <span data-ttu-id="072b7-114">フラット ファイル スキーマに関連付けられたプロパティを公開するために設定する必要があります、**スキーマ エディター拡張機能**のプロパティ、**スキーマ**含めるノード、**フラット ファイル拡張子**.</span><span class="sxs-lookup"><span data-stu-id="072b7-114">To expose the properties associated with flat file schemas, you must set the **Schema Editor Extensions** property of the **Schema** node to include the **Flat File Extension**.</span></span> <span data-ttu-id="072b7-115">EDI 拡張機能などの他のエディター拡張機能に関連付けられているカスタム プロパティと同じ方法で公開されます。 対応する拡張機能を使用して、を選択して、**スキーマ エディター拡張機能**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="072b7-115">The custom properties associated with other editor extensions, such as the EDI extension, are exposed in the same way: by choosing the corresponding extension using the **Schema Editor Extensions** property.</span></span>  
  
 <span data-ttu-id="072b7-116">ここでは、[プロパティ] ウィンドウで確認できるプロパティの相互依存性について、いくつかの例を取り上げました。ただしプロパティの相互依存性をすべて網羅しているものではない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="072b7-116">This list includes examples that are meant to illustrate the types of property interdependencies that you will see when working within the Properties window, but it is not meant to be an exhaustive list of such interdependencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072b7-117">参照</span><span class="sxs-lookup"><span data-stu-id="072b7-117">See Also</span></span>  
-  [<span data-ttu-id="072b7-118">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="072b7-118">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="072b7-119">次のプロパティ[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="072b7-119">The following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
    -  <span data-ttu-id="072b7-120">ノードのプロパティのアルファベット順</span><span class="sxs-lookup"><span data-stu-id="072b7-120">Node Properties Alphabetical Listings</span></span>
    -  <span data-ttu-id="072b7-121">すべてのスキーマのノード プロパティ</span><span class="sxs-lookup"><span data-stu-id="072b7-121">Node Properties of All Schemas</span></span> 
    -  <span data-ttu-id="072b7-122">Schema Editor Extensions</span><span class="sxs-lookup"><span data-stu-id="072b7-122">Schema Editor Extensions</span></span>