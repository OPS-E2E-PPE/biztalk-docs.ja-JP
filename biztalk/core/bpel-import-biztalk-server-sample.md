---
title: "BPEL インポート (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL, orchestrations
- examples, orchestrations
- examples, BPEL Import Wizard
- BPEL, examples
- BPEL Import Wizard, examples
- BPEL Import Wizard, orchestrations
ms.assetid: 3fc70608-ccd9-4249-b238-c09fc6551db1
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b76cead956ade8d16c5cbd26c55f94eabe15e1fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bpel-import-biztalk-server-sample"></a><span data-ttu-id="0a837-102">BPEL インポート (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="0a837-102">BPEL Import (BizTalk Server Sample)</span></span>
<span data-ttu-id="0a837-103">BPEL インポート サンプルは、BPEL (Business Process Execution Language) 処理の記述ファイルと関連アイテムを利用してオーケストレーションを作成する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="0a837-103">The BPEL Import sample demonstrates how to create an orchestration from a Business Process Execution Language (BPEL) process description and its related artifacts.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="0a837-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="0a837-104">What This Sample Does</span></span>  
 <span data-ttu-id="0a837-105">Wide World Importers 社は、小売業者に自動出荷サービスを提供する出荷業者です。</span><span class="sxs-lookup"><span data-stu-id="0a837-105">Wide World Importers is a shipping company that provides automated shipping services to retailers.</span></span> <span data-ttu-id="0a837-106">具体的には、Wide World Importers 社は小売業者に次のサービスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="0a837-106">Specifically, Wide World Importers enables retailers to:</span></span>  
  
-   <span data-ttu-id="0a837-107">注文の出荷要求</span><span class="sxs-lookup"><span data-stu-id="0a837-107">Request order shipments</span></span>  
  
-   <span data-ttu-id="0a837-108">出荷の追跡</span><span class="sxs-lookup"><span data-stu-id="0a837-108">Track shipments</span></span>  
  
-   <span data-ttu-id="0a837-109">出荷の確認</span><span class="sxs-lookup"><span data-stu-id="0a837-109">Confirm shipments</span></span>  
  
-   <span data-ttu-id="0a837-110">出荷に対する請求書発行と支払いの確認</span><span class="sxs-lookup"><span data-stu-id="0a837-110">Confirm invoicing and payment for shipments</span></span>  
  
 <span data-ttu-id="0a837-111">これらのサービスを利用できるかどうかは WSDL (Web Services Description Language) ドキュメントを使用して表すことができます。BPEL ドキュメントでは、製造業者がサービスを呼び出す通常の方法と Wide World Importers 社からの応答方法が記述されます。</span><span class="sxs-lookup"><span data-stu-id="0a837-111">While the availability of these services can be represented by using a Web Services Description Language (WSDL) document, a BPEL document describes the typical way in which the product companies are expected to call the services and how to expect responses from Wide World Importers.</span></span>  
  
 <span data-ttu-id="0a837-112">Northwind Traders という会社が Wide World Importers 社に出荷処理を委託した場合、Northwind Traders 社は全体的な情報のやり取りを記述した BPEL ファイルと関連アイテムを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0a837-112">When Northwind Traders hires Wide World Importers to handle their shipping, they are provided a BPEL file and some related artifacts that describe the entire interaction.</span></span> <span data-ttu-id="0a837-113">Northwind Traders 社はこの BPEL ファイルを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーション (BPELShipping) を作成し、Wide World Importers 社を介して自動的に注文を処理できます。</span><span class="sxs-lookup"><span data-stu-id="0a837-113">Using the BPEL file, Northwind Traders creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application (BPELShipping) to automatically process orders through Wide World Importers.</span></span>  
  
 <span data-ttu-id="0a837-114">このサンプルでは、BPELShipping アプリケーションで次のシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-114">This sample walks you through this scenario in which the BPELShipping application:</span></span>  
  
1.  <span data-ttu-id="0a837-115">Northwind Traders 社の顧客注文システムから注文を受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-115">Receives an order from the Northwind Traders customer order system.</span></span>  
  
2.  <span data-ttu-id="0a837-116">Wide World Importers 社に出荷要求を送信し確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="0a837-116">Sends a shipping request to Wide World Importers and requests confirmation.</span></span>  
  
3.  <span data-ttu-id="0a837-117">Wide World Importers 社から出荷要求の確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-117">Receives shipment request confirmation from Wide World Importers.</span></span>  
  
4.  <span data-ttu-id="0a837-118">Wide World Importers 社からピックアップ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-118">Receives pickup notification from Wide World Importers.</span></span>  
  
5.  <span data-ttu-id="0a837-119">出荷製品が顧客に配送され、受理されるまでの出荷状況メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-119">Receives shipment status messages up to and including when the shipment has been received by the customer.</span></span>  
  
6.  <span data-ttu-id="0a837-120">Wide World Importers 社から請求書を受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-120">Receives an invoice from Wide World Importers.</span></span>  
  
7.  <span data-ttu-id="0a837-121">Wide World Importers 社に請求書受領の応答を返します。</span><span class="sxs-lookup"><span data-stu-id="0a837-121">Responds to Wide World Importers with an invoice acknowledgment.</span></span>  
  
8.  <span data-ttu-id="0a837-122">Wide World Importers 社から支払い確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-122">Receives a payment confirmation from Wide World Importers.</span></span>  
  
