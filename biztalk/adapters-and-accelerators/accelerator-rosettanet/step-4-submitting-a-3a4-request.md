---
title: 手順 4:3A4 要求の送信 |Microsoft Docs
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
ms.openlocfilehash: 6589a46665edf6e446483b673fd4228dd471bbd3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280923"
---
# <a name="step-4-submitting-a-3a4-request"></a><span data-ttu-id="05ae3-102">手順 4:3A4 要求の送信</span><span class="sxs-lookup"><span data-stu-id="05ae3-102">Step 4: Submitting a 3A4 Request</span></span>
<span data-ttu-id="05ae3-103">この手順では、準備し、3a4-request Purchase Order を要求をプロセス PIP (Partner Interface) を使用して、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A4 - Request Purchase Order.</span></span> <span data-ttu-id="05ae3-104">この PIP は、業者に注文要求を送信する購入者組織を使用できます。</span><span class="sxs-lookup"><span data-stu-id="05ae3-104">This PIP enables a buyer organization to submit a purchase order request to a supplier.</span></span> <span data-ttu-id="05ae3-105">一般に、3A4 - 製品の可用性を 3 a 2 - Request Price and Availability PIP を使用してクエリを実行した後の要求の発注書を要求します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-105">Generally, you request the 3A4 - Request Purchase Order after running a product availability query using the 3A2 - Request Price and Availability PIP.</span></span> <span data-ttu-id="05ae3-106">3A4 PIP は、受信確認を送信する非同期の PIP です。</span><span class="sxs-lookup"><span data-stu-id="05ae3-106">The 3A4 PIP is an asynchronous PIP that sends receipt acknowledgements.</span></span>  
  
 <span data-ttu-id="05ae3-107">![&#60;変更なし&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span><span class="sxs-lookup"><span data-stu-id="05ae3-107">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a4flow.gif "RN3_Intro_EETut_3A4Flow")</span></span>  
  
### <a name="to-submit-a-3a4---request-purchase-order"></a><span data-ttu-id="05ae3-108">3A4 の発注書の要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="05ae3-108">To submit a 3A4 - Request Purchase Order</span></span>  
  
1.  <span data-ttu-id="05ae3-109">Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。</span><span class="sxs-lookup"><span data-stu-id="05ae3-109">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="05ae3-110">**Submit Message**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="05ae3-110">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="05ae3-111">**これを使用して、**</span><span class="sxs-lookup"><span data-stu-id="05ae3-111">**Use this**</span></span>|<span data-ttu-id="05ae3-112">**これを行う**</span><span class="sxs-lookup"><span data-stu-id="05ae3-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="05ae3-113">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="05ae3-113">**Home Organization**</span></span>|<span data-ttu-id="05ae3-114">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-114">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="05ae3-115">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="05ae3-115">**Partner Organization**</span></span>|<span data-ttu-id="05ae3-116">型**Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-116">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="05ae3-117">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="05ae3-117">**Pip Code**</span></span>|<span data-ttu-id="05ae3-118">型**3A4**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-118">Type **3A4**.</span></span>|  
    |<span data-ttu-id="05ae3-119">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="05ae3-119">**Pip Version**</span></span>|<span data-ttu-id="05ae3-120">型**V02.02.00**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-120">Type **V02.02.00**.</span></span>|  
    |<span data-ttu-id="05ae3-121">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="05ae3-121">**Pip Instance ID**</span></span>|<span data-ttu-id="05ae3-122">型**3A4_Test**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-122">Type **3A4_Test**.</span></span> <span data-ttu-id="05ae3-123">**重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **Pip インスタンス ID**は送信した各メッセージに一意です。</span><span class="sxs-lookup"><span data-stu-id="05ae3-123">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip Instance ID** is unique for each message that you submit.</span></span> <span data-ttu-id="05ae3-124">今後 3a4_test を実行する場合はこのフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ae3-124">If you run the 3A4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="05ae3-125">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="05ae3-125">**Message Category**</span></span>|<span data-ttu-id="05ae3-126">型**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-126">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="05ae3-127">メモ帳または別のテキスト エディターを使用してある 3A4_Request.xml ファイルを開き、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances のフォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。</span><span class="sxs-lookup"><span data-stu-id="05ae3-127">Using Notepad or another text editor, open the 3A4_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="05ae3-128">クリックして**送信**3A4 要求を Contoso のコンピューターを送信します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-128">Click **Submit** to submit the 3A4 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="05ae3-129">Fabrikam のコンピューターで通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="05ae3-129">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="05ae3-130">**メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-130">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05ae3-131">Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ae3-131">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="05ae3-132">Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。</span><span class="sxs-lookup"><span data-stu-id="05ae3-132">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="05ae3-133">カテゴリ-99 のメッセージでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-133">A category -99 message signifies an error.</span></span> <span data-ttu-id="05ae3-134">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-134">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="05ae3-135">Contoso のコンピューターの通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="05ae3-135">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="05ae3-136">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-136">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="05ae3-137">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-137">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="05ae3-138">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="05ae3-139">\<テーブル\>テキスト] ダイアログ ボックス、[ **BTARNDATA**一覧から。</span><span class="sxs-lookup"><span data-stu-id="05ae3-139">In the \<table\> text dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="05ae3-140">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="05ae3-141">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-141">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="05ae3-142">結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05ae3-143">最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="05ae3-144">Acknowledegment メッセージを表すカテゴリ 25 のメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ae3-144">You should then receive a category 25 message signifying the receipt acknowledegment message.</span></span>  
  
8.  <span data-ttu-id="05ae3-145">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="05ae3-146">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="05ae3-147">クエリ ウィンドウ内で、**結果**ウィンドウで、1 つの送信メッセージを表示することを確認します。</span><span class="sxs-lookup"><span data-stu-id="05ae3-147">In the Query window, in the **Results** pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05ae3-148">Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05ae3-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="05ae3-149">Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05ae3-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ae3-150">参照</span><span class="sxs-lookup"><span data-stu-id="05ae3-150">See Also</span></span>  
 <span data-ttu-id="05ae3-151">[ダブル アクション チュートリアル](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="05ae3-151">[Double Action Tutorial](../../adapters-and-accelerators/accelerator-rosettanet/double-action-tutorial.md) </span></span>  
 [<span data-ttu-id="05ae3-152">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="05ae3-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)