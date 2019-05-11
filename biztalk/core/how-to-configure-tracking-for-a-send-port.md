---
title: 送信ポートの追跡を有効にする |Microsoft Docs
description: メッセージ本文の追跡をオンにし、BizTalk server 送信ポートでメッセージ プロパティの追跡
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578d48c5eefe4866de974b11f1171cf271a24156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385987"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a><span data-ttu-id="c98a9-103">BizTalk server 送信ポートの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-103">Configure send port tracking in BizTalk Server</span></span>
<span data-ttu-id="c98a9-104">使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなどの追跡、送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-104">Use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="c98a9-105">これにより、BizTalk 実装の正常性を監視し、ボトルネックを識別できます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-105">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="c98a9-106">構成する追跡の設定は、すべての送信ポートのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-106">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="c98a9-107">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="c98a9-107">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c98a9-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="c98a9-108">Prerequisites</span></span>  
<span data-ttu-id="c98a9-109">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="c98a9-109">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="c98a9-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-tracking-on-a-send-port"></a><span data-ttu-id="c98a9-111">送信ポートの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c98a9-111">Enable tracking on a send port</span></span>  
  
1.  <span data-ttu-id="c98a9-112">**BizTalk Server 管理**、BizTalk グループを展開し、送信ポートを含む BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-112">In **BizTalk Server Administration**, expand the BizTalk group, and then expand your BizTalk application that has the send port.</span></span>  
  
2.  <span data-ttu-id="c98a9-113">選択**送信ポート**、送信ポートを右クリックし、選択**プロパティ**、し、**追跡**します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-113">Select **Send Ports**, right-click the send port, select **Properties**, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c98a9-114">1 つの送信ポートは、1 つだけ送信パイプラインを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="c98a9-115">送信パイプラインでメッセージ本文の追跡が無効の場合は、送信ポートで追跡されますが何も。</span><span class="sxs-lookup"><span data-stu-id="c98a9-115">If message body tracking is disabled on the send pipeline, then nothing is tracked on the send port.</span></span> <span data-ttu-id="c98a9-116">このようなシナリオで無効にする「追跡」オプションでその送信ポート。</span><span class="sxs-lookup"><span data-stu-id="c98a9-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
3.  <span data-ttu-id="c98a9-117">次の詳細を使用し、クリックして追跡オプションを有効に**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-117">Use the following details to enable the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="c98a9-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c98a9-118">Use this</span></span>|<span data-ttu-id="c98a9-119">目的</span><span class="sxs-lookup"><span data-stu-id="c98a9-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c98a9-120">**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c98a9-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="c98a9-121">保存し、メッセージを受信する前に、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-121">Saves and tracks message content before the message is received.</span></span> <br/><br/> <span data-ttu-id="c98a9-122">**注**:メッセージ本文パイプラインの追跡をポート処理前に、の応答メッセージを正常に追跡を有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-122">**Note**: Be sure to enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="c98a9-123">**メッセージ本文の追跡 - ポート処理後の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="c98a9-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="c98a9-124">保存し、メッセージが受信された後メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-124">Saves and tracks message content after the message is received.</span></span>|  
    |<span data-ttu-id="c98a9-125">**メッセージ本文 – ポート処理前に、の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-125">**Track Message Bodies – Response message before port processing**</span></span>|<span data-ttu-id="c98a9-126">保存し、メッセージが送信される前に、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-126">Saves and tracks message content before the message is sent.</span></span> <span data-ttu-id="c98a9-127">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-127">Only available for solicit-response send ports.</span></span>|    
    |<span data-ttu-id="c98a9-128">**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-128">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="c98a9-129">保存し、メッセージが送信された後、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-129">Saves and tracks message content after the message is sent.</span></span> <span data-ttu-id="c98a9-130">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-130">Only available for solicit-response send ports.</span></span>|  
    |<span data-ttu-id="c98a9-131">**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-131">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="c98a9-132">受信メッセージの昇格させたプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-132">Tracks the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="c98a9-133">**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-133">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="c98a9-134">送信メッセージの昇格させたプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-134">Tracks the promoted properties of an outbound message.</span></span>|  
    |<span data-ttu-id="c98a9-135">**メッセージのプロパティ-ポート処理前に、の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-135">**Track Message Properties – Response message before port processing**</span></span>|<span data-ttu-id="c98a9-136">保存し、メッセージが送信される前に、メッセージのプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-136">Saves and tracks message properties before the message is sent.</span></span> <span data-ttu-id="c98a9-137">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-137">Only available for solicit-response send ports.</span></span>|   
    |<span data-ttu-id="c98a9-138">**メッセージのプロパティ – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="c98a9-138">**Track Message Properties – Response message after port processing**</span></span>|<span data-ttu-id="c98a9-139">保存し、メッセージが送信された後にプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="c98a9-139">Saves and tracks properties after the message is sent.</span></span> <span data-ttu-id="c98a9-140">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c98a9-140">Only available for solicit-response send ports.</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="c98a9-141">参照</span><span class="sxs-lookup"><span data-stu-id="c98a9-141">See Also</span></span>  
 [<span data-ttu-id="c98a9-142">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="c98a9-142">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)
