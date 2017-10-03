---
title: "開く、保存、終了、およびマップの名前を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bad04c72e4c3f0caf1af8e223d3f17e4687b736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-open-save-close-and-rename-maps"></a><span data-ttu-id="b332c-102">マップを開く、保存、終了する方法と、マップの名前を変更する方法</span><span class="sxs-lookup"><span data-stu-id="b332c-102">How to Open, Save, Close, and Rename Maps</span></span>
<span data-ttu-id="b332c-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマップは、.btm という拡張子付きのファイルとして、ファイル システム内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="b332c-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], maps exist as files in the file system with .btm extensions.</span></span> <span data-ttu-id="b332c-104">ただし、マップを開く、保存する、閉じるなどの操作は、BizTalk プロジェクト内から行うのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="b332c-104">Nevertheless, it is much more common to work with maps as items in a BizTalk project, from which you perform operations such as opening, saving, and closing maps.</span></span>  
  
### <a name="to-open-a-map"></a><span data-ttu-id="b332c-105">マップを開くには</span><span class="sxs-lookup"><span data-stu-id="b332c-105">To open a map</span></span>  
  
1.  <span data-ttu-id="b332c-106">ソリューション エクスプローラーで、開くマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="b332c-106">In Solution Explorer, select the map you want to open.</span></span>  
  
2.  <span data-ttu-id="b332c-107">**ビュー**  メニューのをクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="b332c-107">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="b332c-108">マップは、BizTalk マッパーで開きます。</span><span class="sxs-lookup"><span data-stu-id="b332c-108">The map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b332c-109">ソリューション エクスプ ローラーでマップを右クリックしてをクリックして**開く**、またはソリューション エクスプ ローラーでマップをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b332c-109">You can also right-click the map in Solution Explorer, and then click **Open**, or simply double-click the map in Solution Explorer.</span></span>  
  
### <a name="to-save-a-map"></a><span data-ttu-id="b332c-110">マップを保存するには</span><span class="sxs-lookup"><span data-stu-id="b332c-110">To save a map</span></span>  
  
1.  <span data-ttu-id="b332c-111">ソリューション エクスプローラーで、保存するマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="b332c-111">In Solution Explorer, select the map you want to save.</span></span>  
  
2.  <span data-ttu-id="b332c-112">**ファイル** メニューのをクリックして**保存*\<マップの名前 >***です。</span><span class="sxs-lookup"><span data-stu-id="b332c-112">On the **File** menu, click **Save *\<Name of Map>***.</span></span>  
  
### <a name="to-save-a-map-to-a-new-location"></a><span data-ttu-id="b332c-113">マップを別の場所に保存するには</span><span class="sxs-lookup"><span data-stu-id="b332c-113">To save a map to a new location</span></span>  
  
1.  <span data-ttu-id="b332c-114">ソリューション エクスプローラーで、マップの保存先を選択します。</span><span class="sxs-lookup"><span data-stu-id="b332c-114">In Solution Explorer, select the map you want to save to a new location.</span></span>  
  
2.  <span data-ttu-id="b332c-115">**ファイル** メニューのをクリックして**保存*\<マップの名前 >*として**です。</span><span class="sxs-lookup"><span data-stu-id="b332c-115">On the **File** menu, click **Save *\<Name of Map>* As**.</span></span>  
  
3.  <span data-ttu-id="b332c-116">**ファイルに名前を付けて** ダイアログ ボックスで、マップを保存するフォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="b332c-116">In the **Save File As** dialog box, browse to the folder location where you want to save the map.</span></span>  
  
4.  <span data-ttu-id="b332c-117">**ファイル名**ボックスで、ファイルの名前を入力し、をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="b332c-117">In the **File name** box, type a name for the file, and then click **Save**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b332c-118">マップに次の名前を使用しないでください。"XmlContent"、"SourceSchemas"、"TargetSchemas"、または"XsltArgumentListContent"です。そのためコンパイルで問題が発生、対応する .NET アセンブリで生成された c# コードです。</span><span class="sxs-lookup"><span data-stu-id="b332c-118">Do not use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent"; doing so will cause compilation problems in the generated C# code in the corresponding .NET assembly.</span></span> <span data-ttu-id="b332c-119">問題とその解決方法については、次を参照してください。[マップのトラブルシューティング](../core/troubleshooting-maps.md)です。</span><span class="sxs-lookup"><span data-stu-id="b332c-119">For information about issues and their resolution, see [Troubleshooting Maps](../core/troubleshooting-maps.md).</span></span>  
  
### <a name="to-rename-a-map"></a><span data-ttu-id="b332c-120">マップの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="b332c-120">To rename a map</span></span>  
  
1.  <span data-ttu-id="b332c-121">ソリューション エクスプ ローラーで、名前を変更し、をクリックする地図を右クリックして**の名前を変更**です。</span><span class="sxs-lookup"><span data-stu-id="b332c-121">In Solution Explorer, right-click the map that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="b332c-122">ソリューション エクスプローラーで、マップ位置に表示された編集ボックスに新しいマップ名を入力するか、既存の名前を変更し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b332c-122">In the editing box that appears in the location of the map in Solution Explorer, type the new name for the map, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b332c-123">変更することも、**型名**の名前を変更するときにマップします。</span><span class="sxs-lookup"><span data-stu-id="b332c-123">You may also want to change the **Type Name** of the map when you rename it.</span></span> <span data-ttu-id="b332c-124">変更する、**型名**を選択して、**マップ**、ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="b332c-124">You change the **Type Name** by selecting the **map** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
#### <a name="to-close-a-map"></a><span data-ttu-id="b332c-125">マップを閉じるには</span><span class="sxs-lookup"><span data-stu-id="b332c-125">To close a map</span></span>  
  
1.  <span data-ttu-id="b332c-126">ソリューション エクスプローラーで、閉じるマップを選択します。</span><span class="sxs-lookup"><span data-stu-id="b332c-126">In Solution Explorer, select the map you want to close.</span></span>  
  
2.  <span data-ttu-id="b332c-127">**[ファイル]** メニューの **[閉じる]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b332c-127">On the **File** menu, click **Close**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b332c-128">閉じるアイコンをクリックすることもできます ([**x**])、Microsoft の右上隅に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。</span><span class="sxs-lookup"><span data-stu-id="b332c-128">You can also click the close icon ([**x**]) in the upper-right corner of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b332c-129">参照</span><span class="sxs-lookup"><span data-stu-id="b332c-129">See Also</span></span>  
 [<span data-ttu-id="b332c-130">プロジェクト内のマップを管理します。</span><span class="sxs-lookup"><span data-stu-id="b332c-130">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)