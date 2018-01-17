---
title: "メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2fdc186e93bd182b3021a3ef8fc258cee59923
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="verifying-a-message"></a><span data-ttu-id="3bf5d-102">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="3bf5d-102">Verifying a Message</span></span>
<span data-ttu-id="3bf5d-103">このセクションでは、修復されましたが、メッセージを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-103">This section describes how to verify a message that has been repaired.</span></span>  
  
### <a name="to-verify-a-message"></a><span data-ttu-id="3bf5d-104">メッセージを確認するには</span><span class="sxs-lookup"><span data-stu-id="3bf5d-104">To verify a message</span></span>  
  
1.  <span data-ttu-id="3bf5d-105">Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="3bf5d-106">[ホーム] ウィンドウ**ドキュメント**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-106">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="3bf5d-107">ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして **\<*部門名*\>_Verifier**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Verifier**.</span></span>  
  
4.  <span data-ttu-id="3bf5d-108">確認してください ウィンドウで、をクリックして**受信トレイ**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-108">In the Verify window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="3bf5d-109">確認の受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックして**Microsoft Office InfoPath で編集**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-109">In the Verify Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="3bf5d-110">**ファイルのダウンロード**ダイアログ ボックスで、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-110">In the **File Download** dialog box, click **Open**.</span></span>  
  
7.  <span data-ttu-id="3bf5d-111">現在のロールで: RekeyVerify ウィンドウの[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-111">In the Current Roles: RekeyVerify pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="3bf5d-112">示すように、エラーを確認して、**解析と XML 検証エラー**ボックスおよび**BRE 妥当性確認エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-112">Review any errors shown in the **Parse and XML Validation Errors** box and the **BRE Validation Errors** box.</span></span>  
  
8.  <span data-ttu-id="3bf5d-113">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-113">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="3bf5d-114">クリックして元のエラーを参照してください**エラー**現在のロールで: RekeyVerify ウィンドウで、エラー ウィンドウのいずれかでエラーを表示するとします。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-114">You can see what the original error was by clicking **Errors** in the Current Role: RekeyVerify pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="3bf5d-115">クリックして、メッセージのバージョンの未修理と修復されたバージョンを比較することもできます。**メッセージの詳細**で、現在のロール: RekeyVerify ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-115">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: RekeyVerify pane.</span></span>  
  
9. <span data-ttu-id="3bf5d-116">メッセージを検証するためには、をクリックして**検証**、現在のロールで: RekeyVerify ウィンドウで、をクリックして**検証メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-116">To ensure that the message will validate, click **Validation** in the Current Role: RekeyVerify pane, and then click **Validate Message**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-117">現在のロールでのメッセージの検証 [結果] ペイン: RekeyVerify ウィンドウは、キー更新する必要のあるメッセージのすべてのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-117">The Results pane under Message Validation in the Current Role: RekeyVerify pane indicates all fields in the message that you need to rekey.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="3bf5d-118">赤いアスタリスクの付いたメッセージ ウィンドウでこれらのフィールドをマークします。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-118"> marks these fields in the Message pane with a red asterisk.</span></span>  
  
10. <span data-ttu-id="3bf5d-119">ウィンドウで、メッセージ (送信の前に、データを再生成する必要があることを示す)、赤いアスタリスクでマークされたすべてのフィールドにデータを鍵更新します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-119">Rekey data into all fields in the Message pane marked with a red asterisk (indicating that the data must be rekeyed before submission).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-120">メッセージ フィールドにキーを更新する必要のあるデータを表示する をクリックして**メッセージの詳細**現在のロールで: RekeyVerify ウィンドウで、フィールドに、元のメッセージのスクロールとします。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-120">You can display the data that you need to rekey into message fields by clicking **Message Details** in the Current Role: RekeyVerify pane, and scrolling through the original message to the field.</span></span> <span data-ttu-id="3bf5d-121">これは、元のメッセージ内のキー更新フィールドのいずれかで検証エラーが発生した場合を除き、true に鍵を更新するときに、フィールドを修復する必要場合。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-121">This is true unless there was a validation error in one of the rekey fields in the original message, in which case you have to repair the field when you rekey it.</span></span>  
  
11. <span data-ttu-id="3bf5d-122">をクリックして**検証**で、**現在のロール: RekeyVerify**  ウィンドウで、クリックして**検証メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-122">Click **Validation** in the **Current Role: RekeyVerify** pane, and then click **Validate Message**.</span></span> <span data-ttu-id="3bf5d-123">結果ペインがメッセージを表示することを確認してください。**メッセージが有効では**します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-123">Verify that the Results pane displays the message **The message is valid**.</span></span>  
  
12. <span data-ttu-id="3bf5d-124">をクリックして**送信**で、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-124">Click **Submit** in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-125">クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-125">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="3bf5d-126">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-126">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  
  
13. <span data-ttu-id="3bf5d-127">[Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れと共に確認済みのメッセージを送信するためです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-127">In the Submit Message dialog box, click **Accept** to submit the verified message with changes accepted.</span></span> <span data-ttu-id="3bf5d-128">をクリックして**拒否**拒否変更と共に、メッセージを送信するためです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-128">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="3bf5d-129">をクリックして**キャンセル**送信をキャンセルし、フォームに戻る。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-129">Click **Cancel** to cancel the submission and return to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-130">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-130">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-131">メッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成または修復) し、修復ワークフローをリセットします。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-131">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  
  
14. <span data-ttu-id="3bf5d-132">デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (、証明書を検証用に作成した)、署名に使用する証明書を選択し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-132">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the verifier), and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bf5d-133">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.</span><span class="sxs-lookup"><span data-stu-id="3bf5d-133">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="3bf5d-134">このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-134">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  
  
15. <span data-ttu-id="3bf5d-135">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-135">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
16. <span data-ttu-id="3bf5d-136">デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-136">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="3bf5d-137">をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-137">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="3bf5d-138">をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-138">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
17. <span data-ttu-id="3bf5d-139">デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-139">In the Verify Digital Signature window, click **Close**.</span></span>  
  
18. <span data-ttu-id="3bf5d-140">[送信の成功] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-140">In the Submission Success dialog box, click **OK**.</span></span>  
  
19. <span data-ttu-id="3bf5d-141">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-141">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  
  
20. <span data-ttu-id="3bf5d-142">サイトの MRSR クリックして**ドキュメントし、リスト**です。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-142">In MRSR site, click **Documents and Lists**.</span></span> <span data-ttu-id="3bf5d-143">クリックした場合は**Accept**手順 13. の変更を受け入れるようにいることを確認、\<部門名\>_Approve ドキュメント ライブラリには、直前に変更するメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-143">If you clicked **Accept** to accept the changes in step 13, verify that the \<Department name\>_Approve document library contains the message that was just modified.</span></span> <span data-ttu-id="3bf5d-144">開いているドキュメントとリストのウィンドウが既に存在する場合はクリックして**更新**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-144">If you already had the Documents and Lists window open, click **Refresh** on the **View** menu.</span></span> <span data-ttu-id="3bf5d-145">クリックした場合は**拒否**手順 13. の変更を拒否することを確認、 *\<コンピューター名\>*_Outbox ドキュメント ライブラリには、直前に変更するメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3bf5d-145">If you clicked **Reject** to reject the changes in step 13, verify that the *\<computer name\>*_Outbox document library contains the message that was just modified.</span></span>