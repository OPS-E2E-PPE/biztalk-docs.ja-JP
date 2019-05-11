---
title: 手順 3 a:BizTalk Server に Salesforce の営業案件通知を受け取る |Microsoft Docs
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
ms.openlocfilehash: 0c323d7f7975eb20f78aba0c6259d9c998779b1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392580"
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a><span data-ttu-id="54416-102">手順 3 a:BizTalk Server に Salesforce の営業案件通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="54416-102">Step 3a: Receive Salesforce Opportunity Notification into BizTalk Server</span></span>
<span data-ttu-id="54416-103">作成を開始この手順で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="54416-103">In this step, we start creating a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="54416-104">まずことは、Salesforce から取得し、メッセージを処理するオーケストレーションの作成を開始しましたが、営業案件通知メッセージのメッセージ スキーマに含めるべきです。</span><span class="sxs-lookup"><span data-stu-id="54416-104">We should first include the message schema for the opportunities notification message that we’ll get from Salesforce and then start creating an orchestration to process the message.</span></span>  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a><span data-ttu-id="54416-105">Salesforce の営業案件通知スキーマを含める</span><span class="sxs-lookup"><span data-stu-id="54416-105">To include the Salesforce opportunities notification schema</span></span>  
  
1. <span data-ttu-id="54416-106">Salesforce.com ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="54416-106">Login to the Salesforce.com portal.</span></span> <span data-ttu-id="54416-107">Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。</span><span class="sxs-lookup"><span data-stu-id="54416-107">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="54416-108">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。</span><span class="sxs-lookup"><span data-stu-id="54416-108">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
3. <span data-ttu-id="54416-109">**すべてのワークフロー ルール** ページで、をクリックして、**クローズされた営業案件**先ほど作成したワークフロー。</span><span class="sxs-lookup"><span data-stu-id="54416-109">In the **All Workflow Rules** page, click the **Closed Opportunity** workflow that you created earlier.</span></span>  
  
4. <span data-ttu-id="54416-110">**クローズされた営業案件**ワーフクロー ルール ページで、をクリックして**NewOp1**送信メッセージ ワークフロー アクション。</span><span class="sxs-lookup"><span data-stu-id="54416-110">In the **Closed Opportunity** workflow rule page, click **NewOp1** outbound message workflow action.</span></span>  
  
5. <span data-ttu-id="54416-111">**NewOp1**送信メッセージ ワークフロー アクション ページで、リンクを右クリックして**クリックして WSDL**、 をクリックして**として保存ターゲット**、し保存する場所を指定WSDL。</span><span class="sxs-lookup"><span data-stu-id="54416-111">In the **NewOp1** outbound message workflow action page, right-click the link **Click for WSDL**, click **Save target as**, and then specify the location where you want to save the WSDL.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54416-112">.Wsdl の拡張子を持つファイルを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54416-112">You must save the file with a .wsdl extension.</span></span>  
  
6. <span data-ttu-id="54416-113">作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="54416-113">Create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="54416-114">このチュートリアルでは、名前としてプロジェクトをお知らせ`BtsSalesforceIntegration`します。</span><span class="sxs-lookup"><span data-stu-id="54416-114">For this tutorial, let us name the project as `BtsSalesforceIntegration`.</span></span>  
  
7. <span data-ttu-id="54416-115">右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトをポイントして、**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="54416-115">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project in the Solution Explorer, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
8. <span data-ttu-id="54416-116">**生成した項目の追加**ダイアログ ボックスで、をクリックして**Consume WCF サービス**、順にクリックします**追加**を起動する、 **BizTalk WCF サービス使用**ウィザード。</span><span class="sxs-lookup"><span data-stu-id="54416-116">In the **Add Generated Items** dialog box, click **Consume WCF Service**, and then click **Add** to launch the **BizTalk WCF Service Consuming** wizard.</span></span> <span data-ttu-id="54416-117">[ようこそ] ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="54416-117">On the welcome page, click **Next**.</span></span>  
  
