---
title: "送信ポートの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, send ports
- configuring, tracking
- tracking, send ports
- configuring [HAT tracking], send ports
- send ports, tracking
- managing [send ports], configuring
- tracking, configuring
- send ports, configuring
- managing [send ports], tracking
- HAT, send ports
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60ba83b7d3451599a0422ec370fed41eeba94407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-send-port"></a><span data-ttu-id="c3e30-102">送信ポートの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c3e30-102">How to Configure Tracking for a Send Port</span></span>
<span data-ttu-id="c3e30-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信ポートの追跡を構成する方法 (メッセージ本文や昇格させたプロパティを表示するオプションなど) について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3e30-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="c3e30-104">これにより、BizTalk 実装の稼動状況を監視し、ボトルネックを識別できます。</span><span class="sxs-lookup"><span data-stu-id="c3e30-104">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="c3e30-105">構成する追跡の設定は、送信ポートのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3e30-105">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="c3e30-106">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="c3e30-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c3e30-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c3e30-107">Prerequisites</span></span>  
 <span data-ttu-id="c3e30-108">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3e30-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="c3e30-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3e30-109">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-send-port"></a><span data-ttu-id="c3e30-110">送信ポートの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="c3e30-110">To configure tracking for a send port</span></span>  
  
1.  <span data-ttu-id="c3e30-111">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="c3e30-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c3e30-112">コンソール ツリーで、BizTalk グループを展開し、送信ポートの追跡を構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c3e30-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a send port.</span></span>  
  
3.  <span data-ttu-id="c3e30-113">をクリックして**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="c3e30-113">Click **Send Ports**, right-click the send port, click **Properties**, and then click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3e30-114">1 つの送信ポートは 1 つの送信パイプラインにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c3e30-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="c3e30-115">送信パイプラインでメッセージ本文の追跡が無効になっている場合、送信ポートでも追跡できるものはありません。</span><span class="sxs-lookup"><span data-stu-id="c3e30-115">If message body tracking is disabled on the send pipeline, nothing can be tracked on the send port as well.</span></span> <span data-ttu-id="c3e30-116">そのようなシナリオでは、その送信ポートで [追跡] オプションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c3e30-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
4.  <span data-ttu-id="c3e30-117">次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c3e30-117">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="c3e30-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c3e30-118">Use this</span></span>|<span data-ttu-id="c3e30-119">目的</span><span class="sxs-lookup"><span data-stu-id="c3e30-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c3e30-120">**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c3e30-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="c3e30-121">受信前にメッセージの内容を保存および追跡できるようにする場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3e30-121">Select this check box to enable you to save and track message content before the message is received.</span></span> <span data-ttu-id="c3e30-122">**注:**メッセージ本文パイプラインの追跡が正常にポート処理前に、の応答メッセージを追跡するために有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3e30-122">**Note:**  You must enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="c3e30-123">**メッセージ本文の追跡 - ポート処理後の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c3e30-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="c3e30-124">受信後にメッセージの内容を保存および追跡できるようにする場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3e30-124">Select this check box to enable you to save and track message content after the message is received.</span></span>|  
    |||  
    |||  
    |<span data-ttu-id="c3e30-125">**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c3e30-125">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="c3e30-126">受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3e30-126">Select this check box to track the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="c3e30-127">**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c3e30-127">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="c3e30-128">送信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c3e30-128">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
    |||  
    |||  
  
## <a name="see-also"></a><span data-ttu-id="c3e30-129">参照</span><span class="sxs-lookup"><span data-stu-id="c3e30-129">See Also</span></span>  
 [<span data-ttu-id="c3e30-130">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="c3e30-130">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)