---
title: メッセージの承認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c565f40c6c455456101521414edf0c377411014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967107"
---
# <a name="approving-a-message"></a><span data-ttu-id="2f216-102">メッセージの承認</span><span class="sxs-lookup"><span data-stu-id="2f216-102">Approving a Message</span></span>
<span data-ttu-id="2f216-103">このセクションでは、修復され検証されたメッセージを承認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f216-103">This section describes how to approve a message that has been repaired and verified.</span></span>  

### <a name="to-approve-a-message"></a><span data-ttu-id="2f216-104">メッセージを承認するには</span><span class="sxs-lookup"><span data-stu-id="2f216-104">To approve a message</span></span>  

1. <span data-ttu-id="2f216-105">Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。</span><span class="sxs-lookup"><span data-stu-id="2f216-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="2f216-106">[ホーム] ウィンドウ**ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="2f216-107">ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>_Approver**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Approver**.</span></span>  

4. <span data-ttu-id="2f216-108">\<部門名\>_Approver ウィンドウで、をクリックして**受信トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-108">In the \<Department name\>_Approver window, click **Inbox**.</span></span>  

5. <span data-ttu-id="2f216-109">受信トレイ ウィンドウで、メッセージのタイトルをポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="2f216-110">SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="2f216-111">示すように、エラーを確認、**解析と XML の検証エラー**ボックスで、 **BRE 検証エラー**ボックスで、および**ランタイム エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="2f216-111">Review any errors shown in the **Parse and XML Validation Errors** box, the **BRE Validation Errors** box, and the **Runtime Errors** box.</span></span>  

7. <span data-ttu-id="2f216-112">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f216-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="2f216-113">クリックして、元のエラーがわかります**エラー**現在のロール: ペイン、およびエラー ウィンドウのいずれかで、エラーの表示を承認します。</span><span class="sxs-lookup"><span data-stu-id="2f216-113">You can see what the original error was by clicking **Errors** in the Current Role: Approve pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="2f216-114">クリックして、未修理、修正されたバージョンのメッセージを比較することもできます。**メッセージの詳細**、現在のロール: ウィンドウを承認します。</span><span class="sxs-lookup"><span data-stu-id="2f216-114">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: Approve pane.</span></span>  

8. <span data-ttu-id="2f216-115">メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール: 承認ウィンドウで、をクリック**検証メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-115">To ensure that the message will validate, click **Validation** in the Current Role: Approve pane, and then click **Validate Message**.</span></span> <span data-ttu-id="2f216-116">結果ウィンドウが、メッセージが表示されることを確認 **、メッセージが有効な**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-116">Verify that the Results pane displays the message **The message is valid**.</span></span>  

9. <span data-ttu-id="2f216-117">ドキュメントに加えられた変更を承認する場合、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-117">If you approve of the changes that have been made to the document, in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2f216-118">クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f216-118">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="2f216-119">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f216-119">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="2f216-120">[Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで承認されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2f216-120">In the Submit Message dialog box, click **Accept** to submit the approved message with changes accepted.</span></span> <span data-ttu-id="2f216-121">をクリックして**拒否**拒否の変更で、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2f216-121">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="2f216-122">クリックして**キャンセル**送信をキャンセルし、フォームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2f216-122">Click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2f216-123">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="2f216-123">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="2f216-124">メッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成するか修復) と修復のワークフローがリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2f216-124">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  

11. <span data-ttu-id="2f216-125">デジタル署名ウィザード ページで、フォームに署名する証明書を選択するため、フォーム (承認者用に作成した書) の署名に使用する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f216-125">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the approver).</span></span> <span data-ttu-id="2f216-126">クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。</span><span class="sxs-lookup"><span data-stu-id="2f216-126">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="2f216-127">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f216-127">Click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="2f216-128">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.</span><span class="sxs-lookup"><span data-stu-id="2f216-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="2f216-129">確認できます (フォームのみ署名できるワークフローごとに 1 回のユーザーによって)、フォーム以前の済みであるロールをクリックして**デジタル署名**上、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2f216-129">You can also see which roles have signed the form previously (a form can only be signed by a person once per workflow) by clicking **Digital Signatures** on the **Tools** menu.</span></span> <span data-ttu-id="2f216-130">このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2f216-130">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  

12. <span data-ttu-id="2f216-131">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-131">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

13. <span data-ttu-id="2f216-132">デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f216-132">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="2f216-133">クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。</span><span class="sxs-lookup"><span data-stu-id="2f216-133">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="2f216-134">クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-134">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="2f216-135">デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-135">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="2f216-136">[送信の成功] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="2f216-136">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="2f216-137">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2f216-137">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="2f216-138">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、送信されたメッセージを受信するように設定するフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2f216-138">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, open the folder that you set up to receive sent messages.</span></span> <span data-ttu-id="2f216-139">フォルダーが承認済みのメッセージが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f216-139">Verify that the folder contains the approved message.</span></span> <span data-ttu-id="2f216-140">メッセージをメッセージが修復されたことを確認するテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="2f216-140">Open the message in a text editor to verify that the message has been repaired.</span></span>
