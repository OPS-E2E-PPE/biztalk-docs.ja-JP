---
title: '手順 2: Siebel アダプターと BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41338723-055d-46b4-acee-6969ea79fac0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0ed6c6609ccca3d13ea0eba46f9e2d0ee6cc14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222642"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a><span data-ttu-id="1c224-102">手順 2: BizTalk Server 管理コンソールで Siebel アダプターとオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c224-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console with the Siebel adapter</span></span>
<span data-ttu-id="1c224-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="1c224-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="1c224-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="1c224-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="1c224-105">**目標:** このステップでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c224-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="1c224-106">作成、Wcf-custom 送信-受信ポートを使用して、Siebel システムからメッセージを送受信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1c224-106">Create a WCF-Custom send-receive port to send and receive messages from the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="1c224-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c224-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
-   <span data-ttu-id="1c224-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。</span><span class="sxs-lookup"><span data-stu-id="1c224-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="1c224-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="1c224-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="1c224-110">WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c224-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="1c224-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="1c224-111">To create a WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="1c224-112">Siebel システムを使用して、操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="1c224-112">When you generate schema for an operation on the Siebel system using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="1c224-113">このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="1c224-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="1c224-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)です。</span><span class="sxs-lookup"><span data-stu-id="1c224-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372).</span></span>  
  
2.  <span data-ttu-id="1c224-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1c224-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3.  <span data-ttu-id="1c224-116">WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1c224-117">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="1c224-118">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、Siebel システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c224-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and specify the credentials to connect to a Siebel system.</span></span>  
  
6.  <span data-ttu-id="1c224-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c224-119">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="1c224-120">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="1c224-121">右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**ResponseMap**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
     <span data-ttu-id="1c224-122">![受信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span><span class="sxs-lookup"><span data-stu-id="1c224-122">![Configure inbound map](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span></span>  
  
8.  <span data-ttu-id="1c224-123">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="1c224-124">右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**RequestMap**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
     <span data-ttu-id="1c224-125">![送信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span><span class="sxs-lookup"><span data-stu-id="1c224-125">![Configure outbound map](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span></span>  
  
9. <span data-ttu-id="1c224-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c224-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="1c224-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="1c224-127">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="1c224-128">BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="1c224-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="1c224-129">BizTalk アプリケーションを右クリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="1c224-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="1c224-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c224-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="1c224-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c224-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="1c224-132">下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="1c224-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="1c224-133">要求メッセージを削除するファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c224-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="1c224-134">BizTalk オーケストレーションは、要求メッセージを消費し、Siebel システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="1c224-134">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
    2.  <span data-ttu-id="1c224-135">ファイル ポートを BizTalk オーケストレーションが Siebel システムからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c224-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
    3.  <span data-ttu-id="1c224-136">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="1c224-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
    4.  <span data-ttu-id="1c224-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c224-137">Click **OK**.</span></span>  
  
     <span data-ttu-id="1c224-138">アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。</span><span class="sxs-lookup"><span data-stu-id="1c224-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1c224-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="1c224-139">Next Steps</span></span>  
 <span data-ttu-id="1c224-140">WCF ベースを使用して、Siebel システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1c224-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="1c224-141">今すぐ」の説明に従って、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: アプリケーションをテストする移行 Siebel アダプターと](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="1c224-141">You must now test the migrated BizTalk application by sending a request message to invoke the Insert operation on the Account business component, as described in [Step 3: Test the Migrated Application with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c224-142">参照</span><span class="sxs-lookup"><span data-stu-id="1c224-142">See Also</span></span>  
 [<span data-ttu-id="1c224-143">チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="1c224-143">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)