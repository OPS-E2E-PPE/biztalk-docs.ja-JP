---
title: '手順 2: 0c4 を送信するクエリを実行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: ce50b892-c87c-414a-94c5-b40947fec68f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c621b6891b816f72603202bd6f2214882eb4b5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965680"
---
# <a name="step-2-submitting-a-0c4-query"></a><span data-ttu-id="ce3b8-102">手順 2: 送信 a 0 C 4 クエリします。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-102">Step 2: Submitting a 0C4 Query</span></span>
<span data-ttu-id="ce3b8-103">ここでは、0C4 - Synchronous Test Query の PIP (Partner Interface Process) を使用して、要求を作成および送信します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 0C4 - Synchronous Test Query.</span></span> <span data-ttu-id="ce3b8-104">RosettaNet では、この PIP を定義することにより、2 つの異なる組織間で同期通信チャネルが正しく動作するようにしています。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-104">RosettaNet defines this PIP to make sure a successful synchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="ce3b8-105">この PIP は同期通信パターンを持っているため、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] は受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-105">Because this PIP has a synchronous communication pattern, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] does not send receipt acknowledgements.</span></span> <span data-ttu-id="ce3b8-106">この PIP は、2A9 - Query Technical Product Information PIP などの他の同期ダブル アクション PIP と同様のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-106">This PIP follows the same pattern as other synchronous double action PIPs, such as PIP 2A9 - Query Technical Product Information.</span></span>  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a><span data-ttu-id="ce3b8-107">0C4 - Synchronous Test Query を送信するには</span><span class="sxs-lookup"><span data-stu-id="ce3b8-107">To submit a 0C4 - Synchronous Test Query</span></span>  
  
1.  <span data-ttu-id="ce3b8-108">Fabrikam のコンピュータから、Internet Explorer を使用して http://localhost/LOBWebApplication/default.aspx を開きます。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-108">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="ce3b8-109">**Submit Message**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-109">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="ce3b8-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ce3b8-110">Use this</span></span>|<span data-ttu-id="ce3b8-111">目的</span><span class="sxs-lookup"><span data-stu-id="ce3b8-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ce3b8-112">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-112">**Home Organization**</span></span>|<span data-ttu-id="ce3b8-113">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="ce3b8-114">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-114">**Partner Organization**</span></span>|<span data-ttu-id="ce3b8-115">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-115">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="ce3b8-116">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-116">**Pip Code**</span></span>|<span data-ttu-id="ce3b8-117">型**0 C 4**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-117">Type **0C4**.</span></span>|  
    |<span data-ttu-id="ce3b8-118">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-118">**Pip Version**</span></span>|<span data-ttu-id="ce3b8-119">型**R01.02**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-119">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="ce3b8-120">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-120">**Pip Instance ID**</span></span>|<span data-ttu-id="ce3b8-121">型**0C4_Test**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-121">Type **0C4_Test**.</span></span> <span data-ttu-id="ce3b8-122">**重要:** 重複したメッセージ ID のエラーを避けるためには、する必要があることを確認、 **PIP**を送信するメッセージごとに一意です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-122">**Important:**  To avoid duplicate message ID errors, you must make sure that the **PIP** is unique for each message that you submit.</span></span> <span data-ttu-id="ce3b8-123">後で 0C4 を実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-123">If you run the 0C4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="ce3b8-124">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ce3b8-124">**Message Category**</span></span>|<span data-ttu-id="ce3b8-125">型**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-125">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="ce3b8-126">内の 0C4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk 2009 Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-126">Using Notepad or another text editor, open the 0C4_Request.xml file in the *\<drive\>*:\Program Files\Microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="ce3b8-127">をクリックして**送信**C 4 のクエリを Contoso のコンピューターに送信します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-127">Click **Submit** to submit the 0C4 query to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="ce3b8-128">Fabrikam のコンピューターで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="ce3b8-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="ce3b8-129">**メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce3b8-130">受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-130">You should receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="ce3b8-131">カテゴリ -99 のメッセージは、エラーを表します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="ce3b8-132">実際のエラー メッセージを特定するには、イベント ビューアーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-132">You can use the Event Viewer to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="ce3b8-133">Contoso のコンピュータで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="ce3b8-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="ce3b8-134">**[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="ce3b8-135">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに、入力**localhost** **Windows 認証**、 をクリックし、**接続**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce3b8-136">SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-136">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="ce3b8-137">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-137">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="ce3b8-138">\<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-138">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="ce3b8-139">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-139">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="ce3b8-140">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-140">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="ce3b8-141">[クエリ] ウィンドウの結果ペインで、1 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-141">In the Query window, in the Results pane, verify that you see one incoming message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce3b8-142">Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-142">You should see a category 10 message that represents the original request that the Fabrikam computer sent.</span></span>  
  
8.  <span data-ttu-id="ce3b8-143">SQL ウィンドウに、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="ce3b8-144">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="ce3b8-145">[クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce3b8-146">Fabrikam のコンピューターが送信した PIP 0C4 クエリに対する Contoso の応答を表すカテゴリ 50 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-146">You should see a category 50 message that represents the Contoso response to the PIP 0C4 query that Fabrikam sent.</span></span> <span data-ttu-id="ce3b8-147">ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初のクエリ メッセージに応える受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-147">In a double action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial query message.</span></span> <span data-ttu-id="ce3b8-148">応答メッセージが受信確認となります。</span><span class="sxs-lookup"><span data-stu-id="ce3b8-148">The response message serves as the acknowledgement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3b8-149">参照</span><span class="sxs-lookup"><span data-stu-id="ce3b8-149">See Also</span></span>  
 <span data-ttu-id="ce3b8-150">[手順 3: 3 a 2 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span><span class="sxs-lookup"><span data-stu-id="ce3b8-150">[Step 3: Submitting a 3A2 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span></span>  
 [<span data-ttu-id="ce3b8-151">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="ce3b8-151">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)