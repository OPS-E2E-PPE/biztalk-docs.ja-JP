---
title: 構成キャッシュの更新間隔を調整する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9459fadd65af220982ab31ae0e464cb7f1986e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297882"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a><span data-ttu-id="d7811-102">構成キャッシュの更新間隔を調整する方法</span><span class="sxs-lookup"><span data-stu-id="d7811-102">How to Adjust the Configuration Cache Refresh Interval</span></span>
<span data-ttu-id="d7811-103">構成キャッシュの更新間隔は、BizTalk Server が、エンドポイントの構成を更新するまでの時間を定義します。</span><span class="sxs-lookup"><span data-stu-id="d7811-103">The configuration cache refresh interval defines the time period in which BizTalk Server updates the configuration of the endpoints.</span></span> <span data-ttu-id="d7811-104">BizTalk Server を起動すると、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、および追跡データベースへの接続などの BizTalk Server 管理のすべての項目が構成キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d7811-104">When you start BizTalk Server, all items in BizTalk Server administration, such as MessageBox databases, server properties, adapters, and connections to the Tracking database, are stored in the configuration cache.</span></span> <span data-ttu-id="d7811-105">キャッシュ内のすべてのアイテムは、構成の更新間隔で更新されます。</span><span class="sxs-lookup"><span data-stu-id="d7811-105">All items in the cache are refreshed by the configuration refresh interval.</span></span> <span data-ttu-id="d7811-106">既定では、サーバー データベース接続とサーバーのプロパティを除く、60 秒ごとです。</span><span class="sxs-lookup"><span data-stu-id="d7811-106">By default this is every 60 seconds, except for the server database connections and server properties.</span></span> <span data-ttu-id="d7811-107">これは、SMTP ホストなどの BizTalk グループの [全般] プロパティを変更する場合、変更が選択される 60 秒以内ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d7811-107">This means that if you change the general properties for a BizTalk group, such as the SMTP host, the changes are picked up within 60 seconds.</span></span> <span data-ttu-id="d7811-108">更新するまで、現在開いているインスタンス、BizTalk Server 管理コンソールの外部システムの変更は反映されません。</span><span class="sxs-lookup"><span data-stu-id="d7811-108">System changes made outside the currently open instance of the BizTalk Server Administration console are not reflected until you refresh it.</span></span>  
  
 <span data-ttu-id="d7811-109">構成キャッシュの更新間隔は、BizTalk グループのプロパティの一部です。</span><span class="sxs-lookup"><span data-stu-id="d7811-109">The configuration cache refresh interval is part of the BizTalk group properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7811-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="d7811-110">Prerequisites</span></span>  
 <span data-ttu-id="d7811-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7811-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-adjust-the-cache-refresh-interval"></a><span data-ttu-id="d7811-112">キャッシュ更新間隔を調整するには</span><span class="sxs-lookup"><span data-stu-id="d7811-112">To adjust the cache refresh interval</span></span>  
  
1.  <span data-ttu-id="d7811-113">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="d7811-113">Click **Start**, click **All Programs**, click **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d7811-114">コンソール ツリーで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**を右クリックして**BizTalk グループ**、順にクリック**設定**です。</span><span class="sxs-lookup"><span data-stu-id="d7811-114">In the console tree, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
3.  <span data-ttu-id="d7811-115">**BizTalk 設定ダッシュ ボード**ダイアログ ボックスで、**全般**タブです。**構成の更新間隔**プロパティ、入力または時間 (秒単位) を選択するすべての項目、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理キャッシュが構成キャッシュの更新の間の待機する必要があります、クリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="d7811-115">In the **BizTalk Settings Dashboard** dialog box, select the **General** tab. For the **Configuration refresh interval** property, type or select the time (in seconds) that all items in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration cache must wait between configuration cache refreshes, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7811-116">更新される項目には、メッセージ ボックス データベース、サーバーのプロパティ、アダプター、追跡データベースへの接続などがあります。</span><span class="sxs-lookup"><span data-stu-id="d7811-116">Items involved in the refresh include the MessageBox databases, server properties, adapters, and connections to the Tracking database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d7811-117">既定では、構成キャッシュ内のすべてのオブジェクトは、サーバー データベース接続とサーバーのプロパティを除く、60 秒ごとに更新します。</span><span class="sxs-lookup"><span data-stu-id="d7811-117">By default, all objects in the configuration cache are refreshed every 60 seconds, except for the server database connections and server properties.</span></span>