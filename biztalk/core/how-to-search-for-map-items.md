---
title: マップ項目を検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.search
ms.assetid: 3dbb089a-6aa8-4921-a82d-81d3a193e933
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee61bccfae53a79d8fba6bd0aa5af2c537d98270
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255538"
---
# <a name="how-to-search-for-map-items"></a><span data-ttu-id="0c875-102">マップ項目を検索する方法</span><span class="sxs-lookup"><span data-stu-id="0c875-102">How to Search for Map Items</span></span>
<span data-ttu-id="0c875-103">BizTalk マッパーを使用すると、送信元スキーマ、送信先スキーマ、およびグリッド画面の項目を検索できます。</span><span class="sxs-lookup"><span data-stu-id="0c875-103">The BizTalk Mapper enables you to search for items in the source schema, the destination schema, and the grid surface.</span></span> <span data-ttu-id="0c875-104">このトピックでは、次の操作を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c875-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0c875-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="0c875-105">Prerequisites</span></span>  
 <span data-ttu-id="0c875-106">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c875-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-search-for-items"></a><span data-ttu-id="0c875-107">項目を検索するには</span><span class="sxs-lookup"><span data-stu-id="0c875-107">To search for items</span></span>  
 <span data-ttu-id="0c875-108">検索するスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="0c875-108">Select the schema where you want to search.</span></span> <span data-ttu-id="0c875-109">送信元スキーマを選択すると、BizTalk マッパーは送信元スキーマでのみ一致するものを検索します。</span><span class="sxs-lookup"><span data-stu-id="0c875-109">If you select source schema, the BizTalk Mapper searches and looks for the match only in the source schema.</span></span> <span data-ttu-id="0c875-110">ただし、送信元スキーマと送信先スキーマの両方を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0c875-110">However, you can select both source and destination schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c875-111">選択内容を確認するには、スキーマまたはスキーマ項目の前にマークを検索します。</span><span class="sxs-lookup"><span data-stu-id="0c875-111">To confirm selection, look for the mark before the schema or the schema item.</span></span>  
  
 <span data-ttu-id="0c875-112">![マップ項目の検索](../core/media/searching-map-items.gif "Searching_map_items")</span><span class="sxs-lookup"><span data-stu-id="0c875-112">![Searching for map items](../core/media/searching-map-items.gif "Searching_map_items")</span></span>  
  
 <span data-ttu-id="0c875-113">**検索**マッパー ユーティリティ リボンのボックスに検索する項目の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0c875-113">In the **Search** box on the Mapper utility ribbon, type the name of the item you want to search.</span></span> <span data-ttu-id="0c875-114">送信元または送信先スキーマのノードの名前、および Functoid の名前、ラベル、コメント、入力、またはスクリプトで、文字列を検索できます。</span><span class="sxs-lookup"><span data-stu-id="0c875-114">You can search for a string in the name of a node in the source or destination schema, as well as in the name, label, comment, inputs, or scripts for functoids.</span></span>  
  
 <span data-ttu-id="0c875-115">検索文字列を入力すると、検索条件を満たすオブジェクトが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c875-115">As you enter the search string, the objects that meet the search criteria are highlighted.</span></span> <span data-ttu-id="0c875-116">キーボードでキーを使用するか、矢印、検索結果を走査できるまたは![一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")と![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")ユーティリティ リボンでアイコン。</span><span class="sxs-lookup"><span data-stu-id="0c875-116">You can then traverse through the search results either using the arrow keys on the keyboard or the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") and ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") icons on the utility ribbon.</span></span> <span data-ttu-id="0c875-117">検索結果が 3 つのビューすべてに存在する場合、検索結果の移動は送信元スキーマ、リレーションシップ ビュー、送信先スキーマの順に行われます。</span><span class="sxs-lookup"><span data-stu-id="0c875-117">If the search results are spread across all three views, the search results are traversed in the order of the source schema, relationship view, and the destination schema.</span></span> <span data-ttu-id="0c875-118">検索結果を後に、検索文字列を削除するかをクリックして、検索を閉じることができます、(![マッパー検索のクリア](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) 検索文字列の横にあるアイコン。</span><span class="sxs-lookup"><span data-stu-id="0c875-118">After going through the search results, you can close the search either by deleting the search string or by clicking the (![Clear Mapper search](../core/media/mapper-search-cancel.gif "Mapper_Search_Cancel")) icon next to the search string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c875-119">また、Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら J キーを押して、または Ctrl キーを押しながら M キーを押し、次に Ctrl キーを押しながら K キーを押して、検索結果内をそれぞれ上または下に移動できます。</span><span class="sxs-lookup"><span data-stu-id="0c875-119">You can also press CTRL+M, CTRL+J or CTRL+M, CTRL+K to traverse through the search results upwards or downwards, respectively.</span></span> <span data-ttu-id="0c875-120">マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="0c875-120">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c875-121">リレーションシップ ビューの検索結果を 1 つのマップ ビューで表示できない場合は、他のヒットがある方向に点滅する矢印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c875-121">If the search results for the relationship view are not visible in a single map view, the BizTalk Mapper displays blinking arrows in the direction where there are additional hits.</span></span> <span data-ttu-id="0c875-122">上向きの矢印のアイコンなど、(![追加検索結果の双方向](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) をスクロールして表示できる追加の検索結果があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c875-122">For example, the top arrow icon (![Direction for additional search results](../core/media/mapper-search-direction.gif "Mapper_Search_Direction")) denotes that there are additional search results that can be viewed by scrolling up.</span></span> <span data-ttu-id="0c875-123">同様に、検索結果が別のマップ ページにある場合は、そのページのページ タブが黄色で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c875-123">Similarly, if there are search results in different map pages, the page tabs for those pages are highlighted, in yellow.</span></span> <span data-ttu-id="0c875-124">強調表示されたページにマウスを移動すると、ツールヒントにそのページにある一致した検索結果の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c875-124">On moving the mouse over the highlighted page, the tooltip displays the number of search matches on that page.</span></span> <span data-ttu-id="0c875-125">ステータス バーに検索結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c875-125">The status bar displays the search results.</span></span>  
  
 <span data-ttu-id="0c875-126">![ステータス バー、検索結果を表示する](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span><span class="sxs-lookup"><span data-stu-id="0c875-126">![Status bar displaying the search results](../core/media/searching-map-items-statusbar.jpg "Searching_map_items_statusbar")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c875-127">参照</span><span class="sxs-lookup"><span data-stu-id="0c875-127">See Also</span></span>  
 [<span data-ttu-id="0c875-128">BizTalk マッパーの使用</span><span class="sxs-lookup"><span data-stu-id="0c875-128">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)