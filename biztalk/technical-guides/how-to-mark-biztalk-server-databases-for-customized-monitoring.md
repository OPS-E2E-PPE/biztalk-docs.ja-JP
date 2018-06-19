---
title: マーク BizTalk Server データベースのカスタマイズを監視する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cfbdc73d-a108-42ee-a5d8-401d5bfe5e7d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08807b1a365b84765221e3a71cb131d8c037fcf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298242"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="7ec8e-102">カスタマイズした監視の BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="7ec8e-102">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>
<span data-ttu-id="7ec8e-103">Microsoft がインストールされている場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、方法をカスタマイズすることができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のデータベースを監視します。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-103">If you have installed the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack, you can customize the way [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are monitored.</span></span> <span data-ttu-id="7ec8e-104">これにより、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、次の監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-104">This ensures that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack monitors the following [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases:</span></span>  
  
-   <span data-ttu-id="7ec8e-105">BAM アーカイブ (BAMArchive) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-105">BAM Archive (BAMArchive) database</span></span>  
  
-   <span data-ttu-id="7ec8e-106">BAM プライマリ インポート (BAMPrimaryImport) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-106">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="7ec8e-107">BAM スター スキーマ (BAMStarSchema) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-107">BAM Star Schema (BAMStarSchema) database</span></span>  
  
-   <span data-ttu-id="7ec8e-108">BizTalk 追跡 (BizTalkDTADb) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-108">BizTalk Tracking (BizTalkDTADb) database</span></span>  
  
-   <span data-ttu-id="7ec8e-109">BizTalk 管理 (BizTalkMgmtDb) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-109">BizTalk Management (BizTalkMgmtDb) database</span></span>  
  
-   <span data-ttu-id="7ec8e-110">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-110">BizTalk MessageBox (BizTalkMsgBoxDb) database</span></span>  
  
-   <span data-ttu-id="7ec8e-111">ルール エンジン (BizTalkRuleEngineDb) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-111">Rule Engine (BizTalkRuleEngineDb) database</span></span>  
  
-   <span data-ttu-id="7ec8e-112">エンタープライズ シングル サインオン (SSODB) データベース</span><span class="sxs-lookup"><span data-stu-id="7ec8e-112">Enterprise Single Sign-On (SSODB) database</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7ec8e-113">Operations Manager の高度なオペレータ ロールのメンバーとしてログオンする必要がありますまたは[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理グループです。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-113">You must be logged on as a member of the Operations Manager Advanced Operator role or [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] Management Group.</span></span>  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="7ec8e-114">監視をカスタマイズする場合は、BizTalk Server データベースをマークするには</span><span class="sxs-lookup"><span data-stu-id="7ec8e-114">To mark BizTalk Server databases for customized monitoring</span></span>  
  
1.  <span data-ttu-id="7ec8e-115">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**System Center Operations Manager 2007**、順にクリック**オペレーション コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-115">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007**, and then click **Operations Console**.</span></span>  
  
2.  <span data-ttu-id="7ec8e-116">オペレーション コンソールで、 **Authoring**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-116">In the Operations console, click the **Authoring** button.</span></span>  
  
3.  <span data-ttu-id="7ec8e-117">**Authoring**  ウィンドウで、展開**管理パック オブジェクト**、クリックして**オブジェクト検出**です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-117">In the **Authoring** pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
4.  <span data-ttu-id="7ec8e-118">SQL Server の検出を検索するオペレーション コンソール ツールバーのをクリックして**検索**、し、、**探します**テキスト ボックスに「 **SQL 2008** SQL Server 2008 を検索しますします。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-118">To locate a discovery for SQL Server, on the Operations console toolbar click **Find**, and in the **Look for** text box enter **SQL 2008** to search for SQL Server 2008.</span></span>  
  
5.  <span data-ttu-id="7ec8e-119">下にある、**検出された種類: SQL 2008 DB**カテゴリで、**データベース エンジンのデータベースの検出**です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-119">Under the **Discovered Type: SQL 2008 DB** category, select **Discover Databases for a Database Engine**.</span></span>  
  
6.  <span data-ttu-id="7ec8e-120">オペレーション コンソール ツールバーで、をクリックして**オーバーライド**順にポイントして**オブジェクト検出の上書き**です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-120">On the Operations console toolbar, click **Overrides** and then point to **Override the Object Discovery**.</span></span> <span data-ttu-id="7ec8e-121">に対して、特定の種類のオブジェクトまたはグループ内のすべてのオブジェクトの検出の上書きを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-121">You can choose to override the discovery for objects of a specific type or for all objects within a group.</span></span> <span data-ttu-id="7ec8e-122">無効にするオブジェクトの種類のグループを選択した後、**上書きのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-122">After you choose which group of object type to override, the **Override Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ec8e-123">場合、**オーバーライド**ボタンは使用できません、[モニタ] ウィンドウで、モニター、コンテナー オブジェクトではなくを選択したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-123">If the **Overrides** button is not available, make sure you have selected a monitor and not a container object in the Monitors pane.</span></span>  
  
7.  <span data-ttu-id="7ec8e-124">チェック ボックスをオン、**オーバーライド**隣の列、**除外リスト**パラメーター、し、[、**上書き値**] 列を除外するデータベースの名前を入力監視します。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-124">Select the check box in the **Override** column next to the **Exclude List** parameter, and in the **Override Value** column, type the name of the database that you want to exclude from monitoring.</span></span> <span data-ttu-id="7ec8e-125">確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を監視するデータベースが記載されていない、**上書き値**列です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-125">Make sure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that you want to monitor are not listed in the **Override Value** column.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="7ec8e-126">変更されたオブジェクト検出を使用すると、新しい管理パックを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-126">You can use the modified object discoveries to create a new management pack.</span></span> <span data-ttu-id="7ec8e-127">ウィンドウの下部にある、**目的の管理パックを選択して**ドロップダウンの既定値が表示**既定の管理パック**です。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-127">At the bottom of the pane, the **Select destination management pack** drop-down shows a default value of **Default Management Pack**.</span></span> <span data-ttu-id="7ec8e-128">をクリックして**新規**変更済みオブジェクト検出を使用して新しい管理パックを作成します。</span><span class="sxs-lookup"><span data-stu-id="7ec8e-128">Click **New** to create a new management pack using the modified object discoveries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec8e-129">参照</span><span class="sxs-lookup"><span data-stu-id="7ec8e-129">See Also</span></span>  
 [<span data-ttu-id="7ec8e-130">SQL サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="7ec8e-130">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)