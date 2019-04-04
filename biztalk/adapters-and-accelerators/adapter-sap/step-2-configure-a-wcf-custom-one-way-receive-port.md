---
title: '手順 2: Wcf-custom の一方向の構成の受信ポート |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom one-way receive port, configuring
- migration
ms.assetid: e2a8f074-64d5-4e6c-84d0-318fb606c0ba
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d3320e7a2e6b948309087f2b33def57db9db0c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990299"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="a9500-102">手順 2: Wcf-custom の一方向の構成の受信ポート</span><span class="sxs-lookup"><span data-stu-id="a9500-102">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>
<span data-ttu-id="a9500-103">![ステップ 2/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="a9500-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="a9500-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="a9500-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="a9500-105">**目標:** この手順では、SAP システムからフラット ファイル IDOC を受信する WCF カスタム ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a9500-105">**Objective:** In this step, you configure a WCF-Custom port to receive a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="a9500-106">ポートを構成した後、BizTalk を構成する受信ポートの WCF カスタムを使用するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a9500-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a9500-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a9500-107">Prerequisites</span></span>  
 <span data-ttu-id="a9500-108">構築して SAP システムから Idoc を受信する vPrev BizTalk プロジェクトをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9500-108">You must have built and deployed your vPrev BizTalk project to receive IDOCs from an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="a9500-109">Wcf-custom 一方向受信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="a9500-109">To configure a WCF-Custom one-way receive port</span></span>  
  
1. <span data-ttu-id="a9500-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a9500-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="a9500-111">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="a9500-112">受信ポートを作成するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a9500-112">Expand the application under which you want create the receive port.</span></span>  
  
4. <span data-ttu-id="a9500-113">右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-113">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port**.</span></span>  
  
5. <span data-ttu-id="a9500-114">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9500-114">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="a9500-115">**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-115">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="a9500-116">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9500-116">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="a9500-117">**受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9500-117">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="a9500-118">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-118">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="a9500-119">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-119">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="a9500-120">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a9500-120">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="a9500-121">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムからメッセージを受信する接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-121">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to receive messages from the SAP system.</span></span> <span data-ttu-id="a9500-122">SAP システムからメッセージを受信する接続 URI は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9500-122">The connection URI to receive messages from the SAP system must be in the following format:</span></span>  
  
      ```  
      sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
      ```  
  
       <span data-ttu-id="a9500-123">次の図では、指定した uri のポートのプロパティ ダイアログ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="a9500-123">The following figure shows the port properties dialog box with the URI specified:</span></span>  
  
       <span data-ttu-id="a9500-124">![接続を SAP からメッセージを受信する URI](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span><span class="sxs-lookup"><span data-stu-id="a9500-124">![Connection URI to receive messages from SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span></span>  
  
       <span data-ttu-id="a9500-125">接続 URI の詳細については、[SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9500-125">For more information about the connection URI, see [Create a  connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
   2. <span data-ttu-id="a9500-126">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="a9500-127">受信ポートのバインドのプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9500-127">Make sure you specify the following binding properties for the receive port.</span></span>  
  
      |<span data-ttu-id="a9500-128">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="a9500-128">Binding property</span></span>|<span data-ttu-id="a9500-129">値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-129">Set value to</span></span>|  
      |----------------------|------------------|  
      |<span data-ttu-id="a9500-130">flatFileSegmentIndicator</span><span class="sxs-lookup"><span data-stu-id="a9500-130">flatFileSegmentIndicator</span></span>|<span data-ttu-id="a9500-131">**SegmentType**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-131">**SegmentType**.</span></span> <span data-ttu-id="a9500-132">これは、フラット ファイル IDOC 内の各セグメントのセグメントの種類を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a9500-132">This indicates that the flat files should contain the segment type for each segment in the IDOC.</span></span>|  
      |<span data-ttu-id="a9500-133">padReceivedIdocWithSpaces</span><span class="sxs-lookup"><span data-stu-id="a9500-133">padReceivedIdocWithSpaces</span></span>|<span data-ttu-id="a9500-134">**[True]**。</span><span class="sxs-lookup"><span data-stu-id="a9500-134">**True**.</span></span> <span data-ttu-id="a9500-135">IDOC の各行が、正しい長さにスペースが埋め込まれるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-135">Specifies whether each line in the IDOC is padded with spaces to the correct length.</span></span>|  
      |<span data-ttu-id="a9500-136">receiveIDocFormat</span><span class="sxs-lookup"><span data-stu-id="a9500-136">receiveIDocFormat</span></span>|<span data-ttu-id="a9500-137">**文字列**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-137">**String**.</span></span> <span data-ttu-id="a9500-138">これは、1 つの文字列フィールドとして IDOC メッセージを表す必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-138">This specifies that the IDOC message should be represented as a single string field.</span></span>|  
  
       <span data-ttu-id="a9500-139">バインド プロパティの詳細については、[mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9500-139">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   3. <span data-ttu-id="a9500-140">をクリックして、**他**タブをクリックし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-140">Click the **Others** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
   4. <span data-ttu-id="a9500-141">をクリックして、**メッセージ** タブで、および、**受信 BizTalk メッセージ本文**セクションで、選択、**パス**オプション。</span><span class="sxs-lookup"><span data-stu-id="a9500-141">Click the **Messages** tab, and in the **Inbound BizTalk message body** section, choose the **Path** option.</span></span>  
  
   5. <span data-ttu-id="a9500-142">**本文のパス式**テキスト ボックスに、XML メッセージからフラット ファイル IDOC を抽出する XPath クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9500-142">In the **Body path expression** text box, specify the XPath query to extract the flat-file IDOC from the XML message.</span></span> <span data-ttu-id="a9500-143">これにより、受信ポートが IDOC からデータを抽出しの一部である XML タグをトリム、 **ReceiveIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a9500-143">By doing so, the receive port extracts the data from the IDOC and trims the XML tag that is part of the **ReceiveIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a9500-144">メッセージ スキーマの詳細については、 **ReceiveIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9500-144">For more information about the message schema for the **ReceiveIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
       <span data-ttu-id="a9500-145">![フラットを抽出する XPath クエリ&#45;ファイル IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span><span class="sxs-lookup"><span data-stu-id="a9500-145">![XPath query to extract the flat&#45;file IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span></span>  
  
       <span data-ttu-id="a9500-146">次の XPath クエリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9500-146">You must specify the following XPath query:</span></span>  
  
      ```  
      /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
      ```  
  
   6. <span data-ttu-id="a9500-147">**ノード エンコード**ドロップダウン リストで、**文字列**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-147">From the **Node encoding** drop-down list, select **String**.</span></span>  
  
   7. <span data-ttu-id="a9500-148">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-148">Click **Apply**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="a9500-149">受信場所のプロパティ ダイアログ ボックスから、**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-149">In the Receive Location Properties dialog box, from the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="a9500-150">**受信パイプライン**ドロップダウン リストで、 **ConvertToXML**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-150">From the **Receive pipeline** drop-down list, select **ConvertToXML**.</span></span> <span data-ttu-id="a9500-151">このフラット ファイル逆アセンブラー パイプラインは、既に XML IDOC フラット ファイル IDOC に変換する vPrev BizTalk プロジェクトの部分です。</span><span class="sxs-lookup"><span data-stu-id="a9500-151">This flat-file disassembler pipeline is already a part of the vPrev BizTalk project to convert a flat-file IDOC to an XML IDOC.</span></span>  
  
11. <span data-ttu-id="a9500-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9500-152">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="a9500-153">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="a9500-153">To configure the BizTalk application</span></span>  
  
1. <span data-ttu-id="a9500-154">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**オーケストレーションが展開されている BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a9500-154">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2. <span data-ttu-id="a9500-155">BizTalk アプリケーションを右クリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a9500-155">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3. <span data-ttu-id="a9500-156">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9500-156">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="a9500-157">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9500-157">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4. <span data-ttu-id="a9500-158">で、**バインド**ボックスに、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="a9500-158">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
   1. <span data-ttu-id="a9500-159">WCF カスタムでは、このトピックの前半で作成したポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9500-159">Select the WCF-Custom receive port you created earlier in this topic.</span></span>  
  
   2. <span data-ttu-id="a9500-160">フラット ファイル IDOC を受信は、file ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9500-160">Select a file port where you will receive the flat-file IDOC.</span></span>  
  
   3. <span data-ttu-id="a9500-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9500-161">Click **OK**.</span></span>  
  
      <span data-ttu-id="a9500-162">アプリケーションを構成する方法の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9500-162">For more information about configuring an application, see [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a9500-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="a9500-163">Next Steps</span></span>  
 <span data-ttu-id="a9500-164">WCF ベースを使用して SAP システムから Idoc を受信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a9500-164">You have now completed migration of your vPrev BizTalk project to a BizTalk project that receives IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="a9500-165">」の説明に従って、フラット ファイル IDOC を受信することによって、移行済みの BizTalk アプリケーションにテストすること今すぐ必要があります[手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9500-165">You must now test the migrated BizTalk application by receiving a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9500-166">参照</span><span class="sxs-lookup"><span data-stu-id="a9500-166">See Also</span></span>  
 [<span data-ttu-id="a9500-167">チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="a9500-167">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)