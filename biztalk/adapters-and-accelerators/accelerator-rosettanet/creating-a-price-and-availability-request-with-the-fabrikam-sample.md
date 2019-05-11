---
title: Fabrikam サンプルを Price and Availability 要求を作成する |Microsoft Docs
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
ms.openlocfilehash: 37ace1e92767b5eee040cd3c0e11cd747846f5ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284672"
---
# <a name="creating-a-price-and-availability-request-with-the-fabrikam-sample"></a><span data-ttu-id="1bfae-102">Fabrikam サンプルを使用して Price and Availability Request の作成</span><span class="sxs-lookup"><span data-stu-id="1bfae-102">Creating a Price and Availability Request with the Fabrikam Sample</span></span>
<span data-ttu-id="1bfae-103">この手順では、LOBWebApplication ツールを使用して 3 a 2 Price and Availability 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-103">In this step, you create a 3A2 Price and Availability request using the LOBWebApplication tool.</span></span>  
  
### <a name="to-submit-a-3a2-price-and-availability-request-to-contoso"></a><span data-ttu-id="1bfae-104">3 a 2 Price and Availability 要求を Contoso に送信するには</span><span class="sxs-lookup"><span data-stu-id="1bfae-104">To submit a 3A2 Price and Availability request to Contoso</span></span>  
  
1.  <span data-ttu-id="1bfae-105">Internet Explorer で、移動 http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-105">In Internet Explorer, move to http://\<*fabrikam_computername*\>/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="1bfae-106">**LOBWebApplication**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1bfae-106">On the **LOBWebApplication** page, do the following:</span></span>  
  
    |<span data-ttu-id="1bfae-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1bfae-107">Use this</span></span>|<span data-ttu-id="1bfae-108">目的</span><span class="sxs-lookup"><span data-stu-id="1bfae-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1bfae-109">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="1bfae-109">**Home Organization**</span></span>|<span data-ttu-id="1bfae-110">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-110">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="1bfae-111">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="1bfae-111">**Partner Organization**</span></span>|<span data-ttu-id="1bfae-112">型**CONTOSO**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-112">Type **CONTOSO**.</span></span>|  
    |<span data-ttu-id="1bfae-113">**[PIP Code]**</span><span class="sxs-lookup"><span data-stu-id="1bfae-113">**PIP Code**</span></span>|<span data-ttu-id="1bfae-114">型**3 a 2**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-114">Type **3A2**.</span></span>|  
    |<span data-ttu-id="1bfae-115">**[PIP Version]**</span><span class="sxs-lookup"><span data-stu-id="1bfae-115">**PIP Version**</span></span>|<span data-ttu-id="1bfae-116">型**r02.00.00a など**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-116">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="1bfae-117">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="1bfae-117">**Message Category**</span></span>|<span data-ttu-id="1bfae-118">型**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-118">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="1bfae-119">メモ帳または別のテキスト エディターを使用してを開く、 **3A2_Request.xml**ファイルは C:\Program files \microsoft biztalk\<バージョン\>RosettaNet\SDK\LOBApplication\SampleInstancesfolder のアクセラレータテキストを貼り付けるし、コピー、 **Service Content**フィールドで、LOBWebApplication ツール。</span><span class="sxs-lookup"><span data-stu-id="1bfae-119">Using Notepad or another text editor, open the **3A2_Request.xml** file in the C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstancesfolder and copy and paste the text into the **Service Content** field in the LOBWebApplication tool.</span></span>  
  
4.  <span data-ttu-id="1bfae-120">クリックして**送信**を Contoso 3 a 2 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-120">Click **Submit** to submit the 3A2 request to Contoso.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="1bfae-121">Fabrikam のコンピューターで通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="1bfae-121">To verify successful communication on the Fabrikam computer</span></span>  
  
1.  <span data-ttu-id="1bfae-122">**メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-122">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bfae-123">Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfae-123">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="1bfae-124">Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。</span><span class="sxs-lookup"><span data-stu-id="1bfae-124">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="1bfae-125">カテゴリ-99 のメッセージでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-125">A category -99 message signifies an error.</span></span> <span data-ttu-id="1bfae-126">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-126">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
2.  <span data-ttu-id="1bfae-127">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-127">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
3.  <span data-ttu-id="1bfae-128">サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに「 **localhost**を選択します**Windows 認証** をクリックし、 **Connect**.</span><span class="sxs-lookup"><span data-stu-id="1bfae-128">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="1bfae-129">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-129">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="1bfae-130">**\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧から。</span><span class="sxs-lookup"><span data-stu-id="1bfae-130">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
6.  <span data-ttu-id="1bfae-131">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-131">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
7.  <span data-ttu-id="1bfae-132">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-132">Click **Execute** to run the SQL statement.</span></span>  
  
8.  <span data-ttu-id="1bfae-133">結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-133">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bfae-134">Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bfae-134">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="1bfae-135">Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfae-135">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span> <span data-ttu-id="1bfae-136">応答の検証を servicecontent フィールドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bfae-136">You can also use the ServiceContent field to verify the response.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="1bfae-137">Contoso のコンピューターの通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="1bfae-137">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="1bfae-138">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-138">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="1bfae-139">サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスに「 **localhost**を選択します**Windows 認証** をクリックし、 **Connect**.</span><span class="sxs-lookup"><span data-stu-id="1bfae-139">In the Connect to Server dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="1bfae-140">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-140">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="1bfae-141">**\<テーブル\>テキスト**ダイアログ ボックスで、 **BTARNDATA**一覧から。</span><span class="sxs-lookup"><span data-stu-id="1bfae-141">In the **\<table\> text** dialog box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="1bfae-142">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-142">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="1bfae-143">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-143">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="1bfae-144">結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-144">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bfae-145">最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-145">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="1bfae-146">受信確認のメッセージを表すカテゴリ 25 のメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfae-146">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="1bfae-147">**SQL**ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-147">In the **SQL** window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="1bfae-148">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-148">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="1bfae-149">結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。</span><span class="sxs-lookup"><span data-stu-id="1bfae-149">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bfae-150">Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1bfae-150">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="1bfae-151">Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfae-151">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfae-152">参照</span><span class="sxs-lookup"><span data-stu-id="1bfae-152">See Also</span></span>  
 [<span data-ttu-id="1bfae-153">プライベート プロセス チュートリアル</span><span class="sxs-lookup"><span data-stu-id="1bfae-153">Private Process Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-process-tutorial.md)