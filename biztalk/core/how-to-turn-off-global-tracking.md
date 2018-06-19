---
title: グローバル追跡を無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eae3059a-cbdd-47c4-84cd-edfb5480b9fa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c143d19e6071ca4f9ce488ae936082db86dc84dc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007099"
---
# <a name="how-to-turn-off-global-tracking"></a><span data-ttu-id="66691-102">グローバル追跡を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="66691-102">How to Turn Off Global Tracking</span></span>
<span data-ttu-id="66691-103">既定では、BizTalk Server をインストールするときに、グローバル追跡が有効にします。</span><span class="sxs-lookup"><span data-stu-id="66691-103">By default, global tracking is enabled when you install BizTalk Server.</span></span> <span data-ttu-id="66691-104">システム上での [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によるデータ処理に伴って、BizTalk 追跡 (BizTalkDTADb) データベースのサイズが増加します。</span><span class="sxs-lookup"><span data-stu-id="66691-104">The BizTalk Tracking (BizTalkDTADb) database grows in size as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes data on your system.</span></span> <span data-ttu-id="66691-105">BizTalk 追跡データベースのサイズの増加によってディスク パフォーマンスが低下する場合は、追跡データベースからデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="66691-105">If the size of the BizTalk Tracking database causes poor disk performance, you can purge the data from the Tracking database.</span></span> <span data-ttu-id="66691-106">性能上の問題があり、BizTalk 追跡データベースを削除することで一時的に対処している場合、追跡情報を収集しないように BizTalk を構成するには、グローバル追跡を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="66691-106">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span>  
  
 <span data-ttu-id="66691-107">グローバル追跡を無効にすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループ全体の追跡インターセプターが無効になる点を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="66691-107">It is important to understand that turning off global tracking disables the tracking interceptors for the entire [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="66691-108">これは、BizTalk が追跡テーブル内のイベントを追跡しないということを意味します。</span><span class="sxs-lookup"><span data-stu-id="66691-108">This means that BizTalk will not track events in its tracking tables.</span></span> <span data-ttu-id="66691-109">または、個々のイベントの追跡を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="66691-109">Alternatively, you can turn off tracking for individual events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66691-110">ビジネス アクティビティ監視 (BAM) を使用している場合は、グローバル追跡を無効にした場合でも専用の追跡ホストを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66691-110">If you are using Business Activity Monitoring (BAM), you should maintain a dedicated tracking host, even if you disable global tracking.</span></span> <span data-ttu-id="66691-111">これは、BAM イベントが Tracking Data Decode Service (TDDS) を使用するためです。</span><span class="sxs-lookup"><span data-stu-id="66691-111">This is because BAM events use the Tracking Data Decode Service (TDDS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66691-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="66691-112">Prerequisites</span></span>  
 <span data-ttu-id="66691-113">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66691-113">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a><span data-ttu-id="66691-114">グローバル追跡 (SQL Server 2008) をオフにするには</span><span class="sxs-lookup"><span data-stu-id="66691-114">To turn off global tracking (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="66691-115">BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL server、をクリックして**開始**をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**をクリックして**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="66691-115">On the SQL server that hosts the BizTalk Tracking (BizTalkDTADb) database, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="66691-116">**サーバーへの接続**ダイアログ ボックスで、サーバー名と認証を確認し、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="66691-116">In the **Connect to Server** dialog box, verify the server name and authentication, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="66691-117">Microsoft SQL Server Management Studio での**オブジェクト エクスプ ローラー**、展開\<*コンピューター名*\>、展開**データベース**の展開**BizTalkMgmtDb**、展開**テーブル**を右クリックして**adm_Group**、クリックして**テーブルを開く**です。</span><span class="sxs-lookup"><span data-stu-id="66691-117">In Microsoft SQL Server Management Studio, in **Object Explorer**, expand \<*computer name*\>, expand **Databases**, expand **BizTalkMgmtDb**, expand **Tables**, right-click **adm_Group**, and then click **Open Table**.</span></span>  
  
4.  <span data-ttu-id="66691-118">テーブル ビューアーで水平方向にスクロールが見つかるまで**GlobalTrackingOption**です。</span><span class="sxs-lookup"><span data-stu-id="66691-118">In the table viewer, scroll horizontally until you find **GlobalTrackingOption**.</span></span>  
  
5.  <span data-ttu-id="66691-119">**GlobalTrackingOption**列、値を 1 からこの機能をオフにする場合は 0 に変更し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="66691-119">In the **GlobalTrackingOption** column, change the value from 1 to 0, to turn off this feature, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="66691-120">Microsoft SQL Server Management Studio を終了します。</span><span class="sxs-lookup"><span data-stu-id="66691-120">Close Microsoft SQL Server Management Studio.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="66691-121">変更内容を有効にするには、BizTalk ホストを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66691-121">You must restart your BizTalk hosts for the change to take effect.</span></span>  
  
7.  <span data-ttu-id="66691-122">をクリックして**開始**、 をクリックして**プログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="66691-122">Click **Start**, click **Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8.  <span data-ttu-id="66691-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="66691-123">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
9. <span data-ttu-id="66691-124">詳細ウィンドウで、各ホストを右クリックし、をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="66691-124">In the details pane, right-click each host, and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66691-125">参照</span><span class="sxs-lookup"><span data-stu-id="66691-125">See Also</span></span>  
 <span data-ttu-id="66691-126">[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="66691-126">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="66691-127">[BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="66691-127">[How to Purge Data from the BizTalk Tracking Database](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span></span>  
 [<span data-ttu-id="66691-128">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="66691-128">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)