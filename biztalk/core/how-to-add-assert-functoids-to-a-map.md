---
title: 追加する方法にアサート Functoid をマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cfeabbbeac860e927854fb79c90d2b1608b9c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015275"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a><span data-ttu-id="e0468-102">マップにアサート Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e0468-102">How to Add Assert Functoids to a Map</span></span>
<span data-ttu-id="e0468-103">**Assert** functoid では、マップには、条件に関する仮定をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0468-103">The **Assert** functoid enables you to test your assumptions about conditions in your map.</span></span> <span data-ttu-id="e0468-104">たとえば、製品の購入で追加の割引を決定する計算を実行する場合がありますをアサートする追加の割引になる論理 functoid を使用して 100 ドルを超える (**より大きい**または**Less Than**)。</span><span class="sxs-lookup"><span data-stu-id="e0468-104">For example, if you perform some calculations to determine an additional discount on product purchases, you might assert that the additional discount be no more than $100 by using a logical functoid (**Greater Than** or **Less Than**).</span></span>  

> [!NOTE]
>  <span data-ttu-id="e0468-105">**Assert** functoid は、開発途中のビルドにのみ実行されますか、**デバッグ情報の生成**プロジェクトのビルド設定のプロパティに設定されて**True**します。</span><span class="sxs-lookup"><span data-stu-id="e0468-105">The **Assert** functoid only fires in development builds or when the **Generate Debugging Information** property in the project build settings is set to **True**.</span></span> <span data-ttu-id="e0468-106">展開用に、BizTalk アプリケーションをコンパイルするときに、**デバッグ情報の生成**プロパティに設定されて**False** (既定)、アサートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="e0468-106">When your BizTalk application is compiled for deployment and the **Generate Debugging Information** property is set to **False** (the default), assertions are ignored.</span></span>  

 <span data-ttu-id="e0468-107">概念情報については、 **Assert** functoid を参照してください[アサート Functoid](../core/assert-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0468-107">For conceptual information about the **Assert** functoid, see [Assert Functoid](../core/assert-functoid.md).</span></span>  

## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="e0468-108">マップにアサート functoid を追加し、構成</span><span class="sxs-lookup"><span data-stu-id="e0468-108">Add the Assert functoid to a map and configure it</span></span>  

1. <span data-ttu-id="e0468-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="e0468-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="e0468-110">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0468-110">The list of advanced functoids in the chosen category appears.</span></span>  

2. <span data-ttu-id="e0468-111">ドラッグ、 **Assert** functoid (![アサート functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="e0468-111">Drag the **Assert** functoid (![Assert functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e0468-112">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e0468-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="e0468-113">別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0468-113">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span> 
   >    
   >  <span data-ttu-id="e0468-114">複数の Functoid を使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0468-114">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="e0468-115">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0468-115">Functoids are executed from left to right.</span></span> <span data-ttu-id="e0468-116">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="e0468-116">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  

3. <span data-ttu-id="e0468-117">Functoid には 3 つの入力パラメーターが必要で、それによって 1 つの出力パラメーターが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e0468-117">The functoid must have exactly three input parameters and it generates one output parameter.</span></span> <span data-ttu-id="e0468-118">最初のパラメーターを確立するために、 **Assert** functoid からその他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドから。</span><span class="sxs-lookup"><span data-stu-id="e0468-118">To establish the first parameter for the **Assert** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  

4. <span data-ttu-id="e0468-119">2 番目の入力パラメーターを設定する、 **Assert** functoid は、フィールド ノードに送信元スキーマによって、入力リンクを作成、 **Assert** functoid、または定数を挿入します。</span><span class="sxs-lookup"><span data-stu-id="e0468-119">To establish the second input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  

5. <span data-ttu-id="e0468-120">3 番目の入力パラメーターを設定する、 **Assert** functoid、送信元スキーマ内のフィールド ノードで、入力リンクを作成、 **Assert** functoid、定数を挿入または。</span><span class="sxs-lookup"><span data-stu-id="e0468-120">To establish the third input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  

6. <span data-ttu-id="e0468-121">出力パラメーターを使用する、 **Assert** functoid をドラッグして、出力リンクを作成、 **Assert** functoid を送信先スキーマ内のフィールド。</span><span class="sxs-lookup"><span data-stu-id="e0468-121">To use the output parameter from the **Assert** functoid, create an output link by dragging the **Assert** functoid to a field in the destination schema.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="e0468-122">他の functoid の出力と同様、 **Assert** functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0468-122">As with other functoids, the output of the **Assert** functoid can be used as input to another functoid.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e0468-123">参照</span><span class="sxs-lookup"><span data-stu-id="e0468-123">See Also</span></span>  
- <span data-ttu-id="e0468-124">**アサート Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e0468-124">**Assert Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
- [<span data-ttu-id="e0468-125">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="e0468-125">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)
