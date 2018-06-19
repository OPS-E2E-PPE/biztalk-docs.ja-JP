---
title: 送信ポートの追跡を有効にする |Microsoft ドキュメント
description: メッセージ本文の追跡を有効にし、BizTalk Server での送信ポートでメッセージ プロパティの追跡
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
ms.openlocfilehash: 223c417769086cc71f501b044410bf2d3e4cbc74
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2017
ms.locfileid: "26686633"
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a><span data-ttu-id="d4742-103">BizTalk Server で送信ポートの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="d4742-103">Configure send port tracking in BizTalk Server</span></span>
<span data-ttu-id="d4742-104">使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをメッセージ本文や昇格させたプロパティを表示するオプションなどの送信ポートの追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="d4742-104">Use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure tracking for a send port, such as options to view message bodies and promoted properties.</span></span> <span data-ttu-id="d4742-105">これにより、BizTalk 実装の稼動状況を監視し、ボトルネックを識別できます。</span><span class="sxs-lookup"><span data-stu-id="d4742-105">This helps you monitor the health of your BizTalk implementation and identify any bottlenecks.</span></span> <span data-ttu-id="d4742-106">構成する追跡の設定は、送信ポートのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d4742-106">The tracking settings that you configure apply to all of the instances of the send port.</span></span>  
  
 <span data-ttu-id="d4742-107">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="d4742-107">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4742-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d4742-108">Prerequisites</span></span>  
<span data-ttu-id="d4742-109">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="d4742-109">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="d4742-110">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4742-110">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-tracking-on-a-send-port"></a><span data-ttu-id="d4742-111">送信ポートの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d4742-111">Enable tracking on a send port</span></span>  
  
1.  <span data-ttu-id="d4742-112">**BizTalk Server 管理コンソール**し、BizTalk グループを展開し、送信ポートのある BizTalk アプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="d4742-112">In **BizTalk Server Administration**, expand the BizTalk group, and then expand your BizTalk application that has the send port.</span></span>  
  
2.  <span data-ttu-id="d4742-113">選択**送信ポート**、送信ポートを右クリックし、選択**プロパティ**、し、**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="d4742-113">Select **Send Ports**, right-click the send port, select **Properties**, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4742-114">1 つの送信ポートは 1 つの送信パイプラインにのみ関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d4742-114">One send port can be associated with only one send pipeline.</span></span> <span data-ttu-id="d4742-115">送信パイプラインでメッセージ本文の追跡が無効な場合は、送信ポートで追跡されますが何も行われません。</span><span class="sxs-lookup"><span data-stu-id="d4742-115">If message body tracking is disabled on the send pipeline, then nothing is tracked on the send port.</span></span> <span data-ttu-id="d4742-116">そのようなシナリオでは、その送信ポートで [追跡] オプションを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d4742-116">In such a scenario, you can disable the "Tracking" options on that send port.</span></span>  
  
3.  <span data-ttu-id="d4742-117">選択し、追跡オプションを有効にする、次の情報を使用して**OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d4742-117">Use the following details to enable the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="d4742-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d4742-118">Use this</span></span>|<span data-ttu-id="d4742-119">目的</span><span class="sxs-lookup"><span data-stu-id="d4742-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d4742-120">**メッセージ本文の追跡 - ポート処理前に、の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="d4742-120">**Track Message Bodies - Request message before port processing**</span></span>|<span data-ttu-id="d4742-121">保存し、メッセージを受信する前に、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-121">Saves and tracks message content before the message is received.</span></span> <br/><br/> <span data-ttu-id="d4742-122">**注**: メッセージ本文パイプラインの追跡をポート処理前に、の応答メッセージを正常に追跡を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="d4742-122">**Note**: Be sure to enable message body pipeline tracking to successfully track the response message before port processing.</span></span>|  
    |<span data-ttu-id="d4742-123">**メッセージ本文の追跡 - ポート処理後の要求メッセージ**</span><span class="sxs-lookup"><span data-stu-id="d4742-123">**Track Message Bodies - Request message after port processing**</span></span>|<span data-ttu-id="d4742-124">保存し、メッセージを受信した後、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-124">Saves and tracks message content after the message is received.</span></span>|  
    |<span data-ttu-id="d4742-125">**メッセージ本文 – ポート処理前に、の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-125">**Track Message Bodies – Response message before port processing**</span></span>|<span data-ttu-id="d4742-126">保存し、メッセージが送信される前に、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-126">Saves and tracks message content before the message is sent.</span></span> <span data-ttu-id="d4742-127">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4742-127">Only available for solicit-response send ports.</span></span>|    
    |<span data-ttu-id="d4742-128">**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-128">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="d4742-129">保存し、メッセージが送信された後に、メッセージの内容を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-129">Saves and tracks message content after the message is sent.</span></span> <span data-ttu-id="d4742-130">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4742-130">Only available for solicit-response send ports.</span></span>|  
    |<span data-ttu-id="d4742-131">**メッセージ本文 – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-131">**Track Message Bodies – Response message after port processing**</span></span>|<span data-ttu-id="d4742-132">受信メッセージの昇格させたプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-132">Tracks the promoted properties of an inbound message.</span></span>|  
    |<span data-ttu-id="d4742-133">**メッセージのプロパティ - ポート処理後の要求メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-133">**Track Message Properties - Request message after port processing**</span></span>|<span data-ttu-id="d4742-134">送信メッセージの昇格させたプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-134">Tracks the promoted properties of an outbound message.</span></span>|  
    |<span data-ttu-id="d4742-135">**メッセージのプロパティ-ポート処理前に、の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-135">**Track Message Properties – Response message before port processing**</span></span>|<span data-ttu-id="d4742-136">保存し、メッセージが送信される前に、メッセージのプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-136">Saves and tracks message properties before the message is sent.</span></span> <span data-ttu-id="d4742-137">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4742-137">Only available for solicit-response send ports.</span></span>|   
    |<span data-ttu-id="d4742-138">**メッセージのプロパティ – ポート処理後の応答メッセージの追跡します。**</span><span class="sxs-lookup"><span data-stu-id="d4742-138">**Track Message Properties – Response message after port processing**</span></span>|<span data-ttu-id="d4742-139">保存し、メッセージが送信された後にプロパティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="d4742-139">Saves and tracks properties after the message is sent.</span></span> <span data-ttu-id="d4742-140">送信請求-応答送信ポートでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4742-140">Only available for solicit-response send ports.</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="d4742-141">参照</span><span class="sxs-lookup"><span data-stu-id="d4742-141">See Also</span></span>  
 [<span data-ttu-id="d4742-142">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="d4742-142">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)