9. <span data-ttu-id="0a837-123">注文システムに最終的な出荷確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="0a837-123">Sends a final shipping confirmation to the ordering system.</span></span>  
  
 <span data-ttu-id="0a837-124">このサンプルでは、個別の BizTalk アプリケーション (ShipperProcess) を使用して、Wide World Importers 社の役割をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="0a837-124">A separate BizTalk application (ShipperProcess) is used to simulate Wide World Importers for this sample.</span></span> <span data-ttu-id="0a837-125">BPELShipping アプリケーションは、FILE トランスポートを介して ShipperProcess と通信します。ここでは、通信用に共通のファイル システムの場所が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a837-125">The BPELShipping application communicates with ShipperProcess by using the FILE transport, which uses common file system locations for the communication.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="0a837-126">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="0a837-126">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="0a837-127">BPEL for Web Services はビジネス プロセスを記述する XML ベースの言語で、異なる企業間で Web サービスを使用して取引する場合に、ビジネス プロセスを簡単に共有できるようにするものです。</span><span class="sxs-lookup"><span data-stu-id="0a837-127">BPEL for Web services is an XML-based language to describe the business process so that it can be easily shared across different companies who want to do business with each other using Web services.</span></span> <span data-ttu-id="0a837-128">BPEL ではビジネス プロトコル レベルでビジネス プロセスの処理方法を記述します。パートナーから受信した注文書の処理など、企業内部で行うプロセスについては記述しません。</span><span class="sxs-lookup"><span data-stu-id="0a837-128">BPEL describes how to handle the business process at the business protocol level, but it does not describe the internal process in a company, such as the steps a company would take to process a purchase order after receiving it from a partner.</span></span> <span data-ttu-id="0a837-129">このサンプルでは、BPEL ファイルとそれに対応する WSDL ファイルをインポートし、これらのファイルをオーケストレーションに変換した後、パートナーとのビジネス プロセスを開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0a837-129">This sample is designed to show you how to import BPEL and corresponding WSDL files, convert them into an orchestration, and then start to run the business process with the partner.</span></span>  
  
 <span data-ttu-id="0a837-130">以下は、BPEL ファイルと WSDL ファイルをインポートし、これらのファイルをオーケストレーションに変換して、ビルド済みの BizTalk アプリケーション (ShipperProcess) とやり取りする場合の一連の手順です。</span><span class="sxs-lookup"><span data-stu-id="0a837-130">The following is the step-by-step procedure showing how to import the BPEL and WSDL files and convert them into an orchestration to interact with a prebuilt BizTalk application (ShipperProcess).</span></span> <span data-ttu-id="0a837-131">この手順を完了した場合、「BPELShipping アプリケーションをビルドおよび初期化するには」に示されている手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a837-131">If you complete the following steps, you do not need to perform the steps described in "To build and initialize the BPELShipping application".</span></span>  
  
#### <a name="to-import-from-bpel-and-build-a-working-solution"></a><span data-ttu-id="0a837-132">BPEL からインポートして実際のソリューションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="0a837-132">To import from BPEL and build a working solution</span></span>  
  
1.  <span data-ttu-id="0a837-133">Microsoft では[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをクリックして**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-133">In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a837-134">この手順を完了する前に、サポートのプロセスおよびスキーマ プロジェクトを作成する ShipperProcess アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a837-134">Before completing this procedure, you must set up the ShipperProcess application to create the supporting processes and schema projects.</span></span>  
  
2.  <span data-ttu-id="0a837-135">**新しいプロジェクト**ダイアログ ボックスで、プロジェクトの種類 ウィンドウで**BizTalk (プロジェクト)**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-135">In the **New Project** dialog box, in the Project Types pane, select **BizTalk (Projects)**.</span></span> <span data-ttu-id="0a837-136">[テンプレート] ペインで選択**BizTalk Server BPEL インポート プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-136">In the Templates pane, select **BizTalk (Server) BPEL Import Project**.</span></span>  
  
3.  <span data-ttu-id="0a837-137">**名前**ボックスに、入力**BPELShipping**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-137">In the **Name** box, enter **BPELShipping**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a837-138">別の名前を使用すると、最後のバインド ステップで問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0a837-138">If you use a different name, you may experience problems with the final binding step.</span></span>  
  
4.  <span data-ttu-id="0a837-139">プロジェクトの場所を選択し、をクリックして**OK** BPEL インポート ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="0a837-139">Select a location for the project, and then click **OK** to start the BPEL Import Wizard.</span></span>  
  
5.  <span data-ttu-id="0a837-140">**ようこそ** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-140">On the **Welcome** page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="0a837-141">**選択 BPEL、WSDL、および XSD ファイル**] ページで [**参照**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-141">On the **Select BPEL, WSDL, and XSD Files** page, click **Browse**.</span></span>  
  
7.  <span data-ttu-id="0a837-142">すべてのファイルを選択、 \<*サンプル パス*> \Orchestrations\BPELImport\BPELSource フォルダー をクリックして**開く**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-142">Select all the files from the \<*Samples Path*>\Orchestrations\BPELImport\BPELSource folder, click **Open**, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a837-143">このステップでは、ビジネス プロセスを記述する BPEL ファイルと WSDL ファイル、およびビジネス ドキュメント スキーマを表す XSD ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a837-143">In this step, you select the BPEL and WSDL files to describe the business process and the XSD files to represent the business document schemas.</span></span>  
  
8.  <span data-ttu-id="0a837-144">**呼び出した WebServices 用の WSDL ファイルの選択**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-144">On the **Select WSDL Files for Invoked WebServices** page, click **Finish**.</span></span>  
  
9. <span data-ttu-id="0a837-145">BPEL インポート ウィザードにインポートが正常に完了したことが表示されたら、ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0a837-145">After the BPEL Import Wizard reports a successful import, close the wizard.</span></span> <span data-ttu-id="0a837-146">これでプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0a837-146">The project is now created.</span></span>  
  
10. <span data-ttu-id="0a837-147">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) プロジェクトの場所にします。</span><span class="sxs-lookup"><span data-stu-id="0a837-147">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the project location.</span></span>  
  
11. <span data-ttu-id="0a837-148">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-148">Run the following command:</span></span>  
  
     <span data-ttu-id="0a837-149">**sn – k BPELShipping.snk**</span><span class="sxs-lookup"><span data-stu-id="0a837-149">**sn –k BPELShipping.snk**</span></span>  
  
12. <span data-ttu-id="0a837-150">ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-150">In Solution Explorer, right-click the **BPELShipping** project, and then click **Properties**.</span></span>  
  
13. <span data-ttu-id="0a837-151">**Common properties \assembly**、アセンブリ キー ファイルを選択して**BPELShipping.snk**ステップ 11 で作成され、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-151">Under **Common Properties\Assembly**, select the assembly key file **BPELShipping.snk** created in step 11, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="0a837-152">ソリューション エクスプローラーで、すべての .xsd ファイルを選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="0a837-152">In Solution Explorer, select all the .xsd files and delete them.</span></span>  
  
