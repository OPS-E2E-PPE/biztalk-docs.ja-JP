---
title: 手順 2:クエリの送信、0 C 4 |Microsoft Docs
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
ms.openlocfilehash: cd5ea963049d8d7a53c0098c1a53ae54784e0653
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281292"
---
# <a name="step-2-submitting-a-0c4-query"></a><span data-ttu-id="2b761-102">手順 2:4 のクエリの送信</span><span class="sxs-lookup"><span data-stu-id="2b761-102">Step 2: Submitting a 0C4 Query</span></span>
<span data-ttu-id="2b761-103">この手順では、準備し、0 c 4 - 0c4-synchronous Test Query の PIP Partner Interface Process () を使用して、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="2b761-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 0C4 - Synchronous Test Query.</span></span> <span data-ttu-id="2b761-104">RosettaNet では、2 つの異なる組織間で同期通信チャネルが正常かどうかを確認するには、この PIP を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b761-104">RosettaNet defines this PIP to make sure a successful synchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="2b761-105">この PIP は同期通信パターンでは、ため[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="2b761-105">Because this PIP has a synchronous communication pattern, [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] does not send receipt acknowledgements.</span></span> <span data-ttu-id="2b761-106">この PIP は Technical Product Information PIP 2a9 と - などの他の同期のダブル アクション Pip と同様のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="2b761-106">This PIP follows the same pattern as other synchronous double action PIPs, such as PIP 2A9 - Query Technical Product Information.</span></span>  
  
### <a name="to-submit-a-0c4---synchronous-test-query"></a><span data-ttu-id="2b761-107">0 C 4 - 0c4-synchronous Test Query を送信するには</span><span class="sxs-lookup"><span data-stu-id="2b761-107">To submit a 0C4 - Synchronous Test Query</span></span>  
  
1.  <span data-ttu-id="2b761-108">Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。</span><span class="sxs-lookup"><span data-stu-id="2b761-108">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="2b761-109">**Submit Message**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2b761-109">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="2b761-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2b761-110">Use this</span></span>|<span data-ttu-id="2b761-111">目的</span><span class="sxs-lookup"><span data-stu-id="2b761-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2b761-112">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="2b761-112">**Home Organization**</span></span>|<span data-ttu-id="2b761-113">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="2b761-114">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="2b761-114">**Partner Organization**</span></span>|<span data-ttu-id="2b761-115">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-115">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="2b761-116">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="2b761-116">**Pip Code**</span></span>|<span data-ttu-id="2b761-117">型**0 C 4**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-117">Type **0C4**.</span></span>|  
    |<span data-ttu-id="2b761-118">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="2b761-118">**Pip Version**</span></span>|<span data-ttu-id="2b761-119">型**R01.02**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-119">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="2b761-120">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="2b761-120">**Pip Instance ID**</span></span>|<span data-ttu-id="2b761-121">型**0C4_Test**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-121">Type **0C4_Test**.</span></span> <span data-ttu-id="2b761-122">**重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **PIP**は送信した各メッセージに一意です。</span><span class="sxs-lookup"><span data-stu-id="2b761-122">**Important:**  To avoid duplicate message ID errors, you must make sure that the **PIP** is unique for each message that you submit.</span></span> <span data-ttu-id="2b761-123">場合は、0 C 4 は、後でテストを実行すると、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b761-123">If you run the 0C4 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="2b761-124">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="2b761-124">**Message Category**</span></span>|<span data-ttu-id="2b761-125">型**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-125">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="2b761-126">内の 0C4_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk 2009 Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーでは、コピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。</span><span class="sxs-lookup"><span data-stu-id="2b761-126">Using Notepad or another text editor, open the 0C4_Request.xml file in the *\<drive\>*:\Program Files\Microsoft BizTalk 2009 Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="2b761-127">クリックして**送信**C 4 が Contoso のコンピューターにクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="2b761-127">Click **Submit** to submit the 0C4 query to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="2b761-128">Fabrikam のコンピューターで通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="2b761-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="2b761-129">**メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b761-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b761-130">Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b761-130">You should receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="2b761-131">カテゴリ-99 のメッセージでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="2b761-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="2b761-132">イベント ビューアーを使用すると、実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b761-132">You can use the Event Viewer to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="2b761-133">Contoso のコンピューターの通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="2b761-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="2b761-134">**[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b761-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="2b761-135">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b761-136">SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-136">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="2b761-137">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="2b761-137">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2b761-138">\<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧から。</span><span class="sxs-lookup"><span data-stu-id="2b761-138">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="2b761-139">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b761-139">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="2b761-140">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b761-140">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="2b761-141">結果ウィンドウで、クエリ ウィンドウで 1 つの受信メッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b761-141">In the Query window, in the Results pane, verify that you see one incoming message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b761-142">Fabrikam のコンピューターの送信元の要求を表すカテゴリ 10 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b761-142">You should see a category 10 message that represents the original request that the Fabrikam computer sent.</span></span>  
  
8.  <span data-ttu-id="2b761-143">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b761-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="2b761-144">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b761-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="2b761-145">結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。</span><span class="sxs-lookup"><span data-stu-id="2b761-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b761-146">PIP に Contoso の応答を表すカテゴリ 50 のメッセージを表示する必要があります 0c4 クエリの送信を Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="2b761-146">You should see a category 50 message that represents the Contoso response to the PIP 0C4 query that Fabrikam sent.</span></span> <span data-ttu-id="2b761-147">ダブル アクション同期シナリオでは、応答側コンピューターは、最初のクエリ メッセージに対する応答の開始側コンピューターに、受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="2b761-147">In a double action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial query message.</span></span> <span data-ttu-id="2b761-148">応答メッセージが受信確認となります。</span><span class="sxs-lookup"><span data-stu-id="2b761-148">The response message serves as the acknowledgement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b761-149">参照</span><span class="sxs-lookup"><span data-stu-id="2b761-149">See Also</span></span>  
 <span data-ttu-id="2b761-150">[ステップ 3:3 a 2 要求を送信します。](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span><span class="sxs-lookup"><span data-stu-id="2b761-150">[Step 3: Submitting a 3A2 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md) </span></span>  
 [<span data-ttu-id="2b761-151">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="2b761-151">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)