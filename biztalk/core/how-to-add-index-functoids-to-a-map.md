---
title: "インデックス Functoid をマップに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695f7830dcc35fbb0100c012cff10fa207f1ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-index-functoids-to-a-map"></a><span data-ttu-id="c91d8-102">マップにインデックス Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c91d8-102">How to Add Index Functoids to a Map</span></span>
<span data-ttu-id="c91d8-103">**インデックス**functoid では、一連のループ レコードの特定のレコードから情報を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-103">The **Index** functoid enables you to select information from a specific record in a series of looping records.</span></span> <span data-ttu-id="c91d8-104">各**インデックス**functoid が 1 つのフィールドから情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="c91d8-104">Each **Index** functoid selects information from a single field.</span></span>  
  
 <span data-ttu-id="c91d8-105">概要については、**インデックス**functoid を参照してください[インデックス Functoid](../core/index-functoid.md)です。</span><span class="sxs-lookup"><span data-stu-id="c91d8-105">For conceptual information about the **Index** functoid, see [Index Functoid](../core/index-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="c91d8-106">マップにインデックス Functoid を追加して構成するには</span><span class="sxs-lookup"><span data-stu-id="c91d8-106">To add the Index functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="c91d8-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。</span><span class="sxs-lookup"><span data-stu-id="c91d8-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="c91d8-108">選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="c91d8-109">ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) をグリッド ページの適切な場所にツールボックスからです。</span><span class="sxs-lookup"><span data-stu-id="c91d8-109">Drag the **Index** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c91d8-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="c91d8-111">別のグリッド ページに Functoid を配置する場合は、先にそのグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c91d8-111">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c91d8-112">一緒に複数の functoid を使用してマップを構築する場合は、相対左から右への配置を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c91d8-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="c91d8-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="c91d8-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="c91d8-115">フィールドの入力パラメーターを設定する、**インデックス**functoid、送信元スキーマからループ レコード内のフィールドをドラッグして、入力リンクを作成、**インデックス**functoid、をドラッグするか**インデックス**functoid、送信元スキーマのループ レコード内のフィールドを送信します。</span><span class="sxs-lookup"><span data-stu-id="c91d8-115">To establish the field input parameter for the **Index** functoid, create an input link by dragging a field within a looping record from the source schema to the **Index** functoid, or dragging the **Index** functoid to a field within the looping record in the source schema.</span></span>  
  
4.  <span data-ttu-id="c91d8-116">少なくとも 1 つのインデックス入力パラメーターを設定する、**インデックス**functoid は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c91d8-116">To establish at least one index input parameter for the **Index** functoid, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="c91d8-117">**インデックス**functoid を選択すると、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティに、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="c91d8-117">With the **Index** functoid selected, click the ellipsis (**...**) button associated with the **Input Parameters** property in the **Properties** window.</span></span>  
  
    2.  <span data-ttu-id="c91d8-118">**インデックス Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c91d8-118">In the **Configure Index Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span>  
  
    3.  <span data-ttu-id="c91d8-119">編集ボックスに、インデックス入力パラメーターを数値で入力します。</span><span class="sxs-lookup"><span data-stu-id="c91d8-119">In the edit box, type the index input parameter as a numeric value.</span></span> <span data-ttu-id="c91d8-120">追加のインデックス値が必要であり、をクリックした場合に、必要に応じて繰り返します**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c91d8-120">Repeat as necessary if additional index values are required, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c91d8-121">出力パラメーターを使用する、**インデックス**functoid をドラッグして、出力リンクを作成、**インデックス**を送信先スキーマのフィールドをドラッグするか、送信先スキーマのフィールドをfunctoid**インデックス**functoid です。</span><span class="sxs-lookup"><span data-stu-id="c91d8-121">To use the output parameter from the **Index** functoid, create an output link by dragging the **Index** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Index** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c91d8-122">その他の functoid の出力と同様、**インデックス**functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c91d8-122">As with other functoids, the output of the **Index** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c91d8-123">参照</span><span class="sxs-lookup"><span data-stu-id="c91d8-123">See Also</span></span>  
 [<span data-ttu-id="c91d8-124">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="c91d8-124">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)