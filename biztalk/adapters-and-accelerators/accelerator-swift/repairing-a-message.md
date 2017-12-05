---
title: "メッセージの修復 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4489e463257f811fe2c71efea49880940751c66a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="repairing-a-message"></a><span data-ttu-id="03a95-102">メッセージの修復</span><span class="sxs-lookup"><span data-stu-id="03a95-102">Repairing a Message</span></span>
<span data-ttu-id="03a95-103">このセクションでは、検証が失敗したメッセージを修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03a95-103">This section describes how to repair a message that has failed validation.</span></span>  
  
### <a name="to-repair-a-message"></a><span data-ttu-id="03a95-104">メッセージを修復するには</span><span class="sxs-lookup"><span data-stu-id="03a95-104">To repair a message</span></span>  
  
1.  <span data-ttu-id="03a95-105">Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="03a95-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="03a95-106">[ホーム] ウィンドウ**ドキュメント**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-106">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="03a95-107">ドキュメント ウィンドウで **ドキュメント ライブラリ**をクリックして  **\<*部門名*\>**_*** * 修理会社。</span><span class="sxs-lookup"><span data-stu-id="03a95-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>**_**Repairer**.</span></span>  
  
4.  <span data-ttu-id="03a95-108">\<*部門名*\>_Repair ウィンドウで、をクリックして**受信トレイ**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-108">In the \<*Department name*\>_Repair window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="03a95-109">受信トレイ ウィンドウで、メッセージのタイトルにポイント メッセージのタイトルの右側にある矢印をクリックし、をクリックして**Microsoft Office InfoPath で編集**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="03a95-110">SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、いることを確認**エラー**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="03a95-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, ensure that **Errors** is selected.</span></span> <span data-ttu-id="03a95-111">示すように、エラーを確認して、**解析と XML 検証エラー**、 **BRE 妥当性確認エラー**、および**ランタイム エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="03a95-111">Review any errors shown in the **Parse and XML Validation Errors**, **BRE Validation Errors**, and **Runtime Errors** boxes.</span></span>  
  
7.  <span data-ttu-id="03a95-112">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、エラーの場所にスクロールし、エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="03a95-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error, and correct the error.</span></span> <span data-ttu-id="03a95-113">XML 検証エラーがある場合、エラーは赤色で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a95-113">If it is an XML validation error, the error will be highlighted in red.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-114">BRE の妥当性確認エラーが赤色で強調表示されませんが、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="03a95-114">BRE validation errors will not be highlighted in red in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="03a95-115">BRE の検証エラーの詳細については、次を参照してください。 [SWIFT エラーコード](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)です。</span><span class="sxs-lookup"><span data-stu-id="03a95-115">For more information about BRE validation errors, see [SWIFT Error Codes](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-116">ドロップダウン リストが関連付けられているフィールドにエラーが発生する場合、エラーの原因となった元の値を表示することができなきます。</span><span class="sxs-lookup"><span data-stu-id="03a95-116">If the error occurs in a field that is accompanied by a drop-down list, you will not be able to see the original value that caused the error.</span></span> <span data-ttu-id="03a95-117">フィールドが表示されます"Select"元の値の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="03a95-117">The field will display "Select" instead of the original value.</span></span> <span data-ttu-id="03a95-118">ドロップダウン リストから適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="03a95-118">Select the appropriate value from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="03a95-119">メッセージを検証するためには、をクリックして**検証**、現在のロールで: ウィンドウを修復し、をクリックして**検証メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-119">To ensure that the message will validate, click **Validation** in the Current Role: Repair pane, and then click **Validate Message**.</span></span> <span data-ttu-id="03a95-120">結果ペインが表示されることを確認**メッセージが有効では**します。</span><span class="sxs-lookup"><span data-stu-id="03a95-120">Verify that the Results pane displays **The message is valid**.</span></span>  
  
9. <span data-ttu-id="03a95-121">[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-121">In the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-122">クリックすると、**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="03a95-122">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="03a95-123">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03a95-123">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  
  
10. <span data-ttu-id="03a95-124">[Submit Message] ダイアログ ボックスで、 **Accept**変更が受け入れで修復されたメッセージを送信するには、クリックして**拒否**をクリックする、変更を拒否するか**キャンセル**をキャンセルするには送信と、フォームに戻る。</span><span class="sxs-lookup"><span data-stu-id="03a95-124">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-125">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="03a95-125">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-126">修復段階でメッセージの変更を却下した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを MessageBox にルーティングし、イベント ビューアーを読み取るエラーへのポスト「でしたにリセットしないワークフローの最初のステージ。」です。</span><span class="sxs-lookup"><span data-stu-id="03a95-126">If you reject the message changes in the repair stage, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the MessageBox, and posts to the Event Viewer an error that reads "Could not reset to the first stage in the workflow.".</span></span>  
  
11. <span data-ttu-id="03a95-127">クリックした場合は**Accept**または**拒否**手順 10 では、上、**デジタル署名ウィザード** ページで、フォームの署名に使用する証明書を選択 (証明書を修理会社用) を作成し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-127">If you clicked **Accept** or **Reject** in step 10, on the **Digital Signature Wizard** page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03a95-128">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.</span><span class="sxs-lookup"><span data-stu-id="03a95-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
12. <span data-ttu-id="03a95-129">デジタル署名のウィザード ページで、コメントを入力するためには、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-129">On the Digital Signature Wizard page for entering a comment, click **Finish**.</span></span>  
  
13. <span data-ttu-id="03a95-130">デジタル署名ウィザードのページで、フォームを検証するため、メッセージ署名して、署名が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="03a95-130">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing and your signature are correct.</span></span> <span data-ttu-id="03a95-131">をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-131">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
14. <span data-ttu-id="03a95-132">デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-132">In the Verify Digital Signature window, click **Close**.</span></span>  
  
15. <span data-ttu-id="03a95-133">[送信の成功] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-133">In the Submission Success dialog box, click **OK**.</span></span>  
  
16. <span data-ttu-id="03a95-134">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="03a95-134">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  
  
17. <span data-ttu-id="03a95-135">サイトの MRSR クリックして**ドキュメント**です。</span><span class="sxs-lookup"><span data-stu-id="03a95-135">In MRSR site, click **Documents**.</span></span> <span data-ttu-id="03a95-136">クリックした場合は**Accept**手順 11 で変更を受け入れるようにいることを確認、 *\<部門名\>*_ReKeyVerify ドキュメント ライブラリには、修復するメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03a95-136">If you clicked **Accept** to accept the changes in step 11, verify that the *\<Department name\>*_ReKeyVerify document library contains the message that you just repaired.</span></span> <span data-ttu-id="03a95-137">クリックした場合は**拒否**手順 11 で変更を拒否する A4SWIFT_Outbox ドキュメント ライブラリに変更が、メッセージが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="03a95-137">If you clicked **Reject** to reject the changes in step 11, verify that the A4SWIFT_Outbox document library contains the message that was just modified.</span></span>