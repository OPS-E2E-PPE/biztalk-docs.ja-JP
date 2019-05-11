---
title: ローカル サーバーにアセンブリおよび型を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119fa6672ca5b01470336b4f8749c96459112e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333073"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a><span data-ttu-id="4688a-102">ローカル サーバーにあるアセンブリと種類を表示する方法</span><span class="sxs-lookup"><span data-stu-id="4688a-102">How to View Assemblies and Types on the Local Server</span></span>
<span data-ttu-id="4688a-103">BizTalk アセンブリ ビューアーを使用して、すべての BizTalk アセンブリと、ローカル サーバーにインストールされている型を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4688a-103">You can use the BizTalk Assembly Viewer to examine all BizTalk assemblies and types installed on the local server.</span></span>  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a><span data-ttu-id="4688a-104">GAC にインストールされているすべての BizTalk Server アセンブリを表示するには</span><span class="sxs-lookup"><span data-stu-id="4688a-104">To view all BizTalk Server assemblies installed in the GAC</span></span>  
  
-   <span data-ttu-id="4688a-105">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-105">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
     <span data-ttu-id="4688a-106">コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされているすべての BizTalk アセンブリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-106">All BizTalk assemblies installed in the global assembly cache (GAC) on the computer appear.</span></span>  
  
     <span data-ttu-id="4688a-107">![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")</span><span class="sxs-lookup"><span data-stu-id="4688a-107">![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")</span></span>  
<span data-ttu-id="4688a-108">アセンブリ ビューアーの開始ページ</span><span class="sxs-lookup"><span data-stu-id="4688a-108">Assembly Viewer open page</span></span>  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a><span data-ttu-id="4688a-109">BizTalk アセンブリの型、属性、および参照を表示するには</span><span class="sxs-lookup"><span data-stu-id="4688a-109">To view types, attributes, and references for a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="4688a-110">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-110">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="4688a-111">適切なアセンブリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4688a-111">Double click the appropriate assembly.</span></span>  
  
     <span data-ttu-id="4688a-112">BizTalk アセンブリの種類は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-112">The BizTalk assembly types appear in the right pane.</span></span> <span data-ttu-id="4688a-113">属性と型は、左側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-113">The attributes and types appear in the left pane.</span></span>  
  
     <span data-ttu-id="4688a-114">クリックして、アセンブリのインストール場所に移動することもできます、**コードベース** 作業ウィンドウの左上にリンクします。</span><span class="sxs-lookup"><span data-stu-id="4688a-114">You can also navigate to the installed location of the assembly by clicking the **Codebase** link in the upper left section of the task pane.</span></span> <span data-ttu-id="4688a-115">(はフォルダーのビューでは Windows エクスプ ローラーでフォルダーの一覧で、作業ウィンドウが置き換えられるため、このリンクを表示にできません。)</span><span class="sxs-lookup"><span data-stu-id="4688a-115">(You cannot view this link when Windows Explorer is in Folder view because the task pane is replaced by the folder list.)</span></span>  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a><span data-ttu-id="4688a-116">BizTalk アセンブリの型の内容を表示するには</span><span class="sxs-lookup"><span data-stu-id="4688a-116">To view the contents of a type in a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="4688a-117">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-117">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="4688a-118">適切なアセンブリをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4688a-118">Double click the appropriate assembly.</span></span>  
  
3.  <span data-ttu-id="4688a-119">右側のウィンドウで、適切な型をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="4688a-119">In the right pane, double-click the appropriate type.</span></span>  
  
     <span data-ttu-id="4688a-120">**コンテンツの種類ビューアー**ウィンドウが開き、XML 定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-120">The **Type Content Viewer** window opens and the XML definition appears.</span></span>  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a><span data-ttu-id="4688a-121">BizTalk アセンブリを GAC に追加するには</span><span class="sxs-lookup"><span data-stu-id="4688a-121">To add a BizTalk assembly in the GAC</span></span>  
  
