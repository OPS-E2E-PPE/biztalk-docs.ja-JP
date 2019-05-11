---
title: HTTP 受信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0aec49f0334a62e559c0812a7b44029c25b4c95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386448"
---
# <a name="how-to-configure-an-http-receive-handler"></a><span data-ttu-id="c05d8-102">HTTP 受信ハンドラを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c05d8-102">How to Configure an HTTP Receive Handler</span></span>
<span data-ttu-id="c05d8-103">受信ハンドラーを HTTP のプロパティを構成する次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-103">Use the following procedure to configure the properties for an HTTP receive handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c05d8-104">各ホストは、1 つだけの受信ハンドラーが関連付けられていることができます。</span><span class="sxs-lookup"><span data-stu-id="c05d8-104">Each host can have only one receive handler associated with it.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="c05d8-105">HTTP では、BizTalk 分離ホスト インスタンスのコンテキストでアダプターの実行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c05d8-105">The HTTP receive adapter runs in the context of a BizTalk Isolated Host instance.</span></span>  
> 
> [!CAUTION]
>  <span data-ttu-id="c05d8-106">HTTP または SOAP アダプタ ハンドラを使用する場合は、Microsoft では、これらのハンドラーのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="c05d8-106">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] computers.</span></span>  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a><span data-ttu-id="c05d8-107">HTTP の [全般] プロパティの受信ハンドラを構成するには</span><span class="sxs-lookup"><span data-stu-id="c05d8-107">To configure the general properties for an HTTP receive handler</span></span>  
  
1. <span data-ttu-id="c05d8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="c05d8-109">展開したアダプターの一覧でクリックして**HTTP、** 受信ハンドラを構成するをクリックするを右クリックし、右側のウィンドウで**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-109">In the expanded adapter list, click **HTTP,** in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="c05d8-110">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-110">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4. <span data-ttu-id="c05d8-111">クリックして**プロパティ**にアクセスする、**バッチ サイズ**プロパティは、HTTP の受信ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="c05d8-111">Click **Properties** to access the **Batch size** property for the HTTP receive handler.</span></span>  
  
5. <span data-ttu-id="c05d8-112">1 から 256 に値を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-112">Enter a value from 1 to 256 and click **OK**.</span></span>  
  
6. <span data-ttu-id="c05d8-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c05d8-113">Click **OK**.</span></span>  
  
   <span data-ttu-id="c05d8-114">BizTalk Server では、メッセージのバッチを効果的に処理して、1 つのメッセージを非常に高速処理を行わないように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c05d8-114">BizTalk Server is designed to process batches of messages effectively and not to process a single message very quickly.</span></span> <span data-ttu-id="c05d8-115">ように、ハンドラーが 2 つを使用しようとしている場合、この受信方向または要求-応答の受信場所、次の手順の待機時間を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="c05d8-115">So if this receive handler is going to be used for two way/request-response receive locations then you can minimize latency by following these steps:</span></span>  
  
- <span data-ttu-id="c05d8-116">設定、**バッチ サイズ**プロパティ値の 1 にします。</span><span class="sxs-lookup"><span data-stu-id="c05d8-116">Set the **Batch size** property to a value of 1.</span></span>  
  
- <span data-ttu-id="c05d8-117">削減、 **MaxReceiveInterval** 500 の既定値から値を 100 未満の値を**Messaging Isolated、xlang/s では、** と**In-process**サービスクラス。</span><span class="sxs-lookup"><span data-stu-id="c05d8-117">Reduce the **MaxReceiveInterval** value from the default value of 500 to a value less than 100 for the **Messaging Isolated, XLANG/s,** and **Messaging In-Process** service classes.</span></span>  <span data-ttu-id="c05d8-118">変更が加えられた、 **adm_ServiceClass**サービスの種類ごとに 1 つのレコードを含む BizTalk 管理データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="c05d8-118">Changes are made the **adm_ServiceClass** table of the BizTalk Management database, which contains one record for each of these service types.</span></span>  <span data-ttu-id="c05d8-119">これはサービスの種類全体の変更のため、この設定を変更する場合は、注意を使用します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-119">Use caution when changing this setting because this is a service-type-wide change.</span></span> <span data-ttu-id="c05d8-120">この設定を指定します (ミリ秒単位) の最大ポーリング間隔、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージング エージェント、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージをメッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="c05d8-120">This setting specifies the maximum polling interval (in milliseconds) at which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messaging agent polls the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messagebox database for messages.</span></span>  <span data-ttu-id="c05d8-121">また、使用されますスロットル コント ローラーによって負荷条件下でメッセージの制限が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-121">It also is used by the throttle controller to decide whether message throttling is needed under certain load conditions.</span></span> <span data-ttu-id="c05d8-122">必要な場合、制限コント ローラーは、システムのストレス条件に基づいてメッセージ ディスパッチの間隔を遅延増分します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-122">If needed, the throttling controller will incrementally delay the message dispatch interval based upon stress conditions on the system.</span></span> <span data-ttu-id="c05d8-123">高スループットのシステムでは、この設定は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c05d8-123">In a high throughput system, this setting will not be used.</span></span>  <span data-ttu-id="c05d8-124">この値が使用されると、ただし、時間間隔が動的に変更と、maxreceiveinteral/10 と MaxReceiveInterval の間。</span><span class="sxs-lookup"><span data-stu-id="c05d8-124">Once this values is used, however, the time interval will dynamically change between MaxReceiveInteral/10 and MaxReceiveInterval.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c05d8-125">この設定を変更するで作成されたすべてのホストに影響を**ホストの種類**の**Isolated**します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-125">Changing this setting affects all hosts that are created with a **Host Type** of **Isolated**.</span></span>  
  
