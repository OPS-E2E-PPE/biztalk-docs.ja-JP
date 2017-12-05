---
title: "手順 3: 3 a 2 要求の送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 312e5980636d211f1e023331826e016eb141eb4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-submitting-a-3a2-request"></a><span data-ttu-id="41320-102">手順 3: 3 a 2 要求の送信</span><span class="sxs-lookup"><span data-stu-id="41320-102">Step 3: Submitting a 3A2 Request</span></span>
<span data-ttu-id="41320-103">ここでは、3A2 - Request Price and Availability の PIP (Partner Interface Process) を使用して、要求の準備と送信を行います。</span><span class="sxs-lookup"><span data-stu-id="41320-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A2 - Request Price and Availability.</span></span> <span data-ttu-id="41320-104">購入者組織はこの PIP を使用して、特定の製品について価格や入手可能な数などの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="41320-104">This PIP enables a buyer organization to obtain information about a certain product, such as price and number of available units.</span></span> <span data-ttu-id="41320-105">次に、購入者は、ビジネス ルールに基づいてその情報を処理し、業者から製品を購入するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="41320-105">The buyer can then process that information through business rules to determine whether to purchase the product from the supplier.</span></span>  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a><span data-ttu-id="41320-106">3A2 - Request Price and Availability を送信するには</span><span class="sxs-lookup"><span data-stu-id="41320-106">To submit a 3A2 - Request Price and Availability</span></span>  
  
1.  <span data-ttu-id="41320-107">Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。</span><span class="sxs-lookup"><span data-stu-id="41320-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="41320-108">**Submit Message**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="41320-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="41320-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="41320-109">Use this</span></span>|<span data-ttu-id="41320-110">目的</span><span class="sxs-lookup"><span data-stu-id="41320-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="41320-111">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="41320-111">**Home Organization**</span></span>|<span data-ttu-id="41320-112">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="41320-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="41320-113">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="41320-113">**Partner Organization**</span></span>|<span data-ttu-id="41320-114">型**Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="41320-114">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="41320-115">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="41320-115">**Pip Code**</span></span>|<span data-ttu-id="41320-116">型**3 a 2**です。</span><span class="sxs-lookup"><span data-stu-id="41320-116">Type **3A2**.</span></span> <span data-ttu-id="41320-117">**重要:**重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **Pip**を送信するメッセージごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="41320-117">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip** is unique for each message that you submit.</span></span> <span data-ttu-id="41320-118">後で 3A2_Test を実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41320-118">If you run the 3A2 test in the future, you have to change this field.</span></span>|  
    |<span data-ttu-id="41320-119">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="41320-119">**Pip Version**</span></span>|<span data-ttu-id="41320-120">型**r02.00.00a など**です。</span><span class="sxs-lookup"><span data-stu-id="41320-120">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="41320-121">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="41320-121">**Pip Instance ID**</span></span>|<span data-ttu-id="41320-122">型**3A2_Test**です。</span><span class="sxs-lookup"><span data-stu-id="41320-122">Type **3A2_Test**.</span></span>|  
    |<span data-ttu-id="41320-123">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="41320-123">**Message Category**</span></span>|<span data-ttu-id="41320-124">型**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="41320-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="41320-125">メモ帳または別のテキスト エディターを使用して、内の 3A2_Request.xml ファイルを開き、 *\<ドライブ\>*: \プログラムの \program files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーをコピーして貼り付け、内容、 **Service Content**フィールドLOBWebApplication です。</span><span class="sxs-lookup"><span data-stu-id="41320-125">Using Notepad or another text editor, open the file 3A2_Request.xml in the *\<drive\>*:\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="41320-126">をクリックして**送信**Contoso のコンピューターに 3 a 2 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="41320-126">Click **Submit** to submit the 3A2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="41320-127">Fabrikam のコンピューターで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="41320-127">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="41320-128">**メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="41320-128">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41320-129">最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="41320-129">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="41320-130">次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="41320-130">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="41320-131">カテゴリ -99 のメッセージは、エラーを表します。</span><span class="sxs-lookup"><span data-stu-id="41320-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="41320-132">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="41320-132">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="41320-133">Contoso のコンピュータで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="41320-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="41320-134">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="41320-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="41320-135">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="41320-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="41320-136">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="41320-136">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="41320-137">\<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="41320-137">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="41320-138">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="41320-138">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="41320-139">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="41320-139">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="41320-140">[クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41320-140">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41320-141">最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="41320-141">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="41320-142">次に受信しているのは、受信確認メッセージを表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="41320-142">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="41320-143">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="41320-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="41320-144">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="41320-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="41320-145">[クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41320-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="41320-146">Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41320-146">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="41320-147">Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="41320-147">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41320-148">参照</span><span class="sxs-lookup"><span data-stu-id="41320-148">See Also</span></span>  
 <span data-ttu-id="41320-149">[手順 4: 3A4 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span><span class="sxs-lookup"><span data-stu-id="41320-149">[Step 4: Submitting a 3A4 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span></span>  
 [<span data-ttu-id="41320-150">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="41320-150">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)