---
title: 手順 2:BizTalk Server 管理コンソール 1 で、オーケストレーションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration, configruing in BizTalk Server Administration console
- WCF-Custom port, creating
- migration
ms.assetid: fb057bce-5702-4ea0-8ed5-e299d3a78a11
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8759066ddc73af71b069d8ef9fa20a23a67416e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372830"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a><span data-ttu-id="e98f5-102">手順 2:BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>
<span data-ttu-id="e98f5-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="e98f5-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="e98f5-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="e98f5-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="e98f5-105">**目標:** この手順では、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="e98f5-106">WCF カスタム作成を使用して SAP システムからメッセージを送受信ポートの送信の受信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-106">Create a WCF-Custom send-receive port to send and receive messages from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="e98f5-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-107">Configure this port to use the maps that you created in the previous step.</span></span>  
  
- <span data-ttu-id="e98f5-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開されています。</span><span class="sxs-lookup"><span data-stu-id="e98f5-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="e98f5-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="e98f5-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="e98f5-110">WCF カスタム ポートを構成する BizTalk オーケストレーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-110">Deploy the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="e98f5-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="e98f5-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="e98f5-112">使用して、RFC のスキーマを生成すると、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-112">When you generate schema for an RFC using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="e98f5-113">このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。</span><span class="sxs-lookup"><span data-stu-id="e98f5-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="e98f5-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf)します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf).</span></span>  
  
2. <span data-ttu-id="e98f5-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="e98f5-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="e98f5-116">WCF カスタム ポートを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="e98f5-117">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="e98f5-118">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
6. <span data-ttu-id="e98f5-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e98f5-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="e98f5-120">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="e98f5-121">右側のペインの下のフィールドをクリックします。、**マップ**列で、ドロップダウン リストから選択します。 **ResponseMap**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-121">From the right pane, click the field under the **Map** column, and from the drop-down, select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="e98f5-122">![WCF カスタム ポートで受信マップの構成](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span><span class="sxs-lookup"><span data-stu-id="e98f5-122">![Configure the inbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span></span>  
  
8. <span data-ttu-id="e98f5-123">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップします。**</span><span class="sxs-lookup"><span data-stu-id="e98f5-123">From the left pane of the send port properties dialog box, click **Outbound Maps.**</span></span> <span data-ttu-id="e98f5-124">右側のペインの下のフィールドをクリックします。、**マップ**列で、ドロップダウン リストから選択します。 **RequestMap**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-124">From the right pane, click the field under the **Map** column, and from the drop-down, select **RequestMap**.</span></span>  
  
    <span data-ttu-id="e98f5-125">![WCF カスタム ポートで送信マップの構成](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span><span class="sxs-lookup"><span data-stu-id="e98f5-125">![Configure the outbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span></span>  
  
9. <span data-ttu-id="e98f5-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e98f5-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="e98f5-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="e98f5-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="e98f5-128">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="e98f5-129">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="e98f5-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e98f5-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="e98f5-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="e98f5-132">で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="e98f5-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="e98f5-133">File ポートを要求メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="e98f5-134">BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-134">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
   2. <span data-ttu-id="e98f5-135">File ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
   3. <span data-ttu-id="e98f5-136">このトピックの前半で作成した、wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-136">Select the WCF-custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="e98f5-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e98f5-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="e98f5-138">アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e98f5-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="e98f5-139">Next Steps</span></span>  
 <span data-ttu-id="e98f5-140">WCF ベースを使用して SAP システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="e98f5-141">」の説明に従って、SD_RFC_CUSTOMER_GET RFC を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3。移行したアプリケーションをテスト](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)します。</span><span class="sxs-lookup"><span data-stu-id="e98f5-141">You must now test the migrated BizTalk application by sending a request message to invoke the SD_RFC_CUSTOMER_GET RFC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98f5-142">参照</span><span class="sxs-lookup"><span data-stu-id="e98f5-142">See Also</span></span>  
 [<span data-ttu-id="e98f5-143">チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="e98f5-143">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)