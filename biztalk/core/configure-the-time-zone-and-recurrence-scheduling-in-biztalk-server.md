---
title: タイム ゾーンと定期的なアイテムが BizTalk Server でスケジュール設定の構成 |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60ae7be-747e-4034-8b99-46bd7e25fe67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe12e4fe81705d178520f02591f8179e47606f6c
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753306"
---
# <a name="configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server"></a><span data-ttu-id="a096e-102">タイム ゾーンと定期的なアイテムが BizTalk Server でスケジュールを構成します。</span><span class="sxs-lookup"><span data-stu-id="a096e-102">Configure the time zone and recurrence scheduling in BizTalk Server</span></span>
<span data-ttu-id="a096e-103">タイム ゾーンを設定しで、繰り返しのスケジュールを構成、受信場所で[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a096e-103">Set the timezone and configure a recurrence schedule on your receive locations in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="a096e-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、受信場所の高度なスケジューリング機能をいくつかのオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a096e-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, the advanced scheduling feature on receive locations includes some options.</span></span> <span data-ttu-id="a096e-105">詳細設定オプションをスケジュールするには、タイム ゾーンを設定およびも、繰り返しのスケジュールを設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a096e-105">Using the advanced scheduling options, set the time zone, and also set a recurrence schedule.</span></span>

<span data-ttu-id="a096e-106">このトピックでは、これらの機能を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a096e-106">This topic shows you how to configure these features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a096e-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a096e-107">Prerequisites</span></span>
<span data-ttu-id="a096e-108">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)上、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a096e-108">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

## <a name="time-zone"></a><span data-ttu-id="a096e-109">タイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="a096e-109">Time zone</span></span>

<span data-ttu-id="a096e-110">**スケジュール**受信場所のプロパティが含まれています、**タイム ゾーン**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a096e-110">The **Schedule** properties of a receive location includes a **Time Zone** property.</span></span> <span data-ttu-id="a096e-111">設定すると、ローカル コンピューターのタイム ゾーンではなく、受信場所で選択したタイム ゾーンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a096e-111">When set, the time zone you choose in the receive location is used instead of the time zone on the local computer.</span></span> 

<span data-ttu-id="a096e-112">すべての日付と時刻で、**スケジュール**プロパティは選択したタイム ゾーンに固有です。</span><span class="sxs-lookup"><span data-stu-id="a096e-112">All dates and times in the **Schedule** properties are specific to the time zone you choose.</span></span> <span data-ttu-id="a096e-113">既存のスケジュールは、BizTalk 管理データベース (BizTalkMgmtDb) をホストするサーバーのタイム ゾーンに移行されます。</span><span class="sxs-lookup"><span data-stu-id="a096e-113">Any existing schedules are migrated to the time zone of the server hosting the BizTalk Management database (BizTalkMgmtDb).</span></span> 

<span data-ttu-id="a096e-114">夏時間 (DST) を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="a096e-114">You can also adjust for daylight saving time (DST).</span></span> <span data-ttu-id="a096e-115">選択した場合、スケジュールを選択するタイム ゾーンの夏時間へ自動的に調整します。</span><span class="sxs-lookup"><span data-stu-id="a096e-115">When checked, the schedule automatically adjusts to the daylight saving time of the time zone you choose.</span></span> <span data-ttu-id="a096e-116">このオプションは影響しません、スケジュールの場合。</span><span class="sxs-lookup"><span data-stu-id="a096e-116">This option has no impact on the schedule if:</span></span>

* <span data-ttu-id="a096e-117">指定されたタイム ゾーンには、夏時間の期間はありません。</span><span class="sxs-lookup"><span data-stu-id="a096e-117">The specified time zone does not have a daylight saving time</span></span>
* <span data-ttu-id="a096e-118">選択したタイム ゾーンの夏時間のタイムは発生しません</span><span class="sxs-lookup"><span data-stu-id="a096e-118">Daylight saving time is not observed in the time zone you choose</span></span>

