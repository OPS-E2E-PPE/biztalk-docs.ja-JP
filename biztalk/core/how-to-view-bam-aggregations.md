---
title: "BAM 集計を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], viewing aggregations
- viewing, aggregations [BAM]
ms.assetid: aa697f16-ac47-46f9-98a5-a951961d0413
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b1bc81ac4cc85cdb2f9d02903b9c9ba0f3ef7c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-bam-aggregations"></a><span data-ttu-id="3c51c-102">BAM 集計を表示する方法</span><span class="sxs-lookup"><span data-stu-id="3c51c-102">How to View BAM Aggregations</span></span>
<span data-ttu-id="3c51c-103">BAM 集計は、ビジネス アナリストが Excel で Excel アドインを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="3c51c-103">BAM aggregations are defined by the business analyst in Excel using the Excel add-in.</span></span>  
  
### <a name="to-view-your-bam-aggregations"></a><span data-ttu-id="3c51c-104">BAM 集計を表示するには</span><span class="sxs-lookup"><span data-stu-id="3c51c-104">To view your BAM aggregations</span></span>  
  
1.  <span data-ttu-id="3c51c-105">実行するコンピューターで[!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; をクリックして**開始**、 をポイント**すべてのプログラム**を右クリックし**Internet Explorer**、順にクリック**として実行管理者**です。</span><span class="sxs-lookup"><span data-stu-id="3c51c-105">On Computers running [!INCLUDE[btsPlatformsComApis](../includes/btsplatformscomapis-md.md)]; click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span> <span data-ttu-id="3c51c-106">**ユーザー アカウント制御**ダイアログ ボックスで、をクリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="3c51c-106">In the **User Account Control** dialog box, click **Continue**.</span></span> <span data-ttu-id="3c51c-107">Internet Explorer のアドレス バーで、次のように入力します。`http://<server>/BAM/`ここで、 *\<サーバー >* 、BAM ポータルを実行しているコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c51c-107">In the Internet Explorer address bar, type `http://<server>/BAM/`, where *\<server>* is the name of the computer that is running the BAM portal.</span></span>  
  
     <span data-ttu-id="3c51c-108">-- または --</span><span class="sxs-lookup"><span data-stu-id="3c51c-108">-- or --</span></span>  
  
     <span data-ttu-id="3c51c-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BAM ポータル Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="3c51c-109">Click **Start**, click **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2.  <span data-ttu-id="3c51c-110">**マイ ビュー**ナビゲーション ウィンドウで、ビュー、タスクの一覧を表示するビューを展開してをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c51c-110">From the **MyViews** navigation pane, click a view to expand the view to show the task list.</span></span>  
  
3.  <span data-ttu-id="3c51c-111">クリックして、**集計**タスクの一覧を展開するには、集計が定義されています。</span><span class="sxs-lookup"><span data-stu-id="3c51c-111">Click the **Aggregations** task to expand the list of defined aggregations.</span></span>  
  
4.  <span data-ttu-id="3c51c-112">BAM ポータルのコンテンツ フレームに集計をロードするには、集計をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c51c-112">Click an aggregation listed to load the aggregation in the content frame of the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c51c-113">ビューが表示されない場合は、ビューが作成されていないか、ユーザーにアクセス許可が与えられていないかのどちらかです。ビューの作成は通常、ビジネス アナリストが実行するタスクで、権限の許可は通常、管理者が実行するタスクです。</span><span class="sxs-lookup"><span data-stu-id="3c51c-113">If there are no views shown, then either views have not been created, a task typically performed by a business analyst, or permissions have not been granted to the user, a task typically performed by an administrator.</span></span>  
  
 <span data-ttu-id="3c51c-114">詳細については、ライブ データ ブックで何ができる、次を参照してください。[ライブ BAM データの表示](../core/viewing-live-bam-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="3c51c-114">For more information about what you can do with the live data workbooks, see [Viewing Live BAM Data](../core/viewing-live-bam-data.md).</span></span>  
  
 <span data-ttu-id="3c51c-115">事前に計算された BAM 集計を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3c51c-115">The following figure shows pre-calculated BAM aggregations.</span></span>  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
<span data-ttu-id="3c51c-116">事前に計算された BAM 集計</span><span class="sxs-lookup"><span data-stu-id="3c51c-116">Pre-calculated BAM aggregations</span></span>