15. <span data-ttu-id="0a837-153">ソリューション エクスプ ローラーで、次のように選択します。**参照の追加**、および、**プロジェクト** タブで、 をクリック**参照**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-153">In Solution Explorer, select **Add Reference**, and on the **Projects** tab, click **Browse**.</span></span>  
  
16. <span data-ttu-id="0a837-154">選択**ShippingSchemas.dll**の場所から\<*サンプル パス*> \Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development、をクリックして**[Ok]**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-154">Select **ShippingSchemas.dll** from the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\ShipperProcess\ShippingSchemas\bin\Development, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a837-155">このビルド方法については、「ShipperProcess アプリケーションをビルドおよび初期化するには」で説明します。</span><span class="sxs-lookup"><span data-stu-id="0a837-155">The section "To build and initialize the ShipperProcess application" has instructions on how to build this.</span></span>  
  
17. <span data-ttu-id="0a837-156">ソリューション エクスプ ローラーで、 **[ordershippingprocess.bpel.odx]**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-156">In Solution Explorer, double-click **OrderShippingProcess.bpel.odx**.</span></span>  
  
18. <span data-ttu-id="0a837-157">**ビュー**メニューの **その他の Windows/オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-157">On the **View** menu, select **Other Windows/Orchestration View**.</span></span>  
  
19. <span data-ttu-id="0a837-158">オーケストレーションの種類 ウィンドウで、右クリック**オーケストレーションのプロパティ** をクリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="0a837-158">In the Orchestration View window, right-click **Orchestration Properties** and then click **Properties Window**.</span></span>  
  
20. <span data-ttu-id="0a837-159">[プロパティ] ウィンドウで、設定、**エクスポート可能なオーケストレーション**プロパティを**False**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-159">In the Properties window, set the **Orchestration Exportable** property to **False**.</span></span>  
  
21. <span data-ttu-id="0a837-160">ソリューション エクスプ ローラーで、 **[ordershipping.wsdl.odx]**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-160">In Solution Explorer, double-click **OrderShipping.wsdl.odx**.</span></span>  
  
22. <span data-ttu-id="0a837-161">オーケストレーションの種類 ウィンドウで、**型/マルチパート メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-161">In the Orchestration View window, expand **Types/Multipart Message Types**.</span></span>  
  
23. <span data-ttu-id="0a837-162">展開**InvoiceAckMessageType**  をクリックし、 **invoiceackmessagepart**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-162">Expand **InvoiceAckMessageType** and then click **InvoiceAckMessagePart**.</span></span>  
  
24. <span data-ttu-id="0a837-163">[プロパティ] ウィンドウで、展開、**型**フィールド、および select**参照されたアセンブリからスキーマ/選択**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-163">In the Properties window, expand the **Type** field, and select **Schemas/Select from referenced Assembly**.</span></span>  
  
25. <span data-ttu-id="0a837-164">**成果物の種類の選択**ダイアログ ボックスで、をクリックして**ShippingSchemas**を選択、 **Imported_InvoiceAckMessage** 「」と  をクリックして**OK**.</span><span class="sxs-lookup"><span data-stu-id="0a837-164">In the **Select Artifact Type** dialog box, click **ShippingSchemas**, select the **Imported_InvoiceAckMessage** type, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a837-165">ステップ 23 ～ 25 では、BPEL プロセスに参加しているサービスのメッセージの種類を、ShippingSchemas で記述されている対応するメッセージの種類に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a837-165">In steps 23 through 25, you replace the message type of the services that participate in the BPEL process to the corresponding message types described in the ShippingSchemas.</span></span>  
  
26. <span data-ttu-id="0a837-166">メッセージの種類ごとに、次の値を使用してステップ 23 ～ 25 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0a837-166">Repeat steps 23 through 25 for each message type using the following values.</span></span>  
  
    |<span data-ttu-id="0a837-167">メッセージ部分</span><span class="sxs-lookup"><span data-stu-id="0a837-167">Message part</span></span>|<span data-ttu-id="0a837-168">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="0a837-168">Message type</span></span>|  
    |------------------|------------------|  
    |<span data-ttu-id="0a837-169">InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-169">InvoiceMessagePart</span></span>|<span data-ttu-id="0a837-170">ShippingSchemas.Imported_InvoiceMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-170">ShippingSchemas.Imported_InvoiceMessage</span></span>|  
    |<span data-ttu-id="0a837-171">OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-171">OrderAckMessagePart</span></span>|<span data-ttu-id="0a837-172">ShippingSchemas.Imported_OrderAckMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-172">ShippingSchemas.Imported_OrderAckMessage</span></span>|  
    |<span data-ttu-id="0a837-173">OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-173">OrderMessagePart</span></span>|<span data-ttu-id="0a837-174">ShippingSchemas.Imported_OrderMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-174">ShippingSchemas.Imported_OrderMessage</span></span>|  
    |<span data-ttu-id="0a837-175">PaymentConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-175">PaymentConfirmationMessagePart</span></span>|<span data-ttu-id="0a837-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-176">ShippingSchemas.Imported_PaymentConfirmationMessage</span></span>|  
    |<span data-ttu-id="0a837-177">PickupNotificationMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-177">PickupNotificationMessagePart</span></span>|<span data-ttu-id="0a837-178">ShippingSchemas.Imported_PickupNotificationMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-178">ShippingSchemas.Imported_PickupNotificationMessage</span></span>|  
    |<span data-ttu-id="0a837-179">ShipConfirmationMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-179">ShipConfirmationMessagePart</span></span>|<span data-ttu-id="0a837-180">ShippingSchemas.Imported_ShipConfirmationMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-180">ShippingSchemas.Imported_ShipConfirmationMessage</span></span>|  
    |<span data-ttu-id="0a837-181">ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="0a837-181">ShippingHistoryPart</span></span>|<span data-ttu-id="0a837-182">ShippingSchemas.Imported_ShippingHistory</span><span class="sxs-lookup"><span data-stu-id="0a837-182">ShippingSchemas.Imported_ShippingHistory</span></span>|  
    |<span data-ttu-id="0a837-183">ShipRequestAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-183">ShipRequestAckMessagePart</span></span>|<span data-ttu-id="0a837-184">ShippingSchemas.Imported_ShipRequestAckMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-184">ShippingSchemas.Imported_ShipRequestAckMessage</span></span>|  
    |<span data-ttu-id="0a837-185">ShipRequestMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-185">ShipRequestMessagePart</span></span>|<span data-ttu-id="0a837-186">ShippingSchemas.Imported_ShipRequestMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-186">ShippingSchemas.Imported_ShipRequestMessage</span></span>|  
    |<span data-ttu-id="0a837-187">ShipStatusMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-187">ShipStatusMessagePart</span></span>|<span data-ttu-id="0a837-188">ShippingSchemas.Imported_ShipStatusMessage</span><span class="sxs-lookup"><span data-stu-id="0a837-188">ShippingSchemas.Imported_ShipStatusMessage</span></span>|  
  
