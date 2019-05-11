---
title: 有効にするパイプラインの追跡 |Microsoft Docs
description: メッセージ本文の追跡と、パイプラインが BizTalk Server でメッセージを処理するときのイベント
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689d5395d75a558e3f437c4a3efea13c70f593e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385878"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a><span data-ttu-id="a4adc-103">パイプラインが BizTalk Server での追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-103">Configure pipeline tracking in BizTalk Server</span></span>
<span data-ttu-id="a4adc-104">パイプラインの追跡を構成するのにには、BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-104">Use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="a4adc-105">トラブルシューティングと監査のための追跡を構成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4adc-105">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="a4adc-106">メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-106">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="a4adc-107">メッセージ イベントおよびポート イベント メッセージを追跡することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-107">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="a4adc-108">含まれている既定のパイプラインのいずれかの追跡を構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または BizTalk アプリケーションに展開されているカスタム パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="a4adc-108">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="a4adc-109">構成する追跡の設定は、すべてのパイプラインのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-109">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4adc-110">パイプラインの追跡を構成することができます、このパイプラインを使用しているすべてのポートに対してデータをグローバルに収集されたため、大量のデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-110">Although you can configure tracking for a pipeline, this generates a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="a4adc-111">代わりに、推奨を送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-receive-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-111">Instead, we recommend that you configure tracking on your send and receive ports, as described in [Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="a4adc-112">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="a4adc-112">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4adc-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="a4adc-113">Prerequisites</span></span>  
<span data-ttu-id="a4adc-114">BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a4adc-114">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a4adc-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-pipeline-tracking"></a><span data-ttu-id="a4adc-116">パイプラインの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a4adc-116">Enable pipeline tracking</span></span>
  
1.  <span data-ttu-id="a4adc-117">**BizTalk Server 管理**パイプラインが含まれている BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-117">In **BizTalk Server Administration**, expand the BizTalk group that contains the pipeline.</span></span> 
  
2.  <span data-ttu-id="a4adc-118">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a4adc-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="a4adc-119">既定値のいずれかの BizTalk パイプラインの追跡を構成するには、展開\<すべての成果物\>します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts\>.</span></span>  
  
    -   <span data-ttu-id="a4adc-120">BizTalk アプリケーションに展開されているカスタム パイプラインの追跡を構成するには、パイプラインを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
3.  <span data-ttu-id="a4adc-121">選択、**パイプライン**フォルダーは、パイプラインを右クリックし、**追跡**します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-121">Select the **Pipelines** folder, right-click the pipeline, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4adc-122">複数のパイプラインを一度に、Shift キーを押しながら選択を構成するには、各パイプラインの追跡を構成するにはパイプラインの 1 つを右クリックし、**追跡**します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-122">To configure tracking for multiple pipelines at once, hold down the Shift key, select each pipeline to configure, right-click one of the pipelines, and then select **Tracking**.</span></span>  
  
4.  <span data-ttu-id="a4adc-123">次の詳細を使用し、クリックして追跡オプションを構成する**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-123">Use the follwoing details to configure the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="a4adc-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a4adc-124">Use this</span></span>|<span data-ttu-id="a4adc-125">目的</span><span class="sxs-lookup"><span data-stu-id="a4adc-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a4adc-126">**イベントの追跡 - ポートの開始し、終了イベント**</span><span class="sxs-lookup"><span data-stu-id="a4adc-126">**Track Events - Port start and end events**</span></span>|<span data-ttu-id="a4adc-127">インスタンスが開始し、終了時点のみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-127">Tracks only when an instance starts and ends.</span></span> <span data-ttu-id="a4adc-128">詳細についてには、項目の名前、アセンブリ、およびその他のメタデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="a4adc-129">**イベントの追跡 - メッセージの送信および受信イベント**</span><span class="sxs-lookup"><span data-stu-id="a4adc-129">**Track Events - Message send and receive events**</span></span>|<span data-ttu-id="a4adc-130">追跡メッセージの送信およびイベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-130">Tracks message send and receive events.</span></span> <span data-ttu-id="a4adc-131">場合にのみ利用できます**ポートの開始と終了イベントのイベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a4adc-131">Only available if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="a4adc-132">**メッセージ本文の追跡のパイプライン処理前に、のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="a4adc-132">**Track Message Bodies - Messages before pipeline processing**</span></span>|<span data-ttu-id="a4adc-133">保存し、Url などのメタデータを保持し、昇格させたプロパティと、パイプラインで受信メッセージの本文を追跡します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-133">Saves and tracks the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="a4adc-134">受信パイプラインの場合は、トランスポート コンポーネントによって、パイプラインに送信されると、メッセージ本文、生のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a4adc-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="a4adc-135">アプリケーションによっては、メッセージ可能性がある暗号化、署名済み、またはエンコードします。</span><span class="sxs-lookup"><span data-stu-id="a4adc-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="a4adc-136">受信パイプラインを BizTalk マップを使用する場合は、受信マップが処理された後に追跡が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="a4adc-137">場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a4adc-137">Only available if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="a4adc-138">**メッセージ本文の追跡のパイプライン処理後のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="a4adc-138">**Track Message Bodies - Messages after pipeline processing**</span></span>|<span data-ttu-id="a4adc-139">保存し、Url などのメタデータを保持し、昇格させたプロパティと、パイプラインによって送信されたメッセージ本文を追跡します。</span><span class="sxs-lookup"><span data-stu-id="a4adc-139">Saves and tracks the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="a4adc-140">受信パイプラインの場合は、メッセージ本文は、アプリケーションによっては XML である可能性がありますが、メッセージ ボックス データベースへの送信処理されたメッセージです。</span><span class="sxs-lookup"><span data-stu-id="a4adc-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="a4adc-141">送信パイプラインは、この場合は、BizTalk マップを使用している場合は、送信マップが処理される前に追跡が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4adc-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="a4adc-142">場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="a4adc-142">Only available if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4adc-143">参照</span><span class="sxs-lookup"><span data-stu-id="a4adc-143">See Also</span></span>  
 [<span data-ttu-id="a4adc-144">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="a4adc-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)
