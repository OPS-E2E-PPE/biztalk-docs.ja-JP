---
title: 手順 3:3 a 2 要求の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, submitting requests
ms.assetid: 09f22be8-6d7d-48bf-862b-73248bae0506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4feb98c9258c870fc43eb9cf5b9583e932933092
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281044"
---
# <a name="step-3-submitting-a-3a2-request"></a><span data-ttu-id="da846-102">手順 3:3 a 2 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="da846-102">Step 3: Submitting a 3A2 Request</span></span>
<span data-ttu-id="da846-103">この手順では、準備し、3 a 2 - Request Price and Availability をプロセス PIP (Partner Interface) を使用して、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="da846-103">In this step, you prepare and submit a request using the Partner Interface Process (PIP) for a 3A2 - Request Price and Availability.</span></span> <span data-ttu-id="da846-104">この PIP により、購入者の組織が、特定の製品価格と使用可能なユニットの数などに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="da846-104">This PIP enables a buyer organization to obtain information about a certain product, such as price and number of available units.</span></span> <span data-ttu-id="da846-105">購入者には、業者から製品を購入するかどうかを決定するビジネス ルールに基づいてその情報を処理し、できます。</span><span class="sxs-lookup"><span data-stu-id="da846-105">The buyer can then process that information through business rules to determine whether to purchase the product from the supplier.</span></span>  
  
### <a name="to-submit-a-3a2---request-price-and-availability"></a><span data-ttu-id="da846-106">3 a 2 - Request Price and Availability を送信するには</span><span class="sxs-lookup"><span data-stu-id="da846-106">To submit a 3A2 - Request Price and Availability</span></span>  
  
1.  <span data-ttu-id="da846-107">Internet Explorer で、Fabrikam のコンピューターで検索し、開きます http://localhost/LOBWebApplication/default.aspxします。</span><span class="sxs-lookup"><span data-stu-id="da846-107">On the Fabrikam computer, in Internet Explorer, locate and open http://localhost/LOBWebApplication/default.aspx.</span></span>  
  
2.  <span data-ttu-id="da846-108">**Submit Message**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="da846-108">On the **Submit Message** page, do the following:</span></span>  
  
    |<span data-ttu-id="da846-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="da846-109">Use this</span></span>|<span data-ttu-id="da846-110">目的</span><span class="sxs-lookup"><span data-stu-id="da846-110">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="da846-111">**ホーム組織**</span><span class="sxs-lookup"><span data-stu-id="da846-111">**Home Organization**</span></span>|<span data-ttu-id="da846-112">型**FABRIKAM**します。</span><span class="sxs-lookup"><span data-stu-id="da846-112">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="da846-113">**取引先組織**</span><span class="sxs-lookup"><span data-stu-id="da846-113">**Partner Organization**</span></span>|<span data-ttu-id="da846-114">型**Contoso**します。</span><span class="sxs-lookup"><span data-stu-id="da846-114">Type **Contoso**.</span></span>|  
    |<span data-ttu-id="da846-115">**[Pip Code]**</span><span class="sxs-lookup"><span data-stu-id="da846-115">**Pip Code**</span></span>|<span data-ttu-id="da846-116">型**3 a 2**します。</span><span class="sxs-lookup"><span data-stu-id="da846-116">Type **3A2**.</span></span> <span data-ttu-id="da846-117">**重要:** 重複するメッセージ ID のエラーを回避する必要があること確認する、 **Pip**は送信した各メッセージに一意です。</span><span class="sxs-lookup"><span data-stu-id="da846-117">**Important:**  To avoid duplicate message ID errors, you must make sure that the **Pip** is unique for each message that you submit.</span></span> <span data-ttu-id="da846-118">今後 3 a 2 テストを実行する場合は、このフィールドを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da846-118">If you run the 3A2 test in the future, you have to change this field.</span></span>|  
    |<span data-ttu-id="da846-119">**[Pip Version]**</span><span class="sxs-lookup"><span data-stu-id="da846-119">**Pip Version**</span></span>|<span data-ttu-id="da846-120">型**r02.00.00a など**します。</span><span class="sxs-lookup"><span data-stu-id="da846-120">Type **R02.00.00A**.</span></span>|  
    |<span data-ttu-id="da846-121">**Pip インスタンス ID**</span><span class="sxs-lookup"><span data-stu-id="da846-121">**Pip Instance ID**</span></span>|<span data-ttu-id="da846-122">型**3A2_Test**します。</span><span class="sxs-lookup"><span data-stu-id="da846-122">Type **3A2_Test**.</span></span>|  
    |<span data-ttu-id="da846-123">**メッセージのカテゴリ**</span><span class="sxs-lookup"><span data-stu-id="da846-123">**Message Category**</span></span>|<span data-ttu-id="da846-124">型**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="da846-124">Type **Action**.</span></span>|  
  
3.  <span data-ttu-id="da846-125">メモ帳または別のテキスト エディターを使用して、内の 3A2_Request.xml ファイルを開き、 *\<ドライブ\>*: \プログラムの files \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances フォルダーに、コピーして貼り付け、内容、 **Service Content**フィールドにLOBWebApplication します。</span><span class="sxs-lookup"><span data-stu-id="da846-125">Using Notepad or another text editor, open the file 3A2_Request.xml in the *\<drive\>*:\ Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBApplication\SampleInstances folder, and then copy and paste the contents into the **Service Content** field in LOBWebApplication.</span></span>  
  
