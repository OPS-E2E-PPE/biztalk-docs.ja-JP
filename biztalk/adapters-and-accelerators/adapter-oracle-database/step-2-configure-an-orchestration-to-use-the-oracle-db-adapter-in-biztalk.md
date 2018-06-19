---
title: '手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールで、オーケストレーションの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: b348a21a54ece0e5db736e18f60c9bed2b8d047d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215554"
---
# <a name="step-2-configure-the-orchestration-in-biztalk-server-administration-console-to-use-the-oracle-database-adapter"></a><span data-ttu-id="c8b6f-102">手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-102">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the Oracle Database adapter</span></span>
<span data-ttu-id="c8b6f-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="c8b6f-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="c8b6f-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="c8b6f-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="c8b6f-105">**目標:** このステップでは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-105">**Objective:** In this step, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c8b6f-106">WCF カスタムを作成する送信の受信ポートを使用して Oracle データベースからメッセージを送受信、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-106">Create a WCF-Custom send-receive port to send and receive messages from the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c8b6f-107">前の手順で作成したマップを使用するには、このポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-107">Configure this port to use the maps you created in the previous step.</span></span>  
  
-   <span data-ttu-id="c8b6f-108">オーケストレーションを構成する WCF カスタム ポートを使用する最後の手順で展開します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-108">Configure the orchestration you deployed in the last step to use the WCF-Custom port.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="c8b6f-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="c8b6f-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="c8b6f-110">WCF カスタム ポートを構成する場合、BizTalk オーケストレーションを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-110">You must have deployed the BizTalk orchestration for which you want to configure the WCF-Custom port.</span></span>  
  
### <a name="to-create-a-wcf-custom-port"></a><span data-ttu-id="c8b6f-111">WCF カスタム ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="c8b6f-111">To create a WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="c8b6f-112">Oracle データベースを使用して、操作のスキーマを生成すると[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、バインド ファイルが BizTalk プロジェクトにも追加します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-112">When you generate schema for an operation on the Oracle database using [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], a binding file is also added to the BizTalk project.</span></span> <span data-ttu-id="c8b6f-113">このバインド ファイルをインポートすることができますに、BizTalk WCF カスタムを作成するアプリケーションの送受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-113">You can import this binding file into your BizTalk application to create a WCF-Custom send-receive port.</span></span> <span data-ttu-id="c8b6f-114">バインド ファイルのインポート方法の詳細については、次を参照してください。[バインドのインポート](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f)です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-114">For instructions on importing a binding file, see [Importing Bindings](http://msdn.microsoft.com/library/4cac9267-8bd8-453b-96b4-5c038912463f).</span></span>  
  
2.  <span data-ttu-id="c8b6f-115">送信ポートが作成されたバインド ファイルをインポートした後、**送信ポート**BizTalk Server 管理コンソール内のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-115">After you import the binding file, a send port is created under the **Send Ports** folder in the BizTalk Server Administration console.</span></span>  
  
3.  <span data-ttu-id="c8b6f-116">WCF カスタム ポートを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-116">Right-click the WCF-Custom port and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c8b6f-117">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして、**全般**タブです。右側のウィンドウからをクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-117">From the left pane of the send port properties dialog box, click the **General** tab. From the right pane, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c8b6f-118">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、Oracle データベースへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-118">In the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and specify the credentials to connect to an Oracle database.</span></span>  
  
6.  <span data-ttu-id="c8b6f-119">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-119">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c8b6f-120">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**受信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-120">From the left pane of the send port properties dialog box, click **Inbound Maps**.</span></span> <span data-ttu-id="c8b6f-121">右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**ResponseMap**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-121">From the right pane, click the field under the **Map** column, and from the drop-down select **ResponseMap**.</span></span>  
  
     <span data-ttu-id="c8b6f-122">![受信マップを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span><span class="sxs-lookup"><span data-stu-id="c8b6f-122">![Configure inbound map](../../adapters-and-accelerators/adapter-oracle-database/media/a5e49da1-fe34-46fe-80ca-9316d217171a.gif "a5e49da1-fe34-46fe-80ca-9316d217171a")</span></span>  
  
8.  <span data-ttu-id="c8b6f-123">送信ポートのプロパティ ダイアログ ボックスの左ペインで、をクリックして**送信マップ**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-123">From the left pane of the send port properties dialog box, click **Outbound Maps**.</span></span> <span data-ttu-id="c8b6f-124">右側のペインの下のフィールドをクリックして、**マップ**列、およびドロップダウンの選択 から**RequestMap**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-124">From the right pane, click the field under the **Map** column, and from the drop-down select **RequestMap**.</span></span>  
  
     <span data-ttu-id="c8b6f-125">![送信マップを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span><span class="sxs-lookup"><span data-stu-id="c8b6f-125">![Configure outbound map](../../adapters-and-accelerators/adapter-oracle-database/media/697b23d8-4231-4718-8a52-8013fac35e3e.gif "697b23d8-4231-4718-8a52-8013fac35e3e")</span></span>  
  
9. <span data-ttu-id="c8b6f-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-126">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="c8b6f-127">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="c8b6f-127">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="c8b6f-128">BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-128">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="c8b6f-129">BizTalk アプリケーションを右クリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-129">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="c8b6f-130">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-130">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="c8b6f-131">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-131">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="c8b6f-132">下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-132">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="c8b6f-133">要求メッセージを削除するファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-133">Select the file port where you will drop a request message.</span></span> <span data-ttu-id="c8b6f-134">BizTalk オーケストレーションは、要求メッセージを消費し、Oracle データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-134">The BizTalk orchestration will consume the request message and send it to the Oracle database.</span></span>  
  
    2.  <span data-ttu-id="c8b6f-135">ファイル ポートを BizTalk オーケストレーションが Oracle データベースからの応答を含む応答メッセージをドロップする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-135">Select the file port where the BizTalk orchestration will drop the response message containing the response from the Oracle database.</span></span>  
  
    3.  <span data-ttu-id="c8b6f-136">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-136">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
    4.  <span data-ttu-id="c8b6f-137">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-137">Click **OK**.</span></span>  
  
     <span data-ttu-id="c8b6f-138">アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961)です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-138">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkID=196961](http://go.microsoft.com/fwlink/?LinkID=196961).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c8b6f-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="c8b6f-139">Next Steps</span></span>  
 <span data-ttu-id="c8b6f-140">WCF ベースを使用して Oracle データベースにメッセージを送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-140">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends messages to the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c8b6f-141">今すぐ」の説明に従って、Oracle データベースで挿入操作を実行する要求メッセージを送信することによって移行済みの BizTalk アプリケーションをテストする必要があります[手順 3: Oracle データベース アダプターに移行したアプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c8b6f-141">You must now test the migrated BizTalk application by sending a request message to perform an Insert operation on the Oracle database, as described in [Step 3: Test the migrated application to Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/step-3-test-the-migrated-application-to-oracle-database-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b6f-142">参照</span><span class="sxs-lookup"><span data-stu-id="c8b6f-142">See Also</span></span>  
 <span data-ttu-id="c8b6f-143">[チュートリアル: BizTalk プロジェクトを移行します。](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span><span class="sxs-lookup"><span data-stu-id="c8b6f-143">[Tutorial: Migrating BizTalk Projects](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)</span></span>