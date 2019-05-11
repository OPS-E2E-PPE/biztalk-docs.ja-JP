---
title: グローバル追跡を無効にする方法 |Microsoft Docs
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
ms.openlocfilehash: 0e4b12b84ed107c07055a75ace23fea368040935
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383618"
---
# <a name="how-to-turn-off-global-tracking"></a><span data-ttu-id="eaef0-102">グローバル追跡を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="eaef0-102">How to Turn Off Global Tracking</span></span>
<span data-ttu-id="eaef0-103">既定では、BizTalk Server をインストールするときに、グローバル追跡が有効にします。</span><span class="sxs-lookup"><span data-stu-id="eaef0-103">By default, global tracking is enabled when you install BizTalk Server.</span></span> <span data-ttu-id="eaef0-104">BizTalk 追跡 (BizTalkDTADb) データベースのサイズとしてが増加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム上のデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-104">The BizTalk Tracking (BizTalkDTADb) database grows in size as [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes data on your system.</span></span> <span data-ttu-id="eaef0-105">BizTalk 追跡データベースのサイズには、ディスク パフォーマンスの低下が発生する場合は、追跡データベースからデータを削除できます。</span><span class="sxs-lookup"><span data-stu-id="eaef0-105">If the size of the BizTalk Tracking database causes poor disk performance, you can purge the data from the Tracking database.</span></span> <span data-ttu-id="eaef0-106">一時的に、BizTalk 追跡データベースを削除することで対処はパフォーマンスの問題が発生した、不要になった追跡情報を収集する BizTalk を構成する場合は、グローバル追跡を無効にすることを検討する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaef0-106">If you are having performance issues that are momentarily addressed by purging the BizTalk tracking database, and you want to configure BizTalk to no longer collect tracking information, you may want to consider turning off global tracking.</span></span>  
  
 <span data-ttu-id="eaef0-107">グローバル追跡をオフにすると、全体の追跡インターセプターが無効にしますを理解することが重要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="eaef0-107">It is important to understand that turning off global tracking disables the tracking interceptors for the entire [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span> <span data-ttu-id="eaef0-108">これは、BizTalk 追跡テーブル内のイベントは追跡しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-108">This means that BizTalk will not track events in its tracking tables.</span></span> <span data-ttu-id="eaef0-109">また、個々 のイベントの追跡をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="eaef0-109">Alternatively, you can turn off tracking for individual events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaef0-110">ビジネス アクティビティ監視 (BAM) を使用している場合は、グローバル追跡を無効にした場合でも、専用の追跡ホストを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaef0-110">If you are using Business Activity Monitoring (BAM), you should maintain a dedicated tracking host, even if you disable global tracking.</span></span> <span data-ttu-id="eaef0-111">BAM イベントは、Tracking Data Decode Service (TDDS) を使用するためです。</span><span class="sxs-lookup"><span data-stu-id="eaef0-111">This is because BAM events use the Tracking Data Decode Service (TDDS).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eaef0-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="eaef0-112">Prerequisites</span></span>  
 <span data-ttu-id="eaef0-113">この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaef0-113">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-turn-off-global-tracking-sql-server-2008"></a><span data-ttu-id="eaef0-114">グローバル追跡 (SQL Server 2008) をオフにするには</span><span class="sxs-lookup"><span data-stu-id="eaef0-114">To turn off global tracking (SQL Server 2008)</span></span>  
  
1. <span data-ttu-id="eaef0-115">BizTalk 追跡 (BizTalkDTADb) データベースをホストする SQL server で、をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-115">On the SQL server that hosts the BizTalk Tracking (BizTalkDTADb) database, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="eaef0-116">**サーバーへの接続**ダイアログ ボックスで、サーバー名と認証を確認し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-116">In the **Connect to Server** dialog box, verify the server name and authentication, and then click **Connect**.</span></span>  
  
3. <span data-ttu-id="eaef0-117">Microsoft SQL Server Management studio で**オブジェクト エクスプ ローラー**、展開\<*コンピューター名*\>、展開**データベース**の展開**BizTalkMgmtDb**、展開**テーブル**を右クリックして**adm_group**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-117">In Microsoft SQL Server Management Studio, in **Object Explorer**, expand \<*computer name*\>, expand **Databases**, expand **BizTalkMgmtDb**, expand **Tables**, right-click **adm_Group**, and then click **Open Table**.</span></span>  
  
4. <span data-ttu-id="eaef0-118">テーブル ビューアーで水平方向にスクロールが見つかるまで**GlobalTrackingOption**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-118">In the table viewer, scroll horizontally until you find **GlobalTrackingOption**.</span></span>  
  
5. <span data-ttu-id="eaef0-119">**GlobalTrackingOption**列、値 1 から、この機能を無効にする場合は 0 に変更し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-119">In the **GlobalTrackingOption** column, change the value from 1 to 0, to turn off this feature, and then press ENTER.</span></span>  
  
6. <span data-ttu-id="eaef0-120">Microsoft SQL Server Management Studio を閉じます。</span><span class="sxs-lookup"><span data-stu-id="eaef0-120">Close Microsoft SQL Server Management Studio.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="eaef0-121">有効にする変更は、BizTalk ホストを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaef0-121">You must restart your BizTalk hosts for the change to take effect.</span></span>  
  
7. <span data-ttu-id="eaef0-122">クリックして**開始**、 をクリックして**プログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-122">Click **Start**, click **Programs**, point to **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8. <span data-ttu-id="eaef0-123">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-123">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span>  
  
9. <span data-ttu-id="eaef0-124">詳細ペインで、各ホストを右クリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="eaef0-124">In the details pane, right-click each host, and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaef0-125">参照</span><span class="sxs-lookup"><span data-stu-id="eaef0-125">See Also</span></span>  
 <span data-ttu-id="eaef0-126">[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="eaef0-126">[Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) </span></span>  
 <span data-ttu-id="eaef0-127">[BizTalk 追跡データベースからデータを削除する方法](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="eaef0-127">[How to Purge Data from the BizTalk Tracking Database](../core/how-to-purge-data-from-the-biztalk-tracking-database.md) </span></span>  
 [<span data-ttu-id="eaef0-128">BizTalk 追跡データベースからデータを手動で削除する方法</span><span class="sxs-lookup"><span data-stu-id="eaef0-128">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)