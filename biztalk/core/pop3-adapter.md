---
title: POP3 アダプター |Microsoft Docs
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
ms.openlocfilehash: f1be3efdd18efa46213ffc9511bd4bd795a946bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394903"
---
# <a name="pop3-adapter"></a><span data-ttu-id="5d70a-102">POP3 アダプター</span><span class="sxs-lookup"><span data-stu-id="5d70a-102">POP3 Adapter</span></span>
<span data-ttu-id="5d70a-103">POP3 メールボックスの POP3 プロトコル経由の Microsoft BizTalk Server を実行するサーバーにあるサーバーからデータを取得するのにには、Post Office Protocol 3 (POP3) アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-103">You use the Post Office Protocol 3 (POP3) adapter to retrieve data from a server that houses POP3 mailboxes into a server running Microsoft BizTalk Server by means of the POP3 protocol.</span></span>  
  
 <span data-ttu-id="5d70a-104">POP3 アダプターは、1 つだけアダプター、受信アダプターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d70a-104">The POP3 adapter consists of only one adapter, a receive adapter.</span></span> <span data-ttu-id="5d70a-105">受信アダプターは、POP3 アダプターを使用する受信場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-105">The receive adapter controls the receive locations that use the POP3 adapter.</span></span>  
  
 <span data-ttu-id="5d70a-106">このトピックで、POP3 のワークフローを説明する受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="5d70a-106">This topic discusses the workflow of the POP3 receive adapter.</span></span>  
  
 <span data-ttu-id="5d70a-107">**POP3 受信アダプタ**</span><span class="sxs-lookup"><span data-stu-id="5d70a-107">**POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="5d70a-108">POP3 は、指定した POP3 サーバー上の指定したメールボックスからアダプターを取得しますの電子メールを受信します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-108">The POP3 receive adapter retrieves e-mail from a specified mailbox on a specified POP3 server.</span></span> <span data-ttu-id="5d70a-109">既定で、POP3 受信アダプターが MIME 処理をダウンロードし、これらのメッセージをマルチパート BizTalk メッセージとして BizTalk Server に送信する電子メール メッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5d70a-109">By default, the POP3 receive adapter applies MIME processing to the e-mail messages that it downloads and submits these messages to BizTalk Server as multipart BizTalk messages.</span></span> <span data-ttu-id="5d70a-110">POP3 受信アダプターが受信し、次の形式で電子メールを処理します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-110">The POP3 receive adapter can receive and process e-mail in the following formats:</span></span>  
  
- <span data-ttu-id="5d70a-111">プレーン テキスト</span><span class="sxs-lookup"><span data-stu-id="5d70a-111">Plain text</span></span>  
  
- <span data-ttu-id="5d70a-112">MIME エンコード</span><span class="sxs-lookup"><span data-stu-id="5d70a-112">MIME encoded</span></span>  
  
- <span data-ttu-id="5d70a-113">MIME 暗号化</span><span class="sxs-lookup"><span data-stu-id="5d70a-113">MIME encrypted</span></span>  
  
- <span data-ttu-id="5d70a-114">MIME エンコードおよび署名</span><span class="sxs-lookup"><span data-stu-id="5d70a-114">MIME encoded and signed</span></span>  
  
- <span data-ttu-id="5d70a-115">MIME 暗号化および署名</span><span class="sxs-lookup"><span data-stu-id="5d70a-115">MIME encrypted and signed</span></span>  
  
  <span data-ttu-id="5d70a-116">**バッチ処理の POP3 受信アダプタのサポート**</span><span class="sxs-lookup"><span data-stu-id="5d70a-116">**Batching Support for the POP3 Receive Adapter**</span></span>  
  
  <span data-ttu-id="5d70a-117">POP3 受信アダプターはバッチ処理をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5d70a-117">The POP3 receive adapter does not support batching.</span></span>  
  
  <span data-ttu-id="5d70a-118">**POP3 サーバーでの認証**</span><span class="sxs-lookup"><span data-stu-id="5d70a-118">**Authentication with POP3 Server**</span></span>  
  
  <span data-ttu-id="5d70a-119">POP3 アダプターの使用は、次の認証方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d70a-119">The following authentication methods are supported for use with the POP3 adapter:</span></span>  
  
- <span data-ttu-id="5d70a-120">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="5d70a-120">**Basic.**</span></span> <span data-ttu-id="5d70a-121">POP3 サーバーでは、ユーザーの認証のための資格情報の指定を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-121">The POP3 server uses user provided credentials for authentication.</span></span>  <span data-ttu-id="5d70a-122">これらの資格情報はクリア テキストで送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d70a-122">These credentials are sent in clear text.</span></span>  
  
- <span data-ttu-id="5d70a-123">**ダイジェスト (APOP)。**</span><span class="sxs-lookup"><span data-stu-id="5d70a-123">**Digest (APOP).**</span></span> <span data-ttu-id="5d70a-124">POP3 サーバーは、認証、ダイジェスト文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d70a-124">The POP3 server uses a digest string for authentication.</span></span>  
  
- <span data-ttu-id="5d70a-125">**セキュリティで保護されたパスワード認証 (SPA) です。**</span><span class="sxs-lookup"><span data-stu-id="5d70a-125">**Secure Password Authentication (SPA).**</span></span> <span data-ttu-id="5d70a-126">POP3 サーバーでは、現在のプロセスの資格情報を使用して認証。</span><span class="sxs-lookup"><span data-stu-id="5d70a-126">The POP3 server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d70a-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5d70a-127">In This Section</span></span>  
  
-   [<span data-ttu-id="5d70a-128">POP3 アダプターについて</span><span class="sxs-lookup"><span data-stu-id="5d70a-128">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5d70a-129">POP3 アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="5d70a-129">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5d70a-130">チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="5d70a-130">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="5d70a-131">POP3 アダプターでのマルチパート メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="5d70a-131">Processing Multi Part Messages with the POP3 Adapter</span></span>](../core/processing-multi-part-messages-with-the-pop3-adapter.md)