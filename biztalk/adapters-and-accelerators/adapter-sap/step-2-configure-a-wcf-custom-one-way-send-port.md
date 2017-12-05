---
title: "手順 2: Wcf-custom 一方向送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aab14799076d3f774130b357ab90c5ed5335f4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="32629-102">手順 2: Wcf-custom 一方向送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="32629-102">Step 2: Configure a WCF-Custom One-way Send Port</span></span>
<span data-ttu-id="32629-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="32629-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="32629-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="32629-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="32629-105">**目標:**このステップで、フラット ファイル IDOC を SAP システムに送信する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="32629-105">**Objective:** In this step, you configure a WCF-Custom port to send the flat-file IDOC to an SAP system.</span></span> <span data-ttu-id="32629-106">ポートを構成した後は、Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="32629-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32629-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="32629-107">Prerequisites</span></span>  
 <span data-ttu-id="32629-108">構築し、SAP システムに Idoc を送信する vPrev BizTalk プロジェクトを展開した必要があります。</span><span class="sxs-lookup"><span data-stu-id="32629-108">You must have built and deployed your vPrev BizTalk project to send IDOCs to an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="32629-109">Wcf-custom 一方向の送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="32629-109">To configure a WCF-Custom one-way send port</span></span>  
  
1.  <span data-ttu-id="32629-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="32629-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="32629-111">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="32629-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="32629-112">送信ポートを作成するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="32629-112">Expand the application under which you want to create the send port.</span></span>  
  
4.  <span data-ttu-id="32629-113">右クリック**送信ポート**、指す**新規**、 をクリック**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="32629-113">Right-click **Send Ports**, point to **New**, and click **Static One-way Send Port**.</span></span>  
  
5.  <span data-ttu-id="32629-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="32629-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="32629-115">**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="32629-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="32629-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="32629-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="32629-117">クリックして、**全般**] タブで、し、[、**アドレス (URI)**フィールドで、接続、SAP システムにメッセージを送信する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="32629-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to send messages to the SAP system.</span></span> <span data-ttu-id="32629-118">接続 URI の詳細については、次を参照してください。 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="32629-118">For more information about the connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
         <span data-ttu-id="32629-119">![送信ポートで指定された接続 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span><span class="sxs-lookup"><span data-stu-id="32629-119">![Connection URI specified in the send port](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span></span>  
  
    2.  <span data-ttu-id="32629-120">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="32629-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="32629-121">フラット ファイル IDOC を送信するを使用する必要があります、 **SendIdoc** WCF ベースによって公開される操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="32629-121">To send a flat-file IDOC, you must use the **SendIdoc** operation exposed by the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="32629-122">**SendIdoc**操作により、弱い型指定のスキーマが Idoc を送信するクライアントはアダプターです。</span><span class="sxs-lookup"><span data-stu-id="32629-122">**SendIdoc** operation enables adapter clients to send IDOCs having a weakly-typed schema.</span></span> <span data-ttu-id="32629-123">詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="32629-123">For more information, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span> <span data-ttu-id="32629-124">次の図に示しています、**アクション**のアクションを含むテキスト ボックス、 **SendIdoc**操作します。</span><span class="sxs-lookup"><span data-stu-id="32629-124">The following figure shows the **Action** text box with the action for the **SendIdoc** operation.</span></span>  
  
         <span data-ttu-id="32629-125">![送信ポートでアクションの指定](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span><span class="sxs-lookup"><span data-stu-id="32629-125">![Specify action in the send port](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span></span>  
  
    3.  <span data-ttu-id="32629-126">クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。</span><span class="sxs-lookup"><span data-stu-id="32629-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
    4.  <span data-ttu-id="32629-127">クリックして、**資格情報**タブし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="32629-127">Click the **Credentials** tab and specify the credentials to connect to an SAP system.</span></span>  
  
    5.  <span data-ttu-id="32629-128">クリックして、**メッセージ**] タブで、し、[、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。</span><span class="sxs-lookup"><span data-stu-id="32629-128">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
    6.  <span data-ttu-id="32629-129">**XML**テキスト ボックスで、WCF メッセージを構築するために使用されるテンプレートを指定します。</span><span class="sxs-lookup"><span data-stu-id="32629-129">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="32629-130">これによりに準拠したメッセージを作成する、 **SendIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="32629-130">By doing so, you create a message that conforms to the **SendIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="32629-131">メッセージの構造の詳細については、 **SendIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="32629-131">For more information about the message structure for the **SendIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
         <span data-ttu-id="32629-132">![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span><span class="sxs-lookup"><span data-stu-id="32629-132">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span></span>  
  
         <span data-ttu-id="32629-133">SendIdoc 操作は、次のテンプレートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32629-133">For the SendIdoc operation, you must specify the following template:</span></span>  
  
        ```  
        <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
        <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
        </SendIdoc>  
        ```  
  
         <span data-ttu-id="32629-134">上記のテンプレート、`bts-msg-body`がファイルに関連付けられているフラット ファイル逆アセンブラーを使用して作成された XML IDOC の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="32629-134">In the preceding template, the `bts-msg-body` is XML IDOC that is created using the flat-file disassembler associated with the file receive port.</span></span> <span data-ttu-id="32629-135">XML IDOC は SendIdoc メッセージにカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="32629-135">The XML IDOC is encapsulated in the SendIdoc message.</span></span>  
  
    7.  <span data-ttu-id="32629-136">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="32629-136">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="32629-137">**送信ポートのプロパティ** ダイアログ ボックスから、**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="32629-137">In the **Send Port Properties** dialog box, from the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="32629-138">**送信パイプライン**ドロップダウン リストで、 **ConvertToFlatFile**です。</span><span class="sxs-lookup"><span data-stu-id="32629-138">From the **Send pipeline** drop-down list, select **ConvertToFlatFile**.</span></span> <span data-ttu-id="32629-139">このフラット ファイル アセンブラー パイプラインは、vPrev BizTalk プロジェクトの一部では既にし、XML IDOC をフラット ファイル IDOC に変換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="32629-139">This flat-file assembler pipeline is already a part of the vPrev BizTalk project and is used to convert an XML IDOC to a flat-file IDOC.</span></span>  
  
10. <span data-ttu-id="32629-140">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32629-140">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="32629-141">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="32629-141">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="32629-142">BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="32629-142">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="32629-143">BizTalk アプリケーションを右クリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="32629-143">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="32629-144">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32629-144">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="32629-145">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="32629-145">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="32629-146">下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="32629-146">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="32629-147">フラット ファイル IDOC を削除するファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="32629-147">Select the file port where you will drop the flat-file IDOC.</span></span>  
  
    2.  <span data-ttu-id="32629-148">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="32629-148">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
    3.  <span data-ttu-id="32629-149">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32629-149">Click **OK**.</span></span>  
  
     <span data-ttu-id="32629-150">アプリケーションの構成の詳細についてを参照してください「どのように構成するアプリケーションへ」 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。</span><span class="sxs-lookup"><span data-stu-id="32629-150">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="32629-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="32629-151">Next Steps</span></span>  
 <span data-ttu-id="32629-152">WCF ベースを使用して SAP システムに Idoc を送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="32629-152">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="32629-153">」の説明に従って、フラット ファイル IDOC を送信することによって移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)です。</span><span class="sxs-lookup"><span data-stu-id="32629-153">You must now test the migrated BizTalk application by sending a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32629-154">参照</span><span class="sxs-lookup"><span data-stu-id="32629-154">See Also</span></span>  
 [<span data-ttu-id="32629-155">チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="32629-155">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)