---
title: スケジュールを構成する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, receive locations
- managing [receive locations], scheduling
- scheduling, receive locations
- managing [receive locations], configuring
ms.assetid: 2653e1c3-ddbd-4d3f-be64-2a5fcd7cf267
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 598d26b47e954cf4299aabc0d0e77ecb4598c984
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386182"
---
# <a name="how-to-configure-scheduling-for-a-receive-location"></a><span data-ttu-id="87cec-102">スケジュールを構成する方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="87cec-102">How to Configure Scheduling for a Receive Location</span></span>
<span data-ttu-id="87cec-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所のスケジュール設定のプロパティを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="87cec-103">This topic describes how to use the BizTalk Server Administration console to configure scheduling properties for a receive location.</span></span> <span data-ttu-id="87cec-104">受信場所を開始し、メッセージの処理を停止する日付を指定できます。</span><span class="sxs-lookup"><span data-stu-id="87cec-104">You can specify the dates when you want the receive location to start and stop processing messages.</span></span> <span data-ttu-id="87cec-105">受信場所にメッセージを処理する 1 日の特定の時間を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="87cec-105">You can also specify certain times of the day during which you want the receive location to process messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87cec-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="87cec-106">Prerequisites</span></span>  
 <span data-ttu-id="87cec-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="87cec-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="87cec-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="87cec-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-scheduling-for-a-receive-location"></a><span data-ttu-id="87cec-109">受信場所のスケジュールを構成するには</span><span class="sxs-lookup"><span data-stu-id="87cec-109">To configure scheduling for a receive location</span></span>  
  
1. <span data-ttu-id="87cec-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="87cec-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="87cec-111">コンソール ツリーで、BizTalk グループと受信場所のスケジュールを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="87cec-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure scheduling for a receive location.</span></span>  
  
3. <span data-ttu-id="87cec-112">クリックして**受信場所**、受信場所を右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="87cec-112">Click **Receive Locations**, right-click the receive location, and click **Properties**.</span></span>  
  
4. <span data-ttu-id="87cec-113">左側のウィンドウで次のようにクリックします。**スケジュール**次の表に示すようにスケジュール設定のプロパティを構成し、クリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="87cec-113">In the left pane, click **Schedule**, configure scheduling properties as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="87cec-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="87cec-114">Use this</span></span>|<span data-ttu-id="87cec-115">目的</span><span class="sxs-lookup"><span data-stu-id="87cec-115">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="87cec-116">**開始日**</span><span class="sxs-lookup"><span data-stu-id="87cec-116">**Start date**</span></span>|<span data-ttu-id="87cec-117">このチェック ボックスを選択し、プルダウンで表示されるカレンダーから、受信場所がメッセージの処理を開始する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="87cec-117">Select this check box, and then from the pull-down calendar, select the date on which the receive location starts processing messages.</span></span> <span data-ttu-id="87cec-118">年を変更するには、表示されている年をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87cec-118">To change the year, click the displayed year.</span></span>|  
   |<span data-ttu-id="87cec-119">**停止日**</span><span class="sxs-lookup"><span data-stu-id="87cec-119">**Stop date**</span></span>|<span data-ttu-id="87cec-120">このチェック ボックスを選択し、プルダウンで表示されるカレンダーから、受信場所がメッセージの処理を停止する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="87cec-120">Select this check box, and then from the pull-down calendar, select the date on which the receive location stops processing messages.</span></span> <span data-ttu-id="87cec-121">このプロパティは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="87cec-121">This property is optional.</span></span> <span data-ttu-id="87cec-122">停止日を指定しない場合、受信場所の値は無効にするまでアクティブです。</span><span class="sxs-lookup"><span data-stu-id="87cec-122">If you do not specify a stop date, the receive location remains active until it is disabled.</span></span>|  
   |<span data-ttu-id="87cec-123">**サービス時間帯を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="87cec-123">**Enable service window**</span></span>|<span data-ttu-id="87cec-124">は、1 日の時間を指定し、指定の時間のみにメッセージを受信する受信場所を構成するには、このチェック ボックスをオン、**開始時刻と停止時刻**ボックス。</span><span class="sxs-lookup"><span data-stu-id="87cec-124">Select this check box to configure the receive location to receive messages only at specified times of the day, then specify the times in the **Start time and Stop time** boxes.</span></span> <span data-ttu-id="87cec-125">チェック ボックスをオフにした場合、受信場所は、いつでもメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="87cec-125">If the check box is cleared, the receive location receives messages at any time.</span></span> <span data-ttu-id="87cec-126">既定値は false (オフ)。</span><span class="sxs-lookup"><span data-stu-id="87cec-126">The default value is false (cleared).</span></span>|  
   |<span data-ttu-id="87cec-127">**[開始時刻]**</span><span class="sxs-lookup"><span data-stu-id="87cec-127">**Start time**</span></span>|<span data-ttu-id="87cec-128">メッセージを受信する受信場所を開始する時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="87cec-128">Specify the time when the receive location should begin to receive messages.</span></span> <span data-ttu-id="87cec-129">このボックスは、使用可能な場合にのみ、**有効にするサービス時間帯** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="87cec-129">This box is available only when the **Enable service window** check box is selected.</span></span>|  
   |<span data-ttu-id="87cec-130">**停止時刻**</span><span class="sxs-lookup"><span data-stu-id="87cec-130">**Stop time**</span></span>|<span data-ttu-id="87cec-131">メッセージを受信する受信場所を停止する時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="87cec-131">Specify the time when the receive location should cease to receive messages.</span></span> <span data-ttu-id="87cec-132">このボックスは、使用可能な場合にのみ、**有効にするサービス時間帯** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="87cec-132">This box is available only when the **Enable service window** check box is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87cec-133">参照</span><span class="sxs-lookup"><span data-stu-id="87cec-133">See Also</span></span>  
 [<span data-ttu-id="87cec-134">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="87cec-134">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)