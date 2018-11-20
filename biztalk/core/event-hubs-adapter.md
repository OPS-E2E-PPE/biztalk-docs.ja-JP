---
title: Event Hubs アダプターを使用して、|Microsoft Docs
description: BizTalk Server で Azure Event Hubs アダプターを使用してメッセージを送受信します。
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
ms.openlocfilehash: a1e30b1ab1aacc1c5134d1dd5b44744bd670b308
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630335"
---
# <a name="event-hub-adapter-in-biztalk"></a><span data-ttu-id="729a5-103">BizTalk でイベント ハブのアダプター</span><span class="sxs-lookup"><span data-stu-id="729a5-103">Event Hub adapter in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="729a5-104">概要</span><span class="sxs-lookup"><span data-stu-id="729a5-104">Overview</span></span>
<span data-ttu-id="729a5-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、BizTalk Server と Azure Event Hubs 間のメッセージを送受信できます。</span><span class="sxs-lookup"><span data-stu-id="729a5-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can send and receive messages between BizTalk Server and Azure Event Hubs.</span></span> 

<span data-ttu-id="729a5-106">Azure Event Hubs は現在は拡張性の高いデータ ストリーミング プラットフォーム、および受信、および数百万の 1 秒あたりのイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="729a5-106">Azure Event Hubs is a highly scalable data streaming platform, and can receive and process millions of events per second.</span></span> <span data-ttu-id="729a5-107">[Event Hubs とは何ですか。](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="729a5-107">[What is Event Hubs?](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) provides more details.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="729a5-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="729a5-108">Prerequisites</span></span>

* <span data-ttu-id="729a5-109">作成、 [Azure event hubs 名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span><span class="sxs-lookup"><span data-stu-id="729a5-109">Create an [Azure event hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)</span></span>
* <span data-ttu-id="729a5-110">作成、[コンテナーで Azure blob storage アカウント](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span><span class="sxs-lookup"><span data-stu-id="729a5-110">Create an [Azure blob storage account with a container](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)</span></span>
* <span data-ttu-id="729a5-111">インストール[Feature Pack 2](https://aka.ms/bts2016fp2) BizTalk Server で</span><span class="sxs-lookup"><span data-stu-id="729a5-111">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your BizTalk Server</span></span>

<span data-ttu-id="729a5-112">イベント ハブが作成し、イベントの送受信に必要な接続文字列があります。</span><span class="sxs-lookup"><span data-stu-id="729a5-112">Your event hub is now created, and you have the connection strings you need to send and receive events.</span></span>

## <a name="send-messages-to-event-hubs"></a><span data-ttu-id="729a5-113">Event Hubs にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-113">Send messages to Event Hubs</span></span>

1.  <span data-ttu-id="729a5-114">右クリックし、BizTalk Server 管理コンソールで**送信ポート**を選択します**新規**、選択と**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-114">In the BizTalk Server Administration console, right-click **Send Ports**, select **New**, and select **Static One-way send port**.</span></span>

    <span data-ttu-id="729a5-115">[送信ポートを作成](../core/how-to-create-a-send-port2.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="729a5-115">[Create a Send Port](../core/how-to-create-a-send-port2.md) provides some guidance.</span></span>

2. <span data-ttu-id="729a5-116">入力、**名前**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-116">Enter a **Name**.</span></span> <span data-ttu-id="729a5-117">**トランスポート**、設定、**型**に**EventHub**を選択し、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-117">In **Transport**, set the **Type** to **EventHub**, and select **Configure**.</span></span> 

3. <span data-ttu-id="729a5-118">構成、 **Azure アカウント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-118">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="729a5-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="729a5-119">Use this</span></span>|<span data-ttu-id="729a5-120">目的</span><span class="sxs-lookup"><span data-stu-id="729a5-120">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="729a5-121">**サインイン**</span><span class="sxs-lookup"><span data-stu-id="729a5-121">**Sign-in**</span></span> | <span data-ttu-id="729a5-122">Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="729a5-122">Sign into your Azure account</span></span> |
    | <span data-ttu-id="729a5-123">**サブスクリプション**</span><span class="sxs-lookup"><span data-stu-id="729a5-123">**Subscription**</span></span> | <span data-ttu-id="729a5-124">Event Hubs 名前空間を持つサブスクリプションを選択します</span><span class="sxs-lookup"><span data-stu-id="729a5-124">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="729a5-125">**リソース グループ**</span><span class="sxs-lookup"><span data-stu-id="729a5-125">**Resource Group**</span></span> | <span data-ttu-id="729a5-126">Event Hubs 名前空間を持つリソース グループを選択します</span><span class="sxs-lookup"><span data-stu-id="729a5-126">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="729a5-127">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-127">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="729a5-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="729a5-128">Use this</span></span>|<span data-ttu-id="729a5-129">目的</span><span class="sxs-lookup"><span data-stu-id="729a5-129">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="729a5-130">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="729a5-130">**Namespace**</span></span> | <span data-ttu-id="729a5-131">Sb ようなものである、Event Hubs 名前空間を選択://*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="729a5-131">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="729a5-132">**名前**</span><span class="sxs-lookup"><span data-stu-id="729a5-132">**Name**</span></span> | <span data-ttu-id="729a5-133">(これは、Event Hubs 名前空間内で作成された)、イベント ハブの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="729a5-133">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="729a5-134">**既定のパーティション キー**</span><span class="sxs-lookup"><span data-stu-id="729a5-134">**Default Partition Key**</span></span> | <span data-ttu-id="729a5-135">任意。</span><span class="sxs-lookup"><span data-stu-id="729a5-135">Optional.</span></span> <span data-ttu-id="729a5-136">[Event Hubs のプログラミング ガイド](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)このキーの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="729a5-136">[Event Hubs programming guide](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide) provides more details on this key.</span></span> |
    | <span data-ttu-id="729a5-137">**[認証]**</span><span class="sxs-lookup"><span data-stu-id="729a5-137">**Authentication**</span></span> | <span data-ttu-id="729a5-138">**Namespace Access Signature**既定であり、Event Hubs 名前空間を作成するときに作成される RootManageSharedAccessKey は自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="729a5-138">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="729a5-139">**エンティティ アクセス シグネチャ**SAS ポリシーがイベント ハブのレベル (いない、Event Hubs 名前空間レベル) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="729a5-139">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="729a5-140">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="729a5-140">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="729a5-141">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="729a5-141">When finished, your properties look similar to the following:</span></span> 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-properties.png)


5. <span data-ttu-id="729a5-143">任意。</span><span class="sxs-lookup"><span data-stu-id="729a5-143">Optional.</span></span> <span data-ttu-id="729a5-144">構成、**メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-144">Configure the **Message** properties.</span></span> <span data-ttu-id="729a5-145">**ユーザー定義メッセージのプロパティの Namespace**値は、Event Hubs のメッセージ プロパティにマップする BizTalk メッセージのスキーマを表します。</span><span class="sxs-lookup"><span data-stu-id="729a5-145">The **Namespace for User Defined Message Properties** value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span>

6. <span data-ttu-id="729a5-146">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="729a5-146">Select **Ok** to save your changes.</span></span> 


### <a name="test-your-send-port"></a><span data-ttu-id="729a5-147">送信ポートをテストします。</span><span class="sxs-lookup"><span data-stu-id="729a5-147">Test your send port</span></span>

<span data-ttu-id="729a5-148">単純なを使用するファイルの受信ポートと、Azure Event Hub にメッセージを送信する場所。</span><span class="sxs-lookup"><span data-stu-id="729a5-148">You can use a simple File receive port and location to send messages to your Azure Event Hub.</span></span> 

1. <span data-ttu-id="729a5-149">ファイル アダプターを使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="729a5-149">Create a receive port using the File adapter.</span></span> <span data-ttu-id="729a5-150">内で、受信場所、設定、**受信フォルダー**に**C:\Temp\In\\**、ファイル マスクを設定 **\*.xml**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-150">Within your receive location,  set the **Receive folder** to **C:\Temp\In\\**, and set the file mask to **\*.xml**.</span></span>
2. <span data-ttu-id="729a5-151">イベント ハブに送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == FileReceivePort`します。</span><span class="sxs-lookup"><span data-stu-id="729a5-151">In your Event Hub send port properties, set the **Filters** to `BTS.ReceivePortName == FileReceivePort`.</span></span>
3. <span data-ttu-id="729a5-152">テキスト エディターに貼り付け、ファイルに保存します**EventHubMessage.xml**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-152">Paste the following into a text editor, and save the file as **EventHubMessage.xml**.</span></span> <span data-ttu-id="729a5-153">これは、サンプル メッセージです。</span><span class="sxs-lookup"><span data-stu-id="729a5-153">This is your sample message.</span></span> 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. <span data-ttu-id="729a5-154">開始ファイルは、場所とイベント ハブの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-154">Start the File receive location and the Event Hub send port.</span></span>
5. <span data-ttu-id="729a5-155">コピー **EventHubMessage.xml**受信フォルダーにサンプル メッセージ (C:\Temp\In\)します。</span><span class="sxs-lookup"><span data-stu-id="729a5-155">Copy **EventHubMessage.xml** sample message into the receive folder (C:\Temp\In\).</span></span> <span data-ttu-id="729a5-156">送信ポートは、XML ファイルをイベント ハブに送信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-156">The send port sends the XML file to the event hub.</span></span>

## <a name="receive-messages-from-event-hubs"></a><span data-ttu-id="729a5-157">Event Hubs からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-157">Receive messages from Event Hubs</span></span>

1. <span data-ttu-id="729a5-158">右クリックし、BizTalk Server 管理コンソールで**受信ポート**を選択します**新規**、選択と**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-158">In the BizTalk Server Administration console, right-click **Receive Ports**, select **New**, and select **One-Way receive port**.</span></span> 

    <span data-ttu-id="729a5-159">[受信ポートを作成](../core/how-to-create-a-receive-port.md)いくつかのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="729a5-159">[Create a receive port](../core/how-to-create-a-receive-port.md) provides some guidance.</span></span>

2. <span data-ttu-id="729a5-160">名前を入力し、選択**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-160">Enter a name, and select **Receive Locations**.</span></span> 

3. <span data-ttu-id="729a5-161">選択**新規**、および**名前**受信場所。</span><span class="sxs-lookup"><span data-stu-id="729a5-161">Select **New**, and **Name** the receive location.</span></span> <span data-ttu-id="729a5-162">**トランスポート**を選択します**EventHub**から、**型**クリックしてドロップダウン リスト、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="729a5-162">In **Transport**, select **EventHub** from the **Type** drop-down list, and then select **Configure**.</span></span> 

4. <span data-ttu-id="729a5-163">構成、 **Azure アカウント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-163">Configure the **Azure Account** properties:</span></span> 

    |<span data-ttu-id="729a5-164">プロパティ</span><span class="sxs-lookup"><span data-stu-id="729a5-164">Use this</span></span>|<span data-ttu-id="729a5-165">目的</span><span class="sxs-lookup"><span data-stu-id="729a5-165">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="729a5-166">**サインイン**</span><span class="sxs-lookup"><span data-stu-id="729a5-166">**Sign-in**</span></span> | <span data-ttu-id="729a5-167">Azure アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="729a5-167">Sign into your Azure account</span></span> |
    | <span data-ttu-id="729a5-168">**サブスクリプション**</span><span class="sxs-lookup"><span data-stu-id="729a5-168">**Subscription**</span></span> | <span data-ttu-id="729a5-169">Event Hubs 名前空間を持つサブスクリプションを選択します</span><span class="sxs-lookup"><span data-stu-id="729a5-169">Select the subscription that has your EventHubs namespace</span></span> |
    | <span data-ttu-id="729a5-170">**リソース グループ**</span><span class="sxs-lookup"><span data-stu-id="729a5-170">**Resource Group**</span></span> | <span data-ttu-id="729a5-171">Event Hubs 名前空間を持つリソース グループを選択します</span><span class="sxs-lookup"><span data-stu-id="729a5-171">Select your resource group that has your EventHubs namespace</span></span> |

4. <span data-ttu-id="729a5-172">構成、**エンドポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-172">Configure the **Endpoint** properties:</span></span> 

    |<span data-ttu-id="729a5-173">プロパティ</span><span class="sxs-lookup"><span data-stu-id="729a5-173">Use this</span></span>|<span data-ttu-id="729a5-174">目的</span><span class="sxs-lookup"><span data-stu-id="729a5-174">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="729a5-175">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="729a5-175">**Namespace**</span></span> | <span data-ttu-id="729a5-176">Sb ようなものである、Event Hubs 名前空間を選択://*youreventhubnamespace*.servicebus.windows.net/</span><span class="sxs-lookup"><span data-stu-id="729a5-176">Select your Event Hubs namespace, which is something like sb://*youreventhubnamespace*.servicebus.windows.net/</span></span> |
    | <span data-ttu-id="729a5-177">**名前**</span><span class="sxs-lookup"><span data-stu-id="729a5-177">**Name**</span></span> | <span data-ttu-id="729a5-178">(これは、Event Hubs 名前空間内で作成された)、イベント ハブの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="729a5-178">Select the name of your Event Hub (which was created within your Event Hubs namespace)</span></span> |
    | <span data-ttu-id="729a5-179">**コンシューマー グループ**</span><span class="sxs-lookup"><span data-stu-id="729a5-179">**Consumer Group**</span></span> | <span data-ttu-id="729a5-180">イベント ハブ内でコンシューマー グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="729a5-180">Select the Consumer group within your Event Hub.</span></span> <span data-ttu-id="729a5-181">既定のグループが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="729a5-181">A default group is created automatically.</span></span> <br/><br/><span data-ttu-id="729a5-182">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="729a5-182">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) provides more details.</span></span> |
    | <span data-ttu-id="729a5-183">**[認証]**</span><span class="sxs-lookup"><span data-stu-id="729a5-183">**Authentication**</span></span> | <span data-ttu-id="729a5-184">**Namespace Access Signature**既定であり、Event Hubs 名前空間を作成するときに作成される RootManageSharedAccessKey は自動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="729a5-184">**Namespace Access Signature** is the default, and automatically uses the RootManageSharedAccessKey that's created when you create an Event Hubs namespace.</span></span><br/><br/><span data-ttu-id="729a5-185">**エンティティ アクセス シグネチャ**SAS ポリシーがイベント ハブのレベル (いない、Event Hubs 名前空間レベル) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="729a5-185">**Entity Access Signature** is the SAS policy you can create at the Event Hub-level (not the Event Hubs namespace-level).</span></span> <br/><br/><span data-ttu-id="729a5-186">[Event Hubs の機能概要](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="729a5-186">[Event Hubs features overview](https://docs.microsoft.com/azure/event-hubs/event-hubs-features) explains more.</span></span> |

    <span data-ttu-id="729a5-187">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="729a5-187">When finished, your properties look similar to the following:</span></span> 

    ![エンドポイントのプロパティ](../core/media/event-hub-endpoint-receive-properties.png)

5. <span data-ttu-id="729a5-189">構成、**チェックポイント**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-189">Configure the **Checkpoint** properties.</span></span> <span data-ttu-id="729a5-190">このアダプターは、確実に、チェックポイントを使用してイベントを読み取るし、再起動から再開する、Azure blob ストレージ アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="729a5-190">This adapter uses an Azure blob storage account to reliably read events using a checkpoint, and resume from a restart.</span></span> 

    <span data-ttu-id="729a5-191">**ストレージの認証** </span><span class="sxs-lookup"><span data-stu-id="729a5-191">**Storage Authentication** </span></span>  
    <span data-ttu-id="729a5-192">認証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="729a5-192">Select an authentication method.</span></span> <span data-ttu-id="729a5-193">通常、Shared Access Signature を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="729a5-193">Typically, it's recommended to use a Shared Access Signature.</span></span> <span data-ttu-id="729a5-194">これは、シナリオに適切な判断に役立つ優れたリソースを次のリンクには。</span><span class="sxs-lookup"><span data-stu-id="729a5-194">The following links are good resources to help you decide which is right for your scenario:</span></span><br/><br/>[<span data-ttu-id="729a5-195">Azure ストレージ アカウントについて</span><span class="sxs-lookup"><span data-stu-id="729a5-195">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[<span data-ttu-id="729a5-196">Shared access signature (SAS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="729a5-196">Using shared access signatures (SAS)</span></span>](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    <span data-ttu-id="729a5-197">完了したらのプロパティは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="729a5-197">When finished, your properties look similar to the following:</span></span> 

    ![チェックポイントのプロパティ](../core/media/event-hub-receive-checkpoint.png)

6. <span data-ttu-id="729a5-199">構成、**メッセージ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="729a5-199">Configure the **Message** properties:</span></span> 

    |<span data-ttu-id="729a5-200">プロパティ</span><span class="sxs-lookup"><span data-stu-id="729a5-200">Use this</span></span>|<span data-ttu-id="729a5-201">目的</span><span class="sxs-lookup"><span data-stu-id="729a5-201">To do this</span></span>|  
    |---|---|  
    | <span data-ttu-id="729a5-202">**Namespace のユーザー定義メッセージのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="729a5-202">**Namespace for User Defined Message Properties**</span></span> | <span data-ttu-id="729a5-203">`http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` 既定のスキーマが別のスキーマを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="729a5-203">`http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User` is the default schema, but you can enter another schema.</span></span> <span data-ttu-id="729a5-204">この値は、Event Hubs のメッセージ プロパティにマップする BizTalk メッセージのスキーマを表します。</span><span class="sxs-lookup"><span data-stu-id="729a5-204">This value represents a BizTalk message schema mapped to Event Hubs message properties.</span></span> |
    | <span data-ttu-id="729a5-205">**ユーザー定義プロパティを昇格させる**</span><span class="sxs-lookup"><span data-stu-id="729a5-205">**Promote user defined properties**</span></span> | <span data-ttu-id="729a5-206">任意。</span><span class="sxs-lookup"><span data-stu-id="729a5-206">Optional.</span></span> <span data-ttu-id="729a5-207">使用する場合は、これらのプロパティを昇格できます。</span><span class="sxs-lookup"><span data-stu-id="729a5-207">You can promote these properties if you prefer.</span></span> <br/><br/><span data-ttu-id="729a5-208">**注**</span><span class="sxs-lookup"><span data-stu-id="729a5-208">**NOTE**</span></span><br/><span data-ttu-id="729a5-209">プロパティを昇格させる必要があるが展開 porperty スキーマを持っている必要があります*する前に*イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-209">The properties that need to be promoted should have a porperty schema deployed *before* receiving events.</span></span>|

7. <span data-ttu-id="729a5-210">選択**Ok**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="729a5-210">Select **Ok** to save your changes.</span></span> 

### <a name="test-your-receive-settings"></a><span data-ttu-id="729a5-211">テストの設定を受け取る</span><span class="sxs-lookup"><span data-stu-id="729a5-211">Test your receive settings</span></span>

<span data-ttu-id="729a5-212">単純な File 送信ポートを使用すると、Azure イベント ハブからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-212">You can use a simple File send port to receive messages from your Azure Event Hub.</span></span> 

1. <span data-ttu-id="729a5-213">ファイル アダプターを使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="729a5-213">Create a send port using the File adapter.</span></span> <span data-ttu-id="729a5-214">送信ポートのプロパティ内で次のように設定します、**先フォルダー**に**C:\Temp\Out\\**、設定、および**ファイル名**に **%MessageID%.xml。**.</span><span class="sxs-lookup"><span data-stu-id="729a5-214">Within your send port properties, set the **Destination folder** to **C:\Temp\Out\\**, and set the and **File name** to **%MessageID%.xml**.</span></span>
2. <span data-ttu-id="729a5-215">ファイルの送信ポートのプロパティは、設定、**フィルター**に`BTS.ReceivePortName == EHReceivePort`します。</span><span class="sxs-lookup"><span data-stu-id="729a5-215">In your File send port properties, set the **Filters** to  `BTS.ReceivePortName == EHReceivePort`.</span></span>
3. <span data-ttu-id="729a5-216">開始イベント ハブでは、場所とファイルの送信ポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="729a5-216">Start the Event Hub receive location and the File send port.</span></span>
4. <span data-ttu-id="729a5-217">保存先フォルダー (c:\temp\out) にメッセージを探します。</span><span class="sxs-lookup"><span data-stu-id="729a5-217">Look for messages in the destination folder (c:\temp\out).</span></span>

## <a name="do-more"></a><span data-ttu-id="729a5-218">さらに活用します。</span><span class="sxs-lookup"><span data-stu-id="729a5-218">Do more</span></span>
<span data-ttu-id="729a5-219">Event Hubs は、Azure Data Lake、HD Insight などの他の Azure サービスの多くに「フロント ドア」と見なされます。</span><span class="sxs-lookup"><span data-stu-id="729a5-219">Event Hubs is considered the "front door" to a lot of other Azure services, including Azure Data Lake, HD Insight, and more.</span></span> <span data-ttu-id="729a5-220">大量のメッセージを処理し、高速に処理する設計います。</span><span class="sxs-lookup"><span data-stu-id="729a5-220">It's designed to process a lot of messages, and process them fast.</span></span> <span data-ttu-id="729a5-221">Event Hubs とその機能についての詳細。</span><span class="sxs-lookup"><span data-stu-id="729a5-221">Read more about Event Hubs, and its features:</span></span> 

[<span data-ttu-id="729a5-222">Event Hubs の機能の概要</span><span class="sxs-lookup"><span data-stu-id="729a5-222">Event Hubs features overview</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[<span data-ttu-id="729a5-223">Event Hubs とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="729a5-223">What is Event Hubs?</span></span>](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
