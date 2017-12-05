---
title: "メッセージを承認する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3bdbd4845ddc1dff698274492f33ec69d659188
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="approving-a-message"></a><span data-ttu-id="58382-102">メッセージを承認します。</span><span class="sxs-lookup"><span data-stu-id="58382-102">Approving a Message</span></span>
<span data-ttu-id="58382-103">このセクションでは、修復および検証されているメッセージを承認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="58382-103">This section describes how to approve a message that has been repaired and verified.</span></span>  
  
### <a name="to-approve-a-message"></a><span data-ttu-id="58382-104">メッセージを承認するには</span><span class="sxs-lookup"><span data-stu-id="58382-104">To approve a message</span></span>  
  
1.  <span data-ttu-id="58382-105">Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="58382-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="58382-106">[ホーム] ウィンドウ**ドキュメント**です。</span><span class="sxs-lookup"><span data-stu-id="58382-106">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="58382-107">ドキュメント ウィンドウで、**ドキュメント ライブラリ**をクリックして  **\<*部門名*\>_Approver * *。</span><span class="sxs-lookup"><span data-stu-id="58382-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Approver**.</span></span>  
  
4.  <span data-ttu-id="58382-108">\<部門名\>_Approver ウィンドウで、をクリックして**受信トレイ**です。</span><span class="sxs-lookup"><span data-stu-id="58382-108">In the \<Department name\>_Approver window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="58382-109">受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックし、をクリックして**Microsoft Office InfoPath で編集**です。</span><span class="sxs-lookup"><span data-stu-id="58382-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="58382-110">SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**エラー**です。</span><span class="sxs-lookup"><span data-stu-id="58382-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="58382-111">示すようにエラーを確認、**解析と XML 検証エラー**ボックスで、 **BRE 妥当性確認エラー**ボックス、および**ランタイム エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="58382-111">Review any errors shown in the **Parse and XML Validation Errors** box, the **BRE Validation Errors** box, and the **Runtime Errors** box.</span></span>  
  
7.  <span data-ttu-id="58382-112">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの位置までスクロールし、エラーが修正されたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="58382-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="58382-113">クリックして元のエラーを参照してください**エラー**現在のロールで: ペイン、およびエラー ペインのいずれかで、エラーの表示を承認します。</span><span class="sxs-lookup"><span data-stu-id="58382-113">You can see what the original error was by clicking **Errors** in the Current Role: Approve pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="58382-114">クリックして、メッセージのバージョンの未修理と修復されたバージョンを比較することもできます。**メッセージの詳細**、現在のロールで: ウィンドウを承認します。</span><span class="sxs-lookup"><span data-stu-id="58382-114">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: Approve pane.</span></span>  
  
8.  <span data-ttu-id="58382-115">メッセージを検証するためには、をクリックして**検証**、現在のロールで: ウィンドウを承認し、をクリックして**検証メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="58382-115">To ensure that the message will validate, click **Validation** in the Current Role: Approve pane, and then click **Validate Message**.</span></span> <span data-ttu-id="58382-116">結果ペインがメッセージを表示することを確認してください。**メッセージが有効では**します。</span><span class="sxs-lookup"><span data-stu-id="58382-116">Verify that the Results pane displays the message **The message is valid**.</span></span>  
  
9. <span data-ttu-id="58382-117">ドキュメントに加えられた変更の承認した場合、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**です。</span><span class="sxs-lookup"><span data-stu-id="58382-117">If you approve of the changes that have been made to the document, in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58382-118">クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="58382-118">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="58382-119">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58382-119">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  
  
10. <span data-ttu-id="58382-120">[Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れと共に、承認されたメッセージを送信するためです。</span><span class="sxs-lookup"><span data-stu-id="58382-120">In the Submit Message dialog box, click **Accept** to submit the approved message with changes accepted.</span></span> <span data-ttu-id="58382-121">をクリックして**拒否**拒否変更と共に、メッセージを送信するためです。</span><span class="sxs-lookup"><span data-stu-id="58382-121">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="58382-122">をクリックして**キャンセル**送信をキャンセルし、フォームに戻る。</span><span class="sxs-lookup"><span data-stu-id="58382-122">Click **Cancel** to cancel the submission and return to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58382-123">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="58382-123">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58382-124">メッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ワークフローの最初のステージにメッセージが返されます (作成または修復) し、修復ワークフローをリセットします。</span><span class="sxs-lookup"><span data-stu-id="58382-124">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  
  
11. <span data-ttu-id="58382-125">デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (証明書承認用に作成) の署名に使用する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="58382-125">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the approver).</span></span> <span data-ttu-id="58382-126">をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。</span><span class="sxs-lookup"><span data-stu-id="58382-126">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="58382-127">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58382-127">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58382-128">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.</span><span class="sxs-lookup"><span data-stu-id="58382-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="58382-129">表示できます (フォームのみ署名できるワークフローごとに 1 回のユーザーによって)、フォーム以前に署名するロールをクリックして**デジタル署名**上、**ツール**メニュー。</span><span class="sxs-lookup"><span data-stu-id="58382-129">You can also see which roles have signed the form previously (a form can only be signed by a person once per workflow) by clicking **Digital Signatures** on the **Tools** menu.</span></span> <span data-ttu-id="58382-130">このロールの別の署名を追加する必要がある場合に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="58382-130">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  
  
12. <span data-ttu-id="58382-131">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="58382-131">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
13. <span data-ttu-id="58382-132">デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="58382-132">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="58382-133">をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。</span><span class="sxs-lookup"><span data-stu-id="58382-133">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="58382-134">をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。</span><span class="sxs-lookup"><span data-stu-id="58382-134">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
14. <span data-ttu-id="58382-135">デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="58382-135">In the Verify Digital Signature window, click **Close**.</span></span>  
  
15. <span data-ttu-id="58382-136">[送信の成功] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="58382-136">In the Submission Success dialog box, click **OK**.</span></span>  
  
16. <span data-ttu-id="58382-137">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="58382-137">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  
  
17. <span data-ttu-id="58382-138">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、送信メッセージを受信し、設定したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="58382-138">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, open the folder that you set up to receive sent messages.</span></span> <span data-ttu-id="58382-139">フォルダーが承認されたメッセージが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="58382-139">Verify that the folder contains the approved message.</span></span> <span data-ttu-id="58382-140">メッセージをメッセージが修復されたことを確認するテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="58382-140">Open the message in a text editor to verify that the message has been repaired.</span></span>