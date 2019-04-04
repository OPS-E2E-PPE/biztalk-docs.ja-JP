---
title: メッセージの応答側 BTARN でのフロー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629e53f7126c15f84640c8862644beb78e2a5cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980707"
---
# <a name="message-flow-in-the-responder-btarn"></a><span data-ttu-id="98ebf-102">応答側 BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="98ebf-102">Message Flow in the Responder BTARN</span></span>
<span data-ttu-id="98ebf-103">応答側コンピューターのメッセージ フローは、開始側コンピューターからインターネット経由でメッセージを受信することから始まります。</span><span class="sxs-lookup"><span data-stu-id="98ebf-103">Message flow on a responder computer starts with receiving a message over the Internet from the initiator computer.</span></span> <span data-ttu-id="98ebf-104">これには、RNIF (RosettaNet Implementation Framework) 準拠のメッセージをバックエンド アプリケーション専用形式のメッセージに変換し、基幹業務 (LOB) アプリケーションにメッセージをルーティングする処理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="98ebf-104">It involves converting that message from a RosettaNet Implementation Framework (RNIF)-compliant message to a message in the proprietary format of the back-end application, and then routing the message to the line-of-business application.</span></span>  
  
 <span data-ttu-id="98ebf-105">PIP (Partner Interface Process) がシングル アクションの場合の応答は、受信確認のシグナル メッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="98ebf-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="98ebf-106">PIP がダブル アクションの場合、応答側は応答メッセージを処理して送信した後、その応答の受信確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-106">If the PIP is double-action, the responder will process and send a response message, and subsequently receive an acknowledgment for that response.</span></span>  
  
 <span data-ttu-id="98ebf-107">PIP が非同期の場合、インターネットを経由する各メッセージは、個別の HTTP 接続で転送されます。</span><span class="sxs-lookup"><span data-stu-id="98ebf-107">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="98ebf-108">PIP が同期の場合、各メッセージはプロセスが完了するまで HTTP アダプターが保持する接続と同じ接続で転送されます。</span><span class="sxs-lookup"><span data-stu-id="98ebf-108">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="98ebf-109">ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初の要求メッセージに応える受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="98ebf-109">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="98ebf-110">応答メッセージが受信確認となります。</span><span class="sxs-lookup"><span data-stu-id="98ebf-110">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-responder-computer"></a><span data-ttu-id="98ebf-111">応答側コンピューター上の BTARN コンポーネント</span><span class="sxs-lookup"><span data-stu-id="98ebf-111">BTARN Components on the Responder Computer</span></span>  
 <span data-ttu-id="98ebf-112">メッセージが Microsoft を流れるよう[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]応答側コンピューターは、次のコンポーネントによってメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="98ebf-112">As a message flows through Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the responder computer, the following components will process the message:</span></span>  
  
- <span data-ttu-id="98ebf-113">RNIFReceive.aspx ページ</span><span class="sxs-lookup"><span data-stu-id="98ebf-113">RNIFReceive.aspx page</span></span>  
  
- <span data-ttu-id="98ebf-114">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="98ebf-114">HTTP adapter</span></span>  
  
- <span data-ttu-id="98ebf-115">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="98ebf-115">Receive pipeline</span></span>  
  
- <span data-ttu-id="98ebf-116">応答側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="98ebf-116">Responder public process</span></span>  
  
- <span data-ttu-id="98ebf-117">応答側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="98ebf-117">Responder private process</span></span>  
  
- <span data-ttu-id="98ebf-118">SQL アダプター</span><span class="sxs-lookup"><span data-stu-id="98ebf-118">SQL adapter</span></span>  
  
- <span data-ttu-id="98ebf-119">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="98ebf-119">Send pipeline</span></span>  
  
  <span data-ttu-id="98ebf-120">これらのコンポーネントとメッセージの処理方法の詳細については、[BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98ebf-120">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="message-flow-on-the-responder-computer"></a><span data-ttu-id="98ebf-121">応答側コンピューターでのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="98ebf-121">Message Flow on the Responder Computer</span></span>  
 <span data-ttu-id="98ebf-122">応答側 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] コンピュータでの受信メッセージのフローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="98ebf-122">The message flow of a received message through the responder [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer is as follows:</span></span>  
  
 <span data-ttu-id="98ebf-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span><span class="sxs-lookup"><span data-stu-id="98ebf-123">![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")</span></span>  
  
1. <span data-ttu-id="98ebf-124">RNIFReceive aspx ページが開始側から着信メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-124">The RNIFReceive aspx page receives the incoming message from the initiator.</span></span>  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="98ebf-125">がメッセージを HTTP アダプタに送信し、HTTP アダプタがそれを受信パイプラインに送信します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-125">submits the message to the HTTP adapter, which submits it to the receive pipeline.</span></span>  
  
3. <span data-ttu-id="98ebf-126">受信パイプラインがメッセージのデコード、逆アセンブル、およびパーティの解決を実行し、バックエンドの基幹業務 (LOB) アプリケーションの専用形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-126">The receive pipeline decodes, disassembles, and performs party resolution on the message, and then converts the message into the proprietary format of the back-end line-of-business application.</span></span>  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="98ebf-127">が MessageBox データベースにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="98ebf-127">routes the message to the MessageBox database.</span></span>  
  
5. <span data-ttu-id="98ebf-128">パブリック プロセスが、メッセージの RNIF ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-128">The public process processes the RNIF headers of the message.</span></span>  
  
6. <span data-ttu-id="98ebf-129">プライベート プロセスでメッセージの Service Content を処理します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-129">The private process processes the service content of the message.</span></span> <span data-ttu-id="98ebf-130">プライベート プロセスでは受信確認を生成します。この受信確認は、インターネット上でパブリック プロセス、MessageBox データベース、送信パイプライン、HTTP アダプターを経由して開始側に返されます。</span><span class="sxs-lookup"><span data-stu-id="98ebf-130">It generates an acknowledgement that is returned to the public process, to the MessageBox database, to the send pipeline, and then to the HTTP adapter for return over the Internet to the initiator.</span></span>  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="98ebf-131">が MessageBox データベースにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="98ebf-131">routes the message to the MessageBox database.</span></span>  
  
8. <span data-ttu-id="98ebf-132">送信パイプラインがメッセージを編成し、メッセージに署名して、暗号化とエンコードを行います。</span><span class="sxs-lookup"><span data-stu-id="98ebf-132">The send pipeline assembles, and then signs/encrypts/encodes the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="98ebf-133">が SQL アダプタにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="98ebf-133">routes the message to the SQL adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="98ebf-134">が [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] を経由してバックエンドの基幹業務 (LOB) アプリケーションにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="98ebf-134">submits the message to [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and to the line-of-business application on the back end.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ebf-135">参照</span><span class="sxs-lookup"><span data-stu-id="98ebf-135">See Also</span></span>  
 <span data-ttu-id="98ebf-136">[BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="98ebf-136">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 [<span data-ttu-id="98ebf-137">イニシエーター BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="98ebf-137">Message Flow in the Initiator BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)