---
title: 追跡を構成する方法、受信ポート |Microsoft Docs
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
ms.openlocfilehash: a6f45158939210c3b084aa29234bee1b4a032b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385898"
---
# <a name="how-to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="5e6b8-102">追跡を構成する方法、受信ポート</span><span class="sxs-lookup"><span data-stu-id="5e6b8-102">How to Configure Tracking for a Receive Port</span></span>
<span data-ttu-id="5e6b8-103">このトピックでは、使用する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなど、受信ポートの追跡を構成する.</span><span class="sxs-lookup"><span data-stu-id="5e6b8-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a receive port, such as options to view message bodies and promoted properties..</span></span> <span data-ttu-id="5e6b8-104">正常性を監視できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実装し、ボトルネックを識別します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-104">This helps you monitor the health of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementation and identify any bottlenecks.</span></span> <span data-ttu-id="5e6b8-105">構成する追跡の設定は、すべての受信ポートのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-105">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
 <span data-ttu-id="5e6b8-106">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト。メッセージとインスタンス データ追跡](../core/checklist-message-and-instance-data-tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5e6b8-106">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Message and Instance Data Tracking](../core/checklist-message-and-instance-data-tracking.md)</span></span>  
  
 <span data-ttu-id="5e6b8-107">構成する追跡の設定は、すべての受信ポートのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-107">The tracking settings that you configure apply to all of the instances of the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5e6b8-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="5e6b8-108">Prerequisites</span></span>  
 <span data-ttu-id="5e6b8-109">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-109">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="5e6b8-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-receive-port"></a><span data-ttu-id="5e6b8-111">受信ポートの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="5e6b8-111">To configure tracking for a receive port</span></span>  
  
1. <span data-ttu-id="5e6b8-112">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-112">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="5e6b8-113">コンソール ツリーで、BizTalk グループと受信ポートの追跡を構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-113">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a receive port.</span></span>  
  
3. <span data-ttu-id="5e6b8-114">クリックして**受信ポート**受信ポートを右クリックし、クリックして**追跡**します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-114">Click **Receive Ports**, right-click the receive port and click **Tracking**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5e6b8-115">メッセージ本文の受信ポートの追跡を有効にするには、まったく; 受信ポートを追跡することを確認しますオーバーヘッドが考えられます。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-115">Before enabling the message body tracking on a receive port, ensure if you want to track the receive port at all; it could be an overhead.</span></span> <span data-ttu-id="5e6b8-116">たとえば、受信パイプライン RcvPipe が、別の受信ポートで複数の受信場所に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-116">For example, a receive pipeline RcvPipe is used at several receive locations in different receive ports.</span></span> <span data-ttu-id="5e6b8-117">メッセージ本文の追跡 RcvPipe でオプションを有効にした場合の潜在顧客はメッセージ本文の追跡では、すべての受信場所を行いたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-117">If you enable the message body tracking option on RcvPipe, it leads to message body tracking on all the receive locations, which you might not want to do.</span></span> <span data-ttu-id="5e6b8-118">このため、メッセージをセット本文の追跡では、必要に応じてポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-118">Hence, set the message body tracking on receive ports as per your requirement.</span></span>  
  
4. <span data-ttu-id="5e6b8-119">次の表に示すように、必要な追跡オプションを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-119">Configure the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="5e6b8-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5e6b8-120">Use this</span></span>|<span data-ttu-id="5e6b8-121">目的</span><span class="sxs-lookup"><span data-stu-id="5e6b8-121">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="5e6b8-122">**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5e6b8-122">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="5e6b8-123">保存し、メッセージが受信されるまで、メッセージの内容を追跡するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-123">Select this check box to save and track message content before the message is received.</span></span>|  
   |<span data-ttu-id="5e6b8-124">**メッセージ本文の追跡 - ポート処理後の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5e6b8-124">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="5e6b8-125">保存し、メッセージが受信された後メッセージの内容を追跡するには、このチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-125">Select this check box to save and track message content after the message is received.</span></span>|  
   |||  
   |||  
   |<span data-ttu-id="5e6b8-126">**メッセージのプロパティ - ポート処理前に、の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="5e6b8-126">**Track Message Properties - Request message before port processing**</span></span>|<span data-ttu-id="5e6b8-127">受信メッセージの昇格させたプロパティを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-127">Select this check box to track the promoted properties of an inbound message.</span></span>|  
   |<span data-ttu-id="5e6b8-128">**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="5e6b8-128">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="5e6b8-129">送信メッセージの昇格させたプロパティを追跡したい場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5e6b8-129">Select this check box if you want to track the promoted properties of an outbound message.</span></span>|  
   |||  
   |||  
  
## <a name="see-also"></a><span data-ttu-id="5e6b8-130">参照</span><span class="sxs-lookup"><span data-stu-id="5e6b8-130">See Also</span></span>  
 [<span data-ttu-id="5e6b8-131">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="5e6b8-131">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)