---
title: Fabrikam サンプルを使用して Price and Availability 要求を作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating requests
ms.assetid: 6e4f4589-8f01-4b9e-93ee-c9371f32e04a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0619dc77496fd1547505221ff2f437bf486fb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a><span data-ttu-id="6f3b9-102">Fabrikam サンプルを使用して Price and Availability Request の作成</span><span class="sxs-lookup"><span data-stu-id="6f3b9-102">Creating a Price and Availability Request with the Fabrikam Sample</span></span>
<span data-ttu-id="6f3b9-103">ここでは、LOBWebApplication ツールを使用して、3A2 Price and Availability 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-103">In this step, you create a 3A2 Price and Availability request using the LOBWebApplication tool.</span></span>  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a><span data-ttu-id="6f3b9-104">3A2 Price and Availability 要求を Contoso に送信するには</span><span class="sxs-lookup"><span data-stu-id="6f3b9-104">To submit a 3A2 Price and Availability request to Contoso</span></span>  
  
1.  <span data-ttu-id="6f3b9-105">Internet Explorer で、移動 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-105">In Internet Explorer, move to http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="6f3b9-106">**LOBWebApplication**  ページで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-106">On the **LOBWebApplication** page, do the following:</span></span>  
  
    |<span data-ttu-id="6f3b9-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6f3b9-107">Use this</span></span>|<span data-ttu-id="6f3b9-108">目的</span><span class="sxs-lookup"><span data-stu-id="6f3b9-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6f3b9-109">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="6f3b9-109">**Home Organization**</span></span>|<span data-ttu-id="6f3b9-110">型**FABRIKAM**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-110">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="6f3b9-111">**パートナー組織**</span><span class="sxs-lookup"><span data-stu-id="6f3b9-111">**Partner Organization**</span></span>|<span data-ttu-id="6f3b9-112">型**CONTOSO**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="6f3b9-113">**[PIP Code]**</span><span class="sxs-lookup"><span data-stu-id="6f3b9-113">**PIP Code**</span></span>|<span data-ttu-id="6f3b9-114">型**3 a 2**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-114">Type **3A2**.</span></span>|  
    |<span data-ttu-id="6f3b9-115">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="6f3b9-115">**PIP Version**</span></span>|<span data-ttu-id="6f3b9-116">型**r02.00.00a など**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-116">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="6f3b9-117">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="6f3b9-117">**Message Category**</span></span>|<span data-ttu-id="6f3b9-118">型**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-118">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="6f3b9-119">メモ帳または別のテキスト エディターを使用してを開く、 **3A2_Request.xml** C:\Program files \microsoft biztalk ファイル\<バージョン\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder のアクセラレータコピーして貼り付け、テキストを**Service Content**フィールドで、LOBWebApplication ツールです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-119">Using Notepad or another text editor, open the **3A2_Request.xml** file in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstancesfolder and copy and paste the text into the **Service Content** field in the LOBWebApplication tool.</span></span>  
  
4.  <span data-ttu-id="6f3b9-120">をクリックして**送信**を Contoso 3 a 2 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-120">Click **Submit** to submit the 3A2 request to Contoso.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="6f3b9-121">Fabrikam のコンピューターで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="6f3b9-121">To verify successful communication on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="6f3b9-122">**メッセージの状態**LOBWebApplication に ページで、次の 2 つの受信メッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-122">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f3b9-123">最初に受信しているのは、Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-123">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="6f3b9-124">次に受信しているのは、Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-124">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="6f3b9-125">カテゴリ -99 のメッセージは、エラーを表します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-125">A category -99 message signifies an error.</span></span> <span data-ttu-id="6f3b9-126">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-126">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
2.  <span data-ttu-id="6f3b9-127">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-127">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
3.  <span data-ttu-id="6f3b9-128">サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに、入力**localhost**を選択**Windows 認証**、クリックして**接続**.</span><span class="sxs-lookup"><span data-stu-id="6f3b9-128">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="6f3b9-129">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-129">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="6f3b9-130">**\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-130">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
6.  <span data-ttu-id="6f3b9-131">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-131">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  <span data-ttu-id="6f3b9-132">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-132">Click **Execute** to run the SQL statement.</span></span>  
  
8.  <span data-ttu-id="6f3b9-133">[クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-133">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f3b9-134">Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-134">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="6f3b9-135">Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-135">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span> <span data-ttu-id="6f3b9-136">[ServiceContent] フィールドを使用して、応答を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-136">You can also use the ServiceContent field to verify the response.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="6f3b9-137">Contoso のコンピュータで通信が成功したかどうか確認するには</span><span class="sxs-lookup"><span data-stu-id="6f3b9-137">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="6f3b9-138">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-138">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="6f3b9-139">サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに、入力**localhost**を選択**Windows 認証**、クリックして**接続**.</span><span class="sxs-lookup"><span data-stu-id="6f3b9-139">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="6f3b9-140">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-140">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="6f3b9-141">**\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-141">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="6f3b9-142">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-142">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="6f3b9-143">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-143">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="6f3b9-144">[クエリ] ウィンドウの結果ペインで、2 つの着信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-144">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f3b9-145">最初に受信しているのは、Fabrikam のコンピューターが送信した元の要求を表すカテゴリ 10 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-145">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="6f3b9-146">次に受信しているのは、受信確認メッセージを表すカテゴリ 25 のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-146">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="6f3b9-147">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-147">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="6f3b9-148">をクリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-148">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="6f3b9-149">[クエリ] ウィンドウの結果ペインで、1 つの送信メッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-149">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f3b9-150">Contoso のコンピューターから Fabrikam のコンピューターに送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-150">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="6f3b9-151">Contoso の基幹業務 (LOB) アプリケーションから Fabrikam のコンピューターに送信された応答を表すカテゴリ 50 のメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3b9-151">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3b9-152">参照</span><span class="sxs-lookup"><span data-stu-id="6f3b9-152">See Also</span></span>  
 [<span data-ttu-id="6f3b9-153">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6f3b9-153">Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)