## <a name="enable-recurrence-schedule"></a><span data-ttu-id="a096e-119">定期的なスケジュールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a096e-119">Enable recurrence schedule</span></span>
1. <span data-ttu-id="a096e-120">**BizTalk Server 管理**コンソールのいずれかを右クリックし、受信場所、および選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a096e-120">In the **BizTalk Server Administration** console, right-click one of your receive locations, and select **Properties**.</span></span> 
2. <span data-ttu-id="a096e-121">**スケジュール**] ページで、[**有効にするサービス時間帯**します。</span><span class="sxs-lookup"><span data-stu-id="a096e-121">On the **Scheduling** page, select **Enable service window**.</span></span> <span data-ttu-id="a096e-122">**開始時刻**と**停止時刻**スケジュールの実行が許可される最初の時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="a096e-122">The **Start Time** and **Stop time** set the initial time the schedule is allowed to run:</span></span>

    ![有効にするサービスの Windows の受信ポート](../core/media/enable-service-windows-for-receive-port.PNG)

3. <span data-ttu-id="a096e-124">追加のスケジュール オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a096e-124">The additional scheduling options are displayed:</span></span>

    ![高度なスケジュールの受信ポート](../core/media/advanced-scheduling-for-receive-port.PNG)

4. <span data-ttu-id="a096e-126">**繰り返し**プロパティは、すべての日、週、または選択した月の受信ポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="a096e-126">The **Recurrence** property runs the receive port every day, week, or month that you choose:</span></span> 

    1. <span data-ttu-id="a096e-127">使用、**毎日**受信ポートを実行するには、定期的なアイテムすべて*x*の開始日の数、**から**選択した日付と内でのみ、**サービス ウィンドウ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a096e-127">Use the **Daily** recurrence to run the receive port every *x* number of days, starting on the **From** date you choose, and only within the **service window** you choose:</span></span>

        ![毎日のスケジュール](../core/media/daily-schedule.png)

    2. <span data-ttu-id="a096e-129">使用して、**毎週**と内でのみ、1 週間以内の特定の日に受信ポートを実行するには、定期的なアイテム、**サービス時間帯**選択します。</span><span class="sxs-lookup"><span data-stu-id="a096e-129">Use the **Weekly** recurrence to run the receive port on a specific day within a week, and only within the **service window** you choose:</span></span> 

        ![週単位のスケジュール](../core/media/weekly-schedule.png)

    3. <span data-ttu-id="a096e-131">使用して、**毎月**受信ポートを月単位のスケジュールで実行するには、定期的なアイテム。</span><span class="sxs-lookup"><span data-stu-id="a096e-131">Use the **Monthly** recurrence to run the receive port on a monthly schedule.</span></span> <span data-ttu-id="a096e-132">**日**と**で**オプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a096e-132">The **Days** and **On** options are available.</span></span> 
    
        <span data-ttu-id="a096e-133">使用して、**日**内で特定の日付で受信ポートを実行するには、定期的なアイテム、**か月間**選択します。</span><span class="sxs-lookup"><span data-stu-id="a096e-133">Use the **Days** recurrence to run the receive port on specific dates within the **months** you choose:</span></span> 

        ![月単位のスケジュール](../core/media/monthly-schedule.PNG)

        <span data-ttu-id="a096e-135">使用して、**で**月の特定の日に受信ポートを実行するには、定期的なアイテム。</span><span class="sxs-lookup"><span data-stu-id="a096e-135">Use the **On** recurrence to run the receive port on specific days of the month:</span></span>

        ![スケジュールで毎月](../core/media/monthly-on-schedule.PNG)

5. <span data-ttu-id="a096e-137">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a096e-137">Select **OK** to save your changes.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a096e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a096e-138">See also</span></span>
[<span data-ttu-id="a096e-139">Feature Pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="a096e-139">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)
