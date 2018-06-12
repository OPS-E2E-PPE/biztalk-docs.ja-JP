---
title: Event Hubs アダプターを使用して |Microsoft ドキュメント
description: BizTalk Server で Azure Event Hubs アダプターを使用してメッセージの送受信を行う
ms.custom: ''
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: plarsen
manager: anneta
ms.openlocfilehash: cb9bbe26f07d87d7cccc084b6842b6d0974fdbb3
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848922"
---
# <a name="event-hub-adapter-in-biztalk"></a><span data-ttu-id="92c34-103">BizTalk でイベント ハブのアダプター</span><span class="sxs-lookup"><span data-stu-id="92c34-103">Event Hub adapter in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="92c34-104">概要</span><span class="sxs-lookup"><span data-stu-id="92c34-104">Overview</span></span>
<span data-ttu-id="92c34-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、BizTalk Server と Azure Event Hubs 間でメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="92c34-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can send and receive messages between BizTalk Server and Azure Event Hubs.</span></span> 

<span data-ttu-id="92c34-106">Azure Event Hubs は現在ストリーミング プラットフォーム、拡張性の高いデータは、および受信、および数百万の 1 秒あたりのイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="92c34-106">Azure Event Hubs is a highly scalable data streaming platform, and can receive and process millions of events per second.</span></span> <span data-ttu-id="92c34-107">[Event Hubs は何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="92c34-107">[What is Event Hubs?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) provides more details.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92c34-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="92c34-108">Prerequisites</span></span>

* <span data-ttu-id="92c34-109">作成、 [Azure イベント ハブの名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span><span class="sxs-lookup"><span data-stu-id="92c34-109">Create an [Azure event hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span></span>
* <span data-ttu-id="92c34-110">作成、[コンテナーと Azure blob ストレージ アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span><span class="sxs-lookup"><span data-stu-id="92c34-110">Create an [Azure blob storage account with a container](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span></span>
* <span data-ttu-id="92c34-111">インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で</span><span class="sxs-lookup"><span data-stu-id="92c34-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your BizTalk Server</span></span>

<span data-ttu-id="92c34-112">イベント ハブが作成されましたが、およびイベントを送受信する必要がある、接続文字列があります。</span><span class="sxs-lookup"><span data-stu-id="92c34-112">Your event hub is now created, and you have the connection strings you need to send and receive events.</span></span>

## <a name="send-messages-to-event-hubs"></a><span data-ttu-id="92c34-113">Event Hub にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-113">Send messages to Event Hubs</span></span>

1.  <span data-ttu-id="92c34-114">BizTalk Server 管理コンソールを右クリックして**送信ポート****新規**を選択し、**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-114">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="92c34-115">[送信ポートを作成](../core/how-to-create-a-send-port2.md)のガイダンスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="92c34-115">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="92c34-116">入力、**名前**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-116">Enter a **Name**.</span></span> <span data-ttu-id="92c34-117">**トランスポート**、設定、**型**に**EventHub**を選択して**構成**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-117">In **Transport**, set the **Type** to **EventHub**, and select **Configure**.</span></span> 

3. <span data-ttu-id="92c34-118">構成、 **Azure アカウント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92c34-118">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="92c34-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92c34-119">Use this</span></span>|<span data-ttu-id="92c34-120">目的</span><span class="sxs-lookup"><span data-stu-id="92c34-120">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="92c34-121">**サインイン**</span><span class="sxs-lookup"><span data-stu-id="92c34-121">**Sign-in**</span></span> | <span data-ttu-id="92c34-122">Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="92c34-122">Sign into your Azure account</span></span> |
    | <span data-ttu-id="92c34-123">**サブスクリプション**</span><span class="sxs-lookup"><span data-stu-id="92c34-123">**Subscription**</span></span> | <span data-ttu-id="92c34-124">EventHubs 名前空間を持つサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-124">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="92c34-125">**リソース グループ**</span><span class="sxs-lookup"><span data-stu-id="92c34-125">**Resource Group**</span></span> | <span data-ttu-id="92c34-126">EventHubs 名前空間を持つリソース グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-126">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="92c34-127">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92c34-127">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="92c34-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92c34-128">Use this</span></span>|<span data-ttu-id="92c34-129">目的</span><span class="sxs-lookup"><span data-stu-id="92c34-129">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="92c34-130">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="92c34-130">**Namespace**</span></span> | <span data-ttu-id="92c34-131">Sb のようなものである、イベント ハブ名前空間を選択します//*youreventhubnamespace*.servicebus.windows.net/。</span><span class="sxs-lookup"><span data-stu-id="92c34-131">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="92c34-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="92c34-132">**Name**</span></span> | <span data-ttu-id="92c34-133">(これは、イベント ハブ名前空間内で作成した)、イベント ハブの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-133">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="92c34-134">**既定のパーティション キー**</span><span class="sxs-lookup"><span data-stu-id="92c34-134">**Default Partition Key**</span></span> | <span data-ttu-id="92c34-135">任意。</span><span class="sxs-lookup"><span data-stu-id="92c34-135">Optional.</span></span> <span data-ttu-id="92c34-136">[Event Hub プログラミング ガイド](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)このキーの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="92c34-136">[Event Hubs programming guide](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) provides more details on this key.</span></span> |
    | <span data-ttu-id="92c34-137">**[認証]**</span><span class="sxs-lookup"><span data-stu-id="92c34-137">**Authentication**</span></span> | <span data-ttu-id="92c34-138">**Namespace Access Signature** 、既定値は、イベント ハブ名前空間を作成するときに作成される RootManageSharedAccessKey が自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="92c34-138">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="92c34-139">**エンティティ Access Signature** SAS ポリシーが、イベント ハブのレベルで (、イベント ハブ名前空間レベルではなく) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="92c34-139">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="92c34-140">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="92c34-140">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="92c34-141">完了したらのプロパティが、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92c34-141">When finished, your properties look similar to the following:</span></span> 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-properties.png)


5. <span data-ttu-id="92c34-143">任意。</span><span class="sxs-lookup"><span data-stu-id="92c34-143">Optional.</span></span> <span data-ttu-id="92c34-144">構成、**メッセージ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="92c34-144">Configure the **Message** properties.</span></span> <span data-ttu-id="92c34-145">**ユーザー定義メッセージのプロパティの Namespace**値は、Event Hubs メッセージ プロパティにマップされる BizTalk メッセージのスキーマを表します。</span><span class="sxs-lookup"><span data-stu-id="92c34-145">The **Namespace for User Defined Message Properties** value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span>

6. <span data-ttu-id="92c34-146">選択**Ok**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="92c34-146">Select **Ok** to save your changes.</span></span> 


### <a name="test-your-send-port"></a><span data-ttu-id="92c34-147">送信ポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="92c34-147">Test your send port</span></span>

<span data-ttu-id="92c34-148">単純なを使用するファイルの受信ポートと、Azure Event Hub にメッセージを送信する場所です。</span><span class="sxs-lookup"><span data-stu-id="92c34-148">You can use a simple File receive port and location to send messages to your Azure Event Hub.</span></span> 

1. <span data-ttu-id="92c34-149">ファイル アダプターを使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="92c34-149">Create a receive port using the File adapter.</span></span> <span data-ttu-id="92c34-150">内で、受信場所は、設定、**受信フォルダー**に \**C:\Temp\In\** に、ファイル マスクを設定および **\*.xml**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-150">Within your receive location,  set the **Receive folder** to \**C:\Temp\In\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="92c34-151">Event Hub に送信ポートのプロパティを設定、**フィルター**に`BTS.ReceivePortName == FileReceivePort`です。</span><span class="sxs-lookup"><span data-stu-id="92c34-151">In your Event Hub send port properties, set the **Filters** to `BTS.ReceivePortName == FileReceivePort`.</span></span>
3. <span data-ttu-id="92c34-152">テキスト エディターに貼り付け、ファイルに保存**EventHubMessage.xml**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-152">Paste the following into a text editor, and save the file as **EventHubMessage.xml**.</span></span> <span data-ttu-id="92c34-153">これは、サンプル メッセージです。</span><span class="sxs-lookup"><span data-stu-id="92c34-153">This is your sample message.</span></span> 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. <span data-ttu-id="92c34-154">開始ファイルは、場所と、イベント ハブの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-154">Start the File receive location and the Event Hub send port.</span></span>
5. <span data-ttu-id="92c34-155">コピー **EventHubMessage.xml**受信フォルダにサンプル メッセージ (C:\Temp\In\)です。</span><span class="sxs-lookup"><span data-stu-id="92c34-155">Copy **EventHubMessage.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="92c34-156">送信ポートは、XML ファイルを event hub に送信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-156">The send port sends the XML file to the event hub.</span></span>

## <a name="receive-messages-from-event-hubs"></a><span data-ttu-id="92c34-157">Event Hub からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-157">Receive messages from Event Hubs</span></span>

1. <span data-ttu-id="92c34-158">BizTalk Server 管理コンソールを右クリックし**受信ポート****新規**を選択し、**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-158">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span> 

    <span data-ttu-id="92c34-159">[受信ポートを作成](../core/how-to-create-a-receive-port.md)のガイダンスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="92c34-159">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="92c34-160">名前を入力し、選択**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-160">Enter a name, and select **Receive Locations**.</span></span> 

3. <span data-ttu-id="92c34-161">選択**新規**、および**名前**受信場所。</span><span class="sxs-lookup"><span data-stu-id="92c34-161">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="92c34-162">**トランスポート** **EventHub**から、**型**クリックしてドロップダウン リスト、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="92c34-162">In **Transport**, select **EventHub** from the **Type** drop-down list, and then select **Configure**.</span></span> 

4. <span data-ttu-id="92c34-163">構成、 **Azure アカウント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92c34-163">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="92c34-164">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92c34-164">Use this</span></span>|<span data-ttu-id="92c34-165">目的</span><span class="sxs-lookup"><span data-stu-id="92c34-165">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="92c34-166">**サインイン**</span><span class="sxs-lookup"><span data-stu-id="92c34-166">**Sign-in**</span></span> | <span data-ttu-id="92c34-167">Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="92c34-167">Sign into your Azure account</span></span> |
    | <span data-ttu-id="92c34-168">**サブスクリプション**</span><span class="sxs-lookup"><span data-stu-id="92c34-168">**Subscription**</span></span> | <span data-ttu-id="92c34-169">EventHubs 名前空間を持つサブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-169">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="92c34-170">**リソース グループ**</span><span class="sxs-lookup"><span data-stu-id="92c34-170">**Resource Group**</span></span> | <span data-ttu-id="92c34-171">EventHubs 名前空間を持つリソース グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-171">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="92c34-172">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92c34-172">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="92c34-173">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92c34-173">Use this</span></span>|<span data-ttu-id="92c34-174">目的</span><span class="sxs-lookup"><span data-stu-id="92c34-174">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="92c34-175">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="92c34-175">**Namespace**</span></span> | <span data-ttu-id="92c34-176">Sb のようなものである、イベント ハブ名前空間を選択します//*youreventhubnamespace*.servicebus.windows.net/。</span><span class="sxs-lookup"><span data-stu-id="92c34-176">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="92c34-177">**Name**</span><span class="sxs-lookup"><span data-stu-id="92c34-177">**Name**</span></span> | <span data-ttu-id="92c34-178">(これは、イベント ハブ名前空間内で作成した)、イベント ハブの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-178">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="92c34-179">**コンシューマー グループ**</span><span class="sxs-lookup"><span data-stu-id="92c34-179">**Consumer Group**</span></span> | <span data-ttu-id="92c34-180">Event Hub 内のコンシューマー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-180">Select the Consumer group within your Event Hub.</span></span> <span data-ttu-id="92c34-181">既定のグループが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="92c34-181">A default group is created automatically.</span></span> <br/><br/><span data-ttu-id="92c34-182">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="92c34-182">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) provides more details.</span></span> |
    | <span data-ttu-id="92c34-183">**[認証]**</span><span class="sxs-lookup"><span data-stu-id="92c34-183">**Authentication**</span></span> | <span data-ttu-id="92c34-184">**Namespace Access Signature** 、既定値は、イベント ハブ名前空間を作成するときに作成される RootManageSharedAccessKey が自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="92c34-184">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="92c34-185">**エンティティ Access Signature** SAS ポリシーが、イベント ハブのレベルで (、イベント ハブ名前空間レベルではなく) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="92c34-185">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="92c34-186">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="92c34-186">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="92c34-187">完了したらのプロパティが、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92c34-187">When finished, your properties look similar to the following:</span></span> 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-receive-properties.png)

5. <span data-ttu-id="92c34-189">構成、**チェックポイント**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="92c34-189">Configure the **Checkpoint** properties.</span></span> <span data-ttu-id="92c34-190">このアダプターは、確実に、チェックポイントを使用してイベントを読み取るし、再起動からの再開を Azure blob ストレージ アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="92c34-190">This adapter uses an Azure blob storage account to reliably read events using a checkpoint, and resume from a restart.</span></span> 

    <span data-ttu-id="92c34-191">**記憶域の認証** </span><span class="sxs-lookup"><span data-stu-id="92c34-191">**Storage Authentication** </span></span>  
    <span data-ttu-id="92c34-192">認証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="92c34-192">Select an authentication method.</span></span> <span data-ttu-id="92c34-193">通常、共有アクセス署名を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92c34-193">Typically, it's recommended to use a Shared Access Signature.</span></span> <span data-ttu-id="92c34-194">次のリンクでは、これは、シナリオに適したの判断に役立つ優れたリソースです。</span><span class="sxs-lookup"><span data-stu-id="92c34-194">The following links are good resources to help you decide which is right for your scenario:</span></span><br/><br/>[<span data-ttu-id="92c34-195">Azure ストレージ アカウントの概要</span><span class="sxs-lookup"><span data-stu-id="92c34-195">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[<span data-ttu-id="92c34-196">共有アクセス署名 (SAS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="92c34-196">Using shared access signatures (SAS)</span></span>](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    <span data-ttu-id="92c34-197">完了したらのプロパティが、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92c34-197">When finished, your properties look similar to the following:</span></span> 

    ![チェックポイントのプロパティ](../core/media/event-hub-receive-checkpoint.png)

6. <span data-ttu-id="92c34-199">構成、**メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="92c34-199">Configure the **Message** properties:</span></span> 

    |<span data-ttu-id="92c34-200">プロパティ</span><span class="sxs-lookup"><span data-stu-id="92c34-200">Use this</span></span>|<span data-ttu-id="92c34-201">目的</span><span class="sxs-lookup"><span data-stu-id="92c34-201">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="92c34-202">**ユーザーの Namespace メッセージのプロパティを定義します。**</span><span class="sxs-lookup"><span data-stu-id="92c34-202">**Namespace for User Defined Message Properties**</span></span> | <span data-ttu-id="92c34-203">http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User 既定のスキーマが、別のスキーマを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="92c34-203">http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User is the default schema, but you can enter another schema.</span></span> <span data-ttu-id="92c34-204">この値は、Event Hubs メッセージ プロパティにマップされる BizTalk メッセージのスキーマを表します。</span><span class="sxs-lookup"><span data-stu-id="92c34-204">This value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span> |
    | <span data-ttu-id="92c34-205">**ユーザー定義プロパティを昇格させる**</span><span class="sxs-lookup"><span data-stu-id="92c34-205">**Promote user defined properties**</span></span> | <span data-ttu-id="92c34-206">任意。</span><span class="sxs-lookup"><span data-stu-id="92c34-206">Optional.</span></span> <span data-ttu-id="92c34-207">たい場合は、これらのプロパティを昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="92c34-207">You can promote these properties if you prefer.</span></span> <br/><br/><span data-ttu-id="92c34-208">**注**</span><span class="sxs-lookup"><span data-stu-id="92c34-208">**NOTE**</span></span><br/><span data-ttu-id="92c34-209">昇格させる必要があるプロパティが展開されている porperty スキーマを持っている必要があります*する前に*イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-209">The properties that need to be promoted should have a porperty schema deployed *before* receiving events.</span></span>|

7. <span data-ttu-id="92c34-210">選択**Ok**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="92c34-210">Select **Ok** to save your changes.</span></span> 

### <a name="test-your-receive-settings"></a><span data-ttu-id="92c34-211">テストの設定を受け取る</span><span class="sxs-lookup"><span data-stu-id="92c34-211">Test your receive settings</span></span>

<span data-ttu-id="92c34-212">単純な File 送信ポートを使用するには、Azure Event Hub からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-212">You can use a simple File send port to receive messages from your Azure Event Hub.</span></span> 

1. <span data-ttu-id="92c34-213">ファイル アダプターを使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="92c34-213">Create a send port using the File adapter.</span></span> <span data-ttu-id="92c34-214">送信ポートのプロパティ内で、設定、**コピー先フォルダー**に **C:\Temp\Out\**、設定と、および**ファイル名**に **%MessageID%.xml**.</span><span class="sxs-lookup"><span data-stu-id="92c34-214">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="92c34-215">送信ポートのプロパティは、ファイルで、設定、**フィルター**に`BTS.ReceivePortName == EHReceivePort`です。</span><span class="sxs-lookup"><span data-stu-id="92c34-215">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == EHReceivePort`.</span></span>
3. <span data-ttu-id="92c34-216">開始イベント ハブは、場所とファイル送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="92c34-216">Start the Event Hub receive location and the File send port.</span></span>
4. <span data-ttu-id="92c34-217">コピー先フォルダー (c:\temp\out) にメッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="92c34-217">Look for messages in the destination folder (c:\temp\out).</span></span>

## <a name="do-more"></a><span data-ttu-id="92c34-218">複数の操作を行います</span><span class="sxs-lookup"><span data-stu-id="92c34-218">Do more</span></span>
<span data-ttu-id="92c34-219">Event Hubs は、多数の Azure Data Lake、HD Insight など他の Azure サービスへの「フロント ドア」と見なされます。</span><span class="sxs-lookup"><span data-stu-id="92c34-219">Event Hubs is considered the "front door" to a lot of other Azure services, including Azure Data Lake, HD Insight, and more.</span></span> <span data-ttu-id="92c34-220">多数のメッセージを処理し、高速に処理することは想定がします。</span><span class="sxs-lookup"><span data-stu-id="92c34-220">It's designed to process a lot of messages, and process them fast.</span></span> <span data-ttu-id="92c34-221">Event Hubs とその機能について詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92c34-221">Read more about Event Hubs, and its features:</span></span> 

[<span data-ttu-id="92c34-222">Event Hubs の機能の概要</span><span class="sxs-lookup"><span data-stu-id="92c34-222">Event Hubs features overview</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[<span data-ttu-id="92c34-223">Event Hubs は何ですか。</span><span class="sxs-lookup"><span data-stu-id="92c34-223">What is Event Hubs?</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)