---
title: '手順 2: Wcf-custom の一方向送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way send port, configuring
- migration
ms.assetid: ae13222e-42e7-45a7-9b2a-0a6779b21736
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 662007dc6f75e1ca0459e53f576c816d23b71404
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005723"
---
# <a name="step-2-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="f7187-102">手順 2: Wcf-custom の一方向送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7187-102">Step 2: Configure a WCF-Custom One-way Send Port</span></span>
<span data-ttu-id="f7187-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="f7187-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="f7187-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="f7187-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="f7187-105">**目標:** この手順では、フラット ファイル IDOC を SAP システムに送信する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7187-105">**Objective:** In this step, you configure a WCF-Custom port to send the flat-file IDOC to an SAP system.</span></span> <span data-ttu-id="f7187-106">ポートを構成した後は、Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="f7187-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7187-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f7187-107">Prerequisites</span></span>  
 <span data-ttu-id="f7187-108">構築して Idoc を SAP システムに送信する vPrev BizTalk プロジェクトをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7187-108">You must have built and deployed your vPrev BizTalk project to send IDOCs to an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-send-port"></a><span data-ttu-id="f7187-109">Wcf-custom 一方向の送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="f7187-109">To configure a WCF-Custom one-way send port</span></span>  
  
1. <span data-ttu-id="f7187-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="f7187-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="f7187-111">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="f7187-112">送信ポートを作成するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7187-112">Expand the application under which you want to create the send port.</span></span>  
  
4. <span data-ttu-id="f7187-113">右クリックして**送信ポート**、 をポイント**新規**、 をクリック**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-113">Right-click **Send Ports**, point to **New**, and click **Static One-way Send Port**.</span></span>  
  
