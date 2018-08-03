---
title: ポートの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- receive ports
- creating, send ports
- creating, ports
- Configuration database [BizTalk Server], connecting
- receive ports, creating
- send ports
- send ports, creating
ms.assetid: 4f99f884-5b84-4f9f-8cec-dd5da259ba7f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d109e102ada04e673fa5eddc3010201b266a150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015129"
---
# <a name="creating-ports"></a><span data-ttu-id="51f1c-102">ポートの作成</span><span class="sxs-lookup"><span data-stu-id="51f1c-102">Creating Ports</span></span>
<span data-ttu-id="51f1c-103">シングル サインオン用の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信ポートと受信ポートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for Single Sign-on.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="51f1c-104">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="51f1c-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="51f1c-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="51f1c-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="51f1c-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="51f1c-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="51f1c-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="51f1c-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="51f1c-109">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="51f1c-110">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="51f1c-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="51f1c-112">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="51f1c-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="51f1c-114">をクリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="51f1c-115">**PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="51f1c-116">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイルです。</span><span class="sxs-lookup"><span data-stu-id="51f1c-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="51f1c-117">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51f1c-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="51f1c-118">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="51f1c-119">**SSO を使用する****はい**です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="51f1c-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="51f1c-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-121">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="51f1c-122">作成する、受信ポート</span><span class="sxs-lookup"><span data-stu-id="51f1c-122">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="51f1c-123">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="51f1c-123">To create a receive port</span></span>  
  
1.  <span data-ttu-id="51f1c-124">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="51f1c-124">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="51f1c-125">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-125">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="51f1c-126">**受信ポートのプロパティ** ウィンドウで、**全般** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-126">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="51f1c-127">**名前**フィールドに「`ReceiveFromTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="51f1c-127">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="51f1c-128">**認証**グループ ボックスで、認証の使用時のメッセージの処理方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-128">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="51f1c-129">選択、**失敗したメッセージの有効化のルーティングを**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-129">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="51f1c-130">**受信場所** ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-130">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="51f1c-131">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-131">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="51f1c-132">**受信場所**ウィンドウで、**全般** ページで、入力、**名前**受信場所のです。</span><span class="sxs-lookup"><span data-stu-id="51f1c-132">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="51f1c-133">**型**ドロップダウン一覧で、トランスポートの種類を選択してから、**受信ハンドラー**ドロップダウン一覧で、トランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-133">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="51f1c-134">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-134">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="51f1c-135">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-135">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="51f1c-136">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-136">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="51f1c-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="51f1c-138">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-138">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="51f1c-139">**追跡** ページで、必要なメッセージ本文の追跡と追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-139">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="51f1c-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51f1c-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f1c-141">参照</span><span class="sxs-lookup"><span data-stu-id="51f1c-141">See Also</span></span>  
 [<span data-ttu-id="51f1c-142">アダプターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="51f1c-142">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)