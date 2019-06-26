---
title: EDI および AS2 状態レポートの有効化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa40fbad-51ad-40e0-9fe3-68e54beb11a5
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b06ae5e1fde570a9c27c1951a4eca7a7c5481e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349909"
---
# <a name="enabling-edi-and-as2-status-reports"></a><span data-ttu-id="9a5ba-102">EDI および AS2 状態レポートの有効化</span><span class="sxs-lookup"><span data-stu-id="9a5ba-102">Enabling EDI and AS2 Status Reports</span></span>
<span data-ttu-id="9a5ba-103">このトピックでの EDI および AS2 状態レポートを構成する方法を説明します、**グループの概要**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-103">This topic describes how to configure the EDI and AS2 status reports in the **Group Overview** page of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
 <span data-ttu-id="9a5ba-104">状態レポート追跡データは、以下の手順で選択するストレージのプロパティに従って、BizTalk 追跡データベース (BizTalkDTADb) に格納されます。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-104">Status reporting tracking data is stored in the BizTalk tracking database (BizTalkDTADb) in accordance with the storage properties selected in the procedures below.</span></span> <span data-ttu-id="9a5ba-105">各アグリーメントの状態レポート機能を有効にするように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-105">You can configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to enable status reporting for each agreement.</span></span> <span data-ttu-id="9a5ba-106">格納するデータ量に応じて、アクティブなストアからデータを定期的にアーカイブし、その後にアーカイブ ストアから適宜消去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-106">Depending upon the amount of data that you store, you should routinely archive the data from the active store and ultimately clean it out from the archival store, as appropriate.</span></span> <span data-ttu-id="9a5ba-107">BizTalkDTADb データベースの管理の詳細については、次を参照してください。[アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-107">For more information about managing the BizTalkDTADb database, see [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md).</span></span>  
  
 <span data-ttu-id="9a5ba-108">状態レポートは次の 3 種類の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-108">You can enable status reports in three ways:</span></span>  
  
- <span data-ttu-id="9a5ba-109">アグリーメントに解決される受信 EDI インターチェンジまたは送信 EDI インターチェンジに対して状態レポート機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="9a5ba-109">Enable status reports for inbound or outbound EDI interchanges that resolved to an agreement.</span></span>  
  
- <span data-ttu-id="9a5ba-110">インターチェンジの EDI 状態レポートがアクティブであるため、EDI フォールバック アグリーメント プロパティの状態レポートを有効にする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のアグリーメントを特定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-110">Enable status reports for EDI fallback agreement properties, so status reporting is activated for EDI interchanges that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] could not determine an agreement for.</span></span>  
  
- <span data-ttu-id="9a5ba-111">AS2 メッセージの状態レポート機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="9a5ba-111">Enable status reports for AS2 messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a5ba-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="9a5ba-112">Prerequisites</span></span>  
 <span data-ttu-id="9a5ba-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは BizTalk Server B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group or BizTalk Server B2B Operators group.</span></span>  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a><span data-ttu-id="9a5ba-114">アグリーメントの EDI 状態レポート機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="9a5ba-114">To enable EDI status reports for an agreement</span></span>  
  
1. <span data-ttu-id="9a5ba-115">**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**コンソールで、をクリックして、**パーティ**ノードの下、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-115">In the **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration** Console, click the **Parties** node under the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and **BizTalk Group** nodes.</span></span>  
  
2. <span data-ttu-id="9a5ba-116">**パーティとビジネス プロファイル**ウィンドウで、状態レポートを有効にする X12 または EDIFACT アグリーメントのパーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-116">In the **Parties and Business Profiles** pane, click the party that has the X12 or EDIFACT agreement for which you want to enable status reporting.</span></span>  
  
3. <span data-ttu-id="9a5ba-117">**契約**セクションをクリックして、状態レポートを有効にするアグリーメントを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-117">In the **Agreements** section, right-click the agreement for which you want to enable status reporting and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="9a5ba-118">**全般**] タブで、**共通のホスト設定**セクションで、[**レポートを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-118">In the **General** tab, in the **Common Host Settings** section, click **Turn ON Reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-119">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-119">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5. <span data-ttu-id="9a5ba-120">選択**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-120">Select **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-121">バッチ処理オーケストレーションのインスタンスがアクティブなときにトランザクション セットのストレージを有効にした場合は、作成中のバッチについてのトランザクション セットが格納されません。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-121">If you enable storage of transaction sets while an instance of the batching orchestration is activated, transaction sets will not be stored for the batch being created.</span></span> <span data-ttu-id="9a5ba-122">ただし、バッチ処理オーケストレーションのインスタンスがアクティブなときにトランザクション セットのストレージを無効にした場合は、ストレージがバッチ処理の途中で無効になります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-122">However, if you disable storage of transaction sets while an instance of the batching orchestration is activated, the storage will be disabled in the middle of the batching.</span></span>  
  
