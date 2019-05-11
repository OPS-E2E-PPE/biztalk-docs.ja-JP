---
title: 手順 2:Oracle データベース アダプターを使用する BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 598b4ab0-ff22-4dfa-aa9c-774c60c90227
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 113d1b90f02961fd8ecdf5fd7ecc894e664b3796
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375997"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a><span data-ttu-id="c5fc8-102">手順 2:Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter</span></span>
<span data-ttu-id="c5fc8-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="c5fc8-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="c5fc8-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="c5fc8-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="c5fc8-105">**目標:** この手順では、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
- <span data-ttu-id="c5fc8-106">WCF カスタム作成を使用して Oracle データベースからメッセージを送受信ポートの送信の受信、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-106">Create a WCF-Custom send-receive port to send and receive messages from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c5fc8-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
- <span data-ttu-id="c5fc8-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開されています。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="c5fc8-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="c5fc8-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="c5fc8-110">WCF カスタム ポートを構成する BizTalk オーケストレーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="c5fc8-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="c5fc8-111">To create a WCF-Custom port</span></span>  
  
1. <span data-ttu-id="c5fc8-112">使用して Oracle データベースで操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-112">When you generate schema for an operation on the Oracle database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="c5fc8-113">このバインド ファイルをインポートすることに、BizTalk WCF カスタムを作成するアプリケーション送信-受信ポート。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="c5fc8-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f).</span></span>  
  
2. <span data-ttu-id="c5fc8-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3. <span data-ttu-id="c5fc8-116">WCF カスタム ポートを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-116">Right-click the WCF-Custom port and click **Properties**.</span></span>  
  
4. <span data-ttu-id="c5fc8-117">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウからをクリックして、**全般**タブ。右側のウィンドウから次のようにクリックします。**構成**します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5. <span data-ttu-id="c5fc8-118">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、Oracle データベースへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an Oracle database.</span></span>  
  
6. <span data-ttu-id="c5fc8-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-119">Click **OK**.</span></span>  
  
7. <span data-ttu-id="c5fc8-120">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**受信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="c5fc8-121">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**ResponseMap**。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
    <span data-ttu-id="c5fc8-122">![受信マップを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span><span class="sxs-lookup"><span data-stu-id="c5fc8-122">![Configure inbound map](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span></span>  
  
8. <span data-ttu-id="c5fc8-123">送信ポートのプロパティ ダイアログ ボックスの左側のウィンドウから次のようにクリックします。**送信マップ**します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="c5fc8-124">右側のペインの下のフィールドをクリックします。、**マップ**列、およびドロップダウンの選択から**RequestMap**。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
    <span data-ttu-id="c5fc8-125">![送信マップの構成](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span><span class="sxs-lookup"><span data-stu-id="c5fc8-125">![Configure outbound map](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span></span>  
  
9. <span data-ttu-id="c5fc8-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="c5fc8-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="c5fc8-127">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="c5fc8-128">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="c5fc8-129">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="c5fc8-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="c5fc8-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="c5fc8-132">で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="c5fc8-133">File ポートを要求メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="c5fc8-134">BizTalk オーケストレーションは要求メッセージを使用し、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-134">The BizTalk orchestration will consume the request message and send it to the Oracle database.</span></span>  
  
   2. <span data-ttu-id="c5fc8-135">File ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Oracle database.</span></span>  
  
   3. <span data-ttu-id="c5fc8-136">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   4. <span data-ttu-id="c5fc8-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-137">Click **OK**.</span></span>  
  
      <span data-ttu-id="c5fc8-138">アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c5fc8-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="c5fc8-139">Next Steps</span></span>  
 <span data-ttu-id="c5fc8-140">WCF ベースを使用して Oracle データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c5fc8-141">」の説明に従って、Oracle データベースに対して、挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションを今すぐテストする必要があります[手順 3。Oracle データベース アダプターに移行したアプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5fc8-141">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the Oracle database, as described in [Step 3: Test the migrated application to Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5fc8-142">参照</span><span class="sxs-lookup"><span data-stu-id="c5fc8-142">See Also</span></span>  
 <span data-ttu-id="c5fc8-143">[チュートリアル: BizTalk プロジェクトの移行](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="c5fc8-143">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>