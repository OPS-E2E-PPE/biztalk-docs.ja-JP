---
title: マップに Nil 値 Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90d5fa95bb7f7889eeca7a7a047019a67d672acd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343242"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a><span data-ttu-id="87105-102">マップに Nil 値 Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="87105-102">How to Add Nil Value Functoids to a Map</span></span>
<span data-ttu-id="87105-103">**Nil 値**functoid を送信先ノードの値を設定する**Nil**します。</span><span class="sxs-lookup"><span data-stu-id="87105-103">The **Nil Value** functoid sets the value of the destination node to **Nil**.</span></span>  

 <span data-ttu-id="87105-104">概念情報については、 **Nil 値**functoid を参照してください[Nil 値 Functoid](../core/nil-value-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="87105-104">For conceptual information about the **Nil Value** functoid, see [Nil Value Functoid](../core/nil-value-functoid.md).</span></span>  

## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="87105-105">マップに Nil 値 functoid を追加し、構成</span><span class="sxs-lookup"><span data-stu-id="87105-105">Add the Nil Value functoid to a map and configure it</span></span>  

1. <span data-ttu-id="87105-106">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="87105-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="87105-107">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87105-107">The list of advanced functoids in the chosen category appears.</span></span>  

2. <span data-ttu-id="87105-108">ドラッグ、 **Nil 値**functoid (![Nil 値 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="87105-108">Drag the **Nil Value** functoid (![Nil Value functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="87105-109">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="87105-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="87105-110">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87105-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
   >
   >  <span data-ttu-id="87105-111">1 つ以上の functoid を使用するマップを構築する場合は、左から右の相対的な配置を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87105-111">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="87105-112">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="87105-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="87105-113">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="87105-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  

3. <span data-ttu-id="87105-114">**Nil 値**functoid は 1 つの入力パラメーターに 0 であることができます。</span><span class="sxs-lookup"><span data-stu-id="87105-114">The **Nil Value** functoid can have zero to one input parameters.</span></span> <span data-ttu-id="87105-115">この functoid の入力パラメーターがない場合は、ターゲット ノードに設定されている**Nil**します。</span><span class="sxs-lookup"><span data-stu-id="87105-115">If there is no input parameter for this functoid, the target node is set to **Nil**.</span></span> <span data-ttu-id="87105-116">入力パラメーターを設定する、 **Nil 値**functoid からその他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドから。</span><span class="sxs-lookup"><span data-stu-id="87105-116">To establish the input parameter for the **Nil Value** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  

4. <span data-ttu-id="87105-117">出力パラメーターを使用する、 **Nil 値**functoid をドラッグして、出力リンクを作成、 **Nil 値**functoid、レコードまたは送信先スキーマ内のフィールドをします。</span><span class="sxs-lookup"><span data-stu-id="87105-117">To use the output parameter from the **Nil Value** functoid, create an output link by dragging the **Nil Value** functoid to a record or field in the destination schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="87105-118">他の functoid の出力と同様、 **Nil 値**functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="87105-118">As with other functoids, the output of the **Nil Value** functoid can be used as input to another functoid.</span></span>  

## <a name="see-also"></a><span data-ttu-id="87105-119">参照</span><span class="sxs-lookup"><span data-stu-id="87105-119">See Also</span></span>  
- <span data-ttu-id="87105-120">**Nil 値 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="87105-120">**Nil Value Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
- [<span data-ttu-id="87105-121">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="87105-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
