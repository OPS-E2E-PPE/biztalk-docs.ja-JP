---
title: SMTP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, about SMTP adapters
- SMTP adapters, authenticating
- send adapters, SMTP adapters
- authenticating, SMTP adapters
- SMTP adapters
- SMTP adapters, send adapters
ms.assetid: b712f76d-3ce4-4780-9627-951e5951bd8a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76d3451ab6eb6d9dc52538f5b1b9289e2cb99d7a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314496"
---
# <a name="smtp-adapter"></a><span data-ttu-id="78d55-102">SMTP アダプター</span><span class="sxs-lookup"><span data-stu-id="78d55-102">SMTP Adapter</span></span>
<span data-ttu-id="78d55-103">簡易メール転送プロトコル (SMTP) アダプターを使用して、SMTP プロトコルを使用して、Microsoft BizTalk Server と他のアプリケーションを実行するサーバーの間で情報を交換します。</span><span class="sxs-lookup"><span data-stu-id="78d55-103">You use the Simple Mail Transfer Protocol (SMTP) adapter to exchange information between a server running Microsoft BizTalk Server and other applications by means of the SMTP protocol.</span></span> <span data-ttu-id="78d55-104">BizTalk Server は、電子メール メッセージを作成し、指定した電子メール アドレスに配信して、他のアプリケーションにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="78d55-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="78d55-105">内部的には、SMTP 送信アダプターは、SMTP ベースの電子メール メッセージを作成し、対象の電子メール アドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="78d55-105">Internally, the SMTP send adapter creates an SMTP-based e-mail message and sends it to a target e-mail address.</span></span> <span data-ttu-id="78d55-106">ターゲットの電子メール アドレスは、SMTP アダプタのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="78d55-106">The target e-mail address is a property of the SMTP adapter.</span></span> <span data-ttu-id="78d55-107">BizTalk エクスプ ローラーは、SMTP 送信ポートを構成するときに、このプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="78d55-107">BizTalk Explorer exposes this property when you configure the SMTP send port.</span></span>  
  
 <span data-ttu-id="78d55-108">SMTP アダプターでワイルドカード文字をサポートしている、 **TO**、 **FROM**、 **CC**と**サブジェクト**プロパティを実際に解決されます値。</span><span class="sxs-lookup"><span data-stu-id="78d55-108">The SMTP adapter supports wildcard characters in the **TO**, **FROM**, **CC** and **SUBJECT** properties, and resolves them to their actual values.</span></span> <span data-ttu-id="78d55-109">ワイルドカード文字の場合、 **TO**、 **FROM**、および**CC**プロパティを解決することはできません、SMTP トランスポートのエラーが記録され、メッセージを保留キューに配置またはバックアップ トランスポートにメッセージをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="78d55-109">If wildcard characters in the **TO**, **FROM**, and **CC** properties cannot be resolved, the SMTP transport logs an error and puts the message into the suspended queue or redirects the message to the backup transport.</span></span> <span data-ttu-id="78d55-110">ワイルドカード文字を解決できない場合、**サブジェクト**プロパティ、メッセージが送信されると、**サブジェクト**プロパティ (たとえば、「メッセージ MessageID %」) のように正確に指定されたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="78d55-110">If the wildcard characters cannot be resolved in the **SUBJECT** property, the message is sent with the **SUBJECT** property specified exactly as in the property (for example, "Message %MessageID%").</span></span>  
  
 <span data-ttu-id="78d55-111">既定では、SMTP メッセージのメッセージ テキストはプレーン テキストです。</span><span class="sxs-lookup"><span data-stu-id="78d55-111">By default, the message text of SMTP messages is plain text.</span></span> <span data-ttu-id="78d55-112">メッセージ本文で HTML を使用するには、メッセージ テキストを HTML ファイルの内容を使用するアダプターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="78d55-112">To use HTML in message bodies, you can configure the adapter to use the contents of an HTML file for the message text.</span></span>  
  
 <span data-ttu-id="78d55-113">SMTP のセキュリティの問題に関する詳細については、次を参照してください。 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="78d55-113">For more information about SMTP security issues, see [SMTP Adapter Security Recommendations](../core/smtp-adapter-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="78d55-114">SMTP アダプタは、1 つだけアダプター、送信アダプターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="78d55-114">The SMTP adapter consists of only one adapter, a send adapter.</span></span> <span data-ttu-id="78d55-115">送信アダプターは、SMTP アダプタを使用する送信ポートを制御します。</span><span class="sxs-lookup"><span data-stu-id="78d55-115">The send adapter controls the send ports that use the SMTP adapter.</span></span>  
  
 <span data-ttu-id="78d55-116">このトピックでは、SMTP 送信アダプターを通過するメッセージのフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="78d55-116">This topic discusses the flow of a message through the SMTP send adapter.</span></span>  
  
 <span data-ttu-id="78d55-117">**SMTP 送信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="78d55-117">**SMTP Send Adapter**</span></span>  
  
 <span data-ttu-id="78d55-118">SMTP では、サーバーからアダプターを取得しますメッセージを送信し、電子メール受信者に送信する SMTP サーバーに投稿します。</span><span class="sxs-lookup"><span data-stu-id="78d55-118">The SMTP send adapter gets messages from the server and posts them to an SMTP server that sends them to e-mail recipients.</span></span> <span data-ttu-id="78d55-119">SMTP 送信 BizTalk メッセージ オブジェクトのボディ部、指定されたファイルまたはアダプターの構成時に表示されるダイアログ ボックスに入力したテキストに、メッセージの内容になるようにアダプターを取得します。</span><span class="sxs-lookup"><span data-stu-id="78d55-119">The SMTP send adapter gets the message content from the body part of the BizTalk Message object, from a specified file, or from a text entered into a dialog box that is available when configuring the adapter.</span></span>  
  
 <span data-ttu-id="78d55-120">SMTP 送信アダプターには、SMTP サーバーにメッセージを正常に投稿記事、後に、SMTP 送信アダプターはメッセージ ボックス データベースからメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="78d55-120">After the SMTP send adapter successfully posts a message onto the SMTP server, the SMTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="78d55-121">SMTP 送信アダプターでは、配信通知を要求でき、開封確認メッセージが SMTP 送信アダプター経由で送信することができます。</span><span class="sxs-lookup"><span data-stu-id="78d55-121">The SMTP send adapter can request delivery notification and read receipts for messages sent over the SMTP send adapter.</span></span> <span data-ttu-id="78d55-122">SMTP アダプターは、SMTP で指定したアドレスに通知と読み取り受信確認を配信**から**ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="78d55-122">The SMTP adapter delivers the notification and read receipt to the address specified on the SMTP **From** header.</span></span>  
  
 <span data-ttu-id="78d55-123">**SMTP サーバーでの認証**</span><span class="sxs-lookup"><span data-stu-id="78d55-123">**Authentication with SMTP Server**</span></span>  
  
 <span data-ttu-id="78d55-124">SMTP サーバー認証が必要な場合、SMTP 送信アダプタで使用認証の種類のいずれか。</span><span class="sxs-lookup"><span data-stu-id="78d55-124">If you require SMTP server authentication, the SMTP send adapter uses one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="78d55-125">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="78d55-125">**Basic.**</span></span> <span data-ttu-id="78d55-126">SMTP サーバーでは、ユーザーの資格情報を使用して認証。</span><span class="sxs-lookup"><span data-stu-id="78d55-126">The SMTP server uses user-provided credentials for authentication.</span></span>  
  
-   <span data-ttu-id="78d55-127">**プロセス アカウント (NTLM)。**</span><span class="sxs-lookup"><span data-stu-id="78d55-127">**Process account (NTLM).**</span></span> <span data-ttu-id="78d55-128">SMTP サーバーでは、現在のプロセスの資格情報を使用して認証。</span><span class="sxs-lookup"><span data-stu-id="78d55-128">The SMTP server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78d55-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="78d55-129">In This Section</span></span>  
  
-   [<span data-ttu-id="78d55-130">SMTP アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="78d55-130">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="78d55-131">SMTP アダプター構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="78d55-131">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="78d55-132">SMTP アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="78d55-132">SMTP Adapter Security Recommendations</span></span>](../core/smtp-adapter-security-recommendations.md)