6. <span data-ttu-id="9a5ba-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-123">Click **OK**.</span></span>  
  
7. <span data-ttu-id="9a5ba-124">[コンピューターの管理] ダイアログ ボックスで BizTalk サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-124">Restart the BizTalk Service (in the Computer Management dialog box).</span></span> <span data-ttu-id="9a5ba-125">AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインは、ソリューションで使用されている場合、IIS 管理サービスを再起動 (を使用して、 *iisreset*コマンド) もします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-125">If the AS2EdiReceive pipeline or the AS2EdiSend pipeline is being used in your solution, restart the IIS Admin service (using the *iisreset* command), as well.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-126">EDI 状態レポートをアクティブ化または非アクティブ化した後は、変更を有効にするために、BizTalk サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-126">The BizTalk Service needs to be restarted after EDI status reporting has been activated or deactivated for the change to take effect.</span></span> <span data-ttu-id="9a5ba-127">ソリューションで AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインを使用している場合は、変更を有効にするために、BizTalk サービスと IIS サービスの両方を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-127">If the AS2EdiReceive or AS2EdiSend pipeline is being used in your solution, both the BizTalk Service and the IIS service need to be restarted for the change to take effect.</span></span> <span data-ttu-id="9a5ba-128">AS2 状態レポート機能を有効にする場合は、この操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-128">Note that this is not necessary when enabling AS2 status reporting.</span></span>  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a><span data-ttu-id="9a5ba-129">フォールバック アグリーメントの EDI 状態レポート機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="9a5ba-129">To enable EDI status reports for fallback agreements</span></span>  
  
1. <span data-ttu-id="9a5ba-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、ノードを右クリックし**パーティ**を選択し、 **X12 フォールバック設定**または**EDIFACT フォールバックの設定**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group** nodes, right-click **Parties**, and select **X12 Fallback Settings** or **EDIFACT Fallback Settings**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-131">フォールバック アグリーメントで状態レポートを構成する場合は、メッセージのアグリーメントが特定されていないときにのみ、構成が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-131">When you configure status reports in the fallback agreements, the configuration only applies when no agreement has been determined for a message.</span></span>  
  
