---
title: 作成して、新しいメッセージを送信する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42cd2a82fe0ecde75446e68f9f58e17f103e5efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209866"
---
# <a name="creating-and-submitting-a-new-message"></a><span data-ttu-id="889f5-102">作成して、新しいメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="889f5-102">Creating and Submitting a New Message</span></span>
<span data-ttu-id="889f5-103">このセクションでは、新しいメッセージを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="889f5-103">This section describes how to submit a new message.</span></span> <span data-ttu-id="889f5-104">として修復されたメッセージを表示して、新しいメッセージ必要がある確認および承認されたメッセージの作成者は、他のユーザーによってです。</span><span class="sxs-lookup"><span data-stu-id="889f5-104">As with a repaired message, a new message must be verified and approved by people other than the message creator.</span></span>  
  
 <span data-ttu-id="889f5-105">新しいメッセージを送信するには、必要があります、新しい SWIFT メッセージ ドキュメント ライブラリに、メッセージ テンプレート ファイルをアップロードする送信するメッセージの種類。</span><span class="sxs-lookup"><span data-stu-id="889f5-105">To submit a new message, you must upload into the New SWIFT Messages document library a message template file for the type of message that you want to submit.</span></span> <span data-ttu-id="889f5-106">1 つのメッセージ テンプレートを手動でアップロードすることができますか FormPublish ツールを使用してすべてのメッセージのテンプレートをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="889f5-106">You can upload a single message template manually, or you can upload all message templates using the FormPublish tool.</span></span>  
  
### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a><span data-ttu-id="889f5-107">新しいドキュメント ライブラリに 1 つのメッセージのテンプレートをアップロードするには</span><span class="sxs-lookup"><span data-stu-id="889f5-107">To upload a single message template into the new document library</span></span>  
  
1.  <span data-ttu-id="889f5-108">セクションを参照してください[フォーム ジェネレーター ユーティリティ MT/MX InfoPath フォームの生成に](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md)手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="889f5-108">Refer to the section [Form Generator Utility to Generate MT/MX InfoPath Forms](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md) for instructions.</span></span>  
  
### <a name="to-create-and-submit-a-new-message"></a><span data-ttu-id="889f5-109">作成して、新しいメッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="889f5-109">To create and submit a new message</span></span>  
  
1.  <span data-ttu-id="889f5-110">Internet Explorer で、http://localhost/sites/bassite で MRSR サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="889f5-110">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="889f5-111">をクリックして**ドキュメント**、クリックして**新しい SWIFT メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-111">Click **Documents**, and then click **New SWIFT Messages**.</span></span>  
  
3.  <span data-ttu-id="889f5-112">新しい SWIFT メッセージ ページで、作成するには、メッセージの種類を表すカテゴリの名前をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="889f5-112">On the New SWIFT Messages page, double-click the name of the category containing the type of the message that you would like to create.</span></span>  
  
4.  <span data-ttu-id="889f5-113">作成するメッセージのフォーム テンプレートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="889f5-113">Click the form template for the message that you want to create.</span></span>  
  
5.  <span data-ttu-id="889f5-114">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年 ウィンドウのメッセージで、フォームの型メッセージとデータをすべての必須フィールド (アスタリスクで表します) として使用する省略可能なフィールドです。</span><span class="sxs-lookup"><span data-stu-id="889f5-114">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, in the message form, type message data for all required fields (as denoted by an asterisk) and any optional fields you want to use.</span></span>  
  
6.  <span data-ttu-id="889f5-115">現在の役割で、BIC を検索する: ウィンドウの作成 をクリックして**BIC 参照**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-115">To look up a BIC, in the Current Role: Create pane, click **BIC Lookup**.</span></span>  
  
7.  <span data-ttu-id="889f5-116">金融機関、銀行コードと国/地域の名前を入力し、クリックして**検索**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-116">Type the name of the financial institution, the bank code, and the country/region, and then click **Search**.</span></span>  
  
8.  <span data-ttu-id="889f5-117">BIC 参照ペインからは、メッセージ形式で、適切な銀行コード フィールドに、BIC をコピーします。</span><span class="sxs-lookup"><span data-stu-id="889f5-117">From the BIC Lookup pane, copy the BIC into the appropriate bank code field in the message form.</span></span>  
  
9. <span data-ttu-id="889f5-118">現在のロールで: ウィンドウの作成 をクリックして**検証**、順にクリック**検証メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-118">In the Current Role: Create pane, click **Validation**, and then click **Validate Message**.</span></span>  
  
10. <span data-ttu-id="889f5-119">結果ウィンドウで、現在のロールの: ウィンドウを作成、メッセージを修正する必要のあるエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="889f5-119">In the Results pane of the Current Role: Create pane, determine the errors that you need to fix in the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="889f5-120">メッセージのすべての検証エラーを修正した場合にのみ、新しいメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="889f5-120">You can only submit a new message if you have fixed all validation errors in the message.</span></span>  
  
11. <span data-ttu-id="889f5-121">ウィンドウの上部にある [標準] ツールバーからをクリックして**送信**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-121">From the Standard toolbar at the top of the window, click **Submit**.</span></span>  
  
12. <span data-ttu-id="889f5-122">デジタル署名ウィザードのページでフォームに署名する証明書を選択するため、フォーム (証明書の作成者は、作成した) の署名に使用する証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="889f5-122">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the creator).</span></span> <span data-ttu-id="889f5-123">をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。</span><span class="sxs-lookup"><span data-stu-id="889f5-123">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="889f5-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="889f5-124">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="889f5-125">デジタル署名の有効性を確認する をクリックして**デジタル署名**上、**ツール** メニューの デジタル署名を確認し、をクリックする をクリックして**ビュー署名済みフォーム**.</span><span class="sxs-lookup"><span data-stu-id="889f5-125">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
13. <span data-ttu-id="889f5-126">デジタル署名のウィザード ページでコメントを入力するためには、をクリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
14. <span data-ttu-id="889f5-127">デジタル署名ウィザードのページで、フォームを検証するため、署名は、メッセージが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="889f5-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="889f5-128">をクリックして**証明書の表示**正しいシグネチャを使用していることを確認する場合。</span><span class="sxs-lookup"><span data-stu-id="889f5-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="889f5-129">をクリックして**署名する前にこのコンテンツを確認した**をクリックし、**記号**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
15. <span data-ttu-id="889f5-130">デジタル署名の確認 ウィンドウで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-130">In the Verify Digital Signature window, click **Close**.</span></span>  
  
16. <span data-ttu-id="889f5-131">[送信の成功] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="889f5-131">In the Submission Success dialog box, click **OK**.</span></span>  
  
17. <span data-ttu-id="889f5-132">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="889f5-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>