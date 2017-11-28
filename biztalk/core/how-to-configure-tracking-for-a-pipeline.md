---
title: "パイプラインの追跡を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [pipelines], tracking warning
- tracking, pipelines
- tracking, warnings
- configuring, pipelines
- pipelines, tracking
- managing [pipelines], configuring
- tracking, configuring
- pipelines, configuring
- configuring [HAT tracking], pipelines
- HAT, pipelines
- managing [pipelines], tracking
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e933e9b50c99e11013ceaedf65c4f253ad1620c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-pipeline"></a><span data-ttu-id="60668-102">パイプラインの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="60668-102">How to Configure Tracking for a Pipeline</span></span>
<span data-ttu-id="60668-103">このトピックでは、BizTalk Server 管理を使用して、パイプラインの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60668-103">This topic describes how to use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="60668-104">追跡は、トラブルシューティングと監査のために構成できます。</span><span class="sxs-lookup"><span data-stu-id="60668-104">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="60668-105">メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="60668-105">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="60668-106">メッセージのメッセージ イベントおよびポート イベントも追跡できます。</span><span class="sxs-lookup"><span data-stu-id="60668-106">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="60668-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている既定のパイプラインの 1 つ、または BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成できます。</span><span class="sxs-lookup"><span data-stu-id="60668-107">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="60668-108">構成する追跡の設定は、パイプラインのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="60668-108">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60668-109">パイプラインの追跡を構成することはできますが、パイプラインを追跡すると、パイプラインを使用するすべてのポートのデータがグローバルに収集されるので、大量のデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="60668-109">Although you can configure tracking for a pipeline, this will generate a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="60668-110">お勧め代わりに、送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する方法](../core/how-to-configure-tracking-for-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="60668-110">We recommend instead that you configure tracking on your send and receive ports, as described in [How to Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [How to Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="60668-111">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="60668-111">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60668-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="60668-112">Prerequisites</span></span>  
 <span data-ttu-id="60668-113">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60668-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="60668-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="60668-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-pipeline"></a><span data-ttu-id="60668-115">パイプラインの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="60668-115">To configure tracking for a pipeline</span></span>  
  
1.  <span data-ttu-id="60668-116">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="60668-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="60668-117">コンソール ツリーで  **BizTalk Server 管理コンソール**の追跡を構成するパイプラインを含む BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="60668-117">In the console tree, expand **BizTalk Server Administration** and expand the BizTalk group containing the pipeline for which to configure tracking.</span></span>  
  
3.  <span data-ttu-id="60668-118">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="60668-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="60668-119">既定値のいずれかの BizTalk パイプラインの追跡を構成するのには、展開\<すべてのアイテム >。</span><span class="sxs-lookup"><span data-stu-id="60668-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts>.</span></span>  
  
    -   <span data-ttu-id="60668-120">BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成する場合は、パイプラインが含まれているアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="60668-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
4.  <span data-ttu-id="60668-121">クリックして、**パイプライン**フォルダーは、パイプラインを右クリックし、をクリックして**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="60668-121">Click the **Pipelines** folder, right-click the pipeline, and then click **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60668-122">複数のパイプラインを一度に、Shift キーを押しながらクリックを構成するのには、各パイプラインの追跡を構成するのに、パイプラインの 1 つを右クリックして**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="60668-122">To configure tracking for multiple pipelines at once, hold down the Shift key, click each pipeline to configure, right-click one of the pipelines, and then click **Tracking**.</span></span>  
  
5.  <span data-ttu-id="60668-123">次の表の説明に従って、必要な追跡オプションを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="60668-123">Configure tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="60668-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="60668-124">Use this</span></span>|<span data-ttu-id="60668-125">目的</span><span class="sxs-lookup"><span data-stu-id="60668-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="60668-126">**ポートの開始と終了イベント**</span><span class="sxs-lookup"><span data-stu-id="60668-126">**Port start and end events**</span></span>|<span data-ttu-id="60668-127">インスタンスの開始時と終了時のみを追跡する場合に、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="60668-127">Select this check box to track only when an instance starts and ends.</span></span> <span data-ttu-id="60668-128">[詳細] には、項目名、アセンブリ、および他のメタデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="60668-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="60668-129">**メッセージの送信および受信イベント**</span><span class="sxs-lookup"><span data-stu-id="60668-129">**Message send and receive events**</span></span>|<span data-ttu-id="60668-130">メッセージの送信イベントと受信イベントを追跡する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="60668-130">Select this check box to track message send and receive events.</span></span> <span data-ttu-id="60668-131">このチェック ボックスは使用可能な場合にのみ、**ポートの開始と終了イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="60668-131">This check box is available only if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="60668-132">**パイプライン処理前に、のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="60668-132">**Messages before pipeline processing**</span></span>|<span data-ttu-id="60668-133">パイプラインで受信されたメッセージ本文を保存および追跡する場合に、このチェック ボックスをオンにします。このパイプラインでは、URL や昇格させたプロパティなどのメタデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="60668-133">Select this check box to save and track the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="60668-134">パイプラインが受信パイプラインの場合、このメッセージ本文は、トランスポート コンポーネントからパイプラインに送信される時点の未処理のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="60668-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="60668-135">アプリケーションによっては、メッセージは暗号化、署名、またはエンコードされていることがあります。</span><span class="sxs-lookup"><span data-stu-id="60668-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="60668-136">BizTalk マップを使用するときに、これが受信パイプラインである場合は、追跡は受信マップが処理された後で行われます。</span><span class="sxs-lookup"><span data-stu-id="60668-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="60668-137">このチェック ボックスは使用可能な場合にのみ、**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="60668-137">This check box is available only if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="60668-138">**パイプライン処理後のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="60668-138">**Messages after pipeline processing**</span></span>|<span data-ttu-id="60668-139">パイプラインで送信されたメッセージ本文を保存および追跡する場合に、このチェック ボックスをオンにします。このパイプラインでは、URL や昇格させたプロパティなどのメタデータが保持されます。</span><span class="sxs-lookup"><span data-stu-id="60668-139">Select this check box to save and track the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="60668-140">パイプラインが受信パイプラインの場合、このメッセージ本文は、メッセージ ボックス データベースに送信される時点の処理済みのメッセージです。アプリケーションによっては XML 形式である場合があります。</span><span class="sxs-lookup"><span data-stu-id="60668-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="60668-141">BizTalk マップを使用するときに、これが送信パイプラインである場合は、追跡は送信マップが処理される前に行われます。</span><span class="sxs-lookup"><span data-stu-id="60668-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="60668-142">このチェック ボックスは使用可能な場合にのみ、**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="60668-142">This check box is available only if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60668-143">参照</span><span class="sxs-lookup"><span data-stu-id="60668-143">See Also</span></span>  
 [<span data-ttu-id="60668-144">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="60668-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)