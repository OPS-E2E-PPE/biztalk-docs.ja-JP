---
title: '手順 2: BizTalk Server 管理コンソール 1 で、オーケストレーションの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 1783e56891ffd6d5d27058eab1df8a60663f481b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217714"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console"></a><span data-ttu-id="d5279-102">手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d5279-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>
<span data-ttu-id="d5279-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="d5279-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="d5279-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="d5279-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="d5279-105">**目標:** このステップでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5279-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="d5279-106">作成、Wcf-custom 送信-受信ポートを使用して SAP システムからメッセージを送受信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d5279-106">Create a WCF-Custom send-receive port to send and receive messages from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="d5279-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d5279-107">Configure this port to use the maps that you created in the previous step.</span></span>  
  
-   <span data-ttu-id="d5279-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。</span><span class="sxs-lookup"><span data-stu-id="d5279-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="d5279-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="d5279-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="d5279-110">WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d5279-110">Deploy the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="d5279-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="d5279-111">To create a WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="d5279-112">使用して、RFC のスキーマを生成すると、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="d5279-112">When you generate schema for an RFC using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="d5279-113">このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="d5279-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="d5279-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf)です。</span><span class="sxs-lookup"><span data-stu-id="d5279-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/c927efde-29bd-4efe-9da5-942e7da65dbf).</span></span>  
  
2.  <span data-ttu-id="d5279-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d5279-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3.  <span data-ttu-id="d5279-116">WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-116">Right-click the WCF-Custom port, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="d5279-117">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="d5279-118">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5279-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
6.  <span data-ttu-id="d5279-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5279-119">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d5279-120">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="d5279-121">右側のペインの下のフィールドをクリックして、**マップ**列で、ドロップダウン リストから選択して**ResponseMap**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-121">From the right pane, click the field under the **Map** column, and from the drop-down, select **ResponseMap**.</span></span>  
  
     <span data-ttu-id="d5279-122">![WCF カスタム ポートで受信マップを構成する](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span><span class="sxs-lookup"><span data-stu-id="d5279-122">![Configure the inbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/10129a7d-211b-464b-b05a-b3ea72f46873.gif "10129a7d-211b-464b-b05a-b3ea72f46873")</span></span>  
  
8.  <span data-ttu-id="d5279-123">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップします。**</span><span class="sxs-lookup"><span data-stu-id="d5279-123">From the left pane of the send port properties dialog box, click **Outbound Maps.**</span></span> <span data-ttu-id="d5279-124">右側のペインの下のフィールドをクリックして、**マップ**列で、ドロップダウン リストから選択して**RequestMap**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-124">From the right pane, click the field under the **Map** column, and from the drop-down, select **RequestMap**.</span></span>  
  
     <span data-ttu-id="d5279-125">![WCF カスタム ポートで送信マップを構成する](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span><span class="sxs-lookup"><span data-stu-id="d5279-125">![Configure the outbound map on the WCF custom port](../../adapters-and-accelerators/adapter-sap/media/4ffcb4cd-4f53-4b67-92e2-3225d15d97ee.gif "4ffcb4cd-4f53-4b67-92e2-3225d15d97ee")</span></span>  
  
9. <span data-ttu-id="d5279-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5279-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="d5279-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="d5279-127">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="d5279-128">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**、し、オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="d5279-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and then expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="d5279-129">BizTalk アプリケーションを右クリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="d5279-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="d5279-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5279-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="d5279-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5279-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="d5279-132">下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="d5279-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="d5279-133">要求メッセージを削除するファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5279-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="d5279-134">BizTalk オーケストレーションは、要求メッセージを消費し、SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="d5279-134">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="d5279-135">ファイル ポートを BizTalk オーケストレーションが SAP システムからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5279-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
    3.  <span data-ttu-id="d5279-136">このトピックの前半で作成した、wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5279-136">Select the WCF-custom send port you created earlier in this topic.</span></span>  
  
    4.  <span data-ttu-id="d5279-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5279-137">Click **OK**.</span></span>  
  
     <span data-ttu-id="d5279-138">アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。</span><span class="sxs-lookup"><span data-stu-id="d5279-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5279-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="d5279-139">Next Steps</span></span>  
 <span data-ttu-id="d5279-140">WCF ベースを使用して SAP システムにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d5279-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="d5279-141">今すぐ」の説明に従って、SD_RFC_CUSTOMER_GET RFC を呼び出すための要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)です。</span><span class="sxs-lookup"><span data-stu-id="d5279-141">You must now test the migrated BizTalk application by sending a request message to invoke the SD_RFC_CUSTOMER_GET RFC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5279-142">参照</span><span class="sxs-lookup"><span data-stu-id="d5279-142">See Also</span></span>  
 [<span data-ttu-id="d5279-143">チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。</span><span class="sxs-lookup"><span data-stu-id="d5279-143">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)