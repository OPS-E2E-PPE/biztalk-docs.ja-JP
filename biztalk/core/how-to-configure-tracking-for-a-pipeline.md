---
title: 有効にするパイプラインの追跡 |Microsoft ドキュメント
description: メッセージ本文の追跡とパイプラインが BizTalk Server でメッセージを処理するときにイベント
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
ms.openlocfilehash: 2ed836947ff47e21eeeb3bc306e94ea08f5464f0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2017
ms.locfileid: "26686625"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a><span data-ttu-id="5368e-103">パイプラインが BizTalk Server での追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="5368e-103">Configure pipeline tracking in BizTalk Server</span></span>
<span data-ttu-id="5368e-104">BizTalk Server 管理コンソールを使用すると、パイプラインの追跡を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5368e-104">Use the BizTalk Server Administration to configure tracking for a pipeline.</span></span> <span data-ttu-id="5368e-105">追跡は、トラブルシューティングと監査のために構成できます。</span><span class="sxs-lookup"><span data-stu-id="5368e-105">You might want to configure tracking for troubleshooting and auditing purposes.</span></span> <span data-ttu-id="5368e-106">メッセージ プロパティ、ポート イベント、およびメッセージ イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5368e-106">You can view message properties, port events, and message events.</span></span> <span data-ttu-id="5368e-107">メッセージのメッセージ イベントおよびポート イベントも追跡できます。</span><span class="sxs-lookup"><span data-stu-id="5368e-107">You can also track message events and port events for messages.</span></span>  
  
 <span data-ttu-id="5368e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている既定のパイプラインの 1 つ、または BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5368e-108">You can configure tracking for one of the default pipelines included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or a custom pipeline that has been deployed into a BizTalk application.</span></span> <span data-ttu-id="5368e-109">構成する追跡の設定は、パイプラインのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5368e-109">The tracking settings that you configure apply to all of the instances of the pipeline.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5368e-110">パイプラインの追跡を構成できますが、このデータは、パイプラインを使用するすべてのポートに対してグローバルに収集されるため大量のデータが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5368e-110">Although you can configure tracking for a pipeline, this generates a large amount of data because data is gathered globally for all ports that use the pipeline.</span></span> <span data-ttu-id="5368e-111">代わりに、ことをお勧め、送信の追跡を構成し、受信ポート、」の説明に従って[送信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-send-port.md)と[受信ポートの追跡を構成する](../core/how-to-configure-tracking-for-a-receive-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="5368e-111">Instead, we recommend that you configure tracking on your send and receive ports, as described in [Configure Tracking for a Send Port](../core/how-to-configure-tracking-for-a-send-port.md) and [Configure Tracking for a Receive Port](../core/how-to-configure-tracking-for-a-receive-port.md).</span></span>  
  
 <span data-ttu-id="5368e-112">メッセージ イベントおよびサービス インスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)</span><span class="sxs-lookup"><span data-stu-id="5368e-112">For more information about the message event and service instance tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md)</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5368e-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="5368e-113">Prerequisites</span></span>  
<span data-ttu-id="5368e-114">BizTalk Server 管理者グループのメンバーであるアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="5368e-114">Sign in with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5368e-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5368e-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="enable-pipeline-tracking"></a><span data-ttu-id="5368e-116">パイプラインの追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5368e-116">Enable pipeline tracking</span></span>
  
1.  <span data-ttu-id="5368e-117">**BizTalk Server 管理コンソール**パイプラインが含まれている BizTalk グループを展開します。</span><span class="sxs-lookup"><span data-stu-id="5368e-117">In **BizTalk Server Administration**, expand the BizTalk group that contains the pipeline.</span></span> 
  
2.  <span data-ttu-id="5368e-118">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5368e-118">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="5368e-119">既定値のいずれかの BizTalk パイプラインの追跡を構成するのには、展開\<すべての成果物\>です。</span><span class="sxs-lookup"><span data-stu-id="5368e-119">To configure tracking for one of the default BizTalk pipelines, expand \<All Artifacts\>.</span></span>  
  
    -   <span data-ttu-id="5368e-120">BizTalk アプリケーションに展開されたカスタム パイプラインの追跡を構成する場合は、パイプラインが含まれているアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5368e-120">To configure tracking for a custom pipeline that has been deployed into a BizTalk application, expand the application containing the pipeline.</span></span>  
  
3.  <span data-ttu-id="5368e-121">選択、**パイプライン**フォルダーは、パイプラインを右クリックし、**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="5368e-121">Select the **Pipelines** folder, right-click the pipeline, and then select **Tracking**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5368e-122">複数のパイプラインを一度に、Shift キーを押しながら選択を構成するのには、各パイプラインの追跡を構成するにはパイプラインの 1 つを右クリックし、**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="5368e-122">To configure tracking for multiple pipelines at once, hold down the Shift key, select each pipeline to configure, right-click one of the pipelines, and then select **Tracking**.</span></span>  
  
