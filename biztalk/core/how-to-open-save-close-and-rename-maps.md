---
title: 開く、保存、終了、およびマップの名前を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ef0bcaad7dc3cd4bd526657eb86194e2d986e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335817"
---
# <a name="how-to-open-save-close-and-rename-maps"></a><span data-ttu-id="e260a-102">マップを開く、保存、終了する方法と、マップの名前を変更する方法</span><span class="sxs-lookup"><span data-stu-id="e260a-102">How to Open, Save, Close, and Rename Maps</span></span>
<span data-ttu-id="e260a-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマップは、.btm という拡張子付きのファイルとして、ファイル システム内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e260a-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], maps exist as files in the file system with .btm extensions.</span></span> <span data-ttu-id="e260a-104">ただし、マップを開く、保存する、閉じるなどの操作は、BizTalk プロジェクト内から行うのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="e260a-104">Nevertheless, it is much more common to work with maps as items in a BizTalk project, from which you perform operations such as opening, saving, and closing maps.</span></span>  
  
### <a name="to-open-a-map"></a><span data-ttu-id="e260a-105">マップを開くには</span><span class="sxs-lookup"><span data-stu-id="e260a-105">To open a map</span></span>  
  
1.  <span data-ttu-id="e260a-106">ソリューション エクスプローラーで、開くマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="e260a-106">In Solution Explorer, select the map you want to open.</span></span>  
  
2.  <span data-ttu-id="e260a-107">**ビュー**  メニューのをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="e260a-107">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="e260a-108">マップは、BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="e260a-108">The map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e260a-109">ソリューション エクスプ ローラーでマップを右クリックしてもをクリックしたことができます**オープン**、またはソリューション エクスプ ローラーでマップをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e260a-109">You can also right-click the map in Solution Explorer, and then click **Open**, or simply double-click the map in Solution Explorer.</span></span>  
  
### <a name="to-save-a-map"></a><span data-ttu-id="e260a-110">マップを保存するには</span><span class="sxs-lookup"><span data-stu-id="e260a-110">To save a map</span></span>  
  
1. <span data-ttu-id="e260a-111">ソリューション エクスプローラーで、保存するマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="e260a-111">In Solution Explorer, select the map you want to save.</span></span>  
  
2. <span data-ttu-id="e260a-112">**ファイル** メニューのをクリックして \* \* 保存 *\<名のマップの\>* \* \*。</span><span class="sxs-lookup"><span data-stu-id="e260a-112">On the **File** menu, click \*\*Save \*\<Name of Map\>\*\*\*.</span></span>  
  
### <a name="to-save-a-map-to-a-new-location"></a><span data-ttu-id="e260a-113">マップを別の場所に保存するには</span><span class="sxs-lookup"><span data-stu-id="e260a-113">To save a map to a new location</span></span>  
  
1.  <span data-ttu-id="e260a-114">ソリューション エクスプローラーで、マップの保存先を選択します。</span><span class="sxs-lookup"><span data-stu-id="e260a-114">In Solution Explorer, select the map you want to save to a new location.</span></span>  
  
2.  <span data-ttu-id="e260a-115">**ファイル** メニューのをクリックして**保存 *\<名のマップの\>* として**します。</span><span class="sxs-lookup"><span data-stu-id="e260a-115">On the **File** menu, click **Save *\<Name of Map\>* As**.</span></span>  
  
3.  <span data-ttu-id="e260a-116">**ファイルに名前を付けて** ダイアログ ボックスで、マップを保存するフォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="e260a-116">In the **Save File As** dialog box, browse to the folder location where you want to save the map.</span></span>  
  
4.  <span data-ttu-id="e260a-117">**ファイル名**ボックスで、ファイルの名前を入力し、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="e260a-117">In the **File name** box, type a name for the file, and then click **Save**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e260a-118">マップに次の名前は使用しません。"XmlContent"、"SourceSchemas"、"TargetSchemas"、"XsltArgumentListContent"またはそのためのコンパイルで問題が発生、生成されたC#対応する .NET アセンブリ内のコード。</span><span class="sxs-lookup"><span data-stu-id="e260a-118">Do not use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent"; doing so will cause compilation problems in the generated C# code in the corresponding .NET assembly.</span></span> <span data-ttu-id="e260a-119">問題とその解決方法については、次を参照してください。[マップのトラブルシューティング](../core/troubleshooting-maps.md)します。</span><span class="sxs-lookup"><span data-stu-id="e260a-119">For information about issues and their resolution, see [Troubleshooting Maps](../core/troubleshooting-maps.md).</span></span>  
  
### <a name="to-rename-a-map"></a><span data-ttu-id="e260a-120">マップの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="e260a-120">To rename a map</span></span>  
  
1.  <span data-ttu-id="e260a-121">ソリューション エクスプ ローラーで、クリックして、名前を変更するマップを右クリックして**の名前を変更**します。</span><span class="sxs-lookup"><span data-stu-id="e260a-121">In Solution Explorer, right-click the map that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="e260a-122">ソリューション エクスプローラーで、マップ位置に表示された編集ボックスに新しいマップ名を入力するか、既存の名前を変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e260a-122">In the editing box that appears in the location of the map in Solution Explorer, type the new name for the map, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e260a-123">変更することも、**型名**の名前を変更するときにマップします。</span><span class="sxs-lookup"><span data-stu-id="e260a-123">You may also want to change the **Type Name** of the map when you rename it.</span></span> <span data-ttu-id="e260a-124">変更する、**型名**を選択して、**マップ**ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="e260a-124">You change the **Type Name** by selecting the **map** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
#### <a name="to-close-a-map"></a><span data-ttu-id="e260a-125">マップを閉じるには</span><span class="sxs-lookup"><span data-stu-id="e260a-125">To close a map</span></span>  
  
1. <span data-ttu-id="e260a-126">ソリューション エクスプローラーで、閉じるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="e260a-126">In Solution Explorer, select the map you want to close.</span></span>  
  
2. <span data-ttu-id="e260a-127">**[ファイル]** メニューの **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e260a-127">On the **File** menu, click **Close**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e260a-128">ある閉じるアイコンをクリックすることもできます ( **[x]** )、Microsoft の右上隅にある[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="e260a-128">You can also click the close icon ([**x**]) in the upper-right corner of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e260a-129">参照</span><span class="sxs-lookup"><span data-stu-id="e260a-129">See Also</span></span>  
 [<span data-ttu-id="e260a-130">プロジェクト内のマップの管理</span><span class="sxs-lookup"><span data-stu-id="e260a-130">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)