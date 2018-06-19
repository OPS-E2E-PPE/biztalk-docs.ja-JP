---
title: 追跡プロファイルを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, creating
- creating, tracking profiles
ms.assetid: 676ae7e8-f3eb-45f1-ad2e-807b434c0bf9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f5d6cbb210cb292cd8ae7d0e2f4ff811984377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248938"
---
# <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="033b0-102">追跡プロファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="033b0-102">How to Create a Tracking Profile</span></span>
<span data-ttu-id="033b0-103">展開されたアセンブリおよび BizTalk Server メッセージング プロパティに BAM アクティビティ定義をリンクするために、追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="033b0-103">You create tracking profiles to link BAM activity definitions to deployed assemblies and BizTalk Server messaging properties.</span></span> <span data-ttu-id="033b0-104">追跡プロファイル エディターを開くと、インポート アクティビティ リンクまたはインポートのメニュー項目をクリックして、新しい追跡プロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="033b0-104">When you open the Tracking Profile Editor, you can create a new tracking profile by either clicking the import activity link or the import menu item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="033b0-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="033b0-105">Prerequisites</span></span>  
 <span data-ttu-id="033b0-106">このトピックの手順を実行するための前提条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="033b0-106">The following are prerequisites for performing the procedure in this topic:</span></span>  
  
-   <span data-ttu-id="033b0-107">アクセス許可のある既存の BizTalk 管理データベース</span><span class="sxs-lookup"><span data-stu-id="033b0-107">An existing BizTalk Management database to which you have permissions.</span></span>  
  
-   <span data-ttu-id="033b0-108">BizTalk 管理データベースを使用するように構成された TPE</span><span class="sxs-lookup"><span data-stu-id="033b0-108">The TPE configured to use the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="033b0-109">BAM プライマリ インポート データベースにある既存の BAM アクティビティ定義</span><span class="sxs-lookup"><span data-stu-id="033b0-109">An existing BAM activity definition in the BAM Primary Import database.</span></span>  
  
### <a name="to-create-a-tracking-profile"></a><span data-ttu-id="033b0-110">追跡プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="033b0-110">To create a tracking profile</span></span>  
  
1.  <span data-ttu-id="033b0-111">コンピューターまたは送信元システムとして指定したコンピューターで、開く、**追跡プロファイル エディター**です。</span><span class="sxs-lookup"><span data-stu-id="033b0-111">On the computer or computers that you have identified as the source system, open the **Tracking Profile Editor**.</span></span> <span data-ttu-id="033b0-112">これを行うには、をクリックして**開始**、 をクリックして**実行**、型**BTSTrkEditor.exe**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="033b0-112">To do this, click **Start**, click **Run**, type **BTSTrkEditor.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="033b0-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="033b0-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="033b0-114">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="033b0-114">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="033b0-115">TPE の左ペインの途中でクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**リンクします。</span><span class="sxs-lookup"><span data-stu-id="033b0-115">In the middle of the left pane of the TPE, click **Click here to import a BAM Activity Definition** link.</span></span> <span data-ttu-id="033b0-116">開き、 **BAM アクティビティ定義のインポート** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="033b0-116">This opens the **Import BAM Activity Definition** dialog box.</span></span>  
  
3.  <span data-ttu-id="033b0-117">**BAM アクティビティ定義名**ボックスの一覧が、追跡を基になるアクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="033b0-117">From the **BAM Activity Definition Name** list box select the activity on which to base the tracking.</span></span> <span data-ttu-id="033b0-118">アクティビティ名の一部を入力することができます、リストに多くの展開済みアクティビティが含まれている場合、**文字列**テキスト ボックスをクリック、**検索**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="033b0-118">If your list contains many deployed activities, you can type part of the activity name in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="033b0-119">これにより、アクティビティの一覧には、入力した文字列が含まれているアクティビティだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="033b0-119">This limits the list of activities displayed to those whose names contain the partial name entered.</span></span>  
  
4.  <span data-ttu-id="033b0-120">アクティビティを選択すると、クリックして、 **OK**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="033b0-120">Once you have selected the activity, click the **OK** button.</span></span> <span data-ttu-id="033b0-121">これにより、選択したアクティビティに基づいた新しい追跡プロファイルが開き、TPE の左ペインにこのプロファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="033b0-121">This opens a new tracking profile based on the activity selected and displays the profile in the left pane of the TPE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="033b0-122">参照</span><span class="sxs-lookup"><span data-stu-id="033b0-122">See Also</span></span>  
 [<span data-ttu-id="033b0-123">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="033b0-123">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)