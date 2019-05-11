---
title: BPEL インポート (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d86d5b519d05c01389cff1c5a46e071c51e091a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357858"
---
# <a name="bpel-import-biztalk-server-sample"></a><span data-ttu-id="70197-102">BPEL インポート (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="70197-102">BPEL Import (BizTalk Server Sample)</span></span>
<span data-ttu-id="70197-103">BPEL インポート サンプルでは、Business Process Execution Language (BPEL) プロセスの説明とその関連アイテムからオーケストレーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="70197-103">The BPEL Import sample demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) process description and its related artifacts.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="70197-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="70197-104">What This Sample Does</span></span>  
 <span data-ttu-id="70197-105">Wide World importers 社は、小売業者に自動出荷サービスを提供する出荷業者です。</span><span class="sxs-lookup"><span data-stu-id="70197-105">Wide World Importers is a shipping company that provides automated shipping services to retailers.</span></span> <span data-ttu-id="70197-106">具体的には、Wide World importers 社は小売業者に有効にします。</span><span class="sxs-lookup"><span data-stu-id="70197-106">Specifically, Wide World Importers enables retailers to:</span></span>  

- <span data-ttu-id="70197-107">注文の出荷を要求します。</span><span class="sxs-lookup"><span data-stu-id="70197-107">Request order shipments</span></span>  

- <span data-ttu-id="70197-108">出荷を追跡します。</span><span class="sxs-lookup"><span data-stu-id="70197-108">Track shipments</span></span>  

- <span data-ttu-id="70197-109">出荷を確認します。</span><span class="sxs-lookup"><span data-stu-id="70197-109">Confirm shipments</span></span>  

- <span data-ttu-id="70197-110">請求および支払いの送付を確認します。</span><span class="sxs-lookup"><span data-stu-id="70197-110">Confirm invoicing and payment for shipments</span></span>  

  <span data-ttu-id="70197-111">BPEL ドキュメントが全体からの応答を期待する方法と製品の企業がサービスの呼び出しに予定されている通常の方法について説明します、これらのサービスの可用性は、Web サービス記述言語 (WSDL) ドキュメントを使用して表すことが、World importers 社です。</span><span class="sxs-lookup"><span data-stu-id="70197-111">While the availability of these services can be represented by using a Web Services Description Language (WSDL) document, a BPEL document describes the typical way in which the product companies are expected to call the services and how to expect responses from Wide World Importers.</span></span>  

  <span data-ttu-id="70197-112">Northwind Traders 社に出荷処理 Wide World Importers 人材採用と BPEL ファイルが提供されるいくつかの関連成果物全体の相互作用を記述します。</span><span class="sxs-lookup"><span data-stu-id="70197-112">When Northwind Traders hires Wide World Importers to handle their shipping, they are provided a BPEL file and some related artifacts that describe the entire interaction.</span></span> <span data-ttu-id="70197-113">BPEL ファイルを使用して、Northwind Traders の作成、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Wide World importers 社を介して自動的に処理するアプリケーション (BPELShipping) を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="70197-113">Using the BPEL file, Northwind Traders creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application (BPELShipping) to automatically process orders through Wide World Importers.</span></span>  

  <span data-ttu-id="70197-114">このサンプルでは、このシナリオを説明します。 BPELShipping アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="70197-114">This sample walks you through this scenario in which the BPELShipping application:</span></span>  

1. <span data-ttu-id="70197-115">Northwind traders 社の顧客の注文システムから注文を受信します。</span><span class="sxs-lookup"><span data-stu-id="70197-115">Receives an order from the Northwind Traders customer order system.</span></span>  

2. <span data-ttu-id="70197-116">Wide World importers 社と要求の確認に出荷要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="70197-116">Sends a shipping request to Wide World Importers and requests confirmation.</span></span>  

3. <span data-ttu-id="70197-117">Wide World importers 社から出荷要求の確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="70197-117">Receives shipment request confirmation from Wide World Importers.</span></span>  

4. <span data-ttu-id="70197-118">Wide World importers 社からピックアップ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="70197-118">Receives pickup notification from Wide World Importers.</span></span>  

5. <span data-ttu-id="70197-119">最大の出荷状況メッセージと出荷が顧客によって受信されたときなどを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="70197-119">Receives shipment status messages up to and including when the shipment has been received by the customer.</span></span>  

6. <span data-ttu-id="70197-120">Wide World importers 社から請求書を受信します。</span><span class="sxs-lookup"><span data-stu-id="70197-120">Receives an invoice from Wide World Importers.</span></span>  

7. <span data-ttu-id="70197-121">請求書の受信確認では、Wide World importers 社に応答します。</span><span class="sxs-lookup"><span data-stu-id="70197-121">Responds to Wide World Importers with an invoice acknowledgment.</span></span>  

8. <span data-ttu-id="70197-122">Wide World importers 社から支払い確認メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="70197-122">Receives a payment confirmation from Wide World Importers.</span></span>  