4.  <span data-ttu-id="5368e-123">詳細を使用しを選択し、追跡オプションを構成する**OK**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5368e-123">Use the follwoing details to configure the tracking options you want, and then select **OK** to save your changes.</span></span>  
  
    |<span data-ttu-id="5368e-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5368e-124">Use this</span></span>|<span data-ttu-id="5368e-125">目的</span><span class="sxs-lookup"><span data-stu-id="5368e-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5368e-126">**イベントの追跡-ポートの開始し、終了イベント**</span><span class="sxs-lookup"><span data-stu-id="5368e-126">**Track Events - Port start and end events**</span></span>|<span data-ttu-id="5368e-127">インスタンスの開始時し、終了時にのみを追跡します。</span><span class="sxs-lookup"><span data-stu-id="5368e-127">Tracks only when an instance starts and ends.</span></span> <span data-ttu-id="5368e-128">[詳細] には、項目名、アセンブリ、および他のメタデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5368e-128">Details include item name, assembly, and other metadata.</span></span>|  
    |<span data-ttu-id="5368e-129">**イベントの追跡-メッセージの送信および受信イベント**</span><span class="sxs-lookup"><span data-stu-id="5368e-129">**Track Events - Message send and receive events**</span></span>|<span data-ttu-id="5368e-130">追跡メッセージの送信およびイベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="5368e-130">Tracks message send and receive events.</span></span> <span data-ttu-id="5368e-131">場合にのみ利用できます**ポートの開始と終了イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="5368e-131">Only available if **Port start and end events** is selected.</span></span>|  
    |<span data-ttu-id="5368e-132">**メッセージ本文の追跡のパイプライン処理前に、のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="5368e-132">**Track Message Bodies - Messages before pipeline processing**</span></span>|<span data-ttu-id="5368e-133">保存し、Url などのメタデータを保持し、プロパティを昇格するパイプラインで受信メッセージの本文を追跡します。</span><span class="sxs-lookup"><span data-stu-id="5368e-133">Saves and tracks the message bodies received by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="5368e-134">パイプラインが受信パイプラインの場合、このメッセージ本文は、トランスポート コンポーネントからパイプラインに送信される時点の未処理のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="5368e-134">If this is a receive pipeline, the message body is the raw message as submitted to the pipeline by the transport component.</span></span> <span data-ttu-id="5368e-135">アプリケーションによっては、メッセージは暗号化、署名、またはエンコードされていることがあります。</span><span class="sxs-lookup"><span data-stu-id="5368e-135">Depending on the application, the message might be encrypted, signed, or encoded.</span></span> <span data-ttu-id="5368e-136">BizTalk マップを使用するときに、これが受信パイプラインである場合は、追跡は受信マップが処理された後で行われます。</span><span class="sxs-lookup"><span data-stu-id="5368e-136">When using a BizTalk map, if this is a receive pipeline, tracking takes place after the inbound map is processed.</span></span><br /><br /> <span data-ttu-id="5368e-137">場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="5368e-137">Only available if **Message send and receive events** is selected.</span></span>|  
    |<span data-ttu-id="5368e-138">**メッセージ本文の追跡のパイプライン処理後のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="5368e-138">**Track Message Bodies - Messages after pipeline processing**</span></span>|<span data-ttu-id="5368e-139">保存し、Url などのメタデータを保持し、昇格させたプロパティがパイプラインによって送信されたメッセージ本文を追跡します。</span><span class="sxs-lookup"><span data-stu-id="5368e-139">Saves and tracks the message bodies sent by the pipeline, which holds metadata such as URLs and promoted properties.</span></span> <span data-ttu-id="5368e-140">パイプラインが受信パイプラインの場合、このメッセージ本文は、メッセージ ボックス データベースに送信される時点の処理済みのメッセージです。アプリケーションによっては XML 形式である場合があります。</span><span class="sxs-lookup"><span data-stu-id="5368e-140">If this is a receive pipeline, the message body is the processed message to be submitted to the MessageBox database, which may be XML depending on your application.</span></span> <span data-ttu-id="5368e-141">BizTalk マップを使用するときに、これが送信パイプラインである場合は、追跡は送信マップが処理される前に行われます。</span><span class="sxs-lookup"><span data-stu-id="5368e-141">When using a BizTalk map, if this is a send pipeline, tracking takes place before the outbound map is processed.</span></span><br /><br /> <span data-ttu-id="5368e-142">場合にのみ利用できます**メッセージの送信および受信イベント**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="5368e-142">Only available if **Message send and receive events** is selected.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5368e-143">参照</span><span class="sxs-lookup"><span data-stu-id="5368e-143">See Also</span></span>  
 [<span data-ttu-id="5368e-144">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="5368e-144">Managing Pipelines</span></span>](../core/managing-pipelines.md)