5. <span data-ttu-id="f7187-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7187-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="f7187-115">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="f7187-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7187-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="f7187-117">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムにメッセージを送信する接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7187-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to send messages to the SAP system.</span></span> <span data-ttu-id="f7187-118">接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を使用すると、作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7187-118">For more information about the connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
       <span data-ttu-id="f7187-119">![送信ポートで指定された接続 URI](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span><span class="sxs-lookup"><span data-stu-id="f7187-119">![Connection URI specified in the send port](../../adapters-and-accelerators/adapter-sap/media/53ae71e1-89ec-49c5-8096-ff04a2c94c0a.gif "53ae71e1-89ec-49c5-8096-ff04a2c94c0a")</span></span>  
  
   2. <span data-ttu-id="f7187-120">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7187-120">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="f7187-121">フラット ファイル IDOC を送信するには、使用する必要があります、 **SendIdoc** WCF ベースによって公開される操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f7187-121">To send a flat-file IDOC, you must use the **SendIdoc** operation exposed by the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="f7187-122">**SendIdoc**操作には、厳密に型指定のスキーマが Idoc を送信するアダプターのクライアントが使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7187-122">**SendIdoc** operation enables adapter clients to send IDOCs having a weakly-typed schema.</span></span> <span data-ttu-id="f7187-123">詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7187-123">For more information, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span> <span data-ttu-id="f7187-124">次に示します、**アクション**の操作は、テキスト ボックス、 **SendIdoc**操作。</span><span class="sxs-lookup"><span data-stu-id="f7187-124">The following figure shows the **Action** text box with the action for the **SendIdoc** operation.</span></span>  
  
       <span data-ttu-id="f7187-125">![送信ポートでアクションを指定](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span><span class="sxs-lookup"><span data-stu-id="f7187-125">![Specify action in the send port](../../adapters-and-accelerators/adapter-sap/media/94dd1505-5529-43cf-a27b-2588a022dfb9.gif "94dd1505-5529-43cf-a27b-2588a022dfb9")</span></span>  
  
   3. <span data-ttu-id="f7187-126">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
   4. <span data-ttu-id="f7187-127">をクリックして、**資格情報**タブし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7187-127">Click the **Credentials** tab and specify the credentials to connect to an SAP system.</span></span>  
  
   5. <span data-ttu-id="f7187-128">をクリックして、**メッセージ** タブで、および、**送信 WCF メッセージ本文**セクションで、選択、**テンプレート**オプション。</span><span class="sxs-lookup"><span data-stu-id="f7187-128">Click the **Messages** tab, and in the **Outbound WCF message body** section, choose the **Template** option.</span></span>  
  
   6. <span data-ttu-id="f7187-129">**XML**テキスト ボックスに、WCF メッセージの構築に使用されるテンプレートを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7187-129">In the **XML** text box, specify the template that will be used to construct the WCF message.</span></span> <span data-ttu-id="f7187-130">これにより、準拠するメッセージを作成する、 **SendIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f7187-130">By doing so, you create a message that conforms to the **SendIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="f7187-131">メッセージの構造の詳細については、 **SendIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7187-131">For more information about the message structure for the **SendIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
       <span data-ttu-id="f7187-132">![送信 WCF メッセージのテンプレートを指定](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span><span class="sxs-lookup"><span data-stu-id="f7187-132">![Specify template for outbound WCF message](../../adapters-and-accelerators/adapter-sap/media/909835c3-a941-49dc-87f0-858fe0e1fc63.gif "909835c3-a941-49dc-87f0-858fe0e1fc63")</span></span>  
  
       <span data-ttu-id="f7187-133">SendIdoc 操作の場合は、次のテンプレートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7187-133">For the SendIdoc operation, you must specify the following template:</span></span>  
  
      ```  
      <SendIdoc xmlns="http://Microsoft.LobServices.Sap/2007/03/Idoc/">  
      <idocData><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="string"/></idocData>  
      </SendIdoc>  
      ```  
  
       <span data-ttu-id="f7187-134">上記のテンプレート、`bts-msg-body`がファイルに関連付けられているフラット ファイル逆アセンブラーを使用して作成された XML の IDOC の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="f7187-134">In the preceding template, the `bts-msg-body` is XML IDOC that is created using the flat-file disassembler associated with the file receive port.</span></span> <span data-ttu-id="f7187-135">XML の IDOC は SendIdoc メッセージでカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="f7187-135">The XML IDOC is encapsulated in the SendIdoc message.</span></span>  
  
   7. <span data-ttu-id="f7187-136">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-136">Click **Apply**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="f7187-137">**送信ポートのプロパティ** ダイアログ ボックスから、**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-137">In the **Send Port Properties** dialog box, from the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="f7187-138">**送信パイプライン**ドロップダウン リストで、 **ConvertToFlatFile**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-138">From the **Send pipeline** drop-down list, select **ConvertToFlatFile**.</span></span> <span data-ttu-id="f7187-139">このフラット ファイル アセンブラー パイプラインは、vPrev BizTalk プロジェクトの一部になってし、フラット ファイル IDOC を XML IDOC に変換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="f7187-139">This flat-file assembler pipeline is already a part of the vPrev BizTalk project and is used to convert an XML IDOC to a flat-file IDOC.</span></span>  
  
10. <span data-ttu-id="f7187-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7187-140">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="f7187-141">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="f7187-141">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="f7187-142">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f7187-142">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="f7187-143">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f7187-143">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="f7187-144">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7187-144">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="f7187-145">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7187-145">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="f7187-146">で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="f7187-146">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="f7187-147">フラット ファイル IDOC をドロップする場所、ファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7187-147">Select the file port where you will drop the flat-file IDOC.</span></span>  
  
   2. <span data-ttu-id="f7187-148">このトピックの前半で作成した、Wcf-custom 送信ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f7187-148">Select the WCF-Custom send port you created earlier in this topic.</span></span>  
  
   3. <span data-ttu-id="f7187-149">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7187-149">Click **OK**.</span></span>  
  
      <span data-ttu-id="f7187-150">アプリケーションを構成する方法の詳細についてを参照してください「する方法をアプリケーションの構成」 [ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)します。</span><span class="sxs-lookup"><span data-stu-id="f7187-150">For more information about configuring an application, see "How to Configure an Application" at [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f7187-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="f7187-151">Next Steps</span></span>  
 <span data-ttu-id="f7187-152">WCF ベースを使用して、SAP システムに Idoc を送信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f7187-152">You have now completed migration of your vPrev BizTalk project to a BizTalk project that sends IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="f7187-153">」の説明に従って、フラット ファイル IDOC を送信することによって、移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7187-153">You must now test the migrated BizTalk application by sending a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7187-154">参照</span><span class="sxs-lookup"><span data-stu-id="f7187-154">See Also</span></span>  
 [<span data-ttu-id="f7187-155">チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="f7187-155">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)