4.  <span data-ttu-id="da846-126">クリックして**送信**Contoso のコンピューターに 3 a 2 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="da846-126">Click **Submit** to submit the 3A2 request to the Contoso computer.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-fabrikam-computer"></a><span data-ttu-id="da846-127">Fabrikam のコンピューターで通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="da846-127">To verify successful communication on the Fabrikam computer</span></span>  
  
-   <span data-ttu-id="da846-128">**メッセージの状態**LOBWebApplication のページで、2 つのメッセージを受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="da846-128">On the **Message Status** page in LOBWebApplication, verify that you receive two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da846-129">Contoso のコンピューターからの受信確認を表すカテゴリ 25 のメッセージを最初に受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da846-129">You should first receive a category 25 message signifying a receipt acknowledgement from the Contoso computer.</span></span> <span data-ttu-id="da846-130">Contoso のコンピューターからの応答メッセージであるカテゴリ 50 のメッセージを受信する必要がありますから。</span><span class="sxs-lookup"><span data-stu-id="da846-130">You should then receive a category 50 message that is the response message from the Contoso computer.</span></span> <span data-ttu-id="da846-131">カテゴリ-99 のメッセージでは、エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="da846-131">A category -99 message signifies an error.</span></span> <span data-ttu-id="da846-132">使用することができます**イベント ビューアー**を実際のエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="da846-132">You can use **Event Viewer** to determine the actual error message.</span></span>  
  
### <a name="to-verify-successful-communication-on-the-contoso-computer"></a><span data-ttu-id="da846-133">Contoso のコンピューターの通信が成功したことを確認するには</span><span class="sxs-lookup"><span data-stu-id="da846-133">To verify successful communication on the Contoso computer</span></span>  
  
1.  <span data-ttu-id="da846-134">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="da846-134">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="da846-135">**サーバーへの接続** ダイアログ ボックスで、 **SQL Server**ボックスに「 **localhost**、 **Windows 認証**順にクリックします**接続**します。</span><span class="sxs-lookup"><span data-stu-id="da846-135">In the **Connect to Server** dialog box, in the **SQL Server** box, type **localhost**, select **Windows Authentication**, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="da846-136">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="da846-136">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="da846-137">\<テーブル\>テキスト ボックスで、 **BTARNDATA**一覧から。</span><span class="sxs-lookup"><span data-stu-id="da846-137">In the \<table\> text box, select **BTARNDATA** from the list.</span></span>  
  
5.  <span data-ttu-id="da846-138">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="da846-138">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesToLOB  
    ```  
  
6.  <span data-ttu-id="da846-139">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="da846-139">Click **Execute** to run the SQL statement.</span></span>  
  
7.  <span data-ttu-id="da846-140">結果ウィンドウで、クエリ ウィンドウで 2 つのメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da846-140">In the Query window, in the Results pane, verify that you see two incoming messages.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da846-141">最初に、Fabrikam のコンピューターから送信された元の要求を表すカテゴリ 10 のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="da846-141">You should first receive a category 10 message that represents the original request sent by the Fabrikam computer.</span></span> <span data-ttu-id="da846-142">受信確認のメッセージを表すカテゴリ 25 のメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da846-142">You should then receive a category 25 message signifying the receipt acknowledgement message.</span></span>  
  
8.  <span data-ttu-id="da846-143">SQL ウィンドウで、次の SQL ステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="da846-143">In the SQL window, type the following SQL statement:</span></span>  
  
    ```  
    SELECT * From MessagesFromLOB  
    ```  
  
9. <span data-ttu-id="da846-144">クリックして**Execute** SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="da846-144">Click **Execute** to run the SQL statement.</span></span>  
  
10. <span data-ttu-id="da846-145">結果ウィンドウで、クエリ ウィンドウで、1 つの送信メッセージが表示される確認します。</span><span class="sxs-lookup"><span data-stu-id="da846-145">In the Query window, in the Results pane, verify that you see one outgoing message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da846-146">Fabrikam のコンピューターに、Contoso から送信された受信確認を表すカテゴリ 25 のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da846-146">You should see a category 25 message that represents the receipt acknowledgement sent from Contoso to the Fabrikam computer.</span></span> <span data-ttu-id="da846-147">Fabrikam のコンピューターに Contoso の基幹業務 (LOB) アプリケーションから送信された応答を表すカテゴリ 50 のメッセージも表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da846-147">You should also see a category 50 message that represents the response sent from the Contoso line-of-business (LOB) application to the Fabrikam computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da846-148">参照</span><span class="sxs-lookup"><span data-stu-id="da846-148">See Also</span></span>  
 <span data-ttu-id="da846-149">[手順 4:3A4 要求の送信](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span><span class="sxs-lookup"><span data-stu-id="da846-149">[Step 4: Submitting a 3A4 Request](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md) </span></span>  
 [<span data-ttu-id="da846-150">BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="da846-150">Message Flow in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)