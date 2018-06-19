---
title: '手順 3: BizTalk Server に Salesforce の営業案件通知を受け取る |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be9de6e3-6bd9-4275-b2fb-0a756c51aabf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76ab28e8e70c0b8a222f6772a763a93252f2c413
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279410"
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a><span data-ttu-id="27d28-102">手順 3: BizTalk Server に Salesforce の営業案件通知を受信</span><span class="sxs-lookup"><span data-stu-id="27d28-102">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>
<span data-ttu-id="27d28-103">このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="27d28-103">In this step, we start creating a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="27d28-104">メッセージを処理するオーケストレーションの作成を開始する前に、まず、Salesforce から受信する営業案件通知メッセージのメッセージ スキーマを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="27d28-104">We should first include the message schema for the opportunities notification message that we’ll get from Salesforce and then start creating an orchestration to process the message.</span></span>  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a><span data-ttu-id="27d28-105">Salesforce の営業案件通知スキーマを含めるには</span><span class="sxs-lookup"><span data-stu-id="27d28-105">To include the Salesforce opportunities notification schema</span></span>  
  
1.  <span data-ttu-id="27d28-106">Salesforce.com ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="27d28-106">Login to the Salesforce.com portal.</span></span> <span data-ttu-id="27d28-107">Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-107">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="27d28-108">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-108">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
3.  <span data-ttu-id="27d28-109">**すべてのワークフロー ルール** ページで、をクリックして、**クローズされた営業案件**先ほど作成したワークフローです。</span><span class="sxs-lookup"><span data-stu-id="27d28-109">In the **All Workflow Rules** page, click the **Closed Opportunity** workflow that you created earlier.</span></span>  
  
4.  <span data-ttu-id="27d28-110">**クローズされた営業案件** ワーフクロー ルール ページをクリックして**NewOp1**送信メッセージ ワークフロー アクション。</span><span class="sxs-lookup"><span data-stu-id="27d28-110">In the **Closed Opportunity** workflow rule page, click **NewOp1** outbound message workflow action.</span></span>  
  
5.  <span data-ttu-id="27d28-111">**NewOp1**送信メッセージ ワークフロー アクション ページで、リンクを右クリックして**クリックして WSDL**、 をクリックして**として保存対象**、し保存する場所を指定WSDL です。</span><span class="sxs-lookup"><span data-stu-id="27d28-111">In the **NewOp1** outbound message workflow action page, right-click the link **Click for WSDL**, click **Save target as**, and then specify the location where you want to save the WSDL.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27d28-112">ファイルの拡張子は、.wsdl で保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27d28-112">You must save the file with a .wsdl extension.</span></span>  
  
6.  <span data-ttu-id="27d28-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を作成します。</span><span class="sxs-lookup"><span data-stu-id="27d28-113">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="27d28-114">このチュートリアルでは、名前としてプロジェクトをお知らせ`BtsSalesforceIntegration`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-114">For this tutorial, let us name the project as `BtsSalesforceIntegration`.</span></span>  
  
7.  <span data-ttu-id="27d28-115">右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトをポイントし、**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-115">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project in the Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
8.  <span data-ttu-id="27d28-116">**生成した項目の追加**ダイアログ ボックスで、をクリックして**Consume WCF サービス**、クリックして**追加**を起動する、 **BizTalk WCF サービス使用**ウィザード。</span><span class="sxs-lookup"><span data-stu-id="27d28-116">In the **Add Generated Items** dialog box, click **Consume WCF Service**, and then click **Add** to launch the **BizTalk WCF Service Consuming** wizard.</span></span> <span data-ttu-id="27d28-117">[ようこそ] ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-117">On the welcome page, click **Next**.</span></span>  
  
