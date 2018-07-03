---
title: カスタマイズした監視用データベースを BizTalk Server のマークする方法 |Microsoft Docs
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
ms.openlocfilehash: ea069140b9dd89fafa13fe57be9eefa17eceb790
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023712"
---
# <a name="how-to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="3995a-102">カスタマイズした監視用の BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="3995a-102">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>
<span data-ttu-id="3995a-103">Microsoft がインストールされている場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、方法をカスタマイズする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のデータベースを監視します。</span><span class="sxs-lookup"><span data-stu-id="3995a-103">If you have installed the Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack, you can customize the way [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are monitored.</span></span> <span data-ttu-id="3995a-104">これにより、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、次の監視[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="3995a-104">This ensures that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Pack monitors the following [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases:</span></span>  
  
-   <span data-ttu-id="3995a-105">BAM アーカイブ (BAMArchive) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-105">BAM Archive (BAMArchive) database</span></span>  
  
-   <span data-ttu-id="3995a-106">BAM プライマリ インポート (BAMPrimaryImport) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-106">BAM Primary Import (BAMPrimaryImport) database</span></span>  
  
-   <span data-ttu-id="3995a-107">BAM スター スキーマ (BAMStarSchema) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-107">BAM Star Schema (BAMStarSchema) database</span></span>  
  
-   <span data-ttu-id="3995a-108">BizTalk 追跡 (BizTalkDTADb) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-108">BizTalk Tracking (BizTalkDTADb) database</span></span>  
  
-   <span data-ttu-id="3995a-109">BizTalk 管理 (BizTalkMgmtDb) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-109">BizTalk Management (BizTalkMgmtDb) database</span></span>  
  
-   <span data-ttu-id="3995a-110">BizTalk メッセージ ボックス (BizTalkMsgBoxDb) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-110">BizTalk MessageBox (BizTalkMsgBoxDb) database</span></span>  
  
-   <span data-ttu-id="3995a-111">ルール エンジン (BizTalkRuleEngineDb) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-111">Rule Engine (BizTalkRuleEngineDb) database</span></span>  
  
-   <span data-ttu-id="3995a-112">エンタープライズ シングル サインオン (SSODB) データベース</span><span class="sxs-lookup"><span data-stu-id="3995a-112">Enterprise Single Sign-On (SSODB) database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3995a-113">Operations Manager の高度なオペレータ ロールのメンバーとしてログオンする必要がありますまたは[!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)]管理グループ。</span><span class="sxs-lookup"><span data-stu-id="3995a-113">You must be logged on as a member of the Operations Manager Advanced Operator role or [!INCLUDE[opsmgr_short](../includes/opsmgr-short-md.md)] Management Group.</span></span>  
  
### <a name="to-mark-biztalk-server-databases-for-customized-monitoring"></a><span data-ttu-id="3995a-114">監視をカスタマイズするは、BizTalk Server データベースをマークするには</span><span class="sxs-lookup"><span data-stu-id="3995a-114">To mark BizTalk Server databases for customized monitoring</span></span>  
  
1. <span data-ttu-id="3995a-115">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**System Center Operations Manager 2007**、順にクリックします**オペレーション コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="3995a-115">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007**, and then click **Operations Console**.</span></span>  
  
2. <span data-ttu-id="3995a-116">オペレーション コンソールでをクリックして、 **Authoring**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3995a-116">In the Operations console, click the **Authoring** button.</span></span>  
  
3. <span data-ttu-id="3995a-117">**Authoring**ウィンドウで、展開**管理パック オブジェクト**、 をクリックし、**オブジェクト検出**します。</span><span class="sxs-lookup"><span data-stu-id="3995a-117">In the **Authoring** pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
4. <span data-ttu-id="3995a-118">SQL Server の検出を見つけ、オペレーション コンソール ツールバーをクリックして**検索**、し、**探して**テキスト ボックスに「 **SQL 2008** SQL Server 2008 を検索しますします。</span><span class="sxs-lookup"><span data-stu-id="3995a-118">To locate a discovery for SQL Server, on the Operations console toolbar click **Find**, and in the **Look for** text box enter **SQL 2008** to search for SQL Server 2008.</span></span>  
  
5. <span data-ttu-id="3995a-119">で、**検出された種類: SQL 2008 DB**カテゴリで、**データベース エンジンのデータベースの検出**します。</span><span class="sxs-lookup"><span data-stu-id="3995a-119">Under the **Discovered Type: SQL 2008 DB** category, select **Discover Databases for a Database Engine**.</span></span>  
  
6. <span data-ttu-id="3995a-120">オペレーション コンソール ツールバーで、次のようにクリックします。**オーバーライド**順にポイント**オブジェクト検出の上書き**します。</span><span class="sxs-lookup"><span data-stu-id="3995a-120">On the Operations console toolbar, click **Overrides** and then point to **Override the Object Discovery**.</span></span> <span data-ttu-id="3995a-121">に対して、特定の種類のオブジェクトまたはグループ内のすべてのオブジェクトの検出の上書きを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="3995a-121">You can choose to override the discovery for objects of a specific type or for all objects within a group.</span></span> <span data-ttu-id="3995a-122">オーバーライドするにはオブジェクトの種類のグループを選択した後、**上書きのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3995a-122">After you choose which group of object type to override, the **Override Properties** dialog box opens.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="3995a-123">場合、**オーバーライド**ボタンは使用できません [モニタ] ウィンドウで、モニター、コンテナー オブジェクトではなくを選択したかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3995a-123">If the **Overrides** button is not available, make sure you have selected a monitor and not a container object in the Monitors pane.</span></span>  
  
7. <span data-ttu-id="3995a-124">チェック ボックスをオン、**オーバーライド**列隣に、**除外リスト**パラメーター、し、**上書き値** 列を除外するデータベースの名前を入力監視します。</span><span class="sxs-lookup"><span data-stu-id="3995a-124">Select the check box in the **Override** column next to the **Exclude List** parameter, and in the **Override Value** column, type the name of the database that you want to exclude from monitoring.</span></span> <span data-ttu-id="3995a-125">必ず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を監視するデータベースが記載されていない、**上書き値**列。</span><span class="sxs-lookup"><span data-stu-id="3995a-125">Make sure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that you want to monitor are not listed in the **Override Value** column.</span></span>  
  
   > [!TIP]  
   >  <span data-ttu-id="3995a-126">変更されたオブジェクトの検出を使用すると、新しい管理パックを作成します。</span><span class="sxs-lookup"><span data-stu-id="3995a-126">You can use the modified object discoveries to create a new management pack.</span></span> <span data-ttu-id="3995a-127">ウィンドウの下部にある、**目的の管理パックを選択します。** ドロップダウンの既定値を示しています**既定の管理パック**します。</span><span class="sxs-lookup"><span data-stu-id="3995a-127">At the bottom of the pane, the **Select destination management pack** drop-down shows a default value of **Default Management Pack**.</span></span> <span data-ttu-id="3995a-128">クリックして**新規**変更オブジェクト検出を使用して新しい管理パックを作成します。</span><span class="sxs-lookup"><span data-stu-id="3995a-128">Click **New** to create a new management pack using the modified object discoveries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3995a-129">参照</span><span class="sxs-lookup"><span data-stu-id="3995a-129">See Also</span></span>  
 [<span data-ttu-id="3995a-130">SQL Server の監視</span><span class="sxs-lookup"><span data-stu-id="3995a-130">Monitoring SQL Servers</span></span>](../technical-guides/monitoring-sql-servers.md)