---
title: SMTP アダプター |Microsoft ドキュメント
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
ms.openlocfilehash: c0d0d16bf266d0b636aa9955b5c25b37d9ab54d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277602"
---
# <a name="smtp-adapter"></a><span data-ttu-id="47a92-102">SMTP アダプター</span><span class="sxs-lookup"><span data-stu-id="47a92-102">SMTP Adapter</span></span>
<span data-ttu-id="47a92-103">簡易メール転送プロトコル (SMTP) アダプタは、Microsoft BizTalk Server を実行しているサーバーと他のアプリケーション間で SMTP を介して情報を交換するために使用します。</span><span class="sxs-lookup"><span data-stu-id="47a92-103">You use the Simple Mail Transfer Protocol (SMTP) adapter to exchange information between a server running Microsoft BizTalk Server and other applications by means of the SMTP protocol.</span></span> <span data-ttu-id="47a92-104">BizTalk Server から他のアプリケーションにメッセージを送信するには、電子メール メッセージを作成し、指定した電子メール アドレスに配信します。</span><span class="sxs-lookup"><span data-stu-id="47a92-104">BizTalk Server can send messages to other applications by creating an e-mail message and delivering it to a specified e-mail address.</span></span> <span data-ttu-id="47a92-105">内部的には、SMTP 送信アダプタで SMTP ベースの電子メール メッセージを作成し、送信先の電子メール アドレスに送信します。</span><span class="sxs-lookup"><span data-stu-id="47a92-105">Internally, the SMTP send adapter creates an SMTP-based e-mail message and sends it to a target e-mail address.</span></span> <span data-ttu-id="47a92-106">送信先電子メール アドレスは、SMTP アダプタのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="47a92-106">The target e-mail address is a property of the SMTP adapter.</span></span> <span data-ttu-id="47a92-107">このプロパティは、SMTP 送信ポートを構成するとき、BizTalk エクスプローラに表示されます。</span><span class="sxs-lookup"><span data-stu-id="47a92-107">BizTalk Explorer exposes this property when you configure the SMTP send port.</span></span>  
  
 <span data-ttu-id="47a92-108">SMTP アダプターでのワイルドカード文字をサポートしている、**に**、 **FROM**、 **CC**と**サブジェクト**プロパティ、し、実際に解決します。値。</span><span class="sxs-lookup"><span data-stu-id="47a92-108">The SMTP adapter supports wildcard characters in the **TO**, **FROM**, **CC** and **SUBJECT** properties, and resolves them to their actual values.</span></span> <span data-ttu-id="47a92-109">ワイルドカード文字は、場合、 **TO**、 **FROM**、および**CC**プロパティを解決することはできません、SMTP トランスポートのエラーが記録され、メッセージを保留キューに配置またはバックアップ トランスポートにメッセージをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="47a92-109">If wildcard characters in the **TO**, **FROM**, and **CC** properties cannot be resolved, the SMTP transport logs an error and puts the message into the suspended queue or redirects the message to the backup transport.</span></span> <span data-ttu-id="47a92-110">ワイルドカード文字を解決できない場合、**サブジェクト**プロパティでメッセージの送信、**サブジェクト**プロパティ (たとえば、「メッセージ MessageID %」) のように正確に指定されたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="47a92-110">If the wildcard characters cannot be resolved in the **SUBJECT** property, the message is sent with the **SUBJECT** property specified exactly as in the property (for example, "Message %MessageID%").</span></span>  
  
 <span data-ttu-id="47a92-111">既定では、SMTP メッセージのメッセージ テキストはプレーンテキストです。</span><span class="sxs-lookup"><span data-stu-id="47a92-111">By default, the message text of SMTP messages is plain text.</span></span> <span data-ttu-id="47a92-112">メッセージ本文で HTML を使用するために、メッセージ テキストに HTML ファイルの内容を使用するようアダプタを構成できます。</span><span class="sxs-lookup"><span data-stu-id="47a92-112">To use HTML in message bodies, you can configure the adapter to use the contents of an HTML file for the message text.</span></span>  
  
 <span data-ttu-id="47a92-113">SMTP のセキュリティの問題に関する詳細については、次を参照してください。 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)です。</span><span class="sxs-lookup"><span data-stu-id="47a92-113">For more information about SMTP security issues, see [SMTP Adapter Security Recommendations](../core/smtp-adapter-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="47a92-114">SMTP アダプタは、1 つの送信アダプタのみで構成されています。</span><span class="sxs-lookup"><span data-stu-id="47a92-114">The SMTP adapter consists of only one adapter, a send adapter.</span></span> <span data-ttu-id="47a92-115">SMTP 送信アダプタでは、SMTP アダプタを使用する送信ポートを制御します。</span><span class="sxs-lookup"><span data-stu-id="47a92-115">The send adapter controls the send ports that use the SMTP adapter.</span></span>  
  
 <span data-ttu-id="47a92-116">このトピックでは、SMTP 送信アダプタを通過するメッセージ フローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="47a92-116">This topic discusses the flow of a message through the SMTP send adapter.</span></span>  
  
 <span data-ttu-id="47a92-117">**SMTP 送信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="47a92-117">**SMTP Send Adapter**</span></span>  
  
 <span data-ttu-id="47a92-118">SMTP 送信アダプタは、サーバーからメッセージを取得して、電子メール受信者に送信するための SMTP サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="47a92-118">The SMTP send adapter gets messages from the server and posts them to an SMTP server that sends them to e-mail recipients.</span></span> <span data-ttu-id="47a92-119">SMTP 送信アダプタで取得するメッセージの内容の取得元は、BizTalk メッセージ オブジェクトのボディ部、指定したファイル、またはアダプタ構成時に表示されるダイアログ ボックスに入力したテキストです。</span><span class="sxs-lookup"><span data-stu-id="47a92-119">The SMTP send adapter gets the message content from the body part of the BizTalk Message object, from a specified file, or from a text entered into a dialog box that is available when configuring the adapter.</span></span>  
  
 <span data-ttu-id="47a92-120">SMTP サーバーに正常にメッセージが送信されると、メッセージ ボックス データベースからメッセージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="47a92-120">After the SMTP send adapter successfully posts a message onto the SMTP server, the SMTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="47a92-121">SMTP 送信アダプタ経由で送信するメッセージについては、配信通知および開封確認メッセージを要求できます。</span><span class="sxs-lookup"><span data-stu-id="47a92-121">The SMTP send adapter can request delivery notification and read receipts for messages sent over the SMTP send adapter.</span></span> <span data-ttu-id="47a92-122">SMTP アダプターは、SMTP で指定したアドレスに、通知および配信確認メッセージを配信**から**ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="47a92-122">The SMTP adapter delivers the notification and read receipt to the address specified on the SMTP **From** header.</span></span>  
  
 <span data-ttu-id="47a92-123">**SMTP サーバーでの認証**</span><span class="sxs-lookup"><span data-stu-id="47a92-123">**Authentication with SMTP Server**</span></span>  
  
 <span data-ttu-id="47a92-124">SMTP サーバーでの認証を要求した場合、SMTP 送信アダプタによって、以下のいずれかの認証の種類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="47a92-124">If you require SMTP server authentication, the SMTP send adapter uses one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="47a92-125">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="47a92-125">**Basic.**</span></span> <span data-ttu-id="47a92-126">: ユーザーが指定した資格情報を使用して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="47a92-126">The SMTP server uses user-provided credentials for authentication.</span></span>  
  
-   <span data-ttu-id="47a92-127">**プロセス アカウント (NTLM)。**</span><span class="sxs-lookup"><span data-stu-id="47a92-127">**Process account (NTLM).**</span></span> <span data-ttu-id="47a92-128">現在のプロセスの資格情報を使用して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="47a92-128">The SMTP server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47a92-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47a92-129">In This Section</span></span>  
  
-   [<span data-ttu-id="47a92-130">SMTP アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="47a92-130">Configuring the SMTP Adapter</span></span>](../core/configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="47a92-131">SMTP アダプタの構成時の制限事項</span><span class="sxs-lookup"><span data-stu-id="47a92-131">Restrictions When Configuring the SMTP Adapter</span></span>](../core/restrictions-when-configuring-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="47a92-132">SMTP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="47a92-132">SMTP Adapter Security Recommendations</span></span>](../core/smtp-adapter-security-recommendations.md)