9. <span data-ttu-id="27d28-118">**メタデータ ソース**] ページで、[、**メタデータ ファイル (WSDL と XSD)** オプションをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-118">On the **Metadata Source** page, select the **Metadata Files (WSDL and XSD)** option, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="27d28-119">**メタデータ ファイル**] ページで [**追加**、Salesforce ポータルからダウンロードした WSDL ファイルを保存した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="27d28-119">On the **Metadata Files** page, click **Add**, and then navigate to the location where you saved the WSDL file downloaded from the Salesforce portal.</span></span> <span data-ttu-id="27d28-120">WSDL ファイルを選択し、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-120">Select the WSDL file and then click **Next**.</span></span>  
  
11. <span data-ttu-id="27d28-121">次のページで設定と名前空間`NotificationService` をクリックし、**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-121">In the next page, set the namespace as `NotificationService` and then click **Import**.</span></span> <span data-ttu-id="27d28-122">ウィザードでスキーマ ファイルとオーケストレーションが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="27d28-122">The wizard adds the schema files and an orchestration to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="27d28-123">Salesforce から営業案件通知を受信するため、メッセージ スキーマは**NotificationService_soap_sforce_com_2005_09_outbound.xsd**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-123">The message schema for receiving opportunity notifications from Salesforce is **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span>  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a><span data-ttu-id="27d28-124">通知メッセージを受信するためのオーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="27d28-124">To create an orchestration to receive the notification message</span></span>  
  
1.  <span data-ttu-id="27d28-125">完了した後、 **BizTalk WCF サービス使用**ウィザードは、オーケストレーション (**NotificationService.odx**、この例では) に追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="27d28-125">After you complete the **BizTalk WCF Service Consuming** wizard, an orchestration (**NotificationService.odx**, in this example) is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="27d28-126">オーケストレーション ファイルを開いて、オーケストレーション ビューで 2 つの新しいメッセージ変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-126">Open the orchestration file and in the Orchestration view, add two new message variables.</span></span> <span data-ttu-id="27d28-127">名前を付けます`NotificationMessage`と`NotificationAck`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-127">Name them `NotificationMessage` and `NotificationAck`.</span></span> <span data-ttu-id="27d28-128">メッセージ変数のメッセージ種類を、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="27d28-128">Set the message type for these message variables as follows:</span></span>  
  
    1.  <span data-ttu-id="27d28-129">設定**NotificationMessage**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-129">Set **NotificationMessage** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*.</span></span> <span data-ttu-id="27d28-130">このメッセージ変数は、Salesforce から受信する営業案件通知メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="27d28-130">This message variable represents the opportunity notification message received from Salesforce.</span></span>  
  
    2.  <span data-ttu-id="27d28-131">設定**NotificationAck**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-131">Set **NotificationAck** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*.</span></span> <span data-ttu-id="27d28-132">このメッセージ変数は、Salesforce に返信される営業案件通知の確認メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="27d28-132">This message variable represents the opportunity notification acknowledgement message sent back to Salesforce.</span></span>  
  
3.  <span data-ttu-id="27d28-133">オーケストレーションへ受信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-133">Add a receive shape to the orchestration.</span></span> <span data-ttu-id="27d28-134">図形に以下のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="27d28-134">Set the following properties on the shape:</span></span>  
  
    1.  <span data-ttu-id="27d28-135">設定**アクティブ**に**True**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-135">Set **Activate** to **True**.</span></span>  
  
    2.  <span data-ttu-id="27d28-136">設定**名前**に*ReceiveNotificationMessage*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-136">Set **Name** to *ReceiveNotificationMessage*.</span></span>  
  
    3.  <span data-ttu-id="27d28-137">設定**メッセージ**に*NotificationMessage*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-137">Set **Message** to *NotificationMessage*.</span></span>  
  
4.  <span data-ttu-id="27d28-138">受信図形の後にメッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-138">Add a Construct Message shape after the Receive shape.</span></span> <span data-ttu-id="27d28-139">図形の名前はメッセージとして`ConstructNotificationResponse`設定と、**構築メッセージ**プロパティを`NotificationAck`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-139">Name the message shape as `ConstructNotificationResponse` and set the **Messages Constructed** property to `NotificationAck`.</span></span> <span data-ttu-id="27d28-140">構築メッセージの一部として、マップを作成して Salesforce に返信する通知確認メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="27d28-140">As part of the construct message, we’ll also create a map to generate a notification acknowledgement message to be sent back to Salesforce.</span></span>  
  
    1.  <span data-ttu-id="27d28-141">[メッセージの構築] 図形に [変換] 図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-141">Within the Construct Message shape, add a Transform shape.</span></span> <span data-ttu-id="27d28-142">変換図形をダブルクリックし、変換の構成 ダイアログ ボックスで選択、**新しいマップ**オプション。</span><span class="sxs-lookup"><span data-stu-id="27d28-142">Double-click the Transform shape and in the Transform Configuration dialog box, select the **New Map** option.</span></span>  
  
    2.  <span data-ttu-id="27d28-143">マップ名として指定`BtsSalesforceIntegration.MapNotificationResponse`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-143">Specify the map name as `BtsSalesforceIntegration.MapNotificationResponse`.</span></span>  
  
    3.  <span data-ttu-id="27d28-144">ソースとして設定**NotificationMessage**と変換先として**NotificationAck**です。</span><span class="sxs-lookup"><span data-stu-id="27d28-144">Set Source as **NotificationMessage** and Destination as **NotificationAck**.</span></span>  
  
    4.  <span data-ttu-id="27d28-145">チェック ボックスを確認してください **[ok] をクリックしたら BizTalk マッパーを起動**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="27d28-145">Make sure the check box **When I click OK, launch the BizTalk Mapper** is selected.</span></span>  
  
    5.  <span data-ttu-id="27d28-146">**MapNotificationResponse.btm**Salesforce に送信する通知応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="27d28-146">In **MapNotificationResponse.btm**, we’ll create a notification response to be sent back to Salesforce.</span></span> <span data-ttu-id="27d28-147">Salesforce が通知を送信するたびに、確認が返信されることが期待されます。</span><span class="sxs-lookup"><span data-stu-id="27d28-147">Every time Salesforce sends a notification, it expects an acknowledgement in return.</span></span> <span data-ttu-id="27d28-148">通知応答メッセージのスキーマことを示しています、 **Ack**応答内の要素は Boolean 型です。</span><span class="sxs-lookup"><span data-stu-id="27d28-148">The schema of the notification response message shows that the **Ack** element in the response is of type Boolean.</span></span> <span data-ttu-id="27d28-149">そのため、マップでは、削除する必要あります、**値のマッピング**functoid とセット、2 つの入力値 (状態と結果) に`true`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-149">So, in the map, you must drop a **Value Mapping** functoid and set its two input values (Condition and Result) to `true`.</span></span> <span data-ttu-id="27d28-150">をクリックして**OK** functoid を保存します。</span><span class="sxs-lookup"><span data-stu-id="27d28-150">Click **OK** to save the functoid.</span></span>  
  
    6.  <span data-ttu-id="27d28-151">接続、**値のマッピング**functoid を**Ack**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="27d28-151">Connect the **Value Mapping** functoid to the **Ack** element in the destination schema.</span></span>  
  
5.  <span data-ttu-id="27d28-152">オーケストレーションで、メッセージの構築図形の後に、Salesforce に確認を返信する際に使用する送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-152">In the orchestration, after the Construct Message shape, add a Send shape that will be used to send the acknowledgement back to Salesforce.</span></span>  
  
    -   <span data-ttu-id="27d28-153">設定**名前**に*SendNotificationAck*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-153">Set **Name** to *SendNotificationAck*.</span></span>  
  
    -   <span data-ttu-id="27d28-154">設定**メッセージ**に*NotificationAck*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-154">Set **Message** to *NotificationAck*.</span></span>  
  
6.  <span data-ttu-id="27d28-155">オーケストレーションで、Salesforce の通知メッセージを受信し、確認を返信するポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="27d28-155">In the orchestration, add a port to receive Salesforce notification message and send the acknowledgement in response.</span></span> <span data-ttu-id="27d28-156">ポート構成ウィザードで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="27d28-156">In the Port Configuration wizard, select the following options:</span></span>  
  
    -   <span data-ttu-id="27d28-157">ポート名を指定`SalesforceNotificationPort`です。</span><span class="sxs-lookup"><span data-stu-id="27d28-157">Specify the port name as `SalesforceNotificationPort`.</span></span>  
  
    -   <span data-ttu-id="27d28-158">新しいポート種類を作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="27d28-158">Select the option to create a new port type.</span></span>  
  
    -   <span data-ttu-id="27d28-159">設定**通信パターン**に*要求-応答*です。</span><span class="sxs-lookup"><span data-stu-id="27d28-159">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
    -   <span data-ttu-id="27d28-160">設定**ポートの通信方向**に*要求の受信と応答の送信を行います*設定と**ポートのバインド**に*以降を指定*.</span><span class="sxs-lookup"><span data-stu-id="27d28-160">Set **Port direction of communication** to *I’ll be receiving a request and sending a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="27d28-161">接続、**要求**受信図形にポートの操作 (*ReceiveNotificationMessage*) および**応答**送信図形にポートの操作 (*SendNotificationAck*)。</span><span class="sxs-lookup"><span data-stu-id="27d28-161">Connect the **Request** operation of port to the Receive shape (*ReceiveNotificationMessage*) and the **Response** operation of the port to the Send shape (*SendNotificationAck*).</span></span> <span data-ttu-id="27d28-162">次のスクリーンショットは、Salesforce からの営業案件通知を受信し、確認を返信するオーケストレーションの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="27d28-162">The following screenshot depicts the part of the orchestration that receives an opportunity notification from Salesforce and sends an acknowledgement back:</span></span>  
  
     <span data-ttu-id="27d28-163">![営業案件通知を受信し、応答を送信](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span><span class="sxs-lookup"><span data-stu-id="27d28-163">![Receive opportunity notification and send response](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span></span>  
  
 <span data-ttu-id="27d28-164">これで、Salesforce から営業案件通知を受信して、確認を返信するソリューションのセットアップが完了しました。</span><span class="sxs-lookup"><span data-stu-id="27d28-164">By now, we have set up the solution where an opportunity notification is received from Salesforce and an acknowledgement is sent back.</span></span> <span data-ttu-id="27d28-165">次のトピックでは、このソリューションに基づいて、営業案件通知の処理を開始し、その営業案件に関する詳細情報を入手する作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="27d28-165">In the subsequent topics, we’ll build on this solution to start processing the opportunity notification to get more details about the kind of sales opportunity available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d28-166">参照</span><span class="sxs-lookup"><span data-stu-id="27d28-166">See Also</span></span>  
 [<span data-ttu-id="27d28-167">手順 3: Visual Studio での BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="27d28-167">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)