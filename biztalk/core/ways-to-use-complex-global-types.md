---
title: 複合グローバル型を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ddea1c7b-eb0e-4521-8576-0ea6f9460847
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f84b8b872d047a62a913514a695b4bba2d482c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288658"
---
# <a name="ways-to-use-complex-global-types"></a><span data-ttu-id="075c4-102">複合グローバル型の使用方法</span><span class="sxs-lookup"><span data-stu-id="075c4-102">Ways to Use Complex Global Types</span></span>
<span data-ttu-id="075c4-103">複合型を複合グローバル型に変換すると、スキーマ内の他の場所で再利用できます。</span><span class="sxs-lookup"><span data-stu-id="075c4-103">After you have converted a complex type to a global complex type, it becomes available for reuse in other locations within your schema.</span></span> <span data-ttu-id="075c4-104">複合型を定義してグローバル複合型に変換することに関する詳細については、次を参照してください。[複合グローバル型の定義と名前付け](../core/complex-global-type-definition-and-naming.md)です。</span><span class="sxs-lookup"><span data-stu-id="075c4-104">For more information about defining a complex type and then converting it to a global complex type, see [Complex Global Type Definition and Naming](../core/complex-global-type-definition-and-naming.md).</span></span>  
  
 <span data-ttu-id="075c4-105">新しいを挿入する最初に、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="075c4-105">First, you insert a new **Record** node.</span></span> <span data-ttu-id="075c4-106">次に、挿入されたノードを選択し、[プロパティ] ウィンドウの次の 2 つのノード プロパティのいずれかを設定します。これらのプロパティは、それぞれ異なる機能を持っています。</span><span class="sxs-lookup"><span data-stu-id="075c4-106">Then you select the inserted node and set one of the following two node properties in the Properties window, each for a different effect:</span></span>  
  
-   <span data-ttu-id="075c4-107">**Data Structure Type プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="075c4-107">**Data Structure Type property**.</span></span> <span data-ttu-id="075c4-108">変更を加えずに複合グローバル型を使用する場合、このプロパティを、複合グローバル型に対して指定した型名に設定します (ドロップダウン リストから選択できます)。</span><span class="sxs-lookup"><span data-stu-id="075c4-108">If you want to use the complex global type without modifying it in any way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="075c4-109">スキーマ ツリーで、選択されたグローバル ノードの構造が新しい場所にグラフィカルに複製されます。また、スキーマ ツリーの任意の場所でノードの構造が変更された場合、その複合グローバル型を使用しているすべての場所に自動的に変更が適用されます。</span><span class="sxs-lookup"><span data-stu-id="075c4-109">In the schema tree, the chosen global node structure will be graphically duplicated in the new location, and any subsequent changes to the node structure in any of its locations in the schema tree are automatically made to all locations that use that complex global type.</span></span>  
  
-   <span data-ttu-id="075c4-110">**Base Data Type プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="075c4-110">**Base Data Type property**.</span></span> <span data-ttu-id="075c4-111">複合グローバル型のバリエーション (機能を拡張または制限したもののいずれか) を使用したい場合、このプロパティを、複合グローバル型に対して指定した型名に設定します (ドロップダウン リストから選択できます)。</span><span class="sxs-lookup"><span data-stu-id="075c4-111">If you want to use a variation on the complex global type, either extending it or restricting it in some way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="075c4-112">このプロパティを設定すると、 **Derived By**ノードのプロパティに対する変更を**拡張子**(および**コンテンツ タイプ**プロパティに対する変更を**ComplexContent**)、既定の派生型には、複合グローバル型を拡張することを示すです。</span><span class="sxs-lookup"><span data-stu-id="075c4-112">When you set this property, the **Derived By** node property changes to **Extension** (and the **Content Type** property changes to **ComplexContent**), indicating that extending the complex global type is the default derivation type.</span></span> <span data-ttu-id="075c4-113">変更することができます**制限**特性の場合は、変更します。</span><span class="sxs-lookup"><span data-stu-id="075c4-113">You can change it to **Restriction** if your modifications are of that nature.</span></span> <span data-ttu-id="075c4-114">派生元のベースの複合グローバル型を変更すると、派生された型に自動的に変更が反映されます。ただし、派生された型の変更は、基本型に反映されません。</span><span class="sxs-lookup"><span data-stu-id="075c4-114">Changes to the base complex global type from which you are deriving are automatically reflected in the derived type, but changes in the derived type are never reflected in the base type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="075c4-115">これらのプロパティのいずれかを設定すると、もう一方の既存の設定が自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="075c4-115">Setting either one of these properties automatically causes the other one to have any existing setting removed.</span></span> <span data-ttu-id="075c4-116">さらに、自動相互作用の他の設定など、関連するプロパティが表示されます、 **Derived By**プロパティを **(既定)** から既存の設定を削除、**ベースデータ型**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="075c4-116">Further, you will notice other automatic interactions between the related properties, such as setting the **Derived By** property to **(Default)** removes any existing setting from the **Base Data Type** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="075c4-117">XSD ビューの変更を参照しながら、テストのスキーマを作成し、これらのプロパティに別の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="075c4-117">You can create a test schema and use different values for these properties, observing the changes in the XSD view.</span></span>  
  
 <span data-ttu-id="075c4-118">このセクションでは、このトピックで説明するプロパティの設定によって制御されるためとを拡張し、それらを制限することでの両方に、複合グローバル型を使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="075c4-118">This section describes using complex global types, both as is, and by extending and restricting them, as controlled by the settings of the properties described in this topic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="075c4-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="075c4-119">In This Section</span></span>  
  
-   [<span data-ttu-id="075c4-120">複合グローバル型を再利用</span><span class="sxs-lookup"><span data-stu-id="075c4-120">Complex Global Type Re-use</span></span>](../core/complex-global-type-re-use.md)  
  
-   [<span data-ttu-id="075c4-121">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="075c4-121">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)