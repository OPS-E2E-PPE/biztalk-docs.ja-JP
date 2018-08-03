---
title: Message Repair and New Submission のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bbf5114d26f4f3afd56e4a2a020238d4fe44fae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001483"
---
# <a name="message-repair-and-new-submission-troubleshooting"></a><span data-ttu-id="60637-102">Message Repair and New Submission のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="60637-102">Message Repair and New Submission Troubleshooting</span></span>
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a><span data-ttu-id="60637-103">エンベロープ スキーマが展開されていない場合、修復されたメッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="60637-103">A repaired message cannot be submitted if the envelope schema is not deployed</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-104">現象</span><span class="sxs-lookup"><span data-stu-id="60637-104">Symptom</span></span>  
 <span data-ttu-id="60637-105">修復するメッセージを送信しようとしたときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次のメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="60637-105">When you attempt to submit a message that you have repaired, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] posts the following message:</span></span>  
  
 <span data-ttu-id="60637-106">「アダプターは、送信ポートにメッセージの移動を送信できませんでした」<http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed&FolderType=MessagesInbox>"。</span><span class="sxs-lookup"><span data-stu-id="60637-106">"The adapter failed to transmit message going to send port "<http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed&FolderType=MessagesInbox>".</span></span> <span data-ttu-id="60637-107">この送信ポートの指定された再試行間隔後に再送信されます。</span><span class="sxs-lookup"><span data-stu-id="60637-107">It will be retransmitted after the retry interval specified for this Send Port.</span></span> <span data-ttu-id="60637-108">詳細:「80131600」。</span><span class="sxs-lookup"><span data-stu-id="60637-108">Details:"80131600".</span></span> <span data-ttu-id="60637-109">詳細については、ヘルプとサポート センターを参照してください[ http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493)します。</span><span class="sxs-lookup"><span data-stu-id="60637-109">For more information, see Help and Support Center at [http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-110">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-110">Possible Cause</span></span>  
 <span data-ttu-id="60637-111">エンベロープ スキーマは展開されません。</span><span class="sxs-lookup"><span data-stu-id="60637-111">The envelope schema is not deployed.</span></span> <span data-ttu-id="60637-112">これは、MT の true*xxx*メッセージまたはメッセージを解析に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="60637-112">This is true for any MT*xxx* message or any message that has failed parsing.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-113">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-113">Solution</span></span>  
 <span data-ttu-id="60637-114">使用している各メッセージ スキーマに対してエンベロープ スキーマを展開 (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT SRG\<バージョン\>\Category n\MTxxx.xsd)、未解析のエンベロープ スキーマ (\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ パック \SWIFT Messages\ A4SWIFT-SRG\<バージョン\>\ 未解析 Message\EnvelopeUnparsedMessage.xsd)。</span><span class="sxs-lookup"><span data-stu-id="60637-114">Deploy an envelope schema for each message schema that you are using (\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack \SWIFT Messages\ A4SWIFT-SRG\<version\>\Category n\MTxxx.xsd) and for unparsed envelope schema (\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack \SWIFT Messages\ A4SWIFT-SRG\<version\>\ Unparsed Message\EnvelopeUnparsedMessage.xsd).</span></span> <span data-ttu-id="60637-115">詳細については、次を参照してください。 [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。</span><span class="sxs-lookup"><span data-stu-id="60637-115">For more information, see [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a><span data-ttu-id="60637-116">"Unparsed"以外をという名前の MRSR サイト ライブラリから固定未解析メッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="60637-116">You cannot submit a fixed unparsed message from a MRSR site library named other than "Unparsed"</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-117">現象</span><span class="sxs-lookup"><span data-stu-id="60637-117">Symptom</span></span>  
 <span data-ttu-id="60637-118">"Unparsed"名前が付いていません MRSR サイトのドキュメント ライブラリからの修正を未解析メッセージを送信しようとすると、操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="60637-118">When you try to submit an unparsed message that you have fixed from a MRSR site document library that is not named "Unparsed", the operation fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-119">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-119">Possible Cause</span></span>  
 <span data-ttu-id="60637-120">A4SWIFT では、"Unparsed"名前が付いていないライブラリからのメッセージが正常に送信できません。</span><span class="sxs-lookup"><span data-stu-id="60637-120">A4SWIFT cannot successfully submit a message from a library that is not named "Unparsed".</span></span> <span data-ttu-id="60637-121">MRSR (メッセージの修復) 機能をインストールする前に、MRSR サイトで既存の"Unparsed"ドキュメント ライブラリをした場合、A4SWIFT セットアップは未解析メッセージの"Unparsed"のサフィックスを持つ対象のライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="60637-121">If you have an existing "Unparsed" document library in MRSR site before you install the MRSR (message repair) feature, A4SWIFT setup will create a library for unparsed messages entitled "Unparsed" with a suffix.</span></span> <span data-ttu-id="60637-122">A4SWIFT を解析できませんでしたメッセージを受信した場合は、メッセージを作成したライブラリにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="60637-122">When it receives a message that A4SWIFT could not parse, it will route the message to that library that it created.</span></span> <span data-ttu-id="60637-123">ただし、そのライブラリからのメッセージを送信しようとするときに、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="60637-123">However, when you try to submit a message from that library, the operation will fail.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-124">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-124">Solution</span></span>  
 <span data-ttu-id="60637-125">MRSR 機能を削除、未解析のライブラリを削除してから再インストール MRSR 機能します。</span><span class="sxs-lookup"><span data-stu-id="60637-125">Remove the MRSR feature, delete the Unparsed library, and then reinstall the MRSR feature.</span></span>  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a><span data-ttu-id="60637-126">2 段階のワークフロー内のメッセージをループバックことはできません。</span><span class="sxs-lookup"><span data-stu-id="60637-126">Cannot loop back a message in a two-stage workflow</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-127">現象</span><span class="sxs-lookup"><span data-stu-id="60637-127">Symptom</span></span>  
 <span data-ttu-id="60637-128">のみの作成段階と修復段階を持つワークフローの修復段階でメッセージを拒否した場合、送信は失敗します。</span><span class="sxs-lookup"><span data-stu-id="60637-128">If you reject a message in the Repair stage of a workflow that has only a Create stage and a Repair stage, the submission fails.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="60637-129"> メッセージを MessageBox にルーティングし、次のエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="60637-129"> routes the message back to the MessageBox and posts the following error message:</span></span>  
  
 <span data-ttu-id="60637-130">「をリセットできませんでした、ワークフローの最初のステージを。」</span><span class="sxs-lookup"><span data-stu-id="60637-130">"Could not reset to the first stage in the workflow."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-131">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-131">Possible Cause</span></span>  
 <span data-ttu-id="60637-132">メッセージのループバックは作成段階のみと修復段階を持つワークフローではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="60637-132">Message loopback is not supported for a workflow that has only a Create stage and a Repair stage.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-133">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-133">Solution</span></span>  
 <span data-ttu-id="60637-134">2 段階のワークフローに別のステージを追加または送信をキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="60637-134">Add another stage to the two-stage workflow, or cancel the submission.</span></span>  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a><span data-ttu-id="60637-135">MRSR で修復の受信トレイにメッセージを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="60637-135">Cannot open a message in the repair inbox in MRSR</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-136">現象</span><span class="sxs-lookup"><span data-stu-id="60637-136">Symptom</span></span>  
 <span data-ttu-id="60637-137">MRSR で修復の受信トレイにメッセージを開くときに、ポップアップで、次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-137">When you try to open a message in the repair inbox in MRSR, you receive the following error message in a popup:</span></span>  
  
 <span data-ttu-id="60637-138">"ログイン 'A4SWIFT' で要求されたデータベースを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="60637-138">"Cannot open database requested in login 'A4SWIFT'.</span></span> <span data-ttu-id="60637-139">ログインに失敗しました.</span><span class="sxs-lookup"><span data-stu-id="60637-139">Login fails.</span></span> <span data-ttu-id="60637-140">ユーザー ' NT authority \network SERVICE' はログインできませんでした。</span><span class="sxs-lookup"><span data-stu-id="60637-140">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-141">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-141">Possible Cause</span></span>  
 <span data-ttu-id="60637-142">ログイン アカウント A4SWIFT_MRSR の web サービスを実行する web アプリケーションがネットワーク サービス、ローカルではない、またはドメイン アカウントは、A4SWIFT ユーザーのグループでは。</span><span class="sxs-lookup"><span data-stu-id="60637-142">The login account for the web application that the A4SWIFT_MRSR web service runs under is Network Service, not a local or domain account that is in the A4SWIFT Users group.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-143">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-143">Solution</span></span>  
 <span data-ttu-id="60637-144">A4SWIFT_MRSR の web サービスを実行する web アプリケーションのログイン アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="60637-144">Change the login account for the web application that the A4SWIFT_MRSR web service runs under.</span></span>  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a><span data-ttu-id="60637-145">A4SWIFT_MRSR の web サービスを実行する web アプリケーションのログイン アカウントを変更するには</span><span class="sxs-lookup"><span data-stu-id="60637-145">To change the login account for the web application that the A4SWIFT_MRSR web service runs under</span></span>  
  
1.  <span data-ttu-id="60637-146">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="60637-146">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="60637-147">IIS マネージャーで、展開、  ***\<サーバー名\>* (ローカル コンピューター)** ノード、**アプリケーション プール**ノードと**Webサイト**ノード。</span><span class="sxs-lookup"><span data-stu-id="60637-147">In IIS Manager, expand the ***\<server name\>* (local computer)** node, the **Application Pools** node and the **Web Sites** node.</span></span> <span data-ttu-id="60637-148">[Web サイト] ノードで、展開、**既定の Web サイト**ノード。</span><span class="sxs-lookup"><span data-stu-id="60637-148">Under the Web Sites node, expand the **Default Web Site** node.</span></span>  
  
3.  <span data-ttu-id="60637-149">既定の Web サイト ノードを右クリックして**A4SWIFT_MRSR**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="60637-149">Under the Default Web Site node, right-click **A4SWIFT_MRSR**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="60637-150">A4SWIFT_MRSR プロパティ ダイアログ ボックスで、アプリケーション プールに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60637-150">In the A4SWIFT_MRSR Properties dialog box, note the Application pool.</span></span>  
  
5.  <span data-ttu-id="60637-151">IIS マネージャー] ダイアログ ボックスの [アプリケーション プール ノードで、A4SWIFT_MRSR のアプリケーション プールを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="60637-151">In the IIS Manager dialog box, under the Application Pools node, right-click the application pool for A4SWIFT_MRSR, and then click **Properties**.</span></span>  
  
6.  <span data-ttu-id="60637-152">\<アプリケーション プール名\>プロパティ ダイアログ ボックスで、をクリックして、 **Identity**に注意してください。</span><span class="sxs-lookup"><span data-stu-id="60637-152">In the \<application pool name\> Properties dialog box, click the **Identity** note.</span></span> <span data-ttu-id="60637-153">場合**定義済み**がクリックされたと**ネットワーク サービス**が選択されていること、**構成可能**、ローカルまたはドメイン アカウントを入力し、パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="60637-153">If **Predefined** is clicked and **Network Service** is selected, click **Configurable**, enter your local or domain account, and then enter your password.</span></span> <span data-ttu-id="60637-154">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60637-154">Click **OK**.</span></span>  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a><span data-ttu-id="60637-155">ローカライズされたコンピューター上の MRSR サイトで作成されたメッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="60637-155">A message created in MRSR site on a localized computer is not processed</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-156">現象</span><span class="sxs-lookup"><span data-stu-id="60637-156">Symptom</span></span>  
 <span data-ttu-id="60637-157">ローカライズされたプラットフォームで実行されている A4SWIFT の英語版で作業しているユーザーが内のメッセージを作成するときに、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR、フォーム、および Message Repair and New Submission で使用するメッセージが表示されるメッセージを正常に送信する.オーケストレーションが正常に処理されていません。</span><span class="sxs-lookup"><span data-stu-id="60637-157">When a user working on an English version of A4SWIFT that is running on a localized platform creates a message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form in MRSR, and submits the message successfully, the message appears to be consumed by the Message Repair and New Submission orchestration, but is not successfully processed.</span></span> <span data-ttu-id="60637-158">メッセージは、送信トレイに送信されますが、BizTalk アダプタでは取得されません。</span><span class="sxs-lookup"><span data-stu-id="60637-158">The message is submitted to the outbox, but is not picked up by the BizTalk adapter.</span></span> <span data-ttu-id="60637-159">エラーまたは警告が発行されていなければ、イベント ビューアー、および HAT での実行中のオーケストレーション インスタンスのレコードがありません。</span><span class="sxs-lookup"><span data-stu-id="60637-159">No error or warning is posted in the Event Viewer, and there is no record of a running orchestration instance in HAT.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-160">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-160">Possible Cause</span></span>  
 <span data-ttu-id="60637-161">STS の URI として入力するパス。送信トレイの受信場所には、ローカライズされた名前ではなく、英語名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60637-161">The path entered as the URI for the STS.Outbox receive location contains the English name, not the localized name.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-162">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-162">Solution</span></span>  
 <span data-ttu-id="60637-163">STS の URI アドレスを変更します。送信トレイの受信場所を次のようにします。</span><span class="sxs-lookup"><span data-stu-id="60637-163">Change the URI address for the STS.Outbox receive location as follows:</span></span>  
  
1.  <span data-ttu-id="60637-164">BizTalk Server 2009 の管理コンソールで、展開、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション 1 ノード**します。</span><span class="sxs-lookup"><span data-stu-id="60637-164">In the BizTalk Server 2009 Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1 nodes**.</span></span>  
  
2.  <span data-ttu-id="60637-165">クリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="60637-165">Click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="60637-166">ダブルクリック**Sts.Outbox.Location**します。</span><span class="sxs-lookup"><span data-stu-id="60637-166">Double-click **Sts.Outbox.Location**.</span></span>  
  
4.  <span data-ttu-id="60637-167">[受信場所のプロパティ] ダイアログ ボックスで、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="60637-167">In the Receive Location Properties dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="60637-168">トランスポートのプロパティ ダイアログ ボックスでの値を置き換える**SharePointSite URL**ローカライズと等価です。</span><span class="sxs-lookup"><span data-stu-id="60637-168">In the Transport Properties dialog box, replace the value for **SharePointSite URL** with the localized equivalent.</span></span>  
  
6.  <span data-ttu-id="60637-169">をクリックして**OK**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="60637-169">Click **OK**, and then click **OK**.</span></span>  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a><span data-ttu-id="60637-170">ドキュメントおよび成果物の削除が不完全なメッセージの結果を処理している間にロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="60637-170">Removing a role while it is processing a message results in incomplete removal of documents and artifacts</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-171">現象</span><span class="sxs-lookup"><span data-stu-id="60637-171">Symptom</span></span>  
 <span data-ttu-id="60637-172">プロファイル Web クライアント ロールを削除するときに、すべてのドキュメントと、ロールに関連付けられた成果物が削除されることを示すダイアログ ボックスがポストされます。</span><span class="sxs-lookup"><span data-stu-id="60637-172">When you remove a role in the Profile Web Client, a dialog box is posted indicating that all documents and artifacts associated with the role will be removed.</span></span> <span data-ttu-id="60637-173">ただし、ロールは、部門、A4SWIFT 管理コンソール内からは削除されず、MRSR からロールのドキュメント フォルダー (受信トレイおよび送信済みアイテム) は削除されません。</span><span class="sxs-lookup"><span data-stu-id="60637-173">However, the role is not removed from the department in the A4SWIFT Management Console, and the role's document folders (Inbox and Sent Items) are not removed from MRSR.</span></span> <span data-ttu-id="60637-174">パーティ、送信ポート、およびロールに関連付けられているアグリーメントを削除すると、およびロールのプロファイルが展開解除します。</span><span class="sxs-lookup"><span data-stu-id="60637-174">The party, send port, and agreement associated with the role are removed, and the profile of the role is undeployed.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-175">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-175">Possible Cause</span></span>  
 <span data-ttu-id="60637-176">メッセージは、MRSR でロールの受信トレイのままであり、メッセージがで開いてその[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="60637-176">A message is still in the role's inbox in MRSR, and the message is open in its [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-177">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-177">Solution</span></span>  
 <span data-ttu-id="60637-178">MRSR サイトの受信トレイからメッセージを手動で削除し、削除された役割に関連付けられているドキュメント ライブラリを削除します。</span><span class="sxs-lookup"><span data-stu-id="60637-178">Manually delete the message from the MRSR site inbox, and then delete the document library that is associated with the role that you were removing.</span></span> <span data-ttu-id="60637-179">フォームを閉じて、もう一度役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="60637-179">Close the form and remove the role again.</span></span>  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a><span data-ttu-id="60637-180">BIC マスター ポリシーのエラーの結果としてメッセージの処理が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="60637-180">Message processing fails as a result of an error in the BIC Master Policy</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-181">現象</span><span class="sxs-lookup"><span data-stu-id="60637-181">Symptom</span></span>  
 <span data-ttu-id="60637-182">処理対象のメッセージを送信するときに、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-182">When you submit a message for processing, you receive the following error:</span></span>  
  
 <span data-ttu-id="60637-183">"、BicMasterPolicy の実行中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="60637-183">"An error occurred while executing the BicMasterPolicy.</span></span> <span data-ttu-id="60637-184">有効な値について、ポリシーを確認します。"</span><span class="sxs-lookup"><span data-stu-id="60637-184">Check the policy for valid values."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-185">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-185">Possible Cause</span></span>  
 <span data-ttu-id="60637-186">SQL Server 名、BIC データベース名、および BIC_Master_Policy.xml ファイル内の統合セキュリティ値*\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>二重引用符で囲まれた \Base ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60637-186">The SQL Server name, BIC database name, and integrated security value in the BIC_Master_Policy.xml file in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies are contained in double quotes.</span></span> <span data-ttu-id="60637-187">BIC 検証を有効にするこれらの文字列に入力既定 BIC_Master_Policy.xml ファイル」の説明に従って[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。</span><span class="sxs-lookup"><span data-stu-id="60637-187">To enable BIC validation, you enter these strings in the default BIC_Master_Policy.xml file as described in [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-188">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-188">Solution</span></span>  
 <span data-ttu-id="60637-189">BIC マスター ポリシーを修復するには、ように進めます。</span><span class="sxs-lookup"><span data-stu-id="60637-189">To repair the BIC master policy, proceed as follows:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60637-190">BIC マスター ポリシーの展開に関する詳細については、次を参照してください。 [BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)します。</span><span class="sxs-lookup"><span data-stu-id="60637-190">For more information about deploying the BIC master policy, see [Deploying BRE Rules](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).</span></span>  
  
1.  <span data-ttu-id="60637-191">ビジネス ルール作成ツール、BIC_Master_Policy のバージョン 1.0 の展開を解除し、BIC_Master_Policy を削除します。</span><span class="sxs-lookup"><span data-stu-id="60637-191">In Business Rule Composer, undeploy Version 1.0 of the BIC_Master_Policy, and then delete the BIC_Master_Policy.</span></span>  
  
2.  <span data-ttu-id="60637-192">メモ帳などのテキスト エディターで開くで BIC_Master_Policy.xml *\<ドライブ\>*: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン\>\Base ポリシー。</span><span class="sxs-lookup"><span data-stu-id="60637-192">In a text editor, such as Notepad, open BIC_Master_Policy.xml in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="60637-193">SQL Server 名を囲む二重引用符を削除、BIC データベース名、およびセキュリティの値を統合します。</span><span class="sxs-lookup"><span data-stu-id="60637-193">Remove the double quotes around the SQL Server name, BIC database name, and integrated security value.</span></span>  
  
3.  <span data-ttu-id="60637-194">ビジネス ルール エンジン展開ウィザードで、BIC_Master_Policy.xml をインポートし、BIC_Master_Policy.xml を展開します。</span><span class="sxs-lookup"><span data-stu-id="60637-194">In the Business Rules Engine Deployment Wizard, import BIC_Master_Policy.xml, and then deploy BIC_Master_Policy.xml.</span></span>  
  
4.  <span data-ttu-id="60637-195">サービス mmc で、ルール エンジン更新サービスと BizTalk 受信ホスト サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="60637-195">In the Services MMC, restart the Rule Engine Update Service and the BizTalk Receive Host Service.</span></span>  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a><span data-ttu-id="60637-196">A4SWIFT では、適切なデータベース権限のない未解析のメッセージを処理できません。</span><span class="sxs-lookup"><span data-stu-id="60637-196">A4SWIFT will not be able to process an unparsed message without proper database permissions</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-197">現象</span><span class="sxs-lookup"><span data-stu-id="60637-197">Symptom</span></span>  
 <span data-ttu-id="60637-198">A4SWIFT を解析できないメッセージをドロップすると、A4SWIFT は、メッセージを処理することができませんが、キャッチされない例外で失敗します。</span><span class="sxs-lookup"><span data-stu-id="60637-198">When you drop a message that A4SWIFT cannot parse, A4SWIFT is unable to process the message, but fails with an uncaught exception.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-199">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-199">Possible Cause</span></span>  
 <span data-ttu-id="60637-200">データベース アクセス許可の問題があります。</span><span class="sxs-lookup"><span data-stu-id="60637-200">There is a database permission issue.</span></span> <span data-ttu-id="60637-201">HostSvc は、既定では、BizTalk サービスのログオン アカウントは、A4SWIFT 管理者と A4SWIFT ユーザーのグループに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="60637-201">The Log On account for the BizTalk service, which by default is HostSvc, is not included in the A4SWIFT Administrators and A4SWIFT Users groups.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-202">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-202">Solution</span></span>  
 <span data-ttu-id="60637-203">A4SWIFT 管理者と A4SWIFT ユーザーのグループに BizTalk サービスのログオン アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="60637-203">Add the Log On account for the BizTalk service to the A4SWIFT Administrators and A4SWIFT Users groups.</span></span>  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a><span data-ttu-id="60637-204">修復の InfoPath フォームのタイムアウトは、修復ワークフローのさまざまな段階でメッセージの 2 つのコピーで結果ことができます。</span><span class="sxs-lookup"><span data-stu-id="60637-204">A timeout of the InfoPath repair form can result in two copies of a message in different stages of the repair workflow</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-205">現象</span><span class="sxs-lookup"><span data-stu-id="60637-205">Symptom</span></span>  
 <span data-ttu-id="60637-206">フォームの送信でエラーがある場合、ワークフロー ステージ)、(InfoPath フォームからのメッセージを送信するときに、エラー メッセージのコピーを 2 つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60637-206">When you submit a message from an InfoPath form (for any workflow stage), if there is an error in submission of the form, the error could result in two copies of message.</span></span> <span data-ttu-id="60637-207">現在のステージでは、1 つのメッセージは、受信トレイのままであり、ワークフローで [次へ]、ロールの受信トレイの他のメッセージでは。</span><span class="sxs-lookup"><span data-stu-id="60637-207">One message is still in the inbox for the current stages, and the other message is in the inbox for the next role in the workflow.</span></span> <span data-ttu-id="60637-208">これらのメッセージを処理しようとは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="60637-208">Attempting to process these messages will result in the following:</span></span>  
  
-   <span data-ttu-id="60637-209">ワークフローの次のロールの受信トレイからメッセージを送信する場合は、メッセージがワークフローから続行されます。</span><span class="sxs-lookup"><span data-stu-id="60637-209">If you submit the message from the inbox for the next role of the workflow, the message will continue through the workflow.</span></span>  
  
-   <span data-ttu-id="60637-210">現在のステージの次のステージの受信トレイから送信されたメッセージの処理が完了したが、受信トレイからメッセージを送信する場合は、ルーティング エラーにより、現在の受信トレイから送信されたメッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="60637-210">If you submit the message from the inbox for the current stage after the message submitted from the inbox of the next stage has completed processing, the message submitted from the current inbox will be suspended with a routing failure.</span></span>  
  
-   <span data-ttu-id="60637-211">次のステージの受信トレイから送信されたメッセージが完了する前に、現在のステージの受信トレイにメッセージを送信する場合は、処理、そのステージでは、受信トレイに現在のステージの受信トレイから送信されたメッセージが返されますは、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-211">If you submit the message in the inbox for the current stage before the message submitted from the inbox of the next stage has completed processing, the message submitted from the inbox for the current stage will be returned to the inbox for that stage, and you will receive the following error:</span></span>  
    <span data-ttu-id="60637-212">"ためにワークフローをリセットしていますメッセージが改ざんされたか、ユーザーは、このステージでは有効ではありません。"。</span><span class="sxs-lookup"><span data-stu-id="60637-212">"Resetting workflow due to: either the message was tampered with or the user is invalid for this stage."</span></span>  
    <span data-ttu-id="60637-213">その後、次のステージでは、受信トレイからメッセージを送信する場合のワークフローもリセットされます。</span><span class="sxs-lookup"><span data-stu-id="60637-213">After this, if you submit the message from the inbox for the next stage, the workflow for it will also be reset.</span></span> <span data-ttu-id="60637-214">現在のステージの受信トレイに返され、上記のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-214">It will be returned to the inbox for the current stage and you will receive the above error.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-215">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-215">Possible Cause</span></span>  
 <span data-ttu-id="60637-216">InfoPath フォームには、Microsoft Windows Sharepoint Services および検証を実行するカスタム Web サービスを使用して BizTalk Server にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="60637-216">The InfoPath form has submitted the message to BizTalk Server via Microsoft Windows Sharepoint Services and a custom Web service that performs validations.</span></span> <span data-ttu-id="60637-217">メッセージを送信するために複数の手順では、これらの手順は、Windows Sharepoint Services のトランザクションがないため、トランザクションではありません。</span><span class="sxs-lookup"><span data-stu-id="60637-217">Submitting a message is accomplished in multiple steps and these steps are not transactional, because Windows Sharepoint Services is not transactional.</span></span> <span data-ttu-id="60637-218">この制限を対応するためには MRSR オーケストレーションが検出し、メッセージの送信から発生したエラーから回復する回復ロジックで構築されています。</span><span class="sxs-lookup"><span data-stu-id="60637-218">To accommodate this limitation, the MRSR orchestrations have built in recovery logic to detect and recover from errors arising from the message submission.</span></span> <span data-ttu-id="60637-219">MRSR オーケストレーションは、常に SWIFT に送信される重複したメッセージを回避します。</span><span class="sxs-lookup"><span data-stu-id="60637-219">The MRSR orchestrations always prevent duplicate messages being sent to SWIFT.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-220">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-220">Solution</span></span>  
 <span data-ttu-id="60637-221">このような場合は、ワークフロー内にさらにメッセージを選択、ワークフローの初期段階では、その他のメッセージを処理する前に、ワークフローを完了してください。</span><span class="sxs-lookup"><span data-stu-id="60637-221">If this occurs, you should pick the message that is further along in the workflow and complete its workflow before attempting to process the other messages that are in the earlier stages of the workflow.</span></span> <span data-ttu-id="60637-222">ワークフロー内にさらにメッセージが処理を完了してから、必要に応じて (ルーティング エラーにより中断されました) を 2 番目のメッセージを破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="60637-222">After the message that is further along in the workflow has completed processing, you can dispose of the second message (which was suspended with a routing failure) as you see fit.</span></span>  
  
 <span data-ttu-id="60637-223">メッセージさらにに沿ってワークフローの完了しなかった場合、2 番目のメッセージを処理する前に処理、なかで修復 InfoPath フォーム、ワークフローでは、メッセージをもう一度修復し、それを送信ください。</span><span class="sxs-lookup"><span data-stu-id="60637-223">If the message that is further along in the workflow did not complete processing before you processed the second message, you should once again repair the message that is further along in the workflow in the repair InfoPath form, and then submit it.</span></span> <span data-ttu-id="60637-224">処理の完了を許可して、2 番目のメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="60637-224">Allow it to complete processing, and then submit the second message.</span></span> <span data-ttu-id="60637-225">2 番目のメッセージが中断された後は、それを破棄します。</span><span class="sxs-lookup"><span data-stu-id="60637-225">After the second message has been suspended, dispose of it.</span></span>  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a><span data-ttu-id="60637-226">中断されたメッセージが発生しない検証ステージで新しい送信</span><span class="sxs-lookup"><span data-stu-id="60637-226">A new submission with no verify stage will result in a suspended message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-227">現象</span><span class="sxs-lookup"><span data-stu-id="60637-227">Symptom</span></span>  
 <span data-ttu-id="60637-228">検証ステージを持たないワークフローで新しいメッセージを送信するときに、メッセージが中断されます。</span><span class="sxs-lookup"><span data-stu-id="60637-228">When you submit a new message in a workflow that has no verify stage, the message is suspended.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="60637-229">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="60637-229">Possible Cause</span></span>  
 <span data-ttu-id="60637-230">作成するには、A4SWIFT_MRSRLastStage は設定されていない場合、検証ステージの欠如の結果は保留メッセージ。</span><span class="sxs-lookup"><span data-stu-id="60637-230">The lack of a verify stage results in a suspended message if A4SWIFT_MRSRLastStage is not set to Create.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-231">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-231">Solution</span></span>  
 <span data-ttu-id="60637-232">A4SWIFT_MRSRLastStage のサブスクリプションを使用して、メッセージが適切にルーティングされるようにするには作成を = =。</span><span class="sxs-lookup"><span data-stu-id="60637-232">Use a subscription of A4SWIFT_MRSRLastStage == Create to ensure that the message is routed properly.</span></span>  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a><span data-ttu-id="60637-233">メッセージの検証結果を"エラー"で解析フォームの InfoPath タスク ペイン</span><span class="sxs-lookup"><span data-stu-id="60637-233">Validation of message results a "parse error" in the InfoPath form task pane</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-234">現象</span><span class="sxs-lookup"><span data-stu-id="60637-234">Symptom</span></span>  
 <span data-ttu-id="60637-235">InfoPath のフォームの作業ウィンドウで「解析エラー」を表示、説明のないメッセージ ボタンを検証します。</span><span class="sxs-lookup"><span data-stu-id="60637-235">Validate Message button in the InfoPath form task pane shows “parse error” without any description.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-236">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-236">Solution</span></span>  
 <span data-ttu-id="60637-237">MRSR の web サービスを再起動または iisreset を実行します。</span><span class="sxs-lookup"><span data-stu-id="60637-237">Restart the MRSR web service or do iisreset.</span></span>  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a><span data-ttu-id="60637-238">承認エラーの結果、InfoPath フォームの発行</span><span class="sxs-lookup"><span data-stu-id="60637-238">Publishing an InfoPath form results an authorization error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-239">現象</span><span class="sxs-lookup"><span data-stu-id="60637-239">Symptom</span></span>  
 <span data-ttu-id="60637-240">承認エラーは、InfoPath フォームを公開します。</span><span class="sxs-lookup"><span data-stu-id="60637-240">Publishing an InfoPath form gives authorization error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-241">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-241">Solution</span></span>  
 <span data-ttu-id="60637-242">MRSR サイトの URL で localhost では、コンピューター名を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="60637-242">Replace machine name by localhost in the MRSR site URL.</span></span>  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a><span data-ttu-id="60637-243">フォームの InfoPath タスク ペインは、HTML ソース コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="60637-243">InfoPath form task pane shows HTML source code</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-244">現象</span><span class="sxs-lookup"><span data-stu-id="60637-244">Symptom</span></span>  
 <span data-ttu-id="60637-245">InfoPath フォームのタスク ペインには、Web コントロールではなく HTML ソース コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-245">InfoPath form task pane shows HTML source code instead of Web controls.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-246">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-246">Solution</span></span>  
 <span data-ttu-id="60637-247">移動して**ツール**-> **セキュリティ] タブ** -> **インターネット ゾーン**、有効にして**コンテンツに基づいてファイルを開く拡張機能ではなく** [その他。</span><span class="sxs-lookup"><span data-stu-id="60637-247">Go to **Tools**-> **Security Tab** -> **Internet Zone**, and enable **Open file based on content not on extension** under Miscellaneous.</span></span>  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a><span data-ttu-id="60637-248">プロファイル Web クライアントの web サイト認証エラーを結果します。</span><span class="sxs-lookup"><span data-stu-id="60637-248">Profile Web Client website results an Authentication error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="60637-249">現象</span><span class="sxs-lookup"><span data-stu-id="60637-249">Symptom</span></span>  
 <span data-ttu-id="60637-250">Web クライアントの web サイトをプロファイルには、認証エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60637-250">Profile Web Client website displays Authentication error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="60637-251">解決方法</span><span class="sxs-lookup"><span data-stu-id="60637-251">Solution</span></span>  
 <span data-ttu-id="60637-252">実行、 **BTSharePointAdapterWSAppPool**と**DefaultAppPoolApplication** ]-> [し、管理者アカウントでインターネット情報サービス (iis) のプールします。</span><span class="sxs-lookup"><span data-stu-id="60637-252">Run the **BTSharePointAdapterWSAppPool** and **DefaultAppPoolApplication** -> and pool in Internet Information Services(IIS) under the administrator account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60637-253">参照</span><span class="sxs-lookup"><span data-stu-id="60637-253">See Also</span></span>  
 [<span data-ttu-id="60637-254">トラブルシューティング: 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="60637-254">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)