9. <span data-ttu-id="70197-123">注文システムには、最終的な出荷確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="70197-123">Sends a final shipping confirmation to the ordering system.</span></span>  

   <span data-ttu-id="70197-124">別の BizTalk アプリケーション (ShipperProcess) は、このサンプルの Wide World importers 社のシミュレーションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="70197-124">A separate BizTalk application (ShipperProcess) is used to simulate Wide World Importers for this sample.</span></span> <span data-ttu-id="70197-125">BPELShipping アプリケーションは、一般的なファイル システムの場所を通信に使用されるファイル トランスポートを使用して、ShipperProcess と通信します。</span><span class="sxs-lookup"><span data-stu-id="70197-125">The BPELShipping application communicates with ShipperProcess by using the FILE transport, which uses common file system locations for the communication.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="70197-126">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="70197-126">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="70197-127">BPEL の Web サービスは、Web サービスを使用して相互にビジネスを実行するさまざまな企業で簡単に共有できるように、ビジネス プロセスを記述する XML ベースの言語です。</span><span class="sxs-lookup"><span data-stu-id="70197-127">BPEL for Web services is an XML-based language to describe the business process so that it can be easily shared across different companies who want to do business with each other using Web services.</span></span> <span data-ttu-id="70197-128">BPEL はビジネス プロトコル レベルでは、ビジネス プロセスを処理する方法を説明しますが、パートナーから受信した注文書の処理を行う手順のような企業内の内部プロセスが説明されていません。</span><span class="sxs-lookup"><span data-stu-id="70197-128">BPEL describes how to handle the business process at the business protocol level, but it does not describe the internal process in a company, such as the steps a company would take to process a purchase order after receiving it from a partner.</span></span> <span data-ttu-id="70197-129">このサンプルは、BPEL ファイルと対応する WSDL ファイルをインポート、オーケストレーションに変換してから、パートナーとビジネス プロセスを実行する起動する方法について説明する設計されています。</span><span class="sxs-lookup"><span data-stu-id="70197-129">This sample is designed to show you how to import BPEL and corresponding WSDL files, convert them into an orchestration, and then start to run the business process with the partner.</span></span>  

 <span data-ttu-id="70197-130">BPEL および WSDL ファイルをインポートし、事前構築済みの BizTalk アプリケーション (ShipperProcess) と対話するためのオーケストレーションに変換する方法を示す一連の手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70197-130">The following is the step-by-step procedure showing how to import the BPEL and WSDL files and convert them into an orchestration to interact with a prebuilt BizTalk application (ShipperProcess).</span></span> <span data-ttu-id="70197-131">次の手順を完了する場合は、「をビルドおよび初期化する BPELShipping アプリケーション」で説明されている手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="70197-131">If you complete the following steps, you do not need to perform the steps described in "To build and initialize the BPELShipping application".</span></span>  

#### <a name="to-import-from-bpel-and-build-a-working-solution"></a><span data-ttu-id="70197-132">BPEL からインポートし、実用的なソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="70197-132">To import from BPEL and build a working solution</span></span>  

1. <span data-ttu-id="70197-133">Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**。</span><span class="sxs-lookup"><span data-stu-id="70197-133">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="70197-134">この手順を完了する前に、サポートのプロセスとスキーマのプロジェクトを作成する ShipperProcess アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70197-134">Before completing this procedure, you must set up the ShipperProcess application to create the supporting processes and schema projects.</span></span>  

2. <span data-ttu-id="70197-135">**新しいプロジェクト** ダイアログ ボックスで、プロジェクトの種類 ウィンドウで**BizTalk (プロジェクト)** します。</span><span class="sxs-lookup"><span data-stu-id="70197-135">In the **New Project** dialog box, in the Project Types pane, select **BizTalk (Projects)**.</span></span> <span data-ttu-id="70197-136">[テンプレート] ペインで選択**BizTalk Server BPEL インポート プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="70197-136">In the Templates pane, select **BizTalk (Server) BPEL Import Project**.</span></span>  

3. <span data-ttu-id="70197-137">**名前**ボックスに、入力**BPELShipping**します。</span><span class="sxs-lookup"><span data-stu-id="70197-137">In the **Name** box, enter **BPELShipping**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="70197-138">別の名前を使用する場合、最終的なバインドの手順で問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70197-138">If you use a different name, you may experience problems with the final binding step.</span></span>  

4. <span data-ttu-id="70197-139">プロジェクトの場所を選択し、クリックして**OK** BPEL インポート ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="70197-139">Select a location for the project, and then click **OK** to start the BPEL Import Wizard.</span></span>  

5. <span data-ttu-id="70197-140">**へようこそ**  ページで **次**します。</span><span class="sxs-lookup"><span data-stu-id="70197-140">On the **Welcome** page, click **Next**.</span></span>  

6. <span data-ttu-id="70197-141">**選択 BPEL、WSDL、および XSD ファイル**] ページで [**参照**します。</span><span class="sxs-lookup"><span data-stu-id="70197-141">On the **Select BPEL, WSDL, and XSD Files** page, click **Browse**.</span></span>  

7. <span data-ttu-id="70197-142">すべてのファイルを選択、 \<*サンプル パス*\>\Orchestrations\BPELImport\BPELSource フォルダー、 をクリックして**オープン**、順にクリックします**次**.</span><span class="sxs-lookup"><span data-stu-id="70197-142">Select all the files from the \<*Samples Path*\>\Orchestrations\BPELImport\BPELSource folder, click **Open**, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="70197-143">この手順では、ビジネス プロセスの説明に BPEL および WSDL ファイルとビジネス ドキュメント スキーマを表す XSD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="70197-143">In this step, you select the BPEL and WSDL files to describe the business process and the XSD files to represent the business document schemas.</span></span>  

8. <span data-ttu-id="70197-144">**呼び出した WebServices 用の WSDL ファイルの選択**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="70197-144">On the **Select WSDL Files for Invoked WebServices** page, click **Finish**.</span></span>  

9. <span data-ttu-id="70197-145">BPEL インポート ウィザードでは、インポートに成功を報告するウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="70197-145">After the BPEL Import Wizard reports a successful import, close the wizard.</span></span> <span data-ttu-id="70197-146">プロジェクトが作成されました。</span><span class="sxs-lookup"><span data-stu-id="70197-146">The project is now created.</span></span>  

10. <span data-ttu-id="70197-147">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) プロジェクトの場所にします。</span><span class="sxs-lookup"><span data-stu-id="70197-147">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the project location.</span></span>  

11. <span data-ttu-id="70197-148">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="70197-148">Run the following command:</span></span>  

     <span data-ttu-id="70197-149">**sn – k BPELShipping.snk**</span><span class="sxs-lookup"><span data-stu-id="70197-149">**sn –k BPELShipping.snk**</span></span>  

12. <span data-ttu-id="70197-150">ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="70197-150">In Solution Explorer, right-click the **BPELShipping** project, and then click **Properties**.</span></span>  

13. <span data-ttu-id="70197-151">**Common properties \assembly**、アセンブリ キー ファイルを選択**BPELShipping.snk**ステップ 11 で作成され、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="70197-151">Under **Common Properties\Assembly**, select the assembly key file **BPELShipping.snk** created in step 11, and then click **OK**.</span></span>  

14. <span data-ttu-id="70197-152">ソリューション エクスプ ローラーで、すべての .xsd ファイルを選択し、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="70197-152">In Solution Explorer, select all the .xsd files and delete them.</span></span>  

