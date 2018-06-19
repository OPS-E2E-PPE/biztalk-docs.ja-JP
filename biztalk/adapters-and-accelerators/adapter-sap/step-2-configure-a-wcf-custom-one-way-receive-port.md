---
title: '手順 2: 構成 Wcf-custom 一方向受信ポート |Microsoft ドキュメント'
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
ms.openlocfilehash: 6edf75f08bdf6a321188e484eb4f363366f8eb95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218554"
---
# <a name="step-2-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="51b22-102">手順 2: 構成 Wcf-custom 一方向受信ポート</span><span class="sxs-lookup"><span data-stu-id="51b22-102">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>
<span data-ttu-id="51b22-103">![手順 3 の 2](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span><span class="sxs-lookup"><span data-stu-id="51b22-103">![Step 2 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-2of3.gif "Step_2of3")</span></span>  
  
 <span data-ttu-id="51b22-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="51b22-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="51b22-105">**目標:** SAP システムからフラット ファイル IDOC を受信する WCF カスタム ポートを構成するこの手順でします。</span><span class="sxs-lookup"><span data-stu-id="51b22-105">**Objective:** In this step, you configure a WCF-Custom port to receive a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="51b22-106">BizTalk を構成するポートを構成すると、受信ポートの Wcf-custom を使用するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="51b22-106">After configuring the port, you configure the BizTalk application to use the WCF-Custom receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51b22-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="51b22-107">Prerequisites</span></span>  
 <span data-ttu-id="51b22-108">構築し、SAP システムから Idoc を受信する vPrev BizTalk プロジェクトを展開した必要があります。</span><span class="sxs-lookup"><span data-stu-id="51b22-108">You must have built and deployed your vPrev BizTalk project to receive IDOCs from an SAP system.</span></span>  
  
### <a name="to-configure-a-wcf-custom-one-way-receive-port"></a><span data-ttu-id="51b22-109">Wcf-custom 一方向の受信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="51b22-109">To configure a WCF-Custom one-way receive port</span></span>  
  
1.  <span data-ttu-id="51b22-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="51b22-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="51b22-111">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="51b22-112">受信ポートを作成するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="51b22-112">Expand the application under which you want create the receive port.</span></span>  
  
4.  <span data-ttu-id="51b22-113">右クリック**受信ポート**、指す**新規**、 をクリック**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-113">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="51b22-114">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="51b22-114">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6.  <span data-ttu-id="51b22-115">**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-115">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="51b22-116">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51b22-116">The **Receive Location Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="51b22-117">**受信場所のプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51b22-117">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="51b22-118">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-118">Specify a name for the receive location.</span></span>  
  
    2.  <span data-ttu-id="51b22-119">**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-119">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="51b22-120">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="51b22-120">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="51b22-121">クリックして、**全般**] タブで、し、[、**アドレス (URI)** フィールドで、接続、SAP システムからメッセージを受信 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-121">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI to receive messages from the SAP system.</span></span> <span data-ttu-id="51b22-122">SAP システムからメッセージを受信する URI の接続は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51b22-122">The connection URI to receive messages from the SAP system must be in the following format:</span></span>  
  
        ```  
        sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
        ```  
  
         <span data-ttu-id="51b22-123">次の図は、指定された URI でポートのプロパティ ダイアログ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="51b22-123">The following figure shows the port properties dialog box with the URI specified:</span></span>  
  
         <span data-ttu-id="51b22-124">![接続 URI SAP からメッセージを受信する](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span><span class="sxs-lookup"><span data-stu-id="51b22-124">![Connection URI to receive messages from SAP](../../adapters-and-accelerators/adapter-sap/media/91e12582-aea3-4f13-8cdc-af69a9a11a5c.gif "91e12582-aea3-4f13-8cdc-af69a9a11a5c")</span></span>  
  
         <span data-ttu-id="51b22-125">接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="51b22-125">For more information about the connection URI, see [Create a  connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
    2.  <span data-ttu-id="51b22-126">クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-126">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="51b22-127">受信ポートのバインドのプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51b22-127">Make sure you specify the following binding properties for the receive port.</span></span>  
  
        |<span data-ttu-id="51b22-128">プロパティのバインド</span><span class="sxs-lookup"><span data-stu-id="51b22-128">Binding property</span></span>|<span data-ttu-id="51b22-129">値を設定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-129">Set value to</span></span>|  
        |----------------------|------------------|  
        |<span data-ttu-id="51b22-130">flatFileSegmentIndicator</span><span class="sxs-lookup"><span data-stu-id="51b22-130">flatFileSegmentIndicator</span></span>|<span data-ttu-id="51b22-131">**SegmentType**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-131">**SegmentType**.</span></span> <span data-ttu-id="51b22-132">これは、フラット ファイル IDOC 内の各セグメントのセグメントの種類を含める必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="51b22-132">This indicates that the flat files should contain the segment type for each segment in the IDOC.</span></span>|  
        |<span data-ttu-id="51b22-133">padReceivedIdocWithSpaces</span><span class="sxs-lookup"><span data-stu-id="51b22-133">padReceivedIdocWithSpaces</span></span>|<span data-ttu-id="51b22-134">**[True]**。</span><span class="sxs-lookup"><span data-stu-id="51b22-134">**True**.</span></span> <span data-ttu-id="51b22-135">IDOC 内の各行が正しい長さにスペースが埋め込まれるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-135">Specifies whether each line in the IDOC is padded with spaces to the correct length.</span></span>|  
        |<span data-ttu-id="51b22-136">receiveIDocFormat</span><span class="sxs-lookup"><span data-stu-id="51b22-136">receiveIDocFormat</span></span>|<span data-ttu-id="51b22-137">**文字列**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-137">**String**.</span></span> <span data-ttu-id="51b22-138">これは、IDOC メッセージを 1 つの文字列フィールドとして表現する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-138">This specifies that the IDOC message should be represented as a single string field.</span></span>|  
  
         <span data-ttu-id="51b22-139">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="51b22-139">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    3.  <span data-ttu-id="51b22-140">クリックして、**他**タブをクリックし、SAP システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-140">Click the **Others** tab, and specify the credentials to connect to an SAP system.</span></span>  
  
    4.  <span data-ttu-id="51b22-141">クリックして、**メッセージ**] タブで、し、[、**受信 BizTalk メッセージ本文**セクションで、選択、**パス**オプション。</span><span class="sxs-lookup"><span data-stu-id="51b22-141">Click the **Messages** tab, and in the **Inbound BizTalk message body** section, choose the **Path** option.</span></span>  
  
    5.  <span data-ttu-id="51b22-142">**本文のパス式**テキスト ボックスで、XML メッセージからフラット ファイル IDOC を抽出する XPath クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="51b22-142">In the **Body path expression** text box, specify the XPath query to extract the flat-file IDOC from the XML message.</span></span> <span data-ttu-id="51b22-143">これにより、受信ポートが IDOC からデータを抽出しの一部である XML タグを小さくするとき、 **ReceiveIdoc** WCF ベースの操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="51b22-143">By doing so, the receive port extracts the data from the IDOC and trims the XML tag that is part of the **ReceiveIdoc** operation for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="51b22-144">メッセージ スキーマの詳細については、 **ReceiveIdoc**操作を参照してください[IDOC 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="51b22-144">For more information about the message schema for the **ReceiveIdoc** operation, see [Message Schemas for IDOC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-idoc-operations.md).</span></span>  
  
         <span data-ttu-id="51b22-145">![XPath フラット & #45 を抽出するクエリにはファイルの IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span><span class="sxs-lookup"><span data-stu-id="51b22-145">![XPath query to extract the flat&#45;file IDOC](../../adapters-and-accelerators/adapter-sap/media/8b5b8165-a1e7-40ef-bcf7-de3149c6deb0.gif "8b5b8165-a1e7-40ef-bcf7-de3149c6deb0")</span></span>  
  
         <span data-ttu-id="51b22-146">次の XPath クエリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51b22-146">You must specify the following XPath query:</span></span>  
  
        ```  
        /*[local-name()='ReceiveIdoc']/*[local-name()='idocData']  
        ```  
  
    6.  <span data-ttu-id="51b22-147">**ノード エンコード**ドロップダウン リストで、**文字列**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-147">From the **Node encoding** drop-down list, select **String**.</span></span>  
  
    7.  <span data-ttu-id="51b22-148">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-148">Click **Apply**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="51b22-149">受信場所のプロパティ ダイアログ ボックスから、**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-149">In the Receive Location Properties dialog box, from the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="51b22-150">**受信パイプライン**ドロップダウン リストで、 **ConvertToXML**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-150">From the **Receive pipeline** drop-down list, select **ConvertToXML**.</span></span> <span data-ttu-id="51b22-151">このフラット ファイル逆アセンブラー パイプラインはフラット ファイル IDOC を XML IDOC に変換する vPrev BizTalk プロジェクトの一部では既にです。</span><span class="sxs-lookup"><span data-stu-id="51b22-151">This flat-file disassembler pipeline is already a part of the vPrev BizTalk project to convert a flat-file IDOC to an XML IDOC.</span></span>  
  
11. <span data-ttu-id="51b22-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51b22-152">Click **OK**.</span></span>  
  
### <a name="to-configure-the-biztalk-application"></a><span data-ttu-id="51b22-153">BizTalk アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="51b22-153">To configure the BizTalk application</span></span>  
  
1.  <span data-ttu-id="51b22-154">BizTalk Server 管理コンソールで、次のように展開します。 **BizTalk グループ**、展開**アプリケーション**、オーケストレーションが展開されている BizTalk アプリケーションに展開します。</span><span class="sxs-lookup"><span data-stu-id="51b22-154">In the BizTalk Server Administration console, expand **BizTalk Group**, expand **Applications**, and expand the BizTalk Application where the orchestration is deployed.</span></span>  
  
2.  <span data-ttu-id="51b22-155">BizTalk アプリケーションを右クリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="51b22-155">Right-click the BizTalk application, and then select **Configure**.</span></span>  
  
3.  <span data-ttu-id="51b22-156">左側のウィンドウを構成するオーケストレーションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51b22-156">From the left pane, click the orchestration to configure.</span></span> <span data-ttu-id="51b22-157">右側のペインから、**ホスト**ドロップダウン リストで、BizTalk ホスト インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="51b22-157">From the right pane, from the **Host** drop-down list, select a BizTalk host instance.</span></span>  
  
4.  <span data-ttu-id="51b22-158">下にある、**バインド**ボックスで、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマップします。</span><span class="sxs-lookup"><span data-stu-id="51b22-158">Under the **Bindings** box, map the logical ports of the BizTalk orchestration to the physical ports in the BizTalk Server Administration console.</span></span>  
  
    1.  <span data-ttu-id="51b22-159">このトピックの前半で作成したポートを受信する Wcf-custom を選択します。</span><span class="sxs-lookup"><span data-stu-id="51b22-159">Select the WCF-Custom receive port you created earlier in this topic.</span></span>  
  
    2.  <span data-ttu-id="51b22-160">フラット ファイル IDOC を受信するファイル ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="51b22-160">Select a file port where you will receive the flat-file IDOC.</span></span>  
  
    3.  <span data-ttu-id="51b22-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51b22-161">Click **OK**.</span></span>  
  
     <span data-ttu-id="51b22-162">アプリケーションの構成の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360)です。</span><span class="sxs-lookup"><span data-stu-id="51b22-162">For more information about configuring an application, see [http://go.microsoft.com/fwlink/?LinkId=102360](http://go.microsoft.com/fwlink/?LinkId=102360).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="51b22-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="51b22-163">Next Steps</span></span>  
 <span data-ttu-id="51b22-164">WCF ベースを使用して SAP システムから Idoc を受信する BizTalk プロジェクトに vPrev BizTalk プロジェクトの移行が完了したので[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="51b22-164">You have now completed migration of your vPrev BizTalk project to a BizTalk project that receives IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="51b22-165">必要があります今すぐアプリケーションをテストする移行された BizTalk フラット ファイル IDOC を受信して」の説明に従って[手順 3: アプリケーションをテストする移行](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)です。</span><span class="sxs-lookup"><span data-stu-id="51b22-165">You must now test the migrated BizTalk application by receiving a flat-file IDOC, as described in [Step 3: Test the Migrated Application](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b22-166">参照</span><span class="sxs-lookup"><span data-stu-id="51b22-166">See Also</span></span>  
 [<span data-ttu-id="51b22-167">チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信</span><span class="sxs-lookup"><span data-stu-id="51b22-167">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)