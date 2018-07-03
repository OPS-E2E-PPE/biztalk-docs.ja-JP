---
title: '手順 2: Siebel アダプターと BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft Docs'
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
ms.openlocfilehash: f779c9b347c43fb9bd2a6dcdbdb3c33ac8ad09c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009131"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-with-the-siebel-adapter"></a><span data-ttu-id="065df-102">手順 2: Siebel アダプターと BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="065df-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console with the Siebel adapter</span></span>
<span data-ttu-id="065df-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="065df-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="065df-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="065df-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="065df-105">**目標:** この手順では、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="065df-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="065df-106">WCF カスタム作成を使用して Siebel システムからメッセージを送受信ポートの送信、受信、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="065df-106">Create a WCF-Custom send-receive port to send and receive messages from the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="065df-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="065df-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="065df-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開されています。</span><span class="sxs-lookup"><span data-stu-id="065df-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="065df-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="065df-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="065df-110">WCF カスタム ポートを構成する BizTalk オーケストレーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="065df-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="065df-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="065df-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="065df-112">使用して Siebel システムで操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="065df-112">When you generate schema for an operation on the Siebel system using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="065df-113">このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。</span><span class="sxs-lookup"><span data-stu-id="065df-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="065df-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372)します。</span><span class="sxs-lookup"><span data-stu-id="065df-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/908ab90c-2ba2-4c65-9f74-10579f06e372).</span></span>  
  
2. <span data-ttu-id="065df-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="065df-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="065df-116">WCF カスタム ポートを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="065df-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="065df-117">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。</span><span class="sxs-lookup"><span data-stu-id="065df-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="065df-118">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、Siebel システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="065df-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and specify the credentials to connect to a Siebel system.</span></span>  
  
6. <span data-ttu-id="065df-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="065df-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="065df-120">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="065df-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="065df-121">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="065df-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="065df-122">![受信マップを構成する](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span><span class="sxs-lookup"><span data-stu-id="065df-122">![Configure inbound map](../../adapters-and-accelerators/adapter-siebel/media/e1ceee98-9f10-40f1-a611-88d3a2c102a9.gif "e1ceee98-9f10-40f1-a611-88d3a2c102a9")</span></span>  
  
8. <span data-ttu-id="065df-123">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="065df-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="065df-124">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="065df-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="065df-125">![送信マップの構成](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span><span class="sxs-lookup"><span data-stu-id="065df-125">![Configure outbound map](../../adapters-and-accelerators/adapter-siebel/media/8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9.gif "8f8efeaa-d5cd-4ed3-b2f3-a600c48c3bb9")</span></span>  
  
9. <span data-ttu-id="065df-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="065df-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="065df-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="065df-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="065df-128">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="065df-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="065df-129">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="065df-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="065df-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="065df-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="065df-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="065df-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="065df-132">で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="065df-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="065df-133">File ポートを要求メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="065df-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="065df-134">BizTalk オーケストレーションは要求メッセージを使用し、Siebel システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="065df-134">The BizTalk orchestration will consume the request message and send it to the Siebel system.</span></span>  
  
   2. <span data-ttu-id="065df-135">File ポートを BizTalk オーケストレーションで Siebel システムからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="065df-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Siebel system.</span></span>  
  
   3. <span data-ttu-id="065df-136">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="065df-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="065df-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="065df-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="065df-138">アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。</span><span class="sxs-lookup"><span data-stu-id="065df-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="065df-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="065df-139">Next Steps</span></span>  
 <span data-ttu-id="065df-140">WCF ベースを使用して Siebel システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="065df-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="065df-141">」の説明に従って、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3: Siebel アダプターを使用した移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="065df-141">You must now test the migrated BizTalk application by sending a request message to invoke the Insert operation on the Account business component, as described in [Step 3: Test the Migrated Application with the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065df-142">参照</span><span class="sxs-lookup"><span data-stu-id="065df-142">See Also</span></span>  
 [<span data-ttu-id="065df-143">チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="065df-143">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)