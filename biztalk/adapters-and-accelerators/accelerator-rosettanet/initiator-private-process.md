---
title: "開始側プライベート プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d176a15ba5236d5f44d87406d9bbc0a19fca9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="initiator-private-process"></a><span data-ttu-id="5e339-102">開始側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="5e339-102">Initiator Private Process</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="5e339-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]開始側プライベート プロセス (PrivateInitiator.odx) を使用して、開始側コンピュータの service content を処理します。</span><span class="sxs-lookup"><span data-stu-id="5e339-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the initiator private process (PrivateInitiator.odx) to process service content at an initiator computer.</span></span> <span data-ttu-id="5e339-104">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e339-104">This includes the following:</span></span>  
  
-   <span data-ttu-id="5e339-105">元のメッセージの Service Content の作成、および取引先宛てのメッセージのパブリック プロセスへのルーティング</span><span class="sxs-lookup"><span data-stu-id="5e339-105">Creating the service content of an original message and routing the message to the public process, in route to the trading partner</span></span>  
  
-   <span data-ttu-id="5e339-106">リターン シグナル メッセージの処理、および基幹業務 (LOB) アプリケーションへのルーティング</span><span class="sxs-lookup"><span data-stu-id="5e339-106">Processing a return signal message and routing it to the line-of-business (LOB) application</span></span>  
  
-   <span data-ttu-id="5e339-107">場合は、ダブル アクション PIP、戻り値の応答メッセージを処理し、LOB アプリケーションにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="5e339-107">In the case of a double-action PIP, processing a response return message and routing it to the LOB application.</span></span>  
  
 <span data-ttu-id="5e339-108">プライベート プロセスでは、メタデータの設定、および添付ファイルの追加も行います。</span><span class="sxs-lookup"><span data-stu-id="5e339-108">The private process also sets metadata and adds any attachments.</span></span> <span data-ttu-id="5e339-109">プライベート プロセスは、パブリック プロセスに送信メッセージをルーティングします。これによって、RNIF (RosettaNet Implementation Framework) ヘッダーが追加され、メッセージを送信する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="5e339-109">The private process routes outgoing messages to the public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="5e339-110">プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="5e339-110">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
 <span data-ttu-id="5e339-111">このプライベート プロセスは、3A2 および 3A4 の PIP (Partner Interface Process) を使用する購入クエリ/発注プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="5e339-111">This private process automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="5e339-112">他のすべての PIP メッセージも処理します。</span><span class="sxs-lookup"><span data-stu-id="5e339-112">It also handles any other PIP messages.</span></span> <span data-ttu-id="5e339-113">プライベート プロセスは、個々のビジネス プロセスに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="5e339-113">You can customize the private process for your specific business processes.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="5e339-114">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="5e339-114">Message Flow</span></span>  
 <span data-ttu-id="5e339-115">開始側プライベート プロセスを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e339-115">The message flow through the initiator private process is as follows:</span></span>  
  
1.  <span data-ttu-id="5e339-116">開始側プライベート プロセスが、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesFromLOB テーブルから元のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5e339-116">The initiator private process receives the original message from the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="5e339-117">バックエンド LOB アプリケーションは、メッセージをこのテーブルにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="5e339-117">The back-end LOB application routes the message to this table.</span></span>  
  
2.  <span data-ttu-id="5e339-118">プライベート プロセスが元のメッセージの Service Content を準備し、パブリック プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e339-118">The private process prepares the service content of an initiated message, and sends it to the public process.</span></span>  
  
3.  <span data-ttu-id="5e339-119">開始側プライベート プロセスが待機状態になり、リターン シグナルの受信待ちをします。</span><span class="sxs-lookup"><span data-stu-id="5e339-119">The initiator private process then enters a wait state, listening for a return signal.</span></span>  
  
4.  <span data-ttu-id="5e339-120">パブリック プロセスからリターン シグナルを受信すると、プライベート プロセスがシグナル メッセージを作成し、LOB アプリケーション宛てのシグナルを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e339-120">Upon receiving a return signal from the public process, the private process constructs a signal message, and sends the signal to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
5.  <span data-ttu-id="5e339-121">プライベート プロセスがシグナル メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="5e339-121">The private process sends a notification to the LOB application that it put the signal message in the MessagesToLOB table.</span></span>  
  