15. <span data-ttu-id="70197-153">ソリューション エクスプ ローラーで選択**参照の追加**、し、**プロジェクト**] タブで [**参照**します。</span><span class="sxs-lookup"><span data-stu-id="70197-153">In Solution Explorer, select **Add Reference**, and on the **Projects** tab, click **Browse**.</span></span>  

16. <span data-ttu-id="70197-154">選択**ShippingSchemas.dll**の場所から\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development とクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="70197-154">Select **ShippingSchemas.dll** from the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="70197-155">「ビルド、ShipperProcess アプリケーションを初期化して」セクションには、これを構築する方法の手順があります。</span><span class="sxs-lookup"><span data-stu-id="70197-155">The section "To build and initialize the ShipperProcess application" has instructions on how to build this.</span></span>  

17. <span data-ttu-id="70197-156">ソリューション エクスプ ローラーでダブルクリック **[ordershippingprocess.bpel.odx]** します。</span><span class="sxs-lookup"><span data-stu-id="70197-156">In Solution Explorer, double-click **OrderShippingProcess.bpel.odx**.</span></span>  

18. <span data-ttu-id="70197-157">**ビュー**メニューの **その他の Windows/オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="70197-157">On the **View** menu, select **Other Windows/Orchestration View**.</span></span>  

19. <span data-ttu-id="70197-158">オーケストレーションの種類 ウィンドウで、右クリック**オーケストレーションのプロパティ** をクリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="70197-158">In the Orchestration View window, right-click **Orchestration Properties** and then click **Properties Window**.</span></span>  

20. <span data-ttu-id="70197-159">[プロパティ] ウィンドウで次のように設定します。、**エクスポート可能なオーケストレーション**プロパティを**False**します。</span><span class="sxs-lookup"><span data-stu-id="70197-159">In the Properties window, set the **Orchestration Exportable** property to **False**.</span></span>  

21. <span data-ttu-id="70197-160">ソリューション エクスプ ローラーでダブルクリック **[ordershipping.wsdl.odx]** します。</span><span class="sxs-lookup"><span data-stu-id="70197-160">In Solution Explorer, double-click **OrderShipping.wsdl.odx**.</span></span>  

22. <span data-ttu-id="70197-161">オーケストレーションの種類 ウィンドウで、**の種類、マルチパート メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="70197-161">In the Orchestration View window, expand **Types/Multipart Message Types**.</span></span>  

23. <span data-ttu-id="70197-162">展開**InvoiceAckMessageType**し **[invoiceackmessagepart]** します。</span><span class="sxs-lookup"><span data-stu-id="70197-162">Expand **InvoiceAckMessageType** and then click **InvoiceAckMessagePart**.</span></span>  

24. <span data-ttu-id="70197-163">[プロパティ] ウィンドウで、展開、**型**フィールドを選択します**参照されたアセンブリからのスキーマと選択**。</span><span class="sxs-lookup"><span data-stu-id="70197-163">In the Properties window, expand the **Type** field, and select **Schemas/Select from referenced Assembly**.</span></span>  

25. <span data-ttu-id="70197-164">**成果物の種類の選択**ダイアログ ボックスで、 をクリックして**ShippingSchemas**を選択します、 **Imported_InvoiceAckMessage**を入力し、クリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="70197-164">In the **Select Artifact Type** dialog box, click **ShippingSchemas**, select the **Imported_InvoiceAckMessage** type, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="70197-165">手順 23 ~ 25 では、ShippingSchemas で説明されている対応するメッセージの種類、BPEL プロセスに参加しているサービスのメッセージの種類を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="70197-165">In steps 23 through 25, you replace the message type of the services that participate in the BPEL process to the corresponding message types described in the ShippingSchemas.</span></span>  

26. <span data-ttu-id="70197-166">次の値を使用してメッセージの種類ごとにステップ 23 ~ 25 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="70197-166">Repeat steps 23 through 25 for each message type using the following values.</span></span>  


    |          <span data-ttu-id="70197-167">メッセージ部分</span><span class="sxs-lookup"><span data-stu-id="70197-167">Message part</span></span>          |                    <span data-ttu-id="70197-168">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="70197-168">Message type</span></span>                     |
    |--------------------------------|-----------------------------------------------------|
    |       <span data-ttu-id="70197-169">InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-169">InvoiceMessagePart</span></span>       |       <span data-ttu-id="70197-170">ShippingSchemas.Imported_InvoiceMessage</span><span class="sxs-lookup"><span data-stu-id="70197-170">ShippingSchemas.Imported_InvoiceMessage</span></span>       |
    |      <span data-ttu-id="70197-171">OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-171">OrderAckMessagePart</span></span>       |      <span data-ttu-id="70197-172">ShippingSchemas.Imported_OrderAckMessage</span><span class="sxs-lookup"><span data-stu-id="70197-172">ShippingSchemas.Imported_OrderAckMessage</span></span>       |
    |        <span data-ttu-id="70197-173">OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-173">OrderMessagePart</span></span>        |        <span data-ttu-id="70197-174">ShippingSchemas.Imported_OrderMessage</span><span class="sxs-lookup"><span data-stu-id="70197-174">ShippingSchemas.Imported_OrderMessage</span></span>        |
    | <span data-ttu-id="70197-175">PaymentConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-175">PaymentConfirmationMessagePart</span></span> | <span data-ttu-id="70197-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="70197-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span></span> |
    | <span data-ttu-id="70197-177">PickupNotificationMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-177">PickupNotificationMessagePart</span></span>  | <span data-ttu-id="70197-178">ShippingSchemas.Imported_PickupNotificationMessage</span><span class="sxs-lookup"><span data-stu-id="70197-178">ShippingSchemas.Imported_PickupNotificationMessage</span></span>  |
    |  <span data-ttu-id="70197-179">ShipConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-179">ShipConfirmationMessagePart</span></span>   |  <span data-ttu-id="70197-180">ShippingSchemas.Imported_ShipConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="70197-180">ShippingSchemas.Imported_ShipConfirmationMessage</span></span>   |
    |      <span data-ttu-id="70197-181">ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="70197-181">ShippingHistoryPart</span></span>       |      <span data-ttu-id="70197-182">ShippingSchemas.Imported_ShippingHistory</span><span class="sxs-lookup"><span data-stu-id="70197-182">ShippingSchemas.Imported_ShippingHistory</span></span>       |
    |   <span data-ttu-id="70197-183">ShipRequestAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-183">ShipRequestAckMessagePart</span></span>    |   <span data-ttu-id="70197-184">ShippingSchemas.Imported_ShipRequestAckMessage</span><span class="sxs-lookup"><span data-stu-id="70197-184">ShippingSchemas.Imported_ShipRequestAckMessage</span></span>    |
    |     <span data-ttu-id="70197-185">ShipRequestMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-185">ShipRequestMessagePart</span></span>     |     <span data-ttu-id="70197-186">ShippingSchemas.Imported_ShipRequestMessage</span><span class="sxs-lookup"><span data-stu-id="70197-186">ShippingSchemas.Imported_ShipRequestMessage</span></span>     |
    |     <span data-ttu-id="70197-187">ShipStatusMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-187">ShipStatusMessagePart</span></span>      |     <span data-ttu-id="70197-188">ShippingSchemas.Imported_ShipStatusMessage</span><span class="sxs-lookup"><span data-stu-id="70197-188">ShippingSchemas.Imported_ShipStatusMessage</span></span>      |


27. <span data-ttu-id="70197-189">ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。</span><span class="sxs-lookup"><span data-stu-id="70197-189">In Solution Explorer, right-click the **BPELShipping** project, point to **Add**, and then click **Existing Item**.</span></span>  

28. <span data-ttu-id="70197-190">すべての .btm ファイルの場所から選択\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping します。</span><span class="sxs-lookup"><span data-stu-id="70197-190">Select all the .btm files from the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.</span></span>  

29. <span data-ttu-id="70197-191">オーケストレーションの種類 ウィンドウで、**メッセージの割り当て**ConstructMessage1 である MessageAssignment_1 という名前の図形し、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="70197-191">In the Orchestration View window, locate the **Message Assignment** shape named MessageAssignment_1 in ConstructMessage1 and delete it.</span></span>  

30. <span data-ttu-id="70197-192">ツールボックスからドラッグして、**変換**図形を ConstructMessage1 図形にします。</span><span class="sxs-lookup"><span data-stu-id="70197-192">From the Toolbox, drag a **Transform** shape into the ConstructMessage1 shape.</span></span>  

31. <span data-ttu-id="70197-193">プロパティ ウィンドウで、省略記号ボタンをクリックします (**...**) を開くと、**変換の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="70197-193">In the Properties window, click the ellipsis button (**…**) and open the **Transform Configuration** dialog box.</span></span>  

32. <span data-ttu-id="70197-194">選択**既存のマップ**します。</span><span class="sxs-lookup"><span data-stu-id="70197-194">Select **Existing Map**.</span></span>  

33. <span data-ttu-id="70197-195">選択、完全修飾マップ名として **[bpelshipping.order2shiprequest]** します。</span><span class="sxs-lookup"><span data-stu-id="70197-195">Select the fully qualified map name as **BPELShipping.Order2ShipRequest**.</span></span>  

34. <span data-ttu-id="70197-196">ソースとして選択**順序。OrderMessagePart**します。</span><span class="sxs-lookup"><span data-stu-id="70197-196">Select the source as **order.OrderMessagePart**.</span></span>  

35. <span data-ttu-id="70197-197">変換先として選択**ship_request します。ShipRequestMessagePart**クリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="70197-197">Select the destination as **ship_request.ShipRequestMessagePart** and click **OK**.</span></span>  

36. <span data-ttu-id="70197-198">各ステップ 29 ~ 35 を繰り返し、**メッセージの割り当て**図形し、置き換え**変換**次の表に従って図形。</span><span class="sxs-lookup"><span data-stu-id="70197-198">Repeat steps 29 through 35 for each of the **Message Assignment** shapes and replace them with **Transform** shapes according to the following table.</span></span>  


    |  <span data-ttu-id="70197-199">置き換える図形</span><span class="sxs-lookup"><span data-stu-id="70197-199">Shape to replace</span></span>   |              <span data-ttu-id="70197-200">マップを使用するには</span><span class="sxs-lookup"><span data-stu-id="70197-200">Map to use</span></span>              |      <span data-ttu-id="70197-201">ソース ドキュメント</span><span class="sxs-lookup"><span data-stu-id="70197-201">Source document</span></span>       |       <span data-ttu-id="70197-202">宛先のドキュメント</span><span class="sxs-lookup"><span data-stu-id="70197-202">Destination document</span></span>        |
    |---------------------|--------------------------------------|----------------------------|-----------------------------------|
    | <span data-ttu-id="70197-203">MessageAssignment_2</span><span class="sxs-lookup"><span data-stu-id="70197-203">MessageAssignment_2</span></span> |     <span data-ttu-id="70197-204">BPELShipping.Order2OrderAck</span><span class="sxs-lookup"><span data-stu-id="70197-204">BPELShipping.Order2OrderAck</span></span>      |   <span data-ttu-id="70197-205">順序。OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-205">order.OrderMessagePart</span></span>   |   <span data-ttu-id="70197-206">order_ack します。OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-206">order_ack.OrderAckMessagePart</span></span>   |
    | <span data-ttu-id="70197-207">MessageAssignment_3</span><span class="sxs-lookup"><span data-stu-id="70197-207">MessageAssignment_3</span></span> |     <span data-ttu-id="70197-208">BPELShipping.Order2OrderNAck</span><span class="sxs-lookup"><span data-stu-id="70197-208">BPELShipping.Order2OrderNAck</span></span>     |   <span data-ttu-id="70197-209">順序。OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-209">order.OrderMessagePart</span></span>   |   <span data-ttu-id="70197-210">order_ack します。OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-210">order_ack.OrderAckMessagePart</span></span>   |
    | <span data-ttu-id="70197-211">MessageAssignment_4</span><span class="sxs-lookup"><span data-stu-id="70197-211">MessageAssignment_4</span></span> |    <span data-ttu-id="70197-212">BPELShipping.Order2ShipHistory</span><span class="sxs-lookup"><span data-stu-id="70197-212">BPELShipping.Order2ShipHistory</span></span>    |   <span data-ttu-id="70197-213">順序。OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-213">order.OrderMessagePart</span></span>   | <span data-ttu-id="70197-214">ship_history します。ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="70197-214">ship_history.ShippingHistoryPart</span></span>  |
    | <span data-ttu-id="70197-215">MessageAssignment_5</span><span class="sxs-lookup"><span data-stu-id="70197-215">MessageAssignment_5</span></span> |  <span data-ttu-id="70197-216">BPELShipping.ShipHistory2Completed</span><span class="sxs-lookup"><span data-stu-id="70197-216">BPELShipping.ShipHistory2Completed</span></span>  |   <span data-ttu-id="70197-217">順序。OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-217">order.OrderMessagePart</span></span>   | <span data-ttu-id="70197-218">ship_history します。ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="70197-218">ship_history.ShippingHistoryPart</span></span>  |
    | <span data-ttu-id="70197-219">MessageAssignment_6</span><span class="sxs-lookup"><span data-stu-id="70197-219">MessageAssignment_6</span></span> |       <span data-ttu-id="70197-220">BPELShipping.Invoice2Ack</span><span class="sxs-lookup"><span data-stu-id="70197-220">BPELShipping.Invoice2Ack</span></span>       | <span data-ttu-id="70197-221">請求書。InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-221">invoice.InvoiceMessagePart</span></span> | <span data-ttu-id="70197-222">invoice_ack します。[Invoiceackmessagepart]</span><span class="sxs-lookup"><span data-stu-id="70197-222">invoice_ack.InvoiceAckMessagePart</span></span> |
    | <span data-ttu-id="70197-223">MessageAssignment_7</span><span class="sxs-lookup"><span data-stu-id="70197-223">MessageAssignment_7</span></span> | <span data-ttu-id="70197-224">BPELShipping.Order2FinalConfirmation</span><span class="sxs-lookup"><span data-stu-id="70197-224">BPELShipping.Order2FinalConfirmation</span></span> |   <span data-ttu-id="70197-225">順序。OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-225">order.OrderMessagePart</span></span>   | <span data-ttu-id="70197-226">order_shipped します。OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="70197-226">order_shipped.OrderAckMessagePart</span></span> |


37. <span data-ttu-id="70197-227">オーケストレーションを保存します。</span><span class="sxs-lookup"><span data-stu-id="70197-227">Save the orchestration.</span></span>  

38. <span data-ttu-id="70197-228">ダブルクリック **[rule_1]** で、**判断**図形**Decision_1**します。</span><span class="sxs-lookup"><span data-stu-id="70197-228">Double-click **Rule_1** in the **Decide** shape **Decision_1**.</span></span>  

39. <span data-ttu-id="70197-229">BizTalk 式エディターで置き換えます</span><span class="sxs-lookup"><span data-stu-id="70197-229">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="70197-230">ship_request_ack(BPELShipping.Ship_Acknowledged) true = =</span><span class="sxs-lookup"><span data-stu-id="70197-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span></span>  

     <span data-ttu-id="70197-231">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="70197-231">with</span></span>  

     <span data-ttu-id="70197-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) true = =</span><span class="sxs-lookup"><span data-stu-id="70197-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span></span>  

40. <span data-ttu-id="70197-233">ダブルクリックして、**ループ**という名前の図形**Loop_1**します。</span><span class="sxs-lookup"><span data-stu-id="70197-233">Double-click the **Loop** shape named **Loop_1**.</span></span>  

41. <span data-ttu-id="70197-234">BizTalk 式エディターで置き換えます</span><span class="sxs-lookup"><span data-stu-id="70197-234">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="70197-235">ship_history(BPELShipping.Ship_Completed) true = =</span><span class="sxs-lookup"><span data-stu-id="70197-235">ship_history(BPELShipping.Ship_Completed) == true</span></span>  

     <span data-ttu-id="70197-236">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="70197-236">with</span></span>  

     <span data-ttu-id="70197-237">ship_history(ShippingSchemas.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="70197-237">ship_history(ShippingSchemas.Ship_Completed) == true</span></span>  

42. <span data-ttu-id="70197-238">ダブルクリック**Rule_2**で、**判断**図形**Decision_2**します。</span><span class="sxs-lookup"><span data-stu-id="70197-238">Double-click **Rule_2** in the **Decide** shape **Decision_2**.</span></span>  

43. <span data-ttu-id="70197-239">BizTalk 式エディターで置き換えます</span><span class="sxs-lookup"><span data-stu-id="70197-239">In BizTalk Expression Editor, replace</span></span>  

     <span data-ttu-id="70197-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="70197-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span></span>  

     <span data-ttu-id="70197-241">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="70197-241">with</span></span>  

     <span data-ttu-id="70197-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="70197-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span></span>  

44. <span data-ttu-id="70197-243">オーケストレーション ビューで、展開**型/関連付けの種類**クリック***OrderCorrelationSet_Type\\***します。</span><span class="sxs-lookup"><span data-stu-id="70197-243">In the Orchestration View, expand **Types/Correlation Types** and click ***OrderCorrelationSet_Type\\***.</span></span>  

45. <span data-ttu-id="70197-244">[プロパティ] ウィンドウで、省略記号ボタンをクリックします (**...**) で**関連付けのプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="70197-244">In the Properties window, click the ellipsis button (**…**) on **Correlation Properties**.</span></span>  

46. <span data-ttu-id="70197-245">ウィンドウに関連付けるプロパティで、次のようにクリックします。 **bpelshipping.orderid**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="70197-245">In the Properties to correlate on pane, click **BPELShipping.OrderID**, and then click **Remove**.</span></span>  

47. <span data-ttu-id="70197-246">使用可能なプロパティ ウィンドウで  **Shippingschemas**を選択します**注文 ID**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="70197-246">In the Available Properties pane, expand **Shipping Schemas**, select **Order ID**, and then click **Add**.</span></span>  

48. <span data-ttu-id="70197-247">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70197-247">Click **OK**.</span></span>  

49. <span data-ttu-id="70197-248">すべてのファイルを保存し、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="70197-248">Save all the files and build the solution.</span></span>  

50. <span data-ttu-id="70197-249">ソリューションを展開する。</span><span class="sxs-lookup"><span data-stu-id="70197-249">Deploy the solution.</span></span>  

51. <span data-ttu-id="70197-250">場所を参照\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\BPELShipping をダブルクリックします**BindAndStartOnly.bat**をバインドして開始しますオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="70197-250">Browse to the location \<*Samples Path*\>\Orchestrations\BPELImport\Solution\BPELShipping and double-click **BindAndStartOnly.bat** to bind and start the orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="70197-251">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="70197-251">Where to Find This Sample</span></span>  
 <span data-ttu-id="70197-252">*\<パスのサンプル\>* \Orchestrations\BPELImport</span><span class="sxs-lookup"><span data-stu-id="70197-252">*\<Samples Path\>* \Orchestrations\BPELImport</span></span>  

 <span data-ttu-id="70197-253">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="70197-253">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="70197-254">ファイル</span><span class="sxs-lookup"><span data-stu-id="70197-254">File(s)</span></span>|<span data-ttu-id="70197-255">説明</span><span class="sxs-lookup"><span data-stu-id="70197-255">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70197-256">BPELSource\InvoiceAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-256">BPELSource\InvoiceAckMessage.xsd</span></span>|<span data-ttu-id="70197-257">請求書の受信確認のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="70197-257">Invoice acknowledgment schema.</span></span>|  
|<span data-ttu-id="70197-258">BPELSource\InvoiceMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-258">BPELSource\InvoiceMessage.xsd</span></span>|<span data-ttu-id="70197-259">請求書スキーマです。</span><span class="sxs-lookup"><span data-stu-id="70197-259">Invoice schema.</span></span>|  
|<span data-ttu-id="70197-260">BPELSource\OrderAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-260">BPELSource\OrderAckMessage.xsd</span></span>|<span data-ttu-id="70197-261">注文の受信確認のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="70197-261">Order acknowledgment schema.</span></span>|  
|<span data-ttu-id="70197-262">BPELSource\OrderHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-262">BPELSource\OrderHeader.xsd</span></span>|<span data-ttu-id="70197-263">注文ヘッダーのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="70197-263">Order header schema.</span></span>|  
|<span data-ttu-id="70197-264">BPELSource\OrderMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-264">BPELSource\OrderMessage.xsd</span></span>|<span data-ttu-id="70197-265">発注書メッセージのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="70197-265">Order message schema.</span></span>|  
|<span data-ttu-id="70197-266">BPELSource\OrderShipping.wsdl</span><span class="sxs-lookup"><span data-stu-id="70197-266">BPELSource\OrderShipping.wsdl</span></span>|<span data-ttu-id="70197-267">BPEL で参照される WSDL ファイル。</span><span class="sxs-lookup"><span data-stu-id="70197-267">WSDL file referred to by BPEL.</span></span>|  
|<span data-ttu-id="70197-268">BPELSource\OrderShippingProcess.bpel</span><span class="sxs-lookup"><span data-stu-id="70197-268">BPELSource\OrderShippingProcess.bpel</span></span>|<span data-ttu-id="70197-269">BPEL プロセス フローです。</span><span class="sxs-lookup"><span data-stu-id="70197-269">BPEL process flow.</span></span>|  
|<span data-ttu-id="70197-270">BPELSource\PaymentConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-270">BPELSource\PaymentConfirmationMessage.xsd</span></span>|<span data-ttu-id="70197-271">支払い確認メッセージです。</span><span class="sxs-lookup"><span data-stu-id="70197-271">Payment confirmation message.</span></span>|  
|<span data-ttu-id="70197-272">BPELSource\PickupNotificationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-272">BPELSource\PickupNotificationMessage.xsd</span></span>|<span data-ttu-id="70197-273">ピックアップ通知メッセージです。</span><span class="sxs-lookup"><span data-stu-id="70197-273">Pickup notification message.</span></span>|  
|<span data-ttu-id="70197-274">BPELSource\ShipConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-274">BPELSource\ShipConfirmationMessage.xsd</span></span>|<span data-ttu-id="70197-275">出荷確認メッセージです。</span><span class="sxs-lookup"><span data-stu-id="70197-275">Shipment confirmation message.</span></span>|  
|<span data-ttu-id="70197-276">BPELSource\ShippingHistory.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-276">BPELSource\ShippingHistory.xsd</span></span>|<span data-ttu-id="70197-277">出荷履歴ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="70197-277">Shipping history document.</span></span>|  
|<span data-ttu-id="70197-278">BPELSource\ShipRequestAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-278">BPELSource\ShipRequestAckMessage.xsd</span></span>|<span data-ttu-id="70197-279">出荷要求の受信確認。</span><span class="sxs-lookup"><span data-stu-id="70197-279">Ship request acknowledgment.</span></span>|  
|<span data-ttu-id="70197-280">BPELSource\ShipRequestMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-280">BPELSource\ShipRequestMessage.xsd</span></span>|<span data-ttu-id="70197-281">出荷要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="70197-281">Ship request message.</span></span>|  
|<span data-ttu-id="70197-282">BPELSource\ShipStatusMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="70197-282">BPELSource\ShipStatusMessage.xsd</span></span>|<span data-ttu-id="70197-283">出荷状態メッセージです。</span><span class="sxs-lookup"><span data-stu-id="70197-283">Ship status message.</span></span>|  
|<span data-ttu-id="70197-284">Solution\bindings\BPELBindings.xml</span><span class="sxs-lookup"><span data-stu-id="70197-284">Solution\bindings\BPELBindings.xml</span></span>|<span data-ttu-id="70197-285">BPELShipping オーケストレーションのポートのバインドを指定するバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="70197-285">Binding file specifying port bindings for the BPELShipping orchestration.</span></span>|  
|<span data-ttu-id="70197-286">Solution\bindings\ShipperBindings.xml</span><span class="sxs-lookup"><span data-stu-id="70197-286">Solution\bindings\ShipperBindings.xml</span></span>|<span data-ttu-id="70197-287">ShipperProcess オーケストレーションのポートのバインドを指定するバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="70197-287">Binding file specifying port bindings for the ShipperProcess orchestration.</span></span>|  
|<span data-ttu-id="70197-288">Solution\BPELShipping\BindAndStartOnly.bat</span><span class="sxs-lookup"><span data-stu-id="70197-288">Solution\BPELShipping\BindAndStartOnly.bat</span></span>|<span data-ttu-id="70197-289">バインドおよび手動で構築およびデプロイされた後、BPELImport オーケストレーションを開始するのに使用するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="70197-289">Batch file to use for binding and starting the BPELImport orchestration after it has been built manually and deployed.</span></span>|  
|<span data-ttu-id="70197-290">Solution\BPELShipping\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="70197-290">Solution\BPELShipping\cleanup.bat</span></span>|<span data-ttu-id="70197-291">BPELShipping プロセスの削除に使用するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="70197-291">Batch file to use to remove the BPELShipping process.</span></span>|  
|<span data-ttu-id="70197-292">Solution\BPELShipping\Setup.bat</span><span class="sxs-lookup"><span data-stu-id="70197-292">Solution\BPELShipping\Setup.bat</span></span>|<span data-ttu-id="70197-293">使用してインストールし、提供されている BPELShipping サンプルを起動するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="70197-293">Batch file to use to install and start the provided BPELShipping sample.</span></span>|  
|<span data-ttu-id="70197-294">Solution\BPELShipping\BPELShipping.sln</span><span class="sxs-lookup"><span data-stu-id="70197-294">Solution\BPELShipping\BPELShipping.sln</span></span>|<span data-ttu-id="70197-295">事前構築済みの BPELShipping サンプルです。</span><span class="sxs-lookup"><span data-stu-id="70197-295">The prebuilt BPELShipping sample.</span></span>|  
<span data-ttu-id="70197-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span><span class="sxs-lookup"><span data-stu-id="70197-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span></span>|<span data-ttu-id="70197-297">受信確認のマップの請求書を請求します。</span><span class="sxs-lookup"><span data-stu-id="70197-297">Invoice to invoice acknowledgment map.</span></span>|  
|<span data-ttu-id="70197-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span><span class="sxs-lookup"><span data-stu-id="70197-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span></span>|<span data-ttu-id="70197-299">注文メッセージから最終的な出荷確認に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="70197-299">Map to convert from Order message to final shipment confirmation.</span></span>|  
|<span data-ttu-id="70197-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span><span class="sxs-lookup"><span data-stu-id="70197-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span></span>|<span data-ttu-id="70197-301">注文メッセージから注文書受信確認に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="70197-301">Map to convert from Order message to order acknowledgment.</span></span>|  
|<span data-ttu-id="70197-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span><span class="sxs-lookup"><span data-stu-id="70197-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span></span>|<span data-ttu-id="70197-303">注文メッセージから注文否定受信確認応答に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="70197-303">Map to convert from Order message to order negative acknowledgment.</span></span>|  
|<span data-ttu-id="70197-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span><span class="sxs-lookup"><span data-stu-id="70197-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span></span>|<span data-ttu-id="70197-305">注文メッセージから出荷履歴ドキュメントに変換するマップします。</span><span class="sxs-lookup"><span data-stu-id="70197-305">Map to convert from Order message to Shipping history document.</span></span>|  
|<span data-ttu-id="70197-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span><span class="sxs-lookup"><span data-stu-id="70197-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span></span>|<span data-ttu-id="70197-307">注文メッセージを注文出荷要求から変換するマップします。</span><span class="sxs-lookup"><span data-stu-id="70197-307">Map to convert from Order message to order Shipping request.</span></span>|  
|<span data-ttu-id="70197-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span><span class="sxs-lookup"><span data-stu-id="70197-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span></span>|<span data-ttu-id="70197-309">出荷履歴を完了に設定するマップです。</span><span class="sxs-lookup"><span data-stu-id="70197-309">Map to set the Shipping history to completed.</span></span>|  
|<span data-ttu-id="70197-310">Solution\ShipperProcess\setup.bat</span><span class="sxs-lookup"><span data-stu-id="70197-310">Solution\ShipperProcess\setup.bat</span></span>|<span data-ttu-id="70197-311">バッチ ファイルをビルドするには、展開し、バインド、ShipperProcess ヘルパー オーケストレーションとそのポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="70197-311">Batch file to build, deploy, bind, and start the ShipperProcess helper orchestration and its ports.</span></span>|  
|<span data-ttu-id="70197-312">Solution\ShipperProcess\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="70197-312">Solution\ShipperProcess\cleanup.bat</span></span>|<span data-ttu-id="70197-313">停止、参加解除、および ShipperProcess ヘルパー オーケストレーションとそのポートを展開解除するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="70197-313">Batch file to stop, unenlist, and undeploy the ShipperProcess helper orchestration and its ports.</span></span>|  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="70197-314">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="70197-314">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="70197-315">最初の手順をビルドして Wide World importers 社をシミュレートするために使用する ShipperProcess アプリケーションを初期化します。</span><span class="sxs-lookup"><span data-stu-id="70197-315">The first step is to build and initialize the ShipperProcess application used to simulate Wide World Importers.</span></span>  

#### <a name="to-build-and-initialize-the-shipperprocess-application"></a><span data-ttu-id="70197-316">ビルドし、ShipperProcess アプリケーションを初期化するには</span><span class="sxs-lookup"><span data-stu-id="70197-316">To build and initialize the ShipperProcess application</span></span>  

1. <span data-ttu-id="70197-317">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="70197-317">Start **Visual Studio Command Prompt**.</span></span>  

2. <span data-ttu-id="70197-318">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="70197-318">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  

    <span data-ttu-id="70197-319">*\<Samples Path\>* \Orchestrations\BPELImport\Solution\ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="70197-319">*\<Samples Path\>* \Orchestrations\BPELImport\Solution\ShipperProcess</span></span>  

3. <span data-ttu-id="70197-320">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="70197-320">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="70197-321">、、ShipperProcess および BPELShipping プロセスで使用されるスキーマを含む ShippingSchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="70197-321">Builds the ShippingSchemas project, which contains the schemas used in the ShipperProcess and the BPELShipping process</span></span>  

   -   <span data-ttu-id="70197-322">ShipperProcess をビルドします。</span><span class="sxs-lookup"><span data-stu-id="70197-322">Builds the ShipperProcess</span></span>  

   -   <span data-ttu-id="70197-323">ShippingSchemas と ShipperProcess プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="70197-323">Deploys the ShippingSchemas and ShipperProcess projects</span></span>  

   -   <span data-ttu-id="70197-324">ShipperProcess で使用されるポートの受信の作成と送信のバインド</span><span class="sxs-lookup"><span data-stu-id="70197-324">Creates and binds the send and receive ports used by ShipperProcess</span></span>  

   -   <span data-ttu-id="70197-325">ShipperProcess で使用されるポートを開始します</span><span class="sxs-lookup"><span data-stu-id="70197-325">Starts the ports used by ShipperProcess</span></span>  

   -   <span data-ttu-id="70197-326">参加させ、ShipperProcess オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="70197-326">Enlists and starts the ShipperProcess orchestration</span></span>  

   <span data-ttu-id="70197-327">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="70197-327">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="70197-328">1 つ以上の次の警告が表示されます。これらを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="70197-328">One or more of the following warnings may be displayed; you can ignore these.</span></span>  

```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  

> [!NOTE]
>  <span data-ttu-id="70197-329">"BPEL からインポートし、実用的なソリューションをビルドします"に記載の手順を完了している場合は、次の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="70197-329">You do not need to perform the following steps if you completed the steps described in "To import from BPEL and build a working solution."</span></span>  

#### <a name="to-build-and-initialize-the-bpelshipping-application"></a><span data-ttu-id="70197-330">ビルドおよび BPELShipping アプリケーションを初期化するには</span><span class="sxs-lookup"><span data-stu-id="70197-330">To build and initialize the BPELShipping application</span></span>  

1. > [!WARNING]
   >  <span data-ttu-id="70197-331">次の手順を実行する前に使用権を持って「をビルドおよび初期化する ShipperProcess アプリケーション」上記の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70197-331">Before executing these steps, you must complete the steps above entitled “To build and initialize the ShipperProcess application”.</span></span>  

    <span data-ttu-id="70197-332">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="70197-332">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  

    <span data-ttu-id="70197-333">*\<パスのサンプル\>* \Orchestrations\BPELImport\Solution\BPELShipping</span><span class="sxs-lookup"><span data-stu-id="70197-333">*\<Samples Path\>* \Orchestrations\BPELImport\Solution\BPELShipping</span></span>  

2. <span data-ttu-id="70197-334">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="70197-334">Run the file Setup.bat, which performs the following actions:</span></span>  

   -   <span data-ttu-id="70197-335">BPELShipping プロジェクトをビルドします</span><span class="sxs-lookup"><span data-stu-id="70197-335">Builds the BPELShipping project</span></span>  

   -   <span data-ttu-id="70197-336">BPELShipping プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="70197-336">Deploys the BPELShipping project</span></span>  

   -   <span data-ttu-id="70197-337">BPELShipping プロセスで使用されるポートの受信の作成と送信のバインド</span><span class="sxs-lookup"><span data-stu-id="70197-337">Creates and binds the send and receive ports used by the BPELShipping process</span></span>  

   -   <span data-ttu-id="70197-338">BPELShipping プロセスで使用されるポートを開始します</span><span class="sxs-lookup"><span data-stu-id="70197-338">Starts the ports used by the BPELShipping process</span></span>  

   -   <span data-ttu-id="70197-339">参加させ、BPELShipping オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="70197-339">Enlists and starts the BPELShipping orchestration</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="70197-340">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="70197-340">Running This Sample</span></span>  

#### <a name="to-run-the-bpel-import-sample"></a><span data-ttu-id="70197-341">BPEL インポート サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="70197-341">To run the BPEL Import sample</span></span>  

1.  <span data-ttu-id="70197-342">コピー、 **Order.xml**ファイルから、 *\<サンプル パス\>* \Orchestrations\BPELImport\Solution フォルダーから、 \<*サンプル パス\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder フォルダー。</span><span class="sxs-lookup"><span data-stu-id="70197-342">Copy the **Order.xml** file from the *\<Samples Path\>* \Orchestrations\BPELImport\Solution folder to the \<*Samples Path\>* \Orchestrations\BPELImport\Solution\Ports\ReceiveOrder folder.</span></span>  

2.  <span data-ttu-id="70197-343">出荷プロセスを通じて、BPELShipping オーケストレーションが顧客の注文処理システムから注文書としてこのファイルが取得が実行され、ファイルが 1 つでそれぞれ、 \<*サンプル パス*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder フォルダーと\<*サンプル パス*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation フォルダー。</span><span class="sxs-lookup"><span data-stu-id="70197-343">The BPELShipping orchestration picks up this file as an order from the customer order processing system, runs through the shipping process, and produces one file each in the \<*Samples Path*\>\Orchestrations\BPELImport\Solution\Ports\SendOrder folder and the \<*Samples Path*\>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation folder.</span></span> <span data-ttu-id="70197-344">これらのファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* 一意に識別する GUID が生成、メッセージ。</span><span class="sxs-lookup"><span data-stu-id="70197-344">The format of the name of these files is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

## <a name="uninstalling-this-sample"></a><span data-ttu-id="70197-345">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="70197-345">Uninstalling This Sample</span></span>  

#### <a name="to-uninstall-the-bpel-import-sample"></a><span data-ttu-id="70197-346">BPEL インポート サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="70197-346">To uninstall the BPEL Import sample</span></span>  

1. <span data-ttu-id="70197-347">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*\>\Orchestrations\BPELImport\BPELShipping します。</span><span class="sxs-lookup"><span data-stu-id="70197-347">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*\>\Orchestrations\BPELImport\BPELShipping.</span></span>  

2. <span data-ttu-id="70197-348">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="70197-348">Run Cleanup.bat.</span></span>  

3. <span data-ttu-id="70197-349">参照する\<*サンプル パス*\>\Orchestrations\BPELImport\ShipperProcess します。</span><span class="sxs-lookup"><span data-stu-id="70197-349">Browse to \<*Samples Path*\>\Orchestrations\BPELImport\ShipperProcess.</span></span>  

4. <span data-ttu-id="70197-350">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="70197-350">Run Cleanup.bat.</span></span>  

## <a name="see-also"></a><span data-ttu-id="70197-351">参照</span><span class="sxs-lookup"><span data-stu-id="70197-351">See Also</span></span>  
 [<span data-ttu-id="70197-352">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="70197-352">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)