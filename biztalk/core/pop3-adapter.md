---
title: POP3 アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbe21a3cf0e611a690cf22c88b1344926fa72744
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264554"
---
# <a name="pop3-adapter"></a><span data-ttu-id="5fa26-102">POP3 アダプタ</span><span class="sxs-lookup"><span data-stu-id="5fa26-102">POP3 Adapter</span></span>
<span data-ttu-id="5fa26-103">Post Office Protocol 3 (POP3) アダプタを使用すると、POP3 メールボックスのあるサーバーから、Microsoft BizTalk Server を実行しているサーバーに、POP3 プロトコル経由でデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5fa26-103">You use the Post Office Protocol 3 (POP3) adapter to retrieve data from a server that houses POP3 mailboxes into a server running Microsoft BizTalk Server by means of the POP3 protocol.</span></span>  
  
 <span data-ttu-id="5fa26-104">POP3 アダプタは、1 つの受信アダプタのみで構成されています。</span><span class="sxs-lookup"><span data-stu-id="5fa26-104">The POP3 adapter consists of only one adapter, a receive adapter.</span></span> <span data-ttu-id="5fa26-105">受信アダプタでは、POP3 アダプタを使用する受信場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-105">The receive adapter controls the receive locations that use the POP3 adapter.</span></span>  
  
 <span data-ttu-id="5fa26-106">このトピックでは、POP3 受信アダプタのワークフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-106">This topic discusses the workflow of the POP3 receive adapter.</span></span>  
  
 <span data-ttu-id="5fa26-107">**POP3 受信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="5fa26-107">**POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="5fa26-108">POP3 受信アダプタは、指定した POP3 サーバー上の特定のメールボックスから電子メールを取得します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-108">The POP3 receive adapter retrieves e-mail from a specified mailbox on a specified POP3 server.</span></span> <span data-ttu-id="5fa26-109">既定では、ダウンロードする電子メール メッセージに MIME 処理を適用し、これらのメッセージをマルチパート BizTalk メッセージとして BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-109">By default, the POP3 receive adapter applies MIME processing to the e-mail messages that it downloads and submits these messages to BizTalk Server as multipart BizTalk messages.</span></span> <span data-ttu-id="5fa26-110">POP3 受信アダプタは、次の形式の電子メールを受信および処理できます。</span><span class="sxs-lookup"><span data-stu-id="5fa26-110">The POP3 receive adapter can receive and process e-mail in the following formats:</span></span>  
  
-   <span data-ttu-id="5fa26-111">プレーンテキスト</span><span class="sxs-lookup"><span data-stu-id="5fa26-111">Plain text</span></span>  
  
-   <span data-ttu-id="5fa26-112">MIME エンコード</span><span class="sxs-lookup"><span data-stu-id="5fa26-112">MIME encoded</span></span>  
  
-   <span data-ttu-id="5fa26-113">MIME 暗号化</span><span class="sxs-lookup"><span data-stu-id="5fa26-113">MIME encrypted</span></span>  
  
-   <span data-ttu-id="5fa26-114">MIME エンコードおよび署名</span><span class="sxs-lookup"><span data-stu-id="5fa26-114">MIME encoded and signed</span></span>  
  
-   <span data-ttu-id="5fa26-115">MIME 暗号化および署名</span><span class="sxs-lookup"><span data-stu-id="5fa26-115">MIME encrypted and signed</span></span>  
  
 <span data-ttu-id="5fa26-116">**バッチ処理の POP3 受信アダプタのサポート**</span><span class="sxs-lookup"><span data-stu-id="5fa26-116">**Batching Support for the POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="5fa26-117">POP3 受信アダプタは、バッチ処理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5fa26-117">The POP3 receive adapter does not support batching.</span></span>  
  
 <span data-ttu-id="5fa26-118">**POP3 サーバーでの認証**</span><span class="sxs-lookup"><span data-stu-id="5fa26-118">**Authentication with POP3 Server**</span></span>  
  
 <span data-ttu-id="5fa26-119">POP3 アダプタでは、次の認証方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5fa26-119">The following authentication methods are supported for use with the POP3 adapter:</span></span>  
  
-   <span data-ttu-id="5fa26-120">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="5fa26-120">**Basic.**</span></span> <span data-ttu-id="5fa26-121">POP3 サーバーでは、ユーザー認証のための資格情報の指定を使用します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-121">The POP3 server uses user provided credentials for authentication.</span></span>  <span data-ttu-id="5fa26-122">これらの資格情報はクリア テキストで送信されます。</span><span class="sxs-lookup"><span data-stu-id="5fa26-122">These credentials are sent in clear text.</span></span>  
  
-   <span data-ttu-id="5fa26-123">**ダイジェスト (APOP)。**</span><span class="sxs-lookup"><span data-stu-id="5fa26-123">**Digest (APOP).**</span></span> <span data-ttu-id="5fa26-124">: ダイジェスト文字列を使用して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="5fa26-124">The POP3 server uses a digest string for authentication.</span></span>  
  
-   <span data-ttu-id="5fa26-125">**セキュリティで保護されたパスワード認証 (SPA)。**</span><span class="sxs-lookup"><span data-stu-id="5fa26-125">**Secure Password Authentication (SPA).**</span></span> <span data-ttu-id="5fa26-126">: 現在のプロセスの資格情報を使用して認証を行います。</span><span class="sxs-lookup"><span data-stu-id="5fa26-126">The POP3 server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fa26-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5fa26-127">In This Section</span></span>  
  
-   [<span data-ttu-id="5fa26-128">POP3 アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5fa26-128">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5fa26-129">POP3 アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="5fa26-129">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5fa26-130">チュートリアル: POP3 アダプターを使用する BizTalk アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="5fa26-130">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5fa26-131">POP3 アダプタでのマルチパート メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="5fa26-131">Processing Multi Part Messages with the POP3 Adapter</span></span>](../core/processing-multi-part-messages-with-the-pop3-adapter.md)