9. <span data-ttu-id="54416-118">**メタデータ ソース**] ページで、[、**メタデータ ファイル (WSDL と XSD)** オプションをクリックして**次**。</span><span class="sxs-lookup"><span data-stu-id="54416-118">On the **Metadata Source** page, select the **Metadata Files (WSDL and XSD)** option, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="54416-119">**メタデータ ファイル**] ページで [**追加**、Salesforce ポータルからダウンロードした WSDL ファイルを保存した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="54416-119">On the **Metadata Files** page, click **Add**, and then navigate to the location where you saved the WSDL file downloaded from the Salesforce portal.</span></span> <span data-ttu-id="54416-120">WSDL ファイルを選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="54416-120">Select the WSDL file and then click **Next**.</span></span>  
  
11. <span data-ttu-id="54416-121">次のページで設定と名前空間`NotificationService`し**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="54416-121">In the next page, set the namespace as `NotificationService` and then click **Import**.</span></span> <span data-ttu-id="54416-122">スキーマ ファイルとオーケストレーションが追加されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="54416-122">The wizard adds the schema files and an orchestration to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="54416-123">Salesforce から営業案件通知を受信するためのメッセージ スキーマは**NotificationService_soap_sforce_com_2005_09_outbound.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="54416-123">The message schema for receiving opportunity notifications from Salesforce is **NotificationService_soap_sforce_com_2005_09_outbound.xsd**.</span></span>  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a><span data-ttu-id="54416-124">通知メッセージを受信するオーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="54416-124">To create an orchestration to receive the notification message</span></span>  
  
1. <span data-ttu-id="54416-125">完了した後、 **BizTalk WCF サービス使用**ウィザードは、オーケストレーション (**NotificationService.odx**、この例では) に追加されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="54416-125">After you complete the **BizTalk WCF Service Consuming** wizard, an orchestration (**NotificationService.odx**, in this example) is added to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
2. <span data-ttu-id="54416-126">オーケストレーション ファイルを開き、オーケストレーション ビューで 2 つの新しいメッセージ変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-126">Open the orchestration file and in the Orchestration view, add two new message variables.</span></span> <span data-ttu-id="54416-127">名前を付けます`NotificationMessage`と`NotificationAck`します。</span><span class="sxs-lookup"><span data-stu-id="54416-127">Name them `NotificationMessage` and `NotificationAck`.</span></span> <span data-ttu-id="54416-128">次のように、これらのメッセージ変数のメッセージの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="54416-128">Set the message type for these message variables as follows:</span></span>  
  
   1.  <span data-ttu-id="54416-129">設定**NotificationMessage**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*します。</span><span class="sxs-lookup"><span data-stu-id="54416-129">Set **NotificationMessage** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*.</span></span> <span data-ttu-id="54416-130">このメッセージ変数は、Salesforce から受信した営業案件通知メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="54416-130">This message variable represents the opportunity notification message received from Salesforce.</span></span>  
  
   2.  <span data-ttu-id="54416-131">設定**NotificationAck**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*します。</span><span class="sxs-lookup"><span data-stu-id="54416-131">Set **NotificationAck** to *NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*.</span></span> <span data-ttu-id="54416-132">このメッセージ変数は、Salesforce に返信、営業案件通知の受信確認メッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="54416-132">This message variable represents the opportunity notification acknowledgement message sent back to Salesforce.</span></span>  
  
3. <span data-ttu-id="54416-133">受信図形をオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-133">Add a receive shape to the orchestration.</span></span> <span data-ttu-id="54416-134">図形に次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="54416-134">Set the following properties on the shape:</span></span>  
  
   1.  <span data-ttu-id="54416-135">設定**アクティブ**に**True**します。</span><span class="sxs-lookup"><span data-stu-id="54416-135">Set **Activate** to **True**.</span></span>  
  
   2.  <span data-ttu-id="54416-136">設定**名前**に*ReceiveNotificationMessage*します。</span><span class="sxs-lookup"><span data-stu-id="54416-136">Set **Name** to *ReceiveNotificationMessage*.</span></span>  
  
   3.  <span data-ttu-id="54416-137">設定**メッセージ**に*NotificationMessage*します。</span><span class="sxs-lookup"><span data-stu-id="54416-137">Set **Message** to *NotificationMessage*.</span></span>  
  
4. <span data-ttu-id="54416-138">受信図形の後に、メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-138">Add a Construct Message shape after the Receive shape.</span></span> <span data-ttu-id="54416-139">図形の名前はメッセージとして`ConstructNotificationResponse`設定と、**構築メッセージ**プロパティを`NotificationAck`します。</span><span class="sxs-lookup"><span data-stu-id="54416-139">Name the message shape as `ConstructNotificationResponse` and set the **Messages Constructed** property to `NotificationAck`.</span></span> <span data-ttu-id="54416-140">メッセージの構築の一環として、Salesforce に送信される通知の受信確認メッセージを生成するマップも作成します。</span><span class="sxs-lookup"><span data-stu-id="54416-140">As part of the construct message, we’ll also create a map to generate a notification acknowledgement message to be sent back to Salesforce.</span></span>  
  
   1.  <span data-ttu-id="54416-141">メッセージの構築図形内には、変換図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-141">Within the Construct Message shape, add a Transform shape.</span></span> <span data-ttu-id="54416-142">変換図形をダブルクリックし、変換の構成 ダイアログ ボックスで、選択、**新しいマップ**オプション。</span><span class="sxs-lookup"><span data-stu-id="54416-142">Double-click the Transform shape and in the Transform Configuration dialog box, select the **New Map** option.</span></span>  
  
   2.  <span data-ttu-id="54416-143">マップ名として指定`BtsSalesforceIntegration.MapNotificationResponse`します。</span><span class="sxs-lookup"><span data-stu-id="54416-143">Specify the map name as `BtsSalesforceIntegration.MapNotificationResponse`.</span></span>  
  
   3.  <span data-ttu-id="54416-144">ソースとして設定**NotificationMessage**と変換先として**NotificationAck**します。</span><span class="sxs-lookup"><span data-stu-id="54416-144">Set Source as **NotificationMessage** and Destination as **NotificationAck**.</span></span>  
  
   4.  <span data-ttu-id="54416-145">チェック ボックスを必ず **[ok] をクリックしたら BizTalk マッパーを起動**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="54416-145">Make sure the check box **When I click OK, launch the BizTalk Mapper** is selected.</span></span>  
  
   5.  <span data-ttu-id="54416-146">**MapNotificationResponse.btm**Salesforce に送信する通知応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="54416-146">In **MapNotificationResponse.btm**, we’ll create a notification response to be sent back to Salesforce.</span></span> <span data-ttu-id="54416-147">Salesforce では、通知を送信するたびに確認応答を期待します。</span><span class="sxs-lookup"><span data-stu-id="54416-147">Every time Salesforce sends a notification, it expects an acknowledgement in return.</span></span> <span data-ttu-id="54416-148">通知応答メッセージのスキーマを示していますが、 **Ack**応答内の要素は Boolean 型。</span><span class="sxs-lookup"><span data-stu-id="54416-148">The schema of the notification response message shows that the **Ack** element in the response is of type Boolean.</span></span> <span data-ttu-id="54416-149">そのため、マップでは、削除する必要あります、**値のマッピング**functoid とセットの 2 つの入力値 (状態と結果) を`true`します。</span><span class="sxs-lookup"><span data-stu-id="54416-149">So, in the map, you must drop a **Value Mapping** functoid and set its two input values (Condition and Result) to `true`.</span></span> <span data-ttu-id="54416-150">クリックして**OK** functoid を保存します。</span><span class="sxs-lookup"><span data-stu-id="54416-150">Click **OK** to save the functoid.</span></span>  
  
   6.  <span data-ttu-id="54416-151">接続、**値のマッピング**functoid を**Ack**送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="54416-151">Connect the **Value Mapping** functoid to the **Ack** element in the destination schema.</span></span>  
  
5. <span data-ttu-id="54416-152">メッセージの構築図形の後、オーケストレーションでは、Salesforce に返信を返信するために使用する送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-152">In the orchestration, after the Construct Message shape, add a Send shape that will be used to send the acknowledgement back to Salesforce.</span></span>  
  
   -   <span data-ttu-id="54416-153">設定**名前**に*SendNotificationAck*します。</span><span class="sxs-lookup"><span data-stu-id="54416-153">Set **Name** to *SendNotificationAck*.</span></span>  
  
   -   <span data-ttu-id="54416-154">設定**メッセージ**に*NotificationAck*します。</span><span class="sxs-lookup"><span data-stu-id="54416-154">Set **Message** to *NotificationAck*.</span></span>  
  
6. <span data-ttu-id="54416-155">オーケストレーションでは、Salesforce の通知メッセージを受信し、応答の受信確認の送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="54416-155">In the orchestration, add a port to receive Salesforce notification message and send the acknowledgement in response.</span></span> <span data-ttu-id="54416-156">ポート構成ウィザードでは、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="54416-156">In the Port Configuration wizard, select the following options:</span></span>  
  
   - <span data-ttu-id="54416-157">ポート名を指定`SalesforceNotificationPort`します。</span><span class="sxs-lookup"><span data-stu-id="54416-157">Specify the port name as `SalesforceNotificationPort`.</span></span>  
  
   - <span data-ttu-id="54416-158">新しいポートの種類を作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="54416-158">Select the option to create a new port type.</span></span>  
  
   - <span data-ttu-id="54416-159">設定**通信パターン**に*要求-応答*します。</span><span class="sxs-lookup"><span data-stu-id="54416-159">Set **Communication Pattern** to *Request-Response*.</span></span>  
  
   - <span data-ttu-id="54416-160">設定**ポートの通信方向**に*要求の受信と送信の応答を行います*設定と**ポートのバインド**に*以降指定*.</span><span class="sxs-lookup"><span data-stu-id="54416-160">Set **Port direction of communication** to *I’ll be receiving a request and sending a response* and set **Port binding** to *Specify later*.</span></span>  
  
     <span data-ttu-id="54416-161">接続、**要求**受信図形にポートの操作 (*ReceiveNotificationMessage*) および**応答**送信図形にポートの操作 (*SendNotificationAck*)。</span><span class="sxs-lookup"><span data-stu-id="54416-161">Connect the **Request** operation of port to the Receive shape (*ReceiveNotificationMessage*) and the **Response** operation of the port to the Send shape (*SendNotificationAck*).</span></span> <span data-ttu-id="54416-162">次のスクリーン ショットは、Salesforce から営業案件通知を受信し、戻る受信確認を送信、オーケストレーションの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="54416-162">The following screenshot depicts the part of the orchestration that receives an opportunity notification from Salesforce and sends an acknowledgement back:</span></span>  
  
     <span data-ttu-id="54416-163">![営業案件通知を受信し、応答を送信](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span><span class="sxs-lookup"><span data-stu-id="54416-163">![Receive opportunity notification and send response](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")</span></span>  
  
   <span data-ttu-id="54416-164">ここまでで、Salesforce から営業案件通知を受信して、受信確認が返信される場所のソリューションを設定したします。</span><span class="sxs-lookup"><span data-stu-id="54416-164">By now, we have set up the solution where an opportunity notification is received from Salesforce and an acknowledgement is sent back.</span></span> <span data-ttu-id="54416-165">以降のトピックで使用可能な営業案件の種類の詳細を取得する営業案件通知の処理を開始するには、このソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="54416-165">In the subsequent topics, we’ll build on this solution to start processing the opportunity notification to get more details about the kind of sales opportunity available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54416-166">参照</span><span class="sxs-lookup"><span data-stu-id="54416-166">See Also</span></span>  
 [<span data-ttu-id="54416-167">ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="54416-167">Step 3: Create the BizTalk Server Solution in Visual Studio</span></span>](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)