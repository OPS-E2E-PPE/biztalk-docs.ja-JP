---
title: '手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6152560-5ff0-4bdc-818c-e906b9642f52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6293758d9891d86e137d07e9735ce37162d6a96b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984027"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-using-the-sql-adapter"></a><span data-ttu-id="f58e0-102">手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>
<span data-ttu-id="f58e0-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="f58e0-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="f58e0-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="f58e0-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="f58e0-105">**目標:** この手順では、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="f58e0-106">WCF カスタム作成送受信ポートを使用して、SQL Server データベースからのメッセージの送受信、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-106">Create a WCF-Custom send-receive port to send and receive messages from the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f58e0-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="f58e0-108">オーケストレーションを構成する WCF カスタム ポートを使用する前の手順で展開されています。</span><span class="sxs-lookup"><span data-stu-id="f58e0-108">Configure the orchestration you deployed in the previous step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f58e0-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="f58e0-109">Prerequisites</span></span>  
 <span data-ttu-id="f58e0-110">」の説明に従って、WCF カスタム ポートを構成する BizTalk オーケストレーションを配置する必要がある[手順 1: vPrev BizTalk プロジェクトを SQL アダプターを使用して変更](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-110">You should have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port as described in [Step 1: Modify the vPrev BizTalk Project using the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md).</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="f58e0-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f58e0-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="f58e0-112">使用して SQL Server データベースで操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-112">When you generate schema for an operation on the SQL Server database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="f58e0-113">このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。</span><span class="sxs-lookup"><span data-stu-id="f58e0-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="f58e0-114">バインド ファイルのインポート方法の詳細については、[バインドのインポート](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f58e0-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/48de3a04-4ce8-4ba9-91b6-7e125689fd53).</span></span>  
  
2. <span data-ttu-id="f58e0-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**フォルダーで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="f58e0-115">After you import the binding file, a send port is created under the **Send Ports** folder in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
3. <span data-ttu-id="f58e0-116">WCF カスタム ポートを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="f58e0-117">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="f58e0-118">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブで、SQL Server データベースに接続し、をクリックし、資格情報を指定します。 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, specify the credentials to connect to a SQL Server database, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="f58e0-119">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-119">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="f58e0-120">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="f58e0-120">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="f58e0-121">![受信マップを構成する](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span><span class="sxs-lookup"><span data-stu-id="f58e0-121">![Configure inbound map](../../adapters-and-accelerators/adapter-sql/media/21e5a23c-7319-4324-8f09-52118ebeeea9.gif "21e5a23c-7319-4324-8f09-52118ebeeea9")</span></span>  
  
7. <span data-ttu-id="f58e0-122">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-122">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="f58e0-123">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="f58e0-123">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="f58e0-124">![送信マップの構成](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span><span class="sxs-lookup"><span data-stu-id="f58e0-124">![Configure outbound map](../../adapters-and-accelerators/adapter-sql/media/5b54e09b-8784-4df6-a279-e8aed813114e.gif "5b54e09b-8784-4df6-a279-e8aed813114e")</span></span>  
  
8. <span data-ttu-id="f58e0-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f58e0-125">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="f58e0-126">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="f58e0-126">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="f58e0-127">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-127">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="f58e0-128">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-128">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="f58e0-129">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f58e0-129">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="f58e0-130">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-130">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="f58e0-131">下、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートをマップで物理ポートに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="f58e0-131">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
   1.  <span data-ttu-id="f58e0-132">File ポートを要求メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-132">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="f58e0-133">BizTalk オーケストレーションは要求メッセージを使用し、SQL Server データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-133">The BizTalk orchestration will consume the request message and send it to the SQL Server database.</span></span>  
  
   2.  <span data-ttu-id="f58e0-134">File ポートを BizTalk オーケストレーションが、SQL Server データベースからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-134">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SQL Server database.</span></span>  
  
   3.  <span data-ttu-id="f58e0-135">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-135">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4.  <span data-ttu-id="f58e0-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f58e0-136">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f58e0-137">次の手順</span><span class="sxs-lookup"><span data-stu-id="f58e0-137">Next Steps</span></span>  
 <span data-ttu-id="f58e0-138">WCF ベースを使用して SQL Server データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-138">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SQL Server database using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="f58e0-139">」の説明に従って、SQL Server データベースに対して、挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3: SQL アダプタを使用する移行されたアプリケーションをテスト](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-139">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the SQL Server database, as described in [Step 3: Test the Migrated Application that uses the SQL adapter](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f58e0-140">参照</span><span class="sxs-lookup"><span data-stu-id="f58e0-140">See Also</span></span>  
 [<span data-ttu-id="f58e0-141">チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="f58e0-141">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)