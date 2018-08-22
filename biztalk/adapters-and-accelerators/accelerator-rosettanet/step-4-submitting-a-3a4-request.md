---
title: '手順 4: 3A4 要求の送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 2d812cbc-51bc-48d5-b0b2-3698d33664ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff36b6181b167d70340a65913e1e85e7acfeeaf4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965576"
---
# <a name="step-4-submitting-a-3a4-request"></a><span data-ttu-id="f8d0d-102">手順 4: 3A4 要求の送信</span><span class="sxs-lookup"><span data-stu-id="f8d0d-102">Step 4: Submitting a 3A4 Request</span></span>
<span data-ttu-id="f8d0d-103">ここでは、3A4 - Request Purchase Order の PIP (Partner Interface Process) を使用して、要求を作成および送信します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A4 - Request Purchase Order.</span></span> <span data-ttu-id="f8d0d-104">この PIP を使用することにより、購入者組織が発注を業者に送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-104">This PIP enables a buyer organization to submit a purchase order request to a supplier.</span></span> <span data-ttu-id="f8d0d-105">通常は、3A2 - Request Price and Availability PIP を使用して注文可能な製品を照会してから、3A4 - Request Purchase Order を要求します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-105">Generally, you request the 3A4 - Request Purchase Order after running a product availability query using the 3A2 - Request Price and Availability PIP.</span></span> <span data-ttu-id="f8d0d-106">3A4 PIP は、受信確認を送信する非同期の PIP です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-106">The 3A4 PIP is an asynchronous PIP that sends receipt acknowledgements.</span></span>  
  
 <span data-ttu-id="f8d0d-107">![(& m); 60変更なし & #62;。](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span><span class="sxs-lookup"><span data-stu-id="f8d0d-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span></span>  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a><span data-ttu-id="f8d0d-108">3A4 - Request Purchase Order を送信するには</span><span class="sxs-lookup"><span data-stu-id="f8d0d-108">To submit a 3A4 - Request Purchase Order</span></span>  
  
1.  <span data-ttu-id="f8d0d-109">Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-109">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="f8d0d-110">**Submit Message**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-110">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="f8d0d-111">**これを使用してください。**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-111">**Use this**</span></span>|<span data-ttu-id="f8d0d-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="f8d0d-113">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-113">**Home Organization**</span></span>|<span data-ttu-id="f8d0d-114">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-114">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="f8d0d-115">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-115">**Partner Organization**</span></span>|<span data-ttu-id="f8d0d-116">型**Contoso**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-116">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="f8d0d-117">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-117">**Pip Code**</span></span>|<span data-ttu-id="f8d0d-118">型**3A4**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-118">Type **3A4**.</span></span>|  
    |<span data-ttu-id="f8d0d-119">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-119">**Pip Version**</span></span>|<span data-ttu-id="f8d0d-120">型**V02.02.00**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-120">Type **V02.02.00**.</span></span>|  
    |<span data-ttu-id="f8d0d-121">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-121">**Pip Instance ID**</span></span>|<span data-ttu-id="f8d0d-122">型**3A4_Test**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-122">Type **3A4_Test**.</span></span> <span data-ttu-id="f8d0d-123">**重要:** 重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **Pip インスタンス ID**を送信するメッセージごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-123">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip Instance ID** is unique for each message that you submit.</span></span> <span data-ttu-id="f8d0d-124">後で 3A4_Test を実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-124">If you run the 3A4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="f8d0d-125">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="f8d0d-125">**Message Category**</span></span>|<span data-ttu-id="f8d0d-126">型**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-126">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="f8d0d-127">ある 3A4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances フォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-127">Using Notepad or another text editor, open the 3A4_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="f8d0d-128">をクリックして**送信**を Contoso のコンピューター 3A4 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-128">Click **Submit** to submit the 3A4 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="f8d0d-129">Fabrikam のコンピューターで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="f8d0d-129">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="f8d0d-130">**メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-130">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8d0d-131">最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-131">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="f8d0d-132">次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-132">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="f8d0d-133">カテゴリ -99 のメッセージは、エラーを表します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-133">A category -99 message signifies an error.</span></span> <span data-ttu-id="f8d0d-134">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-134">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="f8d0d-135">Contoso のコンピュータで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="f8d0d-135">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="f8d0d-136">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-136">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="f8d0d-137">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-137">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="f8d0d-138">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="f8d0d-139">\<テーブル\>テキスト ダイアログ ボックスで、 **BTARNDATA**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-139">In the \<table\> text dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="f8d0d-140">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="f8d0d-141">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-141">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="f8d0d-142">[クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8d0d-143">最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="f8d0d-144">受信 acknowledegment メッセージを表すカテゴリ 25 のメッセージを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-144">You should then receive a category 25 message signifying the receipt acknowledegment message.</span></span>  
  
8.  <span data-ttu-id="f8d0d-145">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="f8d0d-146">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="f8d0d-147">クエリ ウィンドウ内で、**結果** ウィンドウで、1 つの送信メッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-147">In the Query window, in the **Results** pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8d0d-148">Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="f8d0d-149">Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8d0d-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d0d-150">参照</span><span class="sxs-lookup"><span data-stu-id="f8d0d-150">See Also</span></span>  
 <span data-ttu-id="f8d0d-151">[ダブル アクション チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="f8d0d-151">[Double Action Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span></span>  
 [<span data-ttu-id="f8d0d-152">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="f8d0d-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)