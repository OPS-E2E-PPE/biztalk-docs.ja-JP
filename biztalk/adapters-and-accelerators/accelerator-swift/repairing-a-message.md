---
title: メッセージの修復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9edb8f9cc3c5db67e75ff47125e0d58891a5173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992043"
---
# <a name="repairing-a-message"></a><span data-ttu-id="ee244-102">メッセージの修復</span><span class="sxs-lookup"><span data-stu-id="ee244-102">Repairing a Message</span></span>
<span data-ttu-id="ee244-103">このセクションでは、検証が失敗したメッセージを修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee244-103">This section describes how to repair a message that has failed validation.</span></span>  

### <a name="to-repair-a-message"></a><span data-ttu-id="ee244-104">メッセージを修復するには</span><span class="sxs-lookup"><span data-stu-id="ee244-104">To repair a message</span></span>  

1. <span data-ttu-id="ee244-105">Internet Explorer で、開く、MRSR サイトがhttp://localhost/sites/bassiteします。</span><span class="sxs-lookup"><span data-stu-id="ee244-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="ee244-106">[ホーム] ウィンドウ**ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="ee244-107">ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして **\<*部門名*\>**_**修理会社**.</span><span class="sxs-lookup"><span data-stu-id="ee244-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>**_**Repairer**.</span></span>  

4. <span data-ttu-id="ee244-108">\<*部門名*\>_Repair ウィンドウで、をクリックして**受信トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-108">In the \<*Department name*\>_Repair window, click **Inbox**.</span></span>  

5. <span data-ttu-id="ee244-109">受信トレイ ウィンドウで、メッセージのタイトルをポイントし、メッセージのタイトルの右側にある矢印をクリックします。 をクリック**Microsoft Office InfoPath で編集**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="ee244-110">SWIFT アクセラレータのウィンドウで、 [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、いることを確認**エラー**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ee244-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, ensure that **Errors** is selected.</span></span> <span data-ttu-id="ee244-111">示すように、エラーを確認、**解析と XML の検証エラー**、 **BRE 検証エラー**、および**ランタイム エラー**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ee244-111">Review any errors shown in the **Parse and XML Validation Errors**, **BRE Validation Errors**, and **Runtime Errors** boxes.</span></span>  

7. <span data-ttu-id="ee244-112">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、エラーの場所にスクロールし、エラーを修正します。</span><span class="sxs-lookup"><span data-stu-id="ee244-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error, and correct the error.</span></span> <span data-ttu-id="ee244-113">XML 検証エラーは、エラーは赤で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee244-113">If it is an XML validation error, the error will be highlighted in red.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ee244-114">BRE の検証エラーが赤で強調表示されませんが、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。</span><span class="sxs-lookup"><span data-stu-id="ee244-114">BRE validation errors will not be highlighted in red in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="ee244-115">BRE の検証エラーに関する詳細については、次を参照してください。 [SWIFT エラー コード](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee244-115">For more information about BRE validation errors, see [SWIFT Error Codes](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ee244-116">ドロップダウン リストでは、関連付けられているフィールドに、エラーが発生した場合、エラーの原因となった元の値を表示することができなきます。</span><span class="sxs-lookup"><span data-stu-id="ee244-116">If the error occurs in a field that is accompanied by a drop-down list, you will not be able to see the original value that caused the error.</span></span> <span data-ttu-id="ee244-117">フィールドが表示されます"Select"元の値の代わりにします。</span><span class="sxs-lookup"><span data-stu-id="ee244-117">The field will display "Select" instead of the original value.</span></span> <span data-ttu-id="ee244-118">ドロップダウン リストから適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee244-118">Select the appropriate value from the drop-down list.</span></span>  

8. <span data-ttu-id="ee244-119">メッセージを検証するためには、次のようにクリックします。**検証**、現在のロール: ウィンドウを修復し、順にクリックします**検証メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-119">To ensure that the message will validate, click **Validation** in the Current Role: Repair pane, and then click **Validate Message**.</span></span> <span data-ttu-id="ee244-120">結果ペインが表示されることを確認 **、メッセージが有効な**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-120">Verify that the Results pane displays **The message is valid**.</span></span>  

9. <span data-ttu-id="ee244-121">[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、をクリックして**送信**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-121">In the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ee244-122">クリックすると**送信**、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]メッセージで XML 検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee244-122">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="ee244-123">検証が成功しなかった場合は、続行する前に検証エラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee244-123">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="ee244-124">Submit Message ダイアログ ボックスで、 **Accept**を受け入れられる変更では修復されたメッセージを送信する をクリックして**拒否**、変更を拒否またはをクリックする**キャンセル**をキャンセルするには送信と、フォームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="ee244-124">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ee244-125">メッセージの変更を受け入れる場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ BRE 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="ee244-125">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="ee244-126">修復段階でメッセージの変更を拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを MessageBox にルーティングし、イベント ビューアーを読み取るエラーへの投稿「をリセットできませんでした、ワークフローの最初のステージを。」です。</span><span class="sxs-lookup"><span data-stu-id="ee244-126">If you reject the message changes in the repair stage, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the MessageBox, and posts to the Event Viewer an error that reads "Could not reset to the first stage in the workflow.".</span></span>  

11. <span data-ttu-id="ee244-127">クリックした場合**Accept**または**拒否**に手順 10 で、**デジタル署名ウィザード**ページで、フォームの署名に使用する証明書を選択します (証明書を用に作成、修理会社)、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-127">If you clicked **Accept** or **Reject** in step 10, on the **Digital Signature Wizard** page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ee244-128">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.</span><span class="sxs-lookup"><span data-stu-id="ee244-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  

12. <span data-ttu-id="ee244-129">デジタル署名のウィザード ページで、コメントを入力するためには、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-129">On the Digital Signature Wizard page for entering a comment, click **Finish**.</span></span>  

13. <span data-ttu-id="ee244-130">デジタル署名ウィザード ページで、フォームを検証するため、メッセージに署名して、署名が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee244-130">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing and your signature are correct.</span></span> <span data-ttu-id="ee244-131">クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-131">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="ee244-132">デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-132">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="ee244-133">[送信の成功] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-133">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="ee244-134">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="ee244-134">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="ee244-135">サイトの MRSR クリックして**ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="ee244-135">In MRSR site, click **Documents**.</span></span> <span data-ttu-id="ee244-136">クリックした場合**Accept**手順 11 で変更を許可することを確認、 *\<部門名\>*_ReKeyVerify ドキュメント ライブラリには、修復したメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee244-136">If you clicked **Accept** to accept the changes in step 11, verify that the *\<Department name\>*_ReKeyVerify document library contains the message that you just repaired.</span></span> <span data-ttu-id="ee244-137">クリックした場合は**拒否**手順 11 で変更を却下する A4SWIFT_Outbox ドキュメント ライブラリに変更されたメッセージが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee244-137">If you clicked **Reject** to reject the changes in step 11, verify that the A4SWIFT_Outbox document library contains the message that was just modified.</span></span>
