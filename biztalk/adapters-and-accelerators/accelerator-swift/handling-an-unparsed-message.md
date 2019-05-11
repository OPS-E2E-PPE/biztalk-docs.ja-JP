---
title: 未解析メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77478326c3f2f457c5b88b4234d8087ec512215b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377501"
---
# <a name="handling-an-unparsed-message"></a><span data-ttu-id="22256-102">未解析メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="22256-102">Handling an Unparsed Message</span></span>
<span data-ttu-id="22256-103">このセクションでは、未解析のメッセージを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22256-103">This section describes how to handle an unparsed message.</span></span> <span data-ttu-id="22256-104">検証に失敗したメッセージとは異なり、メッセージを修復することはできませんを[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]を解析できません。</span><span class="sxs-lookup"><span data-stu-id="22256-104">Unlike messages that fail validation, you cannot repair a message that [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cannot parse.</span></span> <span data-ttu-id="22256-105">Message Repair and New Submission は、メッセージと、解析エラーの性質を表示し、メッセージを印刷したり、ローカル ファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="22256-105">Message Repair and New Submission displays the message and the nature of the parsing error, and enables you to print the message or save it to a local file.</span></span> <span data-ttu-id="22256-106">エンティティは解析エラーの特定の性質にメッセージを送信し、通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="22256-106">You can then alert the entity that sent the message to the specific nature of the parsing failure.</span></span>  

### <a name="to-handle-an-unparsed-message"></a><span data-ttu-id="22256-107">未解析メッセージを処理するには</span><span class="sxs-lookup"><span data-stu-id="22256-107">To handle an unparsed message</span></span>  

1. <span data-ttu-id="22256-108">Internet Explorer で、開く、MRSR サイトが http://localhost/sites/bassite します。</span><span class="sxs-lookup"><span data-stu-id="22256-108">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="22256-109">[ホーム] ウィンドウ**ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="22256-109">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="22256-110">ドキュメント ウィンドウで [**ドキュメント ライブラリ**、] をクリックして**Unparsed**します。</span><span class="sxs-lookup"><span data-stu-id="22256-110">In the Documents window, under **Document Libraries**, click **Unparsed**.</span></span>  

4. <span data-ttu-id="22256-111">未解析のウィンドウでは、次のようにクリックします。**受信トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="22256-111">In the Unparsed window, click **Inbox**.</span></span>  

5. <span data-ttu-id="22256-112">未解析の受信トレイ] ウィンドウで、メッセージをポイントして、でしたいない解析、メッセージの右側にある矢印をクリックし、[ **Microsoft Office InfoPath で編集**します。</span><span class="sxs-lookup"><span data-stu-id="22256-112">In the Unparsed Inbox window, point to the message that did not parse, click the arrow to the right of the message, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="22256-113">SWIFT アクセラレータ ウィンドウで次のようにクリックします。**エラー**します。</span><span class="sxs-lookup"><span data-stu-id="22256-113">In the SWIFT Accelerator pane, click **Errors**.</span></span>  

7. <span data-ttu-id="22256-114">解析と XML の検証エラー ウィンドウで、解析エラーを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="22256-114">In the Parse and XML Validation Errors pane, read the parse error.</span></span>  

8. <span data-ttu-id="22256-115">未解析メッセージのウィンドウで、メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="22256-115">In the Unparsed Message pane, review the message.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="22256-116">未解析メッセージのウィンドウで、メッセージを印刷する場合、**ファイル** メニューのをクリックして**印刷**します。</span><span class="sxs-lookup"><span data-stu-id="22256-116">If you want to print the message, in the Unparsed Message pane, on the **File** menu, click **Print**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="22256-117">未解析メッセージのウィンドウで、ローカル ファイルにメッセージを保存する場合、**ファイル** メニューのをクリックして**名前を付けて保存**します。</span><span class="sxs-lookup"><span data-stu-id="22256-117">If you want to save the message to a local file, in the Unparsed Message pane, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="22256-118">**名前を付けて保存** ダイアログ ボックスで、**で保存**ドロップダウン リストをクリックして、ファイルを保存するフォルダーに移動**OK**します。</span><span class="sxs-lookup"><span data-stu-id="22256-118">In the **Save As** dialog box, in the **Save in** drop-down list, move to the folder that you want to save the file in, and then click **OK**.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="22256-119">XML 形式でメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="22256-119">saves the message in XML format.</span></span>  

9. <span data-ttu-id="22256-120">未解析メッセージのウィンドウで、必要に応じて変更し、**送信**します。</span><span class="sxs-lookup"><span data-stu-id="22256-120">In the Unparsed Message pane, make the necessary changes, and then click **Submit**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="22256-121">修復が未解析メッセージを検証することはできません。</span><span class="sxs-lookup"><span data-stu-id="22256-121">You cannot validate an unparsed message that you have repaired.</span></span>  

10. <span data-ttu-id="22256-122">Submit Message ダイアログ ボックスで、 **Accept**を受け入れられる変更では修復されたメッセージを送信する をクリックして**拒否**、変更を拒否またはをクリックする**キャンセル**をキャンセルするには送信と、フォームに戻ります。</span><span class="sxs-lookup"><span data-stu-id="22256-122">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  

11. <span data-ttu-id="22256-123">クリックした場合は**Accept**または**拒否**デジタル署名ウィザード ページで、手順 11 では、フォーム (修理会社用に作成した書) の署名に使用する証明書を選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="22256-123">If you clicked **Accept** or **Reject** in step 11, on the Digital Signature Wizard page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="22256-124">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認して、クリックする をクリックして**サインイン フォームの表示**.</span><span class="sxs-lookup"><span data-stu-id="22256-124">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="22256-125">任意のロールを実行するすべてのユーザーには、それを修復が未解析のメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="22256-125">Any user performing any role can submit an unparsed message that they have repaired.</span></span>  

12. <span data-ttu-id="22256-126">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="22256-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

13. <span data-ttu-id="22256-127">デジタル署名のウィザード ページで、フォームを検証するためには、上に署名するメッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="22256-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="22256-128">クリックして**証明書の表示**は正しいシグネチャを使用していることを確認したい場合。</span><span class="sxs-lookup"><span data-stu-id="22256-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="22256-129">クリックして**署名する前にこのコンテンツを確認した**、順にクリックします**サインオン**します。</span><span class="sxs-lookup"><span data-stu-id="22256-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="22256-130">デジタル署名の確認 ウィンドウで、次のようにクリックします。**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="22256-130">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="22256-131">[送信の成功] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="22256-131">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="22256-132">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="22256-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>
