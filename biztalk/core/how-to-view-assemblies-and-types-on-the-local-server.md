---
title: "ローカル サーバー上のアセンブリと型を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c0f49559de7c4b1a13982578478cf249520479
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a><span data-ttu-id="01b0b-102">ローカル サーバーにあるアセンブリと種類を表示する方法</span><span class="sxs-lookup"><span data-stu-id="01b0b-102">How to View Assemblies and Types on the Local Server</span></span>
<span data-ttu-id="01b0b-103">BizTalk アセンブリ ビューアーを使用すると、ローカル サーバーにインストールされているすべての BizTalk アセンブリと種類を表示できます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-103">You can use the BizTalk Assembly Viewer to examine all BizTalk assemblies and types installed on the local server.</span></span>  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a><span data-ttu-id="01b0b-104">GAC にインストールされているすべての BizTalk Server アセンブリを表示するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-104">To view all BizTalk Server assemblies installed in the GAC</span></span>  
  
-   <span data-ttu-id="01b0b-105">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-105">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
     <span data-ttu-id="01b0b-106">コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされているすべての BizTalk アセンブリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-106">All BizTalk assemblies installed in the global assembly cache (GAC) on the computer appear.</span></span>  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
<span data-ttu-id="01b0b-107">アセンブリ ビューアーの開始ページ</span><span class="sxs-lookup"><span data-stu-id="01b0b-107">Assembly Viewer open page</span></span>  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a><span data-ttu-id="01b0b-108">BizTalk アセンブリの種類、属性、および参照を表示するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-108">To view types, attributes, and references for a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="01b0b-109">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-109">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="01b0b-110">対象のアセンブリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-110">Double click the appropriate assembly.</span></span>  
  
     <span data-ttu-id="01b0b-111">右ペインに、BizTalk アセンブリの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-111">The BizTalk assembly types appear in the right pane.</span></span> <span data-ttu-id="01b0b-112">左ペインに、属性と種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-112">The attributes and types appear in the left pane.</span></span>  
  
     <span data-ttu-id="01b0b-113">クリックして、アセンブリのインストール場所に移動することもできます、**コードベース**左上の作業ウィンドウの領域にリンクします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-113">You can also navigate to the installed location of the assembly by clicking the **Codebase** link in the upper left section of the task pane.</span></span> <span data-ttu-id="01b0b-114">(Windows エクスプローラーがフォルダー ビューになっているときは、作業ウィンドウがフォルダー リストで置き換えられるため、このリンクは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="01b0b-114">(You cannot view this link when Windows Explorer is in Folder view because the task pane is replaced by the folder list.)</span></span>  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a><span data-ttu-id="01b0b-115">BizTalk アセンブリの種類の内容を表示するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-115">To view the contents of a type in a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="01b0b-116">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-116">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="01b0b-117">対象のアセンブリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-117">Double click the appropriate assembly.</span></span>  
  
3.  <span data-ttu-id="01b0b-118">右ペインで、対象の種類をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-118">In the right pane, double-click the appropriate type.</span></span>  
  
     <span data-ttu-id="01b0b-119">**コンテンツの種類ビューアー**ウィンドウが開き、XML 定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-119">The **Type Content Viewer** window opens and the XML definition appears.</span></span>  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a><span data-ttu-id="01b0b-120">BizTalk アセンブリを GAC に追加するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-120">To add a BizTalk assembly in the GAC</span></span>  
  
1.  <span data-ttu-id="01b0b-121">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-121">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="01b0b-122">Windows エクスプローラーで、GAC に追加するアセンブリに移動します。</span><span class="sxs-lookup"><span data-stu-id="01b0b-122">Use Windows Explorer to navigate to the assembly that you want to add in the GAC.</span></span>  
  
3.  <span data-ttu-id="01b0b-123">アセンブリをドラッグして、BizTalk アセンブリ ビューアーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-123">Drag the assembly and drop it into the BizTalk Assembly Viewer.</span></span>  
  
     <span data-ttu-id="01b0b-124">BizTalk アセンブリ ビューアーは、BizTalk Server アセンブリのみを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-124">The BizTalk Assembly Viewer accepts only BizTalk Server assemblies.</span></span> <span data-ttu-id="01b0b-125">BizTalk 以外のアセンブリをビューアーにドロップしても無視されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-125">If you drop a non-BizTalk assembly in the viewer, it is ignored.</span></span>  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a><span data-ttu-id="01b0b-126">GAC から BizTalk アセンブリを削除するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-126">To remove a BizTalk assembly from the GAC</span></span>  
  
1.  <span data-ttu-id="01b0b-127">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-127">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="01b0b-128">クリックして、GAC から削除するアセンブリを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-128">Right-click the assembly you want to remove from the GAC and click **Delete**.</span></span>  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a><span data-ttu-id="01b0b-129">すべての BizTalk アセンブリの種類を検索するには</span><span class="sxs-lookup"><span data-stu-id="01b0b-129">To search for a type in all BizTalk assemblies</span></span>  
  
1.  <span data-ttu-id="01b0b-130">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、順にダブルクリック**BizTalk Server アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="01b0b-130">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="01b0b-131">メニュー バーからをクリックして、 **Biztalk Server 検索**アイコン。</span><span class="sxs-lookup"><span data-stu-id="01b0b-131">From the menu bar, click the **Biz Talk Server Search** icon.</span></span>  
  
3.  <span data-ttu-id="01b0b-132">[検索] ウィンドウ内の型を指定、**種類の検索**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="01b0b-132">In the Search window, specify the type in the **Find Types** drop-down list.</span></span>  
  
4.  <span data-ttu-id="01b0b-133">**BizTalk Server アセンブリ ファイルの場所**ドロップダウン リストで、検索対象のアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="01b0b-133">In the **Look in BizTalk Server assemblies** drop-down list, select the assemblies to be searched.</span></span>  
  
5.  <span data-ttu-id="01b0b-134">指定した種類から参照されている種類だけが表示されるように検索を絞り込むには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="01b0b-134">To narrow your search to include only types that are referenced by a specified type, do the following:</span></span>  
  
    1.  <span data-ttu-id="01b0b-135">クリックして、**高度な検索条件**リンクします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-135">Click the **Advanced Search Criteria** link.</span></span>  
  
    2.  <span data-ttu-id="01b0b-136">**によって参照されている**ドロップダウン リストで、種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="01b0b-136">In the **Which are referenced by** drop-down list, select the type.</span></span>  
  
    3.  <span data-ttu-id="01b0b-137">**[検索]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01b0b-137">Click **Search**.</span></span>  
  
         <span data-ttu-id="01b0b-138">指定した種類が検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="01b0b-138">The specified types appear in the search results.</span></span>  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
<span data-ttu-id="01b0b-139">BizTalk アセンブリの種類</span><span class="sxs-lookup"><span data-stu-id="01b0b-139">BizTalk Assembly Types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b0b-140">参照</span><span class="sxs-lookup"><span data-stu-id="01b0b-140">See Also</span></span>  
 [<span data-ttu-id="01b0b-141">BizTalk アセンブリ ビューアーを使用してアセンブリを表示します。</span><span class="sxs-lookup"><span data-stu-id="01b0b-141">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)