27. <span data-ttu-id="0a837-189">ソリューション エクスプ ローラーで右クリックし、 **BPELShipping**プロジェクトをポイントし、**追加**、順にクリック**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="0a837-189">In Solution Explorer, right-click the **BPELShipping** project, point to **Add**, and then click **Existing Item**.</span></span>  
  
28. <span data-ttu-id="0a837-190">すべての .btm ファイル位置から選択する\<*サンプル パス*> \Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping です。</span><span class="sxs-lookup"><span data-stu-id="0a837-190">Select all the .btm files from the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\BPELShipping\BPELShipping.</span></span>  
  
29. <span data-ttu-id="0a837-191">オーケストレーションの種類 ウィンドウで、**メッセージの割り当て**ConstructMessage1 内の名前付きの MessageAssignment_1 図形し、それを削除します。</span><span class="sxs-lookup"><span data-stu-id="0a837-191">In the Orchestration View window, locate the **Message Assignment** shape named MessageAssignment_1 in ConstructMessage1 and delete it.</span></span>  
  
30. <span data-ttu-id="0a837-192">ツールボックスからドラッグして、**変換**図形を ConstructMessage1 図形にします。</span><span class="sxs-lookup"><span data-stu-id="0a837-192">From the Toolbox, drag a **Transform** shape into the ConstructMessage1 shape.</span></span>  
  
31. <span data-ttu-id="0a837-193">プロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) を開くと、**変換の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="0a837-193">In the Properties window, click the ellipsis button (**…**) and open the **Transform Configuration** dialog box.</span></span>  
  
32. <span data-ttu-id="0a837-194">選択**既存のマップ**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-194">Select **Existing Map**.</span></span>  
  
33. <span data-ttu-id="0a837-195">完全修飾マップ名を選択して**[bpelshipping.order2shiprequest]**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-195">Select the fully qualified map name as **BPELShipping.Order2ShipRequest**.</span></span>  
  
34. <span data-ttu-id="0a837-196">ソースとして選択**順序。OrderMessagePart**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-196">Select the source as **order.OrderMessagePart**.</span></span>  
  
35. <span data-ttu-id="0a837-197">変換先として選択**ship_request です。ShipRequestMessagePart**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-197">Select the destination as **ship_request.ShipRequestMessagePart** and click **OK**.</span></span>  
  
36. <span data-ttu-id="0a837-198">各ステップ 29 ~ 35 を繰り返し、**メッセージの割り当て**図形し、の置換**変換**次の表に従って図形です。</span><span class="sxs-lookup"><span data-stu-id="0a837-198">Repeat steps 29 through 35 for each of the **Message Assignment** shapes and replace them with **Transform** shapes according to the following table.</span></span>  
  
    |<span data-ttu-id="0a837-199">置き換える図形</span><span class="sxs-lookup"><span data-stu-id="0a837-199">Shape to replace</span></span>|<span data-ttu-id="0a837-200">使用するマップ</span><span class="sxs-lookup"><span data-stu-id="0a837-200">Map to use</span></span>|<span data-ttu-id="0a837-201">置き換え元ドキュメント</span><span class="sxs-lookup"><span data-stu-id="0a837-201">Source document</span></span>|<span data-ttu-id="0a837-202">置き換え先ドキュメント</span><span class="sxs-lookup"><span data-stu-id="0a837-202">Destination document</span></span>|  
    |----------------------|----------------|---------------------|--------------------------|  
    |<span data-ttu-id="0a837-203">MessageAssignment_2</span><span class="sxs-lookup"><span data-stu-id="0a837-203">MessageAssignment_2</span></span>|<span data-ttu-id="0a837-204">BPELShipping.Order2OrderAck</span><span class="sxs-lookup"><span data-stu-id="0a837-204">BPELShipping.Order2OrderAck</span></span>|<span data-ttu-id="0a837-205">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-205">order.OrderMessagePart</span></span>|<span data-ttu-id="0a837-206">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-206">order_ack.OrderAckMessagePart</span></span>|  
    |<span data-ttu-id="0a837-207">MessageAssignment_3</span><span class="sxs-lookup"><span data-stu-id="0a837-207">MessageAssignment_3</span></span>|<span data-ttu-id="0a837-208">BPELShipping.Order2OrderNAck</span><span class="sxs-lookup"><span data-stu-id="0a837-208">BPELShipping.Order2OrderNAck</span></span>|<span data-ttu-id="0a837-209">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-209">order.OrderMessagePart</span></span>|<span data-ttu-id="0a837-210">order_ack.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-210">order_ack.OrderAckMessagePart</span></span>|  
    |<span data-ttu-id="0a837-211">MessageAssignment_4</span><span class="sxs-lookup"><span data-stu-id="0a837-211">MessageAssignment_4</span></span>|<span data-ttu-id="0a837-212">BPELShipping.Order2ShipHistory</span><span class="sxs-lookup"><span data-stu-id="0a837-212">BPELShipping.Order2ShipHistory</span></span>|<span data-ttu-id="0a837-213">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-213">order.OrderMessagePart</span></span>|<span data-ttu-id="0a837-214">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="0a837-214">ship_history.ShippingHistoryPart</span></span>|  
    |<span data-ttu-id="0a837-215">MessageAssignment_5</span><span class="sxs-lookup"><span data-stu-id="0a837-215">MessageAssignment_5</span></span>|<span data-ttu-id="0a837-216">BPELShipping.ShipHistory2Completed</span><span class="sxs-lookup"><span data-stu-id="0a837-216">BPELShipping.ShipHistory2Completed</span></span>|<span data-ttu-id="0a837-217">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-217">order.OrderMessagePart</span></span>|<span data-ttu-id="0a837-218">ship_history.ShippingHistoryPart</span><span class="sxs-lookup"><span data-stu-id="0a837-218">ship_history.ShippingHistoryPart</span></span>|  
    |<span data-ttu-id="0a837-219">MessageAssignment_6</span><span class="sxs-lookup"><span data-stu-id="0a837-219">MessageAssignment_6</span></span>|<span data-ttu-id="0a837-220">BPELShipping.Invoice2Ack</span><span class="sxs-lookup"><span data-stu-id="0a837-220">BPELShipping.Invoice2Ack</span></span>|<span data-ttu-id="0a837-221">invoice.InvoiceMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-221">invoice.InvoiceMessagePart</span></span>|<span data-ttu-id="0a837-222">invoice_ack.InvoiceAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-222">invoice_ack.InvoiceAckMessagePart</span></span>|  
    |<span data-ttu-id="0a837-223">MessageAssignment_7</span><span class="sxs-lookup"><span data-stu-id="0a837-223">MessageAssignment_7</span></span>|<span data-ttu-id="0a837-224">BPELShipping.Order2FinalConfirmation</span><span class="sxs-lookup"><span data-stu-id="0a837-224">BPELShipping.Order2FinalConfirmation</span></span>|<span data-ttu-id="0a837-225">order.OrderMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-225">order.OrderMessagePart</span></span>|<span data-ttu-id="0a837-226">order_shipped.OrderAckMessagePart</span><span class="sxs-lookup"><span data-stu-id="0a837-226">order_shipped.OrderAckMessagePart</span></span>|  
  
