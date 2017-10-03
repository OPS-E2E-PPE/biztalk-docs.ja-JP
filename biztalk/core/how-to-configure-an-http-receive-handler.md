---
title: "HTTP 受信ハンドラを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0380804039d45efbe3db06b6fc072a3afb8b6b48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-receive-handler"></a><span data-ttu-id="d5029-102">HTTP 受信ハンドラを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d5029-102">How to Configure an HTTP Receive Handler</span></span>
<span data-ttu-id="d5029-103">次の手順を実行して、HTTP 受信ハンドラのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="d5029-103">Use the following procedure to configure the properties for an HTTP receive handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5029-104">各ホストに関連付けられる受信ハンドラは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="d5029-104">Each host can have only one receive handler associated with it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5029-105">HTTP 受信アダプタは、BizTalk 分離ホスト インスタンスのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d5029-105">The HTTP receive adapter runs in the context of a BizTalk Isolated Host instance.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d5029-106">HTTP アダプター ハンドラーまたは SOAP アダプター ハンドラーを使用するときは、これらのハンドラーのホスト インスタンスを Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] コンピューターにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d5029-106">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computers.</span></span>  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a><span data-ttu-id="d5029-107">HTTP 受信ハンドラの全般プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="d5029-107">To configure the general properties for an HTTP receive handler</span></span>  
  
1.  <span data-ttu-id="d5029-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="d5029-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="d5029-109">展開したアダプターの一覧でクリックして**HTTP、**右側のウィンドウで、構成、およびをクリックする受信ハンドラを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d5029-109">In the expanded adapter list, click **HTTP,** in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="d5029-110">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5029-110">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="d5029-111">をクリックして**プロパティ**にアクセスする、**バッチ サイズ**プロパティは、HTTP の受信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="d5029-111">Click **Properties** to access the **Batch size** property for the HTTP receive handler.</span></span>  
  
5.  <span data-ttu-id="d5029-112">1 から 256 に値を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d5029-112">Enter a value from 1 to 256 and click **OK**.</span></span>  
  
6.  <span data-ttu-id="d5029-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5029-113">Click **OK**.</span></span>  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="d5029-114"> は、単一メッセージを非常に高速に処理するのではなく、バッチ メッセージを効果的に処理するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d5029-114"> is designed to process batches of messages effectively and not to process a single message very quickly.</span></span> <span data-ttu-id="d5029-115">したがって、この受信ハンドラーを双方向 (要求 - 応答) の受信場所で使用する場合は、次の手順に従うことで、待機時間を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="d5029-115">So if this receive handler is going to be used for two way/request-response receive locations then you can minimize latency by following these steps:</span></span>  
  
-   <span data-ttu-id="d5029-116">設定、**バッチ サイズ**プロパティを 1 の値にします。</span><span class="sxs-lookup"><span data-stu-id="d5029-116">Set the **Batch size** property to a value of 1.</span></span>  
  
-   <span data-ttu-id="d5029-117">削減、 **MaxReceiveInterval** 500 の既定値から値を 100 未満の値を**Messaging Isolated、xlang/s では、**と**メッセージング インプロセス**サービスクラス。</span><span class="sxs-lookup"><span data-stu-id="d5029-117">Reduce the **MaxReceiveInterval** value from the default value of 500 to a value less than 100 for the **Messaging Isolated, XLANG/s,** and **Messaging In-Process** service classes.</span></span>  <span data-ttu-id="d5029-118">変更が加えられた、 **adm_ServiceClass**サービスの種類ごとに 1 つのレコードを含む BizTalk 管理データベースのテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d5029-118">Changes are made the **adm_ServiceClass** table of the BizTalk Management database, which contains one record for each of these service types.</span></span>  <span data-ttu-id="d5029-119">これは、サービスの種類全体の変更であるために、この設定を変更する場合は、注意を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5029-119">Use caution when changing this setting because this is a service-type-wide change.</span></span> <span data-ttu-id="d5029-120">この設定は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング エージェントが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースでメッセージをポーリングするときの最大ポーリング間隔 (ミリ秒) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5029-120">This setting specifies the maximum polling interval (in milliseconds) at which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messaging agent polls the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox database for messages.</span></span>  <span data-ttu-id="d5029-121">また、特定の負荷条件下でメッセージの制限が必要かどうかを制限コントローラーが判断する際にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5029-121">It also is used by the throttle controller to decide whether message throttling is needed under certain load conditions.</span></span> <span data-ttu-id="d5029-122">必要な場合、制限コントローラーは、システムのストレス条件に基づいてメッセージ ディスパッチの間隔を段階的に遅らせます。</span><span class="sxs-lookup"><span data-stu-id="d5029-122">If needed, the throttling controller will incrementally delay the message dispatch interval based upon stress conditions on the system.</span></span> <span data-ttu-id="d5029-123">高スループットのシステムでは、この設定は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d5029-123">In a high throughput system, this setting will not be used.</span></span>  <span data-ttu-id="d5029-124">ただし、一度この値を使用すると、MaxReceiveInteral/10 と MaxReceiveInterval の間で間隔が動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d5029-124">Once this values is used, however, the time interval will dynamically change between MaxReceiveInteral/10 and MaxReceiveInterval.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5029-125">この設定の変更で作成されるすべてのホストに影響を与える、**ホストの種類**の**Isolated**です。</span><span class="sxs-lookup"><span data-stu-id="d5029-125">Changing this setting affects all hosts that are created with a **Host Type** of **Isolated**.</span></span>  
  
-   <span data-ttu-id="d5029-126">構成済みの HTTP 受信機能に関連付けられている IIS アプリケーション プールを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d5029-126">Restart the IIS Application Pool(s) associated with any HTTP receive functions that you have configured.</span></span>  
  
 <span data-ttu-id="d5029-127">ログオン アカウント、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りが必要し、HTTP が使用する分離コード ファイルを動的にコンパイルする一時ディレクトリまたはディレクトリへの書き込み権限が関数を受信します。</span><span class="sxs-lookup"><span data-stu-id="d5029-127">The logon account for the **BizTalkServerIsolatedHost** host instance must have Read and Write permissions to the temp directory or directories to dynamically compile the code-behind files used by the HTTP receive function.</span></span> <span data-ttu-id="d5029-128">アクセス許可を与えるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5029-128">Use the following procedure to grant permissions.</span></span>  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a><span data-ttu-id="d5029-129">BizTalkServerIsolatedHost ホスト インスタンスのアカウントに、BizTalk Server の一時ディレクトリの読み取りアクセス許可と書き込みアクセス許可を与えるには</span><span class="sxs-lookup"><span data-stu-id="d5029-129">To grant the account for the BizTalkServerIsolatedHost host instance Read and Write permissions to the temp directory of your BizTalk server</span></span>  
  
1.  <span data-ttu-id="d5029-130">をクリックして**開始**、 をクリックして**実行**、型**CMD**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d5029-130">Click **Start**, click **Run**, type **CMD**, and press ENTER.</span></span>  
  
2.  <span data-ttu-id="d5029-131">コマンド プロンプトで次のように入力します。 **set TEMP**に関連付けられているディレクトリを表示するには ENTER キーを押すと、 **TEMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="d5029-131">At the command prompt, type **set TEMP** and press ENTER to display the directory associated with the **TEMP** environment variable.</span></span>  
  
3.  <span data-ttu-id="d5029-132">コマンド プロンプトで次のように入力します。 **set TMP**に関連付けられているディレクトリを表示するには ENTER キーを押すと、 **TMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="d5029-132">At the command prompt, type **set TMP** and press ENTER to display the directory associated with the **TMP** environment variable.</span></span>  
  
 <span data-ttu-id="d5029-133">ログオン アカウントとして指定されているアカウントに付与、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りおよび書き込みアクセス許可に関連付けられているディレクトリを**TEMP**と**TMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="d5029-133">Grant the account that is specified as the logon account for the **BizTalkServerIsolatedHost** host instance Read and Write permissions to the directory or directories associated with the **TEMP** and **TMP** environment variables.</span></span> <span data-ttu-id="d5029-134">ログオン アカウントを特定する、 **BizTalkServerIsolatedHost**インスタンスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックし、 **BizTalkServerIsolatedHost**ホスト右側のペインでインスタンス化し、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d5029-134">To determine the logon account for the **BizTalkServerIsolatedHost** instance, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click the **BizTalkServerIsolatedHost** host instance in the right pane, and then click **Properties**.</span></span> <span data-ttu-id="d5029-135">ホスト インスタンスで使用するログオン アカウントが横に表示されている、**ログオン**ラベル。</span><span class="sxs-lookup"><span data-stu-id="d5029-135">The logon account used for the host instance is listed next to the **Logon** label.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5029-136">参照</span><span class="sxs-lookup"><span data-stu-id="d5029-136">See Also</span></span>  
 [<span data-ttu-id="d5029-137">HTTP アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="d5029-137">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)