6.  <span data-ttu-id="5e339-122">RNIF バージョンが 1.1 の場合、プライベート プロセスは受信確認のシグナル メッセージを待ちます。</span><span class="sxs-lookup"><span data-stu-id="5e339-122">If the RNIF version is 1.1, the private process waits for an acceptance acknowledgement signal message.</span></span> <span data-ttu-id="5e339-123">シグナルを受信すると、シグナル メッセージを作成し、LOB アプリケーション宛てのシグナルを MessagesToLOB テーブルに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e339-123">If it receives the signal, it constructs the signal message, and sends the signal to the MessagesToLOB table, in route to the LOB application.</span></span>  
  
7.  <span data-ttu-id="5e339-124">元のメッセージがシングル アクション メッセージの場合、プライベート プロセスはシグナル メッセージを LOB アプリケーションに返すと完了します。</span><span class="sxs-lookup"><span data-stu-id="5e339-124">If the original message(s) was a single-action message, the private process is complete after it has returned the signal message to the LOB application.</span></span> <span data-ttu-id="5e339-125">元のメッセージがダブル アクション メッセージの場合、プライベート プロセスは応答メッセージを受信待ちします。</span><span class="sxs-lookup"><span data-stu-id="5e339-125">If the original message was a double-action message, the private process listens for a response message.</span></span>  
  
8.  <span data-ttu-id="5e339-126">プライベート プロセスはパブリック プロセスから応答メッセージを受信すると、LOB アプリケーションの形式で応答メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e339-126">If the private process receives a response message from the public process, it constructs a response message in the format of the LOB application.</span></span> <span data-ttu-id="5e339-127">これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e339-127">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
9. <span data-ttu-id="5e339-128">プライベート プロセスが [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="5e339-128">The private process routes the message to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
10. <span data-ttu-id="5e339-129">応答メッセージに添付ファイルがある場合、プライベート プロセスは AttachmentHelper ツールを呼び出して添付ファイルを処理します。</span><span class="sxs-lookup"><span data-stu-id="5e339-129">If the response message has an attachment, the private process calls the AttachmentHelper tool to process the attachment.</span></span>  
  
11. <span data-ttu-id="5e339-130">プライベート プロセスが応答メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知し、終了します。</span><span class="sxs-lookup"><span data-stu-id="5e339-130">The private process sends a notification to the LOB application that it put the response message in the MessagesToLOB table, and then is complete.</span></span>  
  
## <a name="handling-of-incorrect-messages"></a><span data-ttu-id="5e339-131">誤ったメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="5e339-131">Handling of Incorrect Messages</span></span>  
 <span data-ttu-id="5e339-132">開始側プライベート プロセスが LOB アプリケーションから誤ったメッセージを受信した場合は、LOB に例外メッセージを送り返します。</span><span class="sxs-lookup"><span data-stu-id="5e339-132">When the initiator private process receives an incorrect message from the LOB application, the private process sends an exception message back to the LOB.</span></span> <span data-ttu-id="5e339-133">ただし、プライベート プロセスは、誤ったメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理コンソールに渡しません。</span><span class="sxs-lookup"><span data-stu-id="5e339-133">However, the private process does not post the incorrect message in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk Administration Console.</span></span> <span data-ttu-id="5e339-134">したがって、誤ったメッセージを BizTalk 管理コンソールで表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e339-134">Therefore, you are not able to view the incorrect message in BizTalk Administration Console.</span></span> <span data-ttu-id="5e339-135">例外メッセージを使用して、どれが誤ったメッセージなのかを判断してから、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA データベースの MessagesFromLOB テーブルで該当するメッセージを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e339-135">You can use the exception message to access the incorrect message to determine which message was incorrect, and then access the incorrect message in the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span> <span data-ttu-id="5e339-136">ただし、このメッセージは、プライベート プロセスが使用したメッセージと異なっている可能性があります。これは、保存されているプロセスとメッセージ処理に使用されたアダプターが、メッセージを編集するためです。</span><span class="sxs-lookup"><span data-stu-id="5e339-136">However, this message may not be the same as the message that the private process consumed, because the stored process and adapter used to process the message edit it.</span></span> <span data-ttu-id="5e339-137">この編集によって、ルート要素と名前空間がメッセージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5e339-137">They add a root element and namespace to the message.</span></span> <span data-ttu-id="5e339-138">保存されているプロセスとアダプターは、複数のレコードを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="5e339-138">The stored process and adapter possibly return multiple records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e339-139">参照</span><span class="sxs-lookup"><span data-stu-id="5e339-139">See Also</span></span>  
 <span data-ttu-id="5e339-140">[プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="5e339-140">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="5e339-141">[応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="5e339-141">[Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span></span>  
 <span data-ttu-id="5e339-142">[オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="5e339-142">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="5e339-143">PrivateInitiator サンプル</span><span class="sxs-lookup"><span data-stu-id="5e339-143">PrivateInitiator Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)