---
title: 手順 1:0c2 要求の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 698c4a43-20b9-46b7-ab66-1dfa24232024
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc9102198305d6f9ea92ca4d1462d1839c4f5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281421"
---
# <a name="step-1-submitting-a-0c2-request"></a><span data-ttu-id="7e006-102">手順 1:要求の送信</span><span class="sxs-lookup"><span data-stu-id="7e006-102">Step 1: Submitting a 0C2 Request</span></span>
<span data-ttu-id="7e006-103">この手順では、準備し、0 c 2 - 0c2-asynchronous Test Request の PIP Partner Interface Process () を使用して、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="7e006-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for an 0C2 - Asynchronous Test Request.</span></span> <span data-ttu-id="7e006-104">この PIP により、非同期通信チャネルが 2 つの異なる組織間で正常に動作するようになります。</span><span class="sxs-lookup"><span data-stu-id="7e006-104">This PIP ensures that an asynchronous communication channel is working correctly between two different organizations.</span></span> <span data-ttu-id="7e006-105">この PIP は Purchase Order PIP 3A4 - などの他の非同期のダブル アクション Pip と同様のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="7e006-105">This PIP follows the same pattern as other asynchronous double action PIPs, such as the 3A4 - Request Purchase Order PIP.</span></span>  
  
### <a name="to-submit-a-0c2---asynchronous-test-request"></a><span data-ttu-id="7e006-106">0 の C 2 - 0c2-asynchronous Test Request を送信するには</span><span class="sxs-lookup"><span data-stu-id="7e006-106">To submit a 0C2 - Asynchronous Test Request</span></span>  
  
1.  <span data-ttu-id="7e006-107">Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。</span><span class="sxs-lookup"><span data-stu-id="7e006-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="7e006-108">**Submit Message**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7e006-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="7e006-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7e006-109">Use this</span></span>|<span data-ttu-id="7e006-110">目的</span><span class="sxs-lookup"><span data-stu-id="7e006-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7e006-111">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="7e006-111">**Home Organization**</span></span>|<span data-ttu-id="7e006-112">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="7e006-113">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="7e006-113">**Partner Organization**</span></span>|<span data-ttu-id="7e006-114">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-114">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="7e006-115">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="7e006-115">**Pip Code**</span></span>|<span data-ttu-id="7e006-116">型**0c2**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-116">Type **0C2**.</span></span>|  
    |<span data-ttu-id="7e006-117">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="7e006-117">**Pip Version**</span></span>|<span data-ttu-id="7e006-118">型**R01.02**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-118">Type **R01.02**.</span></span>|  
    |<span data-ttu-id="7e006-119">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="7e006-119">**Pip Instance ID**</span></span>|<span data-ttu-id="7e006-120">型**0C2_Test**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-120">Type **0C2_Test**.</span></span> <span data-ttu-id="7e006-121">**重要:** 必ず必要がありますが、 **PIP**は重複するメッセージ ID のエラーを回避するために送信する各メッセージに一意です。</span><span class="sxs-lookup"><span data-stu-id="7e006-121">**Important:**  You must make sure that the **PIP** is unique for each message that you submit to avoid duplicate message ID errors.</span></span> <span data-ttu-id="7e006-122">0 の C 2 は、後でテストを実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e006-122">If you run the 0C2 test in the future, you will have to change this field.</span></span>|  
    |<span data-ttu-id="7e006-123">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="7e006-123">**Message Category**</span></span>|<span data-ttu-id="7e006-124">型**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="7e006-125">内の 0C2_Request.xml ファイルを開くメモ帳または別のテキスト エディターを使用して、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances のフォルダーをコピーして貼り付け、内容、 **Service Content** LOBWebApplication のフィールド。</span><span class="sxs-lookup"><span data-stu-id="7e006-125">Using Notepad or another text editor, open the 0C2_Request.xml file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e006-126">Submit Message フォームの Service Content フィールドで、既存のテキストを削除するには、テキスト、プレス アンド ホールドの先頭にカーソルを置き、 **Shift**と**Ctrl**ボタン、をクリックして**終了**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-126">To delete the existing text in the Service Content field of the Submit Message form, place the cursor at the beginning of the text, press and hold the **Shift** and **Ctrl** buttons, click **End**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="7e006-127">クリックして**送信**C 2 が Contoso のコンピューターに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="7e006-127">Click **Submit** to submit the 0C2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="7e006-128">Fabrikam のコンピューターで通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="7e006-128">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="7e006-129">**メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e006-129">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e006-130">Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e006-130">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="7e006-131">Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。</span><span class="sxs-lookup"><span data-stu-id="7e006-131">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="7e006-132">カテゴリ-99 のメッセージでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="7e006-132">A category -99 message signifies an error.</span></span> <span data-ttu-id="7e006-133">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e006-133">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="7e006-134">Contoso のコンピューターの通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="7e006-134">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="7e006-135">**[スタート]** ボタンをクリックし、 **[すべてのプログラム]**、 **[Microsoft SQL Server]** の順にポイントし、 **[SQL Server Management Studio]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e006-135">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="7e006-136">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-136">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e006-137">SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-137">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="7e006-138">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="7e006-138">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="7e006-139">\<テーブル\>テキスト ダイアログ ボックス、 **BTARNDATA**  をクリックし、一覧から**OK**。</span><span class="sxs-lookup"><span data-stu-id="7e006-139">In the \<table\> text dialog box, select **BTARNDATA** from the list, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="7e006-140">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="7e006-140">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="7e006-141">**クエリ** メニューのをクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e006-141">On the **Query** menu, click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="7e006-142">結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e006-142">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e006-143">最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="7e006-143">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="7e006-144">受信確認のメッセージを表すカテゴリ 25 のメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e006-144">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="7e006-145">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="7e006-145">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="7e006-146">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="7e006-146">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="7e006-147">結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。</span><span class="sxs-lookup"><span data-stu-id="7e006-147">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7e006-148">Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e006-148">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="7e006-149">Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e006-149">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e006-150">参照</span><span class="sxs-lookup"><span data-stu-id="7e006-150">See Also</span></span>  
 <span data-ttu-id="7e006-151">[手順 2:4 のクエリの送信](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span><span class="sxs-lookup"><span data-stu-id="7e006-151">[Step 2: Submitting a 0C4 Query](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md) </span></span>  
 [<span data-ttu-id="7e006-152">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="7e006-152">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)