1.  <span data-ttu-id="4688a-122">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-122">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="4688a-123">Windows エクスプ ローラーを使用すると、GAC に追加するアセンブリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4688a-123">Use Windows Explorer to navigate to the assembly that you want to add in the GAC.</span></span>  
  
3.  <span data-ttu-id="4688a-124">アセンブリをドラッグし、BizTalk アセンブリ ビューアーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="4688a-124">Drag the assembly and drop it into the BizTalk Assembly Viewer.</span></span>  
  
     <span data-ttu-id="4688a-125">BizTalk アセンブリ ビューアーは、BizTalk Server アセンブリのみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4688a-125">The BizTalk Assembly Viewer accepts only BizTalk Server assemblies.</span></span> <span data-ttu-id="4688a-126">非 BizTalk アセンブリ ビューアーを削除する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-126">If you drop a non-BizTalk assembly in the viewer, it is ignored.</span></span>  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a><span data-ttu-id="4688a-127">BizTalk アセンブリを GAC から削除するには</span><span class="sxs-lookup"><span data-stu-id="4688a-127">To remove a BizTalk assembly from the GAC</span></span>  
  
1.  <span data-ttu-id="4688a-128">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-128">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="4688a-129">クリックして、GAC から削除するアセンブリを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="4688a-129">Right-click the assembly you want to remove from the GAC and click **Delete**.</span></span>  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a><span data-ttu-id="4688a-130">すべての BizTalk アセンブリ内の型を検索するには</span><span class="sxs-lookup"><span data-stu-id="4688a-130">To search for a type in all BizTalk assemblies</span></span>  
  
1.  <span data-ttu-id="4688a-131">BizTalk アセンブリ ビューアーを開くにはダブルクリック**マイ コンピューター**、し、ダブルクリック**BizTalk Server アセンブリ**。</span><span class="sxs-lookup"><span data-stu-id="4688a-131">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="4688a-132">メニュー バーからをクリックして、 **Biztalk Server 検索**アイコン。</span><span class="sxs-lookup"><span data-stu-id="4688a-132">From the menu bar, click the **Biz Talk Server Search** icon.</span></span>  
  
3.  <span data-ttu-id="4688a-133">[検索] ウィンドウで種類を指定、**種類の検索**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="4688a-133">In the Search window, specify the type in the **Find Types** drop-down list.</span></span>  
  
4.  <span data-ttu-id="4688a-134">**BizTalk Server アセンブリ立ち寄る**ドロップダウン リストで検索するアセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="4688a-134">In the **Look in BizTalk Server assemblies** drop-down list, select the assemblies to be searched.</span></span>  
  
5.  <span data-ttu-id="4688a-135">指定した型によって参照されている型のみを含めるために検索を絞り込むには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4688a-135">To narrow your search to include only types that are referenced by a specified type, do the following:</span></span>  
  
    1.  <span data-ttu-id="4688a-136">をクリックして、**検索条件の高度な**リンク。</span><span class="sxs-lookup"><span data-stu-id="4688a-136">Click the **Advanced Search Criteria** link.</span></span>  
  
    2.  <span data-ttu-id="4688a-137">**によって参照される**ドロップダウン リストで、種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="4688a-137">In the **Which are referenced by** drop-down list, select the type.</span></span>  
  
    3.  <span data-ttu-id="4688a-138">**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4688a-138">Click **Search**.</span></span>  
  
         <span data-ttu-id="4688a-139">指定した型は、検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4688a-139">The specified types appear in the search results.</span></span>  
  
         <span data-ttu-id="4688a-140">![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")</span><span class="sxs-lookup"><span data-stu-id="4688a-140">![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")</span></span>  
<span data-ttu-id="4688a-141">BizTalk アセンブリの種類</span><span class="sxs-lookup"><span data-stu-id="4688a-141">BizTalk Assembly Types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4688a-142">参照</span><span class="sxs-lookup"><span data-stu-id="4688a-142">See Also</span></span>  
 [<span data-ttu-id="4688a-143">BizTalk アセンブリ ビューアーを使用したアセンブリの表示</span><span class="sxs-lookup"><span data-stu-id="4688a-143">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)