37. <span data-ttu-id="0a837-227">オーケストレーションを保存します。</span><span class="sxs-lookup"><span data-stu-id="0a837-227">Save the orchestration.</span></span>  
  
38. <span data-ttu-id="0a837-228">ダブルクリックして**Rule_1**で、**判断**図形**Decision_1**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-228">Double-click **Rule_1** in the **Decide** shape **Decision_1**.</span></span>  
  
39. <span data-ttu-id="0a837-229">BizTalk 式エディターで、次の部分を探します。</span><span class="sxs-lookup"><span data-stu-id="0a837-229">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="0a837-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="0a837-230">ship_request_ack(BPELShipping.Ship_Acknowledged) == true</span></span>  
  
     <span data-ttu-id="0a837-231">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a837-231">with</span></span>  
  
     <span data-ttu-id="0a837-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span><span class="sxs-lookup"><span data-stu-id="0a837-232">ship_request_ack(ShippingSchemas.Ship_Acknowledged) == true</span></span>  
  
40. <span data-ttu-id="0a837-233">ダブルクリックして、**ループ**という名前の図形**Loop_1**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-233">Double-click the **Loop** shape named **Loop_1**.</span></span>  
  
41. <span data-ttu-id="0a837-234">BizTalk 式エディターで、次の部分を探します。</span><span class="sxs-lookup"><span data-stu-id="0a837-234">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="0a837-235">ship_history(BPELShipping.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="0a837-235">ship_history(BPELShipping.Ship_Completed) == true</span></span>  
  
     <span data-ttu-id="0a837-236">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a837-236">with</span></span>  
  
     <span data-ttu-id="0a837-237">ship_history(ShippingSchemas.Ship_Completed) == true</span><span class="sxs-lookup"><span data-stu-id="0a837-237">ship_history(ShippingSchemas.Ship_Completed) == true</span></span>  
  
42. <span data-ttu-id="0a837-238">ダブルクリックして**Rule_2**で、**判断**図形**Decision_2**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-238">Double-click **Rule_2** in the **Decide** shape **Decision_2**.</span></span>  
  
43. <span data-ttu-id="0a837-239">BizTalk 式エディターで、次の部分を探します。</span><span class="sxs-lookup"><span data-stu-id="0a837-239">In BizTalk Expression Editor, replace</span></span>  
  
     <span data-ttu-id="0a837-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="0a837-240">ship_status(BPELShipping.ShipStatus) == "DONE"</span></span>  
  
     <span data-ttu-id="0a837-241">これを次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a837-241">with</span></span>  
  
     <span data-ttu-id="0a837-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span><span class="sxs-lookup"><span data-stu-id="0a837-242">ship_status(ShippingSchemas.ShipStatus) == "DONE"</span></span>  
  
44. <span data-ttu-id="0a837-243">オーケストレーション ビューで、展開**型/関連付けの種類** をクリック**_OrderCorrelationSet_Type\_**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-243">In the Orchestration View, expand **Types/Correlation Types** and click **_OrderCorrelationSet_Type\_**.</span></span>  
  
45. <span data-ttu-id="0a837-244">[プロパティ] ウィンドウで、省略記号ボタンをクリックします (**.**) で**関連付けのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-244">In the Properties window, click the ellipsis button (**…**) on **Correlation Properties**.</span></span>  
  
46. <span data-ttu-id="0a837-245">ウィンドウに関連付けるプロパティで、をクリックして**[bpelshipping.orderid]**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-245">In the Properties to correlate on pane, click **BPELShipping.OrderID**, and then click **Remove**.</span></span>  
  
47. <span data-ttu-id="0a837-246">使用可能なプロパティ ウィンドウで  **Shippingschemas****注文 ID**、順にクリック**追加**。</span><span class="sxs-lookup"><span data-stu-id="0a837-246">In the Available Properties pane, expand **Shipping Schemas**, select **Order ID**, and then click **Add**.</span></span>  
  
48. <span data-ttu-id="0a837-247">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a837-247">Click **OK**.</span></span>  
  
49. <span data-ttu-id="0a837-248">すべてのファイルを保存し、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-248">Save all the files and build the solution.</span></span>  
  
50. <span data-ttu-id="0a837-249">ソリューションを展開する。</span><span class="sxs-lookup"><span data-stu-id="0a837-249">Deploy the solution.</span></span>  
  
51. <span data-ttu-id="0a837-250">場所を参照\<*サンプル パス*> \Orchestrations\BPELImport\Solution\BPELShipping およびダブルクリック**BindAndStartOnly.bat**をバインドし、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="0a837-250">Browse to the location \<*Samples Path*>\Orchestrations\BPELImport\Solution\BPELShipping and double-click **BindAndStartOnly.bat** to bind and start the orchestration.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="0a837-251">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="0a837-251">Where to Find This Sample</span></span>  
 <span data-ttu-id="0a837-252">*\<サンプル パス >*\Orchestrations\BPELImport</span><span class="sxs-lookup"><span data-stu-id="0a837-252">*\<Samples Path>*\Orchestrations\BPELImport</span></span>  
  
 <span data-ttu-id="0a837-253">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="0a837-253">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="0a837-254">ファイル</span><span class="sxs-lookup"><span data-stu-id="0a837-254">File(s)</span></span>|<span data-ttu-id="0a837-255">Description</span><span class="sxs-lookup"><span data-stu-id="0a837-255">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a837-256">BPELSource\InvoiceAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-256">BPELSource\InvoiceAckMessage.xsd</span></span>|<span data-ttu-id="0a837-257">請求書の受信確認応答スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0a837-257">Invoice acknowledgment schema.</span></span>|  
|<span data-ttu-id="0a837-258">BPELSource\InvoiceMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-258">BPELSource\InvoiceMessage.xsd</span></span>|<span data-ttu-id="0a837-259">請求書スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0a837-259">Invoice schema.</span></span>|  
|<span data-ttu-id="0a837-260">BPELSource\OrderAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-260">BPELSource\OrderAckMessage.xsd</span></span>|<span data-ttu-id="0a837-261">注文書の受信確認応答スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0a837-261">Order acknowledgment schema.</span></span>|  
|<span data-ttu-id="0a837-262">BPELSource\OrderHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-262">BPELSource\OrderHeader.xsd</span></span>|<span data-ttu-id="0a837-263">注文書ヘッダー スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0a837-263">Order header schema.</span></span>|  
|<span data-ttu-id="0a837-264">BPELSource\OrderMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-264">BPELSource\OrderMessage.xsd</span></span>|<span data-ttu-id="0a837-265">注文書メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="0a837-265">Order message schema.</span></span>|  
|<span data-ttu-id="0a837-266">BPELSource\OrderShipping.wsdl</span><span class="sxs-lookup"><span data-stu-id="0a837-266">BPELSource\OrderShipping.wsdl</span></span>|<span data-ttu-id="0a837-267">BPEL で参照されている WSDL ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-267">WSDL file referred to by BPEL.</span></span>|  
|<span data-ttu-id="0a837-268">BPELSource\OrderShippingProcess.bpel</span><span class="sxs-lookup"><span data-stu-id="0a837-268">BPELSource\OrderShippingProcess.bpel</span></span>|<span data-ttu-id="0a837-269">BPEL プロセス フローです。</span><span class="sxs-lookup"><span data-stu-id="0a837-269">BPEL process flow.</span></span>|  
|<span data-ttu-id="0a837-270">BPELSource\PaymentConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-270">BPELSource\PaymentConfirmationMessage.xsd</span></span>|<span data-ttu-id="0a837-271">支払い確認メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0a837-271">Payment confirmation message.</span></span>|  
|<span data-ttu-id="0a837-272">BPELSource\PickupNotificationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-272">BPELSource\PickupNotificationMessage.xsd</span></span>|<span data-ttu-id="0a837-273">ピックアップ通知メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0a837-273">Pickup notification message.</span></span>|  
|<span data-ttu-id="0a837-274">BPELSource\ShipConfirmationMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-274">BPELSource\ShipConfirmationMessage.xsd</span></span>|<span data-ttu-id="0a837-275">出荷確認メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0a837-275">Shipment confirmation message.</span></span>|  
|<span data-ttu-id="0a837-276">BPELSource\ShippingHistory.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-276">BPELSource\ShippingHistory.xsd</span></span>|<span data-ttu-id="0a837-277">出荷履歴ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="0a837-277">Shipping history document.</span></span>|  
|<span data-ttu-id="0a837-278">BPELSource\ShipRequestAckMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-278">BPELSource\ShipRequestAckMessage.xsd</span></span>|<span data-ttu-id="0a837-279">出荷要求の受信確認応答です。</span><span class="sxs-lookup"><span data-stu-id="0a837-279">Ship request acknowledgment.</span></span>|  
|<span data-ttu-id="0a837-280">BPELSource\ShipRequestMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-280">BPELSource\ShipRequestMessage.xsd</span></span>|<span data-ttu-id="0a837-281">出荷要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0a837-281">Ship request message.</span></span>|  
|<span data-ttu-id="0a837-282">BPELSource\ShipStatusMessage.xsd</span><span class="sxs-lookup"><span data-stu-id="0a837-282">BPELSource\ShipStatusMessage.xsd</span></span>|<span data-ttu-id="0a837-283">出荷状態メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0a837-283">Ship status message.</span></span>|  
|<span data-ttu-id="0a837-284">Solution\bindings\BPELBindings.xml</span><span class="sxs-lookup"><span data-stu-id="0a837-284">Solution\bindings\BPELBindings.xml</span></span>|<span data-ttu-id="0a837-285">BPELShipping オーケストレーションのポートのバインドを指定するバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-285">Binding file specifying port bindings for the BPELShipping orchestration.</span></span>|  
|<span data-ttu-id="0a837-286">Solution\bindings\ShipperBindings.xml</span><span class="sxs-lookup"><span data-stu-id="0a837-286">Solution\bindings\ShipperBindings.xml</span></span>|<span data-ttu-id="0a837-287">ShipperProcess オーケストレーションのポートのバインドを指定するバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-287">Binding file specifying port bindings for the ShipperProcess orchestration.</span></span>|  
|<span data-ttu-id="0a837-288">Solution\BPELShipping\BindAndStartOnly.bat</span><span class="sxs-lookup"><span data-stu-id="0a837-288">Solution\BPELShipping\BindAndStartOnly.bat</span></span>|<span data-ttu-id="0a837-289">手動でビルドし展開した BPELImport オーケストレーションを、バインドおよび開始するときに使用するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-289">Batch file to use for binding and starting the BPELImport orchestration after it has been built manually and deployed.</span></span>|  
|<span data-ttu-id="0a837-290">Solution\BPELShipping\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0a837-290">Solution\BPELShipping\cleanup.bat</span></span>|<span data-ttu-id="0a837-291">BPELShipping プロセスの削除に使用するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-291">Batch file to use to remove the BPELShipping process.</span></span>|  
|<span data-ttu-id="0a837-292">Solution\BPELShipping\Setup.bat</span><span class="sxs-lookup"><span data-stu-id="0a837-292">Solution\BPELShipping\Setup.bat</span></span>|<span data-ttu-id="0a837-293">提供されている BPELShipping サンプルをインストールおよび開始するときに使用するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-293">Batch file to use to install and start the provided BPELShipping sample.</span></span>|  
|<span data-ttu-id="0a837-294">Solution\BPELShipping\BPELShipping.sln</span><span class="sxs-lookup"><span data-stu-id="0a837-294">Solution\BPELShipping\BPELShipping.sln</span></span>|<span data-ttu-id="0a837-295">ビルド済みの BPELShipping サンプルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-295">The prebuilt BPELShipping sample.</span></span>|  
<span data-ttu-id="0a837-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-296">olution\BPELShipping\BPELShipping\Invoice2Ack.btm</span></span>|<span data-ttu-id="0a837-297">請求書と請求書の受信確認応答を関連付けるマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-297">Invoice to invoice acknowledgment map.</span></span>|  
|<span data-ttu-id="0a837-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-298">Solution\BPELShipping\BPELShipping\Order2FinalConfirmation.btm</span></span>|<span data-ttu-id="0a837-299">注文書メッセージを最終的な出荷確認に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-299">Map to convert from Order message to final shipment confirmation.</span></span>|  
|<span data-ttu-id="0a837-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-300">Solution\BPELShipping\BPELShipping\Order2OrderAck.btm</span></span>|<span data-ttu-id="0a837-301">注文書メッセージを注文書の受信確認応答に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-301">Map to convert from Order message to order acknowledgment.</span></span>|  
|<span data-ttu-id="0a837-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-302">Solution\BPELShipping\BPELShipping\Order2OrderNack.btm</span></span>|<span data-ttu-id="0a837-303">注文書メッセージを注文書の否定応答に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-303">Map to convert from Order message to order negative acknowledgment.</span></span>|  
|<span data-ttu-id="0a837-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-304">Solution\BPELShipping\BPELShipping\Order2ShipHistory.btm</span></span>|<span data-ttu-id="0a837-305">注文書メッセージを出荷履歴ドキュメントに変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-305">Map to convert from Order message to Shipping history document.</span></span>|  
|<span data-ttu-id="0a837-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-306">Solution\BPELShipping\BPELShipping\Order2ShipRequest.btm</span></span>|<span data-ttu-id="0a837-307">注文書メッセージを注文出荷要求に変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-307">Map to convert from Order message to order Shipping request.</span></span>|  
|<span data-ttu-id="0a837-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span><span class="sxs-lookup"><span data-stu-id="0a837-308">Solution\BPELShipping\BPELShipping\ShipRequest2Completed.btm</span></span>|<span data-ttu-id="0a837-309">出荷履歴を完了に設定するマップです。</span><span class="sxs-lookup"><span data-stu-id="0a837-309">Map to set the Shipping history to completed.</span></span>|  
|<span data-ttu-id="0a837-310">Solution\ShipperProcess\setup.bat</span><span class="sxs-lookup"><span data-stu-id="0a837-310">Solution\ShipperProcess\setup.bat</span></span>|<span data-ttu-id="0a837-311">ShipperProcess ヘルパー オーケストレーションとそのポートをビルド、展開、バインド、および開始するためのバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-311">Batch file to build, deploy, bind, and start the ShipperProcess helper orchestration and its ports.</span></span>|  
|<span data-ttu-id="0a837-312">Solution\ShipperProcess\cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0a837-312">Solution\ShipperProcess\cleanup.bat</span></span>|<span data-ttu-id="0a837-313">ShipperProcess ヘルパー オーケストレーションとそのポートを停止、参加解除、および展開解除するためのバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0a837-313">Batch file to stop, unenlist, and undeploy the ShipperProcess helper orchestration and its ports.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="0a837-314">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="0a837-314">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="0a837-315">最初のステップでは、Wide World Importers 社の役割をシミュレートするために使用する ShipperProcess アプリケーションをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="0a837-315">The first step is to build and initialize the ShipperProcess application used to simulate Wide World Importers.</span></span>  
  
#### <a name="to-build-and-initialize-the-shipperprocess-application"></a><span data-ttu-id="0a837-316">ShipperProcess アプリケーションをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="0a837-316">To build and initialize the ShipperProcess application</span></span>  
  
1.  <span data-ttu-id="0a837-317">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="0a837-317">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="0a837-318">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="0a837-318">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="0a837-319">*\<サンプル パス >*\Orchestrations\BPELImport\Solution\ShipperProcess</span><span class="sxs-lookup"><span data-stu-id="0a837-319">*\<Samples Path>*\Orchestrations\BPELImport\Solution\ShipperProcess</span></span>  
  
3.  <span data-ttu-id="0a837-320">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-320">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="0a837-321">ShipperProcess および BPELShipping プロセスで使用されるスキーマを含む ShippingSchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-321">Builds the ShippingSchemas project, which contains the schemas used in the ShipperProcess and the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="0a837-322">ShipperProcess をビルドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-322">Builds the ShipperProcess</span></span>  
  
    -   <span data-ttu-id="0a837-323">ShippingSchemas プロジェクトと ShipperProcess プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="0a837-323">Deploys the ShippingSchemas and ShipperProcess projects</span></span>  
  
    -   <span data-ttu-id="0a837-324">ShipperProcess で使用される送信ポートと受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-324">Creates and binds the send and receive ports used by ShipperProcess</span></span>  
  
    -   <span data-ttu-id="0a837-325">ShipperProcess で使用されるポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="0a837-325">Starts the ports used by ShipperProcess</span></span>  
  
    -   <span data-ttu-id="0a837-326">ShipperProcess オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="0a837-326">Enlists and starts the ShipperProcess orchestration</span></span>  
  
 <span data-ttu-id="0a837-327">このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a837-327">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="0a837-328">次の警告が 1 つ以上表示される場合がありますが、これらの警告は無視できます。</span><span class="sxs-lookup"><span data-stu-id="0a837-328">One or more of the following warnings may be displayed; you can ignore these.</span></span>  
  
```  
The 'http://contoso.org/samples/Fragments:XXXX' element is not declared. An error occurred at , (35, 16).  
<SAMPLE_LOCATION>\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(667,22): convoy found at 'activate receive(Receive_ShipOrder.Operation_1, Request, initialize Correl)'  
<SAMPLE_LOCATION>\Samples\Orchestrations\BPELImport\Solution\ShipperProcess\ShipperProcess\ShipperProcess.odx(701,13): and 'receive(ReceiveInvoiceAck.Operation_1, Invoice_Ack, Correl)'  
```  
  
> [!NOTE]
>  <span data-ttu-id="0a837-329">「BPEL からインポートして実際のソリューションをビルドするには」に記載されている手順を完了した場合、次の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a837-329">You do not need to perform the following steps if you completed the steps described in "To import from BPEL and build a working solution."</span></span>  
  
#### <a name="to-build-and-initialize-the-bpelshipping-application"></a><span data-ttu-id="0a837-330">BPELShipping アプリケーションをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="0a837-330">To build and initialize the BPELShipping application</span></span>  
  
1.  > [!WARNING]
    >  <span data-ttu-id="0a837-331">以下の手順を実行する前に、「ShipperProcess アプリケーションをビルドおよび初期化するには」の手順を完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a837-331">Before executing these steps, you must complete the steps above entitled “To build and initialize the ShipperProcess application”.</span></span>  
  
     <span data-ttu-id="0a837-332">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="0a837-332">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="0a837-333">*\<サンプル パス >*\Orchestrations\BPELImport\Solution\BPELShipping</span><span class="sxs-lookup"><span data-stu-id="0a837-333">*\<Samples Path>*\Orchestrations\BPELImport\Solution\BPELShipping</span></span>  
  
2.  <span data-ttu-id="0a837-334">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-334">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="0a837-335">BPELShipping プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-335">Builds the BPELShipping project</span></span>  
  
    -   <span data-ttu-id="0a837-336">BPELShipping プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="0a837-336">Deploys the BPELShipping project</span></span>  
  
    -   <span data-ttu-id="0a837-337">BPELShipping プロセスで使用される送信ポートと受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="0a837-337">Creates and binds the send and receive ports used by the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="0a837-338">BPELShipping プロセスで使用されるポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="0a837-338">Starts the ports used by the BPELShipping process</span></span>  
  
    -   <span data-ttu-id="0a837-339">BPELShipping オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="0a837-339">Enlists and starts the BPELShipping orchestration</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="0a837-340">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="0a837-340">Running This Sample</span></span>  
  
#### <a name="to-run-the-bpel-import-sample"></a><span data-ttu-id="0a837-341">BPEL インポート サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="0a837-341">To run the BPEL Import sample</span></span>  
  
1.  <span data-ttu-id="0a837-342">コピー、 **Order.xml**ファイルから、 *\<サンプル パス >*\Orchestrations\BPELImport\Solution フォルダーを\<*サンプル パス >*\Orchestrations\BPELImport\Solution\Ports\ReceiveOrder フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0a837-342">Copy the **Order.xml** file from the *\<Samples Path>*\Orchestrations\BPELImport\Solution folder to the \<*Samples Path>*\Orchestrations\BPELImport\Solution\Ports\ReceiveOrder folder.</span></span>  
  
2.  <span data-ttu-id="0a837-343">顧客の注文処理システムから注文としてオーケストレーションがこのファイルを取得 BPELShipping が、出荷プロセス実行され、いずれかのファイルを生成では、それぞれ、 \<*サンプル パス*> \Orchestrations\BPELImport\Solution\Ports\SendOrder フォルダーおよび\<*サンプル パス*> \Orchestrations\BPELImport\Solution\Ports\FinalConfirmation フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0a837-343">The BPELShipping orchestration picks up this file as an order from the customer order processing system, runs through the shipping process, and produces one file each in the \<*Samples Path*>\Orchestrations\BPELImport\Solution\Ports\SendOrder folder and the \<*Samples Path*>\Orchestrations\BPELImport\Solution\Ports\FinalConfirmation folder.</span></span> <span data-ttu-id="0a837-344">これらのファイルの名前の形式が\< *MessageID*> .xml、場所 *\<MessageID >*メッセージを一意に識別する GUID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0a837-344">The format of the name of these files is \<*MessageID*>.xml, where *\<MessageID>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="0a837-345">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="0a837-345">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-bpel-import-sample"></a><span data-ttu-id="0a837-346">BPEL インポート サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="0a837-346">To uninstall the BPEL Import sample</span></span>  
  
1.  <span data-ttu-id="0a837-347">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*> \Orchestrations\BPELImport\BPELShipping です。</span><span class="sxs-lookup"><span data-stu-id="0a837-347">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*>\Orchestrations\BPELImport\BPELShipping.</span></span>  
  
2.  <span data-ttu-id="0a837-348">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-348">Run Cleanup.bat.</span></span>  
  
3.  <span data-ttu-id="0a837-349">参照\<*パスのサンプル*> \Orchestrations\BPELImport\ShipperProcess です。</span><span class="sxs-lookup"><span data-stu-id="0a837-349">Browse to \<*Samples Path*>\Orchestrations\BPELImport\ShipperProcess.</span></span>  
  
4.  <span data-ttu-id="0a837-350">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a837-350">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a837-351">参照</span><span class="sxs-lookup"><span data-stu-id="0a837-351">See Also</span></span>  
 [<span data-ttu-id="0a837-352">オーケストレーション (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="0a837-352">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)