2. <span data-ttu-id="9a5ba-132">**フォールバック設定の [全般] ページ**] タブで [ **EDI のアクティブ化レポート**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-132">In the **Fallback Settings General Pages** tab, click **Activate EDI reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-133">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-133">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
3. <span data-ttu-id="9a5ba-134">選択**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-134">Select **Store transaction set/payload for reporting** to store transaction sets in the EDI tables of the tracking (BizTalkDTADb) database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-135">**EDIFACT でエンコードされたメッセージ**:このプロパティを選択する場合は、EDI グローバル プロパティ ダイアログ ボックスの UNB セグメントの定義 ページで unb3.2 フィールド (コード修飾子) の値を選択することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-135">**For EDIFACT-encoded messages**: If you select this property, you must also select a value for the UNB3.2 field (Code qualifier) in the UNB Segment Definition page of the EDI Global Properties dialog box.</span></span> <span data-ttu-id="9a5ba-136">既定では、このプロパティが設定されていないと場合、インターチェンジは中断されます**レポート用にトランザクション セット/ペイロードを格納**が選択されているが、UNB3.2 の値が選択されていません。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-136">This property is not set by default, and the interchange will be suspended if **Store transaction set/payload for reporting** is selected, but a value is not selected for UNB3.2.</span></span>  
  
4. <span data-ttu-id="9a5ba-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-137">Click **OK**.</span></span>  
  
### <a name="to-enable-as2-status-reports"></a><span data-ttu-id="9a5ba-138">AS2 状態レポート機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="9a5ba-138">To enable AS2 status reports</span></span>  
  
1. <span data-ttu-id="9a5ba-139">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**ノード、をクリックして、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and **BizTalk Group** nodes, click the **Parties** node.</span></span>  
  
2. <span data-ttu-id="9a5ba-140">**パーティとビジネス プロファイル**ウィンドウで、状態レポートを有効にする X12 または EDIFACT アグリーメントのパーティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-140">In the **Parties and Business Profiles** pane, click the party that has the X12 or EDIFACT agreement for which you want to enable status reporting.</span></span>  
  
3. <span data-ttu-id="9a5ba-141">**契約**セクションをクリックして、状態レポートを有効にするアグリーメントを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-141">In the **Agreements** section, right-click the agreement for which you want to enable status reporting and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="9a5ba-142">**共通のホスト設定**セクションで、**レポートを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-142">In the **Common Host Settings** section, click **Turn ON Reporting**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-143">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-143">This step causes message entries to be entered in the status report UI in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
5. <span data-ttu-id="9a5ba-144">一方向アグリーメント タブで、**アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして、**受信者メッセージ追跡 (NRR)** ページ。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-144">In the one-way agreement tab of the **Agreement Properties** dialog box, click the **Receiver Message Tracking (NRR)** page.</span></span>  
  
6. <span data-ttu-id="9a5ba-145">**受信者メッセージ追跡 (NRR)** ] ページで [**受信のエンコードされた AS2 メッセージに対して有効な NRR**受信メッセージのワイヤ形式の表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-145">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for inbound encoded AS2 messages** to enable display of the wire format of incoming messages.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-146">AS2 メッセージおよび関連 MDN の状態 ページでメッセージを右クリックしをクリックすると、メッセージのワイヤ形式が表示されます**メッセージのワイヤ形式**します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-146">The wire format of the message will be displayed when you right-click the message in the AS2 Message and Correlated MDN Status Page, and then click **Message Wire Format**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9a5ba-147">**レポートを有効にする**のデータを否認不可データベース ストレージを有効にするためのプロパティを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-147">The **Turn ON Reporting** property must be selected for you to enable storage of any data in the non-repudiation database.</span></span> <span data-ttu-id="9a5ba-148">このプロパティまたは否認不可データベースへの格納を有効にする他のプロパティを選択した場合は、AS2 レポートをアクティブにするように通知するポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-148">If you select this or any of the other properties enabling storage in the non-repudiation database, a popup will be displayed prompting you to activate AS2 reporting.</span></span> <span data-ttu-id="9a5ba-149">クリックすると**はい**、AS2 レポートはでアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-149">If you click **Yes**, AS2 reporting will be activated for you.</span></span>  
  
7. <span data-ttu-id="9a5ba-150">**受信者メッセージ追跡 (NRR)** ] ページで [**受信のデコードされた AS2 メッセージに対して有効な NRR**デコードされた形式の受信メッセージの表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-150">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for inbound decoded AS2 messages** to enable display of the decoded format of incoming messages.</span></span>  
  
8. <span data-ttu-id="9a5ba-151">**受信者メッセージ追跡 (NRR)** ] ページで [**送信 MDN の NRR の有効化**受信メッセージへの MDN 応答を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-151">In the **Receiver Message Tracking (NRR)** page, click **NRR enabled for outbound MDN** to enable display of MDN responses to incoming messages.</span></span>  
  
9. <span data-ttu-id="9a5ba-152">一方向アグリーメント タブで、**アグリーメントのプロパティ**ダイアログ ボックスで、をクリックして、**送信者メッセージ追跡 (NRR)** ページ。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-152">In the one-way agreement tab of the **Agreement Properties** dialog box, click the **Sender Message Tracking (NRR)** page.</span></span>  
  
10. <span data-ttu-id="9a5ba-153">**送信者メッセージ追跡 (NRR)** ] ページで [**エンコードされた送信の AS2 メッセージに対して有効な NRR**送信メッセージのワイヤ形式の表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-153">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for outbound encoded AS2 messages** to enable display of the wire format of outgoing messages.</span></span>  
  
11. <span data-ttu-id="9a5ba-154">**送信者メッセージ追跡 (NRR)** ] ページで [**送信のデコードされた AS2 メッセージに対して有効な NRR**送信メッセージのデコードされた形式の表示を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-154">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for outbound decoded AS2 messages** to enable display of the decoded format of outgoing messages.</span></span>  
  
12. <span data-ttu-id="9a5ba-155">**送信者メッセージ追跡 (NRR)** ] ページで [**受信 MDN の NRR の有効化**送信メッセージへの MDN 応答を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-155">In the **Sender Message Tracking (NRR)** page, click **NRR enabled for inbound MDN** to enable display of MDN responses to outgoing messages.</span></span>  
  
13. <span data-ttu-id="9a5ba-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a5ba-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5ba-157">参照</span><span class="sxs-lookup"><span data-stu-id="9a5ba-157">See Also</span></span>  
 <span data-ttu-id="9a5ba-158">[EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="9a5ba-158">[Monitoring EDI and AS2 Solutions](../core/monitoring-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="9a5ba-159">[EDI および AS2 状態レポートを構成します。](../core/configuring-an-edi-and-as2-status-report.md) </span><span class="sxs-lookup"><span data-stu-id="9a5ba-159">[Configuring an EDI and AS2 Status Report](../core/configuring-an-edi-and-as2-status-report.md) </span></span>  
 [<span data-ttu-id="9a5ba-160">EDI および AS2 状態レポート</span><span class="sxs-lookup"><span data-stu-id="9a5ba-160">EDI and AS2 Status Reporting</span></span>](../core/edi-and-as2-status-reporting.md)   