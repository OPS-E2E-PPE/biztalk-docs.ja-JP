---
title: メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cff0cb63f88bf2b69dc01862bf8257864c00d54
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529645"
---
# <a name="verifying-a-message"></a><span data-ttu-id="cea5f-102">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="cea5f-102">Verifying a Message</span></span>
<span data-ttu-id="cea5f-103">このセクションでは、修復が完了するメッセージを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-103">This section describes how to verify a message that has been repaired.</span></span>  

### <a name="to-verify-a-message"></a><span data-ttu-id="cea5f-104">メッセージを確認するには</span><span class="sxs-lookup"><span data-stu-id="cea5f-104">To verify a message</span></span>  

1. <span data-ttu-id="cea5f-105">Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="cea5f-106">[ホーム] ウィンドウ**ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="cea5f-107">ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>_Verifier**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Verifier**.</span></span>  

4. <span data-ttu-id="cea5f-108">[確認] ウィンドウ**受信トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-108">In the Verify window, click **Inbox**.</span></span>  

5. <span data-ttu-id="cea5f-109">確認の受信トレイ ウィンドウで、メッセージのタイトルにポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-109">In the Verify Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="cea5f-110">**ファイルのダウンロード**ダイアログ ボックスで、をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-110">In the **File Download** dialog box, click **Open**.</span></span>  

7. <span data-ttu-id="cea5f-111">現在のロール。RekeyVerify ウィンドウ、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-111">In the Current Roles: RekeyVerify pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="cea5f-112">示すように、エラーを確認、**解析と XML の検証エラー**ボックスおよび**BRE 検証エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="cea5f-112">Review any errors shown in the **Parse and XML Validation Errors** box and the **BRE Validation Errors** box.</span></span>  

8. <span data-ttu-id="cea5f-113">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-113">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="cea5f-114">クリックして、元のエラーがわかります**エラー**現在のロール。RekeyVerify ウィンドウで、およびエラー ウィンドウのいずれかでこのエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-114">You can see what the original error was by clicking **Errors** in the Current Role: RekeyVerify pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="cea5f-115">クリックして、未修理、修正されたバージョンのメッセージを比較することもできます。**メッセージの詳細**、現在のロール。RekeyVerify ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="cea5f-115">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: RekeyVerify pane.</span></span>  

9. <span data-ttu-id="cea5f-116">メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール。RekeyVerify ウィンドウで、をクリックし、**検証メッセージ**。</span><span class="sxs-lookup"><span data-stu-id="cea5f-116">To ensure that the message will validate, click **Validation** in the Current Role: RekeyVerify pane, and then click **Validate Message**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="cea5f-117">[現在のロールでのメッセージの検証の結果ウィンドウ:RekeyVerify] ウィンドウでは、キーを再入力する必要のあるメッセージのすべてのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-117">The Results pane under Message Validation in the Current Role: RekeyVerify pane indicates all fields in the message that you need to rekey.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="cea5f-118">赤いアスタリスクが付けられてメッセージ ウィンドウでこれらのフィールドをマークします。</span><span class="sxs-lookup"><span data-stu-id="cea5f-118">marks these fields in the Message pane with a red asterisk.</span></span>  

10. <span data-ttu-id="cea5f-119">(データを送信する前に変更する必要があることを示す) 赤いアスタリスクでマークされたメッセージのウィンドウですべてのフィールドにデータを再入力します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-119">Rekey data into all fields in the Message pane marked with a red asterisk (indicating that the data must be rekeyed before submission).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cea5f-120">クリックして、メッセージのフィールドにキーを再入力する必要があるデータを表示できる**メッセージの詳細**現在のロール。RekeyVerify ウィンドウとフィールドに、元のメッセージをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="cea5f-120">You can display the data that you need to rekey into message fields by clicking **Message Details** in the Current Role: RekeyVerify pane, and scrolling through the original message to the field.</span></span> <span data-ttu-id="cea5f-121">これは、元のメッセージ内のキーを再入力フィールドのいずれかで検証エラーが発生した場合を除き、true を再入力すると、フィールドを修復する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="cea5f-121">This is true unless there was a validation error in one of the rekey fields in the original message, in which case you have to repair the field when you rekey it.</span></span>  

11. <span data-ttu-id="cea5f-122">クリックして**検証**で、**現在のロール。RekeyVerify**ペイン、およびクリック**検証メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-122">Click **Validation** in the **Current Role: RekeyVerify** pane, and then click **Validate Message**.</span></span> <span data-ttu-id="cea5f-123">結果ウィンドウが、メッセージが表示されることを確認 **、メッセージが有効な**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-123">Verify that the Results pane displays the message **The message is valid**.</span></span>  

12. <span data-ttu-id="cea5f-124">クリックして**送信**で、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cea5f-124">Click **Submit** in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cea5f-125">クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-125">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="cea5f-126">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea5f-126">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

13. <span data-ttu-id="cea5f-127">[Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで検証済みのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-127">In the Submit Message dialog box, click **Accept** to submit the verified message with changes accepted.</span></span> <span data-ttu-id="cea5f-128">をクリックして**拒否**拒否の変更で、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-128">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="cea5f-129">クリックして**キャンセル**送信をキャンセルし、フォームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cea5f-129">Click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cea5f-130">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="cea5f-130">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="cea5f-131">メッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成するか修復) と修復のワークフローがリセットされます。</span><span class="sxs-lookup"><span data-stu-id="cea5f-131">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  

14. <span data-ttu-id="cea5f-132">デジタル署名のウィザード ページで、フォームに署名する証明書を選択するためには、フォーム (検証用に作成した書) の署名に使用する証明書を選択し をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-132">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the verifier), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cea5f-133">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.</span><span class="sxs-lookup"><span data-stu-id="cea5f-133">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="cea5f-134">このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="cea5f-134">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  

15. <span data-ttu-id="cea5f-135">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-135">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

16. <span data-ttu-id="cea5f-136">デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-136">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="cea5f-137">クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。</span><span class="sxs-lookup"><span data-stu-id="cea5f-137">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="cea5f-138">クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-138">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

17. <span data-ttu-id="cea5f-139">デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-139">In the Verify Digital Signature window, click **Close**.</span></span>  

18. <span data-ttu-id="cea5f-140">[送信の成功] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-140">In the Submission Success dialog box, click **OK**.</span></span>  

19. <span data-ttu-id="cea5f-141">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cea5f-141">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

20. <span data-ttu-id="cea5f-142">サイトの MRSR クリックして**ドキュメントし、リスト**します。</span><span class="sxs-lookup"><span data-stu-id="cea5f-142">In MRSR site, click **Documents and Lists**.</span></span> <span data-ttu-id="cea5f-143">クリックした場合は**Accept**手順 13 で変更を許可することを確認、\<部門名\>_Approve ドキュメント ライブラリが変更されただけのメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cea5f-143">If you clicked **Accept** to accept the changes in step 13, verify that the \<Department name\>_Approve document library contains the message that was just modified.</span></span> <span data-ttu-id="cea5f-144">ドキュメントとリストのウィンドウが開いて既にが存在する場合にクリックします**更新**上、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="cea5f-144">If you already had the Documents and Lists window open, click **Refresh** on the **View** menu.</span></span> <span data-ttu-id="cea5f-145">クリックした場合は**拒否**手順 13 で変更を却下することを確認、 *\<コンピューター名\>*_Outbox ドキュメント ライブラリが変更されただけのメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cea5f-145">If you clicked **Reject** to reject the changes in step 13, verify that the *\<computer name\>*_Outbox document library contains the message that was just modified.</span></span>