- <span data-ttu-id="c05d8-126">再起動を任意の HTTP に関連付けられている IIS アプリケーション プールに構成されている関数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c05d8-126">Restart the IIS Application Pool(s) associated with any HTTP receive functions that you have configured.</span></span>  
  
  <span data-ttu-id="c05d8-127">ログオン アカウント、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りが必要し、HTTP が使用する分離コード ファイルを動的にコンパイルする一時ディレクトリまたはディレクトリに書き込みアクセス許可は、関数を受信します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-127">The logon account for the **BizTalkServerIsolatedHost** host instance must have Read and Write permissions to the temp directory or directories to dynamically compile the code-behind files used by the HTTP receive function.</span></span> <span data-ttu-id="c05d8-128">次の手順を使用して、アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-128">Use the following procedure to grant permissions.</span></span>  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a><span data-ttu-id="c05d8-129">Biztalkserverisolatedhost アカウントに付与するには、ホスト インスタンスの読み取りし、BizTalk server の一時ディレクトリに対する書き込みアクセス許可</span><span class="sxs-lookup"><span data-stu-id="c05d8-129">To grant the account for the BizTalkServerIsolatedHost host instance Read and Write permissions to the temp directory of your BizTalk server</span></span>  
  
1. <span data-ttu-id="c05d8-130">クリックして**開始**、 をクリックして**実行**、型**CMD**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-130">Click **Start**, click **Run**, type **CMD**, and press ENTER.</span></span>  
  
2. <span data-ttu-id="c05d8-131">コマンド プロンプトで「 **TEMP 設定**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TEMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="c05d8-131">At the command prompt, type **set TEMP** and press ENTER to display the directory associated with the **TEMP** environment variable.</span></span>  
  
3. <span data-ttu-id="c05d8-132">コマンド プロンプトで「 **set TMP**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="c05d8-132">At the command prompt, type **set TMP** and press ENTER to display the directory associated with the **TMP** environment variable.</span></span>  
  
   <span data-ttu-id="c05d8-133">ログオン アカウントとして指定されているアカウントに付与、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りと書き込みアクセス許可に関連付けられているディレクトリを**TEMP**と**TMP**環境変数。</span><span class="sxs-lookup"><span data-stu-id="c05d8-133">Grant the account that is specified as the logon account for the **BizTalkServerIsolatedHost** host instance Read and Write permissions to the directory or directories associated with the **TEMP** and **TMP** environment variables.</span></span> <span data-ttu-id="c05d8-134">ログオン アカウントを特定する、 **BizTalkServerIsolatedHost**インスタンスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックし、 **BizTalkServerIsolatedHost**ホスト右側のペインでインスタンスをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c05d8-134">To determine the logon account for the **BizTalkServerIsolatedHost** instance, in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click the **BizTalkServerIsolatedHost** host instance in the right pane, and then click **Properties**.</span></span> <span data-ttu-id="c05d8-135">ホスト インスタンスを使用するログオン アカウントが横に表示されます、**ログオン**ラベル。</span><span class="sxs-lookup"><span data-stu-id="c05d8-135">The logon account used for the host instance is listed next to the **Logon** label.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05d8-136">参照</span><span class="sxs-lookup"><span data-stu-id="c05d8-136">See Also</span></span>  
 [<span data-ttu-id="c05d8-137">HTTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="c05d8-137">Configuring the HTTP Adapter</span></span>](../core/configuring-the-http-adapter.md)