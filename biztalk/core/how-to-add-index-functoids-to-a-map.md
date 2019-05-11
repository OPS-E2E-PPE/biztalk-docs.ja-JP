---
title: マップにインデックス Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab94f8c3b922f6847fdeff9c514025b5718336c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343287"
---
# <a name="how-to-add-index-functoids-to-a-map"></a><span data-ttu-id="a72de-102">マップにインデックス Functoid を追加する方法</span><span class="sxs-lookup"><span data-stu-id="a72de-102">How to Add Index Functoids to a Map</span></span>
<span data-ttu-id="a72de-103">**インデックス**functoid では、一連のループ レコードの特定のレコードから情報を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="a72de-103">The **Index** functoid enables you to select information from a specific record in a series of looping records.</span></span> <span data-ttu-id="a72de-104">各**インデックス**functoid は、1 つのフィールドから情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="a72de-104">Each **Index** functoid selects information from a single field.</span></span>  
  
 <span data-ttu-id="a72de-105">概念情報については、**インデックス**functoid を参照してください[インデックス Functoid](../core/index-functoid.md)します。</span><span class="sxs-lookup"><span data-stu-id="a72de-105">For conceptual information about the **Index** functoid, see [Index Functoid](../core/index-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="a72de-106">マップにインデックス functoid を追加し、構成するには</span><span class="sxs-lookup"><span data-stu-id="a72de-106">To add the Index functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="a72de-107">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。</span><span class="sxs-lookup"><span data-stu-id="a72de-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="a72de-108">選択したカテゴリでの高度な functoid の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a72de-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="a72de-109">ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) ツールボックスからグリッド ページの適切な場所にします。</span><span class="sxs-lookup"><span data-stu-id="a72de-109">Drag the **Index** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a72de-110">Functoid は表示されているグリッド ページに配置されます。</span><span class="sxs-lookup"><span data-stu-id="a72de-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="a72de-111">別のグリッド ページに functoid を配置する場合は、最初に、その他のグリッド ページを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a72de-111">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a72de-112">まとめて 1 つ以上の functoid を使用してマップを構築する場合は、左から右の相対的な配置を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a72de-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="a72de-113">Functoids は左から順に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a72de-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="a72de-114">1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。</span><span class="sxs-lookup"><span data-stu-id="a72de-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="a72de-115">フィールドの入力パラメーターを設定する、**インデックス**functoid、送信元スキーマからループ レコード内のフィールドをドラッグして、入力リンクを作成、**インデックス**functoid、をドラッグするか**インデックス**functoid を送信元スキーマのループ レコード内のフィールド。</span><span class="sxs-lookup"><span data-stu-id="a72de-115">To establish the field input parameter for the **Index** functoid, create an input link by dragging a field within a looping record from the source schema to the **Index** functoid, or dragging the **Index** functoid to a field within the looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="a72de-116">少なくとも 1 つのインデックス入力パラメーターを設定する、**インデックス**functoid は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a72de-116">To establish at least one index input parameter for the **Index** functoid, perform the following steps:</span></span>  
  
   1.  <span data-ttu-id="a72de-117">**インデックス**functoid を選択すると、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a72de-117">With the **Index** functoid selected, click the ellipsis (**...**) button associated with the **Input Parameters** property in the **Properties** window.</span></span>  
  
   2.  <span data-ttu-id="a72de-118">**インデックス Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a72de-118">In the **Configure Index Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span>  
  
   3.  <span data-ttu-id="a72de-119">編集ボックスで、数値の値として、インデックス入力パラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="a72de-119">In the edit box, type the index input parameter as a numeric value.</span></span> <span data-ttu-id="a72de-120">追加のインデックス値が必要ですが、クリックすると、必要に応じて繰り返します**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a72de-120">Repeat as necessary if additional index values are required, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="a72de-121">出力パラメーターを使用する、**インデックス**functoid をドラッグして、出力リンクを作成、**インデックス**または、を送信先スキーマのフィールドをドラッグして、送信先スキーマのフィールドをfunctoid**インデックス**functoid。</span><span class="sxs-lookup"><span data-stu-id="a72de-121">To use the output parameter from the **Index** functoid, create an output link by dragging the **Index** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Index** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a72de-122">他の functoid の出力と同様、**インデックス**functoid を別の functoid への入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a72de-122">As with other functoids, the output of the **Index** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a72de-123">参照</span><span class="sxs-lookup"><span data-stu-id="a72de-123">See Also</span></span>  
 [<span data-ttu-id="a72de-124">マップへの高度な Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="a72de-124">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)