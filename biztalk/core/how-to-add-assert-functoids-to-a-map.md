---
title: 追加する方法、マップにアサート Functoid |Microsoft ドキュメント
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
ms.openlocfilehash: 553daa0c6e97d09e8284d2369e801c5d2ff8beee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247762"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a><span data-ttu-id="4680c-102">マップにアサート Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4680c-102">How to Add Assert Functoids to a Map</span></span>
<span data-ttu-id="4680c-103">**Assert** functoid では、マップには、条件に関する仮定をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="4680c-103">The **Assert** functoid enables you to test your assumptions about conditions in your map.</span></span> <span data-ttu-id="4680c-104">たとえば、製品の購入で追加の割引を決定する計算を実行する場合がありますをアサートする追加の割引である論理 functoid を使用して 100 ドルを超える (**より大きい**または**Less Than**)。</span><span class="sxs-lookup"><span data-stu-id="4680c-104">For example, if you perform some calculations to determine an additional discount on product purchases, you might assert that the additional discount be no more than $100 by using a logical functoid (**Greater Than** or **Less Than**).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4680c-105">**Assert** functoid は、開発ビルドでのみ発生させる場合や、**デバッグ情報の生成**プロジェクトのビルド設定のプロパティに設定されて**True**です。</span><span class="sxs-lookup"><span data-stu-id="4680c-105">The **Assert** functoid only fires in development builds or when the **Generate Debugging Information** property in the project build settings is set to **True**.</span></span> <span data-ttu-id="4680c-106">展開用に、BizTalk アプリケーションをコンパイルするときに、**デバッグ情報の生成**プロパティに設定されている**False** (既定)、アサートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4680c-106">When your BizTalk application is compiled for deployment and the **Generate Debugging Information** property is set to **False** (the default), assertions are ignored.</span></span>  
  
 <span data-ttu-id="4680c-107">概要については、 **Assert** functoid を参照してください[アサート Functoid](../core/assert-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="4680c-107">For conceptual information about the **Assert** functoid, see [Assert Functoid](../core/assert-functoid.md).</span></span>  
  
## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="4680c-108">マップにアサート functoid を追加し、構成</span><span class="sxs-lookup"><span data-stu-id="4680c-108">Add the Assert functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="4680c-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="4680c-109">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="4680c-110">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4680c-110">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="4680c-111">ドラッグ、 **Assert** functoid (![アサート functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) をグリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="4680c-111">Drag the **Assert** functoid (![Assert functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4680c-112">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="4680c-112">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="4680c-113">別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4680c-113">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span> 
    >    
    >  <span data-ttu-id="4680c-114">複数の Functoid を使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4680c-114">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="4680c-115">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4680c-115">Functoids are executed from left to right.</span></span> <span data-ttu-id="4680c-116">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="4680c-116">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="4680c-117">Functoid には 3 つの入力パラメーターが必要で、それによって 1 つの出力パラメーターが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4680c-117">The functoid must have exactly three input parameters and it generates one output parameter.</span></span> <span data-ttu-id="4680c-118">最初のパラメーターを確立するために、 **Assert** functoid から他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドからです。</span><span class="sxs-lookup"><span data-stu-id="4680c-118">To establish the first parameter for the **Assert** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="4680c-119">2 番目の入力パラメーターを設定する、 **Assert** functoid、送信元スキーマ内のフィールド ノードによって、入力リンクを作成、 **Assert** functoid は、定数を挿入またはします。</span><span class="sxs-lookup"><span data-stu-id="4680c-119">To establish the second input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
5.  <span data-ttu-id="4680c-120">3 番目の入力パラメーターを確立するために、 **Assert** functoid、送信元スキーマ内のフィールド ノードによって、入力リンクを作成、 **Assert** functoid は、定数を挿入または。</span><span class="sxs-lookup"><span data-stu-id="4680c-120">To establish the third input parameter for the **Assert** functoid, create an input link by a field node in the source schema to the **Assert** functoid, or insert a constant.</span></span>  
  
6.  <span data-ttu-id="4680c-121">出力パラメーターを使用する、 **Assert** functoid をドラッグして、出力リンクを作成、 **Assert** functoid を送信先スキーマ内のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="4680c-121">To use the output parameter from the **Assert** functoid, create an output link by dragging the **Assert** functoid to a field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4680c-122">その他の functoid の出力と同様、 **Assert** functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4680c-122">As with other functoids, the output of the **Assert** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4680c-123">参照</span><span class="sxs-lookup"><span data-stu-id="4680c-123">See Also</span></span>  
-  <span data-ttu-id="4680c-124">**アサート Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4680c-124">**Assert Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="4680c-125">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="4680c-125">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)