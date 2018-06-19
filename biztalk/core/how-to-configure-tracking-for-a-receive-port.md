---
title: 追跡を構成する方法、受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring [HAT tracking], receive ports
- tracking, receive ports
- receive ports, tracking
- configuring, tracking
- receive ports, configuring
- tracking, configuring
- HAT, receive ports
- configuring, receive ports
- managing [receive ports], tracking
ms.assetid: dd569e84-cb1c-4191-912a-0c2eb2781a85
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e18748a5d9ff8088d09dfe28bf23c7b729b6afc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249106"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="04761-102">受信ポートの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="04761-102">How to Configure Tracking for a Receive Port</span></span>
<span data-ttu-id="04761-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して受信ポートの追跡を構成する方法 (メッセージ本文や昇格させたプロパティを表示するオプションなど) について説明します。</span><span class="sxs-lookup"><span data-stu-id="04761-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a receive port, such as options to view message bodies and promoted properties..</span></span> <span data-ttu-id="04761-104">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実装の稼動状況を監視し、ボトルネックを識別できます。</span><span class="sxs-lookup"><span data-stu-id="04761-104">This helps you monitor the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementation and identify any bottlenecks.</span></span> <span data-ttu-id="04761-105">構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="04761-105">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
 <span data-ttu-id="04761-106">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: メッセージとインスタンス データの追跡](../core/checklist-message-and-instance-data-tracking.md)</span><span class="sxs-lookup"><span data-stu-id="04761-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Message and Instance Data Tracking](../core/checklist-message-and-instance-data-tracking.md)</span></span>  
  
 <span data-ttu-id="04761-107">構成する追跡の設定は、受信ポートのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="04761-107">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="04761-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="04761-108">Prerequisites</span></span>  
 <span data-ttu-id="04761-109">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04761-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="04761-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="04761-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="04761-111">受信ポートの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="04761-111">To configure tracking for a receive port</span></span>  
  
1.  <span data-ttu-id="04761-112">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="04761-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="04761-113">コンソール ツリーで、BizTalk グループを展開し、受信ポートの追跡を構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="04761-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a receive port.</span></span>  
  
3.  <span data-ttu-id="04761-114">をクリックして**受信ポート**受信ポートを右クリックし、クリックして、**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="04761-114">Click **Receive Ports**, right-click the receive port and click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04761-115">受信ポートでメッセージ本文の追跡を有効にする前に、受信ポートを本当に追跡するかどうかを確認します。この処理はオーバーヘッドになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04761-115">Before enabling the message body tracking on a receive port, ensure if you want to track the receive port at all; it could be an overhead.</span></span> <span data-ttu-id="04761-116">たとえば、受信パイプライン RcvPipe が異なる受信ポートの複数の受信場所で使用されます。</span><span class="sxs-lookup"><span data-stu-id="04761-116">For example, a receive pipeline RcvPipe is used at several receive locations in different receive ports.</span></span> <span data-ttu-id="04761-117">メッセージ本文の追跡 RcvPipe でオプションを有効にした場合は、メッセージ本文のすべての受信場所で、実行する可能性がありますいないを追跡につながります。</span><span class="sxs-lookup"><span data-stu-id="04761-117">If you enable the message body tracking option on RcvPipe, it leads to message body tracking on all the receive locations, which you might not want to do.</span></span> <span data-ttu-id="04761-118">そのため、設定、メッセージ本文の追跡では、必要に応じてポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="04761-118">Hence, set the message body tracking on receive ports as per your requirement.</span></span>  
  
4.  <span data-ttu-id="04761-119">次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="04761-119">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="04761-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="04761-120">Use this</span></span>|<span data-ttu-id="04761-121">目的</span><span class="sxs-lookup"><span data-stu-id="04761-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="04761-122">**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="04761-122">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="04761-123">受信前にメッセージの内容を保存および追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04761-123">Select this check box to save and track message content before the message is received.</span></span>|  
    |<span data-ttu-id="04761-124">**メッセージ本文の追跡 - ポート処理後の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="04761-124">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="04761-125">受信後にメッセージの内容を保存および追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04761-125">Select this check box to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="04761-126">**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="04761-126">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="04761-127">受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04761-127">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="04761-128">**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="04761-128">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="04761-129">送信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="04761-129">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="04761-130">参照</span><span class="sxs-lookup"><span data-stu-id="04761-130">See Also</span></span>  
 [<span data-ttu-id="04761-131">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="04761-131">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)