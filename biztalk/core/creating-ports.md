---
title: ポートの作成 |Microsoft Docs
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
ms.openlocfilehash: 4f9370442e6f24222a361aa2a6c9901dca0772f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353630"
---
# <a name="creating-ports"></a><span data-ttu-id="a6154-102">ポートの作成</span><span class="sxs-lookup"><span data-stu-id="a6154-102">Creating Ports</span></span>
<span data-ttu-id="a6154-103">次の手順を使用して作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信および受信ポートをシングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a6154-103">Use the following procedures to create [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports for Single Sign-on.</span></span>  
  
## <a name="creating-a-send-port"></a><span data-ttu-id="a6154-104">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="a6154-104">Creating a Send Port</span></span>  
  
#### <a name="to-create-a-send-port"></a><span data-ttu-id="a6154-105">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6154-105">To create a send port</span></span>  
  
1.  <span data-ttu-id="a6154-106">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a6154-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="a6154-107">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a6154-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="a6154-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6154-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a6154-109">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`します。</span><span class="sxs-lookup"><span data-stu-id="a6154-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="a6154-110">**型**ドロップダウン リストで、 **PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="a6154-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="a6154-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="a6154-112">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="a6154-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="a6154-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="a6154-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
    6.  <span data-ttu-id="a6154-114">クリックして**構成**送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a6154-114">Click **Configure** to configure the send port.</span></span>  
  
4.  <span data-ttu-id="a6154-115">**PeopleSoft トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6154-115">In the **PeopleSoft Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="a6154-116">展開**アダプターに必要なプロパティ**、入力と**アプリケーション サーバーのパス**、 **JAVA_HOME**、**ユーザー名**、 **パスワード**、および Peoplesoft システムに接続するための Jar ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6154-116">Expand **Adapter Required Properties**, and enter **Application Server Path**, **JAVA_HOME**, **user name**, **password**, and the Jar file for connecting into the Peoplesoft system.</span></span>  
  
         <span data-ttu-id="a6154-117">ログオン情報を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6154-117">You do not have to set the logon information.</span></span>  
  
    2.  <span data-ttu-id="a6154-118">一覧で、PeopleSoft システムを表すよう作成した SSO 関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-118">In the list, select the SSO affiliate application you created to represent the PeopleSoft system.</span></span>  
  
    3.  <span data-ttu-id="a6154-119">**SSO を使用**、**はい**します。</span><span class="sxs-lookup"><span data-stu-id="a6154-119">For **Use SSO**, select **Yes**.</span></span>  
  
    4.  <span data-ttu-id="a6154-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6154-120">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a6154-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6154-121">Click **OK**.</span></span>  
  
## <a name="creating-a-receive-port"></a><span data-ttu-id="a6154-122">作成、受信ポート</span><span class="sxs-lookup"><span data-stu-id="a6154-122">Creating a Receive Port</span></span>  
  
#### <a name="to-create-a-receive-port"></a><span data-ttu-id="a6154-123">受信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6154-123">To create a receive port</span></span>  
  
1.  <span data-ttu-id="a6154-124">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a6154-124">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="a6154-125">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a6154-125">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="a6154-126">**受信ポートのプロパティ**ウィンドウの**全般**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6154-126">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="a6154-127">**名前**フィールドに「`ReceiveFromTIBCOEMS`します。</span><span class="sxs-lookup"><span data-stu-id="a6154-127">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="a6154-128">**認証**グループ ボックスで、認証の使用時にメッセージを処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6154-128">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="a6154-129">選択、**失敗したメッセージのルーティングを有効にする**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a6154-129">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="a6154-130">**受信場所**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6154-130">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="a6154-131">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6154-131">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="a6154-132">**受信場所**ウィンドウで、**全般**ページで、入力、**名前**受信場所の。</span><span class="sxs-lookup"><span data-stu-id="a6154-132">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="a6154-133">**型**ドロップダウン リストで、トランスポートの種類の選択との間、**受信ハンドラー**ドロップダウン一覧でトランスポート アドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-133">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="a6154-134">**受信パイプライン**ドロップダウン リストで、受信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-134">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="a6154-135">**スケジュール**] ページで、[、**開始日**と**終了日**ドキュメントの受信を制限します。</span><span class="sxs-lookup"><span data-stu-id="a6154-135">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="a6154-136">選択、**有効にするサービス時間帯**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a6154-136">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="a6154-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6154-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a6154-138">**受信マップ**ページで、選択したポートでドキュメントを変換するための受信マップを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-138">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="a6154-139">**追跡** ページで、必要なメッセージ本文を追跡および追跡メッセージのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6154-139">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="a6154-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6154-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6154-141">参照</span><span class="sxs-lookup"><span data-stu-id="a6154-141">See Also</span></span>  
 [<span data-ttu-id="a6154-142">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a6154-142">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)