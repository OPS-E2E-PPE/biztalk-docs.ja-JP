---
title: 複合グローバル型を使用する方法 |Microsoft Docs
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
ms.openlocfilehash: 4bf40f80a1c1353dc56b11c8e84e8d7d395beb37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393614"
---
# <a name="ways-to-use-complex-global-types"></a><span data-ttu-id="886fb-102">複合グローバル型の使用方法</span><span class="sxs-lookup"><span data-stu-id="886fb-102">Ways to Use Complex Global Types</span></span>
<span data-ttu-id="886fb-103">複合型を複合グローバル型に変換した後、スキーマ内の他の場所で再利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="886fb-103">After you have converted a complex type to a global complex type, it becomes available for reuse in other locations within your schema.</span></span> <span data-ttu-id="886fb-104">複合型を定義して、グローバルな複合型への変換の詳細については、次を参照してください。[複合グローバル型の定義と名前付け](../core/complex-global-type-definition-and-naming.md)します。</span><span class="sxs-lookup"><span data-stu-id="886fb-104">For more information about defining a complex type and then converting it to a global complex type, see [Complex Global Type Definition and Naming](../core/complex-global-type-definition-and-naming.md).</span></span>  
  
 <span data-ttu-id="886fb-105">最初に、新しい挿入**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="886fb-105">First, you insert a new **Record** node.</span></span> <span data-ttu-id="886fb-106">挿入されたノードを選択し、それぞれ異なる効果を [プロパティ] ウィンドウで、次の 2 つのノード プロパティのいずれかの設定。</span><span class="sxs-lookup"><span data-stu-id="886fb-106">Then you select the inserted node and set one of the following two node properties in the Properties window, each for a different effect:</span></span>  
  
-   <span data-ttu-id="886fb-107">**Data Structure Type プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="886fb-107">**Data Structure Type property**.</span></span> <span data-ttu-id="886fb-108">をまったく変更せず、複合グローバル型を使用する場合は、このプロパティを設定がドロップダウン リストの選択肢として利用可能な複合グローバル型に対して指定した型名にします。</span><span class="sxs-lookup"><span data-stu-id="886fb-108">If you want to use the complex global type without modifying it in any way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="886fb-109">スキーマ ツリーで選択されたグローバル ノード構造が新しい場所にグラフィカルに複製し、スキーマ ツリーでその場所のいずれかでノードの構造が変更されたは、その複合グローバル型を使用するすべての場所に自動的にされます.</span><span class="sxs-lookup"><span data-stu-id="886fb-109">In the schema tree, the chosen global node structure will be graphically duplicated in the new location, and any subsequent changes to the node structure in any of its locations in the schema tree are automatically made to all locations that use that complex global type.</span></span>  
  
-   <span data-ttu-id="886fb-110">**Base Data Type プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="886fb-110">**Base Data Type property**.</span></span> <span data-ttu-id="886fb-111">複合グローバル型のバリエーションの 1 つを使用するには、何らかの方法での制限または拡張することは設定がドロップダウン リストの選択肢として利用可能な複合グローバル型に対して指定した型名をこのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="886fb-111">If you want to use a variation on the complex global type, either extending it or restricting it in some way, set this property to the type name you gave to the complex global type, which is available as a choice in the drop-down list.</span></span> <span data-ttu-id="886fb-112">このプロパティを設定するときに、 **Derived By**ノードのプロパティに対する変更を**拡張子**(と**コンテンツの種類**プロパティに対する変更を**ComplexContent**)、既定の派生型が複合グローバル型を拡張することを示します。</span><span class="sxs-lookup"><span data-stu-id="886fb-112">When you set this property, the **Derived By** node property changes to **Extension** (and the **Content Type** property changes to **ComplexContent**), indicating that extending the complex global type is the default derivation type.</span></span> <span data-ttu-id="886fb-113">変更することができます**制限**変更内容がその性質である場合。</span><span class="sxs-lookup"><span data-stu-id="886fb-113">You can change it to **Restriction** if your modifications are of that nature.</span></span> <span data-ttu-id="886fb-114">派生する基本の複合グローバル型への変更は、派生型では、自動的に反映されますが、基本データ型の派生型の変更が反映されることはありません。</span><span class="sxs-lookup"><span data-stu-id="886fb-114">Changes to the base complex global type from which you are deriving are automatically reflected in the derived type, but changes in the derived type are never reflected in the base type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="886fb-115">これらのプロパティのいずれかが自動的に設定すると、既存の設定を削除して、もう 1 つ。</span><span class="sxs-lookup"><span data-stu-id="886fb-115">Setting either one of these properties automatically causes the other one to have any existing setting removed.</span></span> <span data-ttu-id="886fb-116">さらに、その他の自動の設定など、関連するプロパティ間の相互作用が表示されます、 **Derived By**プロパティを **(既定)** から既存の設定を削除、**ベースデータ型**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="886fb-116">Further, you will notice other automatic interactions between the related properties, such as setting the **Derived By** property to **(Default)** removes any existing setting from the **Base Data Type** property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="886fb-117">テストのスキーマを作成し、XSD ビューの変更を観察し、これらのプロパティの異なる値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="886fb-117">You can create a test schema and use different values for these properties, observing the changes in the XSD view.</span></span>  
  
 <span data-ttu-id="886fb-118">このセクションでは、このトピックで説明されているプロパティの設定で制御されるとを拡張して、それらを制限することによっての両方に、複合グローバル型を使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="886fb-118">This section describes using complex global types, both as is, and by extending and restricting them, as controlled by the settings of the properties described in this topic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="886fb-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="886fb-119">In This Section</span></span>  
  
-   [<span data-ttu-id="886fb-120">複合グローバル型の再利用</span><span class="sxs-lookup"><span data-stu-id="886fb-120">Complex Global Type Re-use</span></span>](../core/complex-global-type-re-use.md)  
  
-   [<span data-ttu-id="886fb-121">複合グローバル型の派生</span><span class="sxs-lookup"><span data-stu-id="886fb-121">Complex Global Type Derivation</span></span>](../core/complex-global-type-derivation.md)