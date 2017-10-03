---
title: "手順 1: 0c2 要求の送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 089ad320f9363e1a3284af863512c89bcb67167d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-submitting-a-0c2-request"></a><span data-ttu-id="15992-102">手順 1: a 0 C の送信要求します。</span><span class="sxs-lookup"><span data-stu-id="15992-102">Step 1: Submitting a 0C2 Request</span></span>
<span data-ttu-id="15992-103">ここでは、0C2 - Asynchronous Test Request の PIP (Partner Interface Process) を使用して、要求を作成および送信します。</span><span class="sxs-lookup"><span data-stu-id="15992-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for an 0C2 - Asynchronous Test Request.</span></span> <span data-ttu-id="15992-104">この PIP を使用することにより、非同期通信チャネルが 2 つの異なる組織間で正常に動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="15992-104">This PIP ensures that an asynchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="15992-105">この PIP は、3A4 - Request Purchase Order PIP などの他の非同期ダブル アクション PIP と同様のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="15992-105">This PIP follows the same pattern as other asynchronous double action PIPs, such as the 3A4 - Request Purchase Order PIP.</span></span>  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a><span data-ttu-id="15992-106">0C2 - Asynchronous Test Request を送信するには</span><span class="sxs-lookup"><span data-stu-id="15992-106">To submit a 0C2 - Asynchronous Test Request</span></span>  
  
1.  <span data-ttu-id="15992-107">Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。</span><span class="sxs-lookup"><span data-stu-id="15992-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="15992-108">**Submit Message**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="15992-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="15992-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15992-109">Use this</span></span>|<span data-ttu-id="15992-110">目的</span><span class="sxs-lookup"><span data-stu-id="15992-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="15992-111">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="15992-111">**Home Organization**</span></span>|<span data-ttu-id="15992-112">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="15992-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="15992-113">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="15992-113">**Partner Organization**</span></span>|<span data-ttu-id="15992-114">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="15992-114">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="15992-115">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="15992-115">**Pip Code**</span></span>|<span data-ttu-id="15992-116">型**0c2**です。</span><span class="sxs-lookup"><span data-stu-id="15992-116">Type **0C2**.</span></span>|  
    |<span data-ttu-id="15992-117">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="15992-117">**Pip Version**</span></span>|<span data-ttu-id="15992-118">型**R01.02**です。</span><span class="sxs-lookup"><span data-stu-id="15992-118">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="15992-119">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="15992-119">**Pip Instance ID**</span></span>|<span data-ttu-id="15992-120">型**0C2_Test**です。</span><span class="sxs-lookup"><span data-stu-id="15992-120">Type **0C2_Test**.</span></span> <span data-ttu-id="15992-121">**重要:**するように注意してください、 **PIP**重複したメッセージ ID のエラーを避けるために送信するメッセージごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="15992-121">**Important:**  You must make sure that the **PIP** is unique for each message that you submit to avoid duplicate message ID errors.</span></span> <span data-ttu-id="15992-122">後で 0C2_Test を実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15992-122">If you run the 0C2 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="15992-123">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="15992-123">**Message Category**</span></span>|<span data-ttu-id="15992-124">型**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="15992-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="15992-125">ある 0C2_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances フォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="15992-125">Using Notepad or another text editor, open the 0C2_Request.xml file in the \<*drive*>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15992-126">Submit Message フォームの Service Content フィールドに既存のテキストを削除するには、テキスト、プレス アンド ホールドの先頭にカーソルを置き、 **shift キーを押し**と**Ctrl**ボタン、をクリックして**終了**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="15992-126">To delete the existing text in the Service Content field of the Submit Message form, place the cursor at the beginning of the text, press and hold the **Shift** and **Ctrl** buttons, click **End**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="15992-127">をクリックして**送信**C 2 を要求を Contoso のコンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="15992-127">Click **Submit** to submit the 0C2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="15992-128">Fabrikam のコンピューターで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="15992-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="15992-129">**メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="15992-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15992-130">最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="15992-130">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="15992-131">次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="15992-131">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="15992-132">カテゴリ -99 のメッセージは、エラーを表します。</span><span class="sxs-lookup"><span data-stu-id="15992-132">A category -99 message signifies an error.</span></span> <span data-ttu-id="15992-133">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="15992-133">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="15992-134">Contoso のコンピュータで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="15992-134">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="15992-135">**[スタート]**ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]**の順にポイントし、 **[SQL Server Management Studio]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15992-135">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="15992-136">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="15992-136">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15992-137">SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="15992-137">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="15992-138">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="15992-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="15992-139">\<テーブル > テキスト ダイアログ ボックスで、 **BTARNDATA**  をクリックし、一覧から**OK**です。</span><span class="sxs-lookup"><span data-stu-id="15992-139">In the \<table> text dialog box, select **BTARNDATA** from the list, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="15992-140">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="15992-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="15992-141">**クエリ** メニューのをクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="15992-141">On the **Query** menu, click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="15992-142">[クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15992-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15992-143">最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="15992-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="15992-144">次に受信しているのは、受信確認メッセージを表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="15992-144">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="15992-145">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="15992-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="15992-146">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="15992-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="15992-147">[クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15992-147">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15992-148">Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15992-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="15992-149">Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="15992-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15992-150">参照</span><span class="sxs-lookup"><span data-stu-id="15992-150">See Also</span></span>  
 <span data-ttu-id="15992-151">[手順 2: 送信 a 0 C 4 クエリします。](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span><span class="sxs-lookup"><span data-stu-id="15992-151">[Step 2: Submitting a 0C4 Query](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span></span>  
 [<span data-ttu-id="15992-152">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="15992-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)