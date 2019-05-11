---
title: 開始側プライベート プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0bcf79ba696068e1dfa52b3d2d44542343060b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283474"
---
# <a name="initiator-private-process"></a><span data-ttu-id="3130f-102">開始側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="3130f-102">Initiator Private Process</span></span>
<span data-ttu-id="3130f-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]開始側プライベート プロセス (PrivateInitiator.odx) を使用して、開始側コンピュータでのサービス内容を処理します。</span><span class="sxs-lookup"><span data-stu-id="3130f-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the initiator private process (PrivateInitiator.odx) to process service content at an initiator computer.</span></span> <span data-ttu-id="3130f-104">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3130f-104">This includes the following:</span></span>  
  
- <span data-ttu-id="3130f-105">元のメッセージの service content を作成して、取引先パートナーへのルートで、パブリック プロセスへのメッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="3130f-105">Creating the service content of an original message and routing the message to the public process, in route to the trading partner</span></span>  
  
- <span data-ttu-id="3130f-106">リターン シグナル メッセージを処理し、基幹業務 (LOB) アプリケーションへのルーティング</span><span class="sxs-lookup"><span data-stu-id="3130f-106">Processing a return signal message and routing it to the line-of-business (LOB) application</span></span>  
  
- <span data-ttu-id="3130f-107">場合はダブル アクション PIP、戻り値の応答メッセージを処理し、LOB アプリケーションへのルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3130f-107">In the case of a double-action PIP, processing a response return message and routing it to the LOB application.</span></span>  
  
  <span data-ttu-id="3130f-108">プライベート プロセスは、メタデータを設定し、すべての添付ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="3130f-108">The private process also sets metadata and adds any attachments.</span></span> <span data-ttu-id="3130f-109">プライベート プロセスは、RosettaNet Implementation Framework (RNIF) ヘッダーを追加して、メッセージ転送の準備が整います、パブリック プロセスに送信メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3130f-109">The private process routes outgoing messages to the public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="3130f-110">プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3130f-110">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
  <span data-ttu-id="3130f-111">このプライベート プロセスは、3 a 2 および 3A4 の Partner Interface Process (Pip) を使用する購入クエリ/発注注文プロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="3130f-111">This private process automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="3130f-112">他のすべての PIP メッセージも処理します。</span><span class="sxs-lookup"><span data-stu-id="3130f-112">It also handles any other PIP messages.</span></span> <span data-ttu-id="3130f-113">特定のビジネス プロセスのプライベート プロセスをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3130f-113">You can customize the private process for your specific business processes.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="3130f-114">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="3130f-114">Message Flow</span></span>  
 <span data-ttu-id="3130f-115">開始側プライベート プロセスを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3130f-115">The message flow through the initiator private process is as follows:</span></span>  
  
1. <span data-ttu-id="3130f-116">開始側プライベート プロセスが MessagesFromLOB テーブルから、元のメッセージを受信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="3130f-116">The initiator private process receives the original message from the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="3130f-117">バックエンドの LOB アプリケーションは、このテーブルにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="3130f-117">The back-end LOB application routes the message to this table.</span></span>  
  
2. <span data-ttu-id="3130f-118">プライベート プロセスでは、発信されたメッセージの service content を準備し、パブリック プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="3130f-118">The private process prepares the service content of an initiated message, and sends it to the public process.</span></span>  
  
3. <span data-ttu-id="3130f-119">開始側プライベート プロセスは、リターン シグナルの待機、待機状態を入力します。</span><span class="sxs-lookup"><span data-stu-id="3130f-119">The initiator private process then enters a wait state, listening for a return signal.</span></span>  
  
4. <span data-ttu-id="3130f-120">パブリック プロセスからリターン シグナルを受信すると、プライベート プロセスがシグナル メッセージを作成し、シグナルを MessagesToLOB テーブルに送信します、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベースで、LOB アプリケーションへのルートでします。</span><span class="sxs-lookup"><span data-stu-id="3130f-120">Upon receiving a return signal from the public process, the private process constructs a signal message, and sends the signal to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
5. <span data-ttu-id="3130f-121">プライベート プロセスは、シグナル メッセージを MessagesToLOB テーブルに配置が LOB アプリケーションに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="3130f-121">The private process sends a notification to the LOB application that it put the signal message in the MessagesToLOB table.</span></span>  
  
6. <span data-ttu-id="3130f-122">RNIF のバージョンが 1.1 の場合は、プライベート プロセスへの同意の確認のシグナル メッセージを待ちます。</span><span class="sxs-lookup"><span data-stu-id="3130f-122">If the RNIF version is 1.1, the private process waits for an acceptance acknowledgement signal message.</span></span> <span data-ttu-id="3130f-123">シグナルを受信した場合、シグナル メッセージを作成し、シグナルを MessagesToLOB テーブルに LOB アプリケーションへのルートに送信します。</span><span class="sxs-lookup"><span data-stu-id="3130f-123">If it receives the signal, it constructs the signal message, and sends the signal to the MessagesToLOB table, in route to the LOB application.</span></span>  
  
7. <span data-ttu-id="3130f-124">元のメッセージがシングル アクション メッセージの場合は、シグナル メッセージを LOB アプリケーションに戻った後、プライベート プロセスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="3130f-124">If the original message(s) was a single-action message, the private process is complete after it has returned the signal message to the LOB application.</span></span> <span data-ttu-id="3130f-125">元のメッセージがダブル アクション メッセージの場合は、プライベート プロセスは、応答メッセージをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="3130f-125">If the original message was a double-action message, the private process listens for a response message.</span></span>  
  
8. <span data-ttu-id="3130f-126">プライベート プロセスは、パブリック プロセスから応答メッセージを受信した場合は、LOB アプリケーションの形式で応答メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="3130f-126">If the private process receives a response message from the public process, it constructs a response message in the format of the LOB application.</span></span> <span data-ttu-id="3130f-127">これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3130f-127">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
9. <span data-ttu-id="3130f-128">プライベート プロセスは、メッセージを MessagesToLOB テーブルにルーティング、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="3130f-128">The private process routes the message to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
10. <span data-ttu-id="3130f-129">応答メッセージに添付ファイルがある場合は、プライベート プロセスは AttachmentHelper ツールで、添付ファイルを処理するを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3130f-129">If the response message has an attachment, the private process calls the AttachmentHelper tool to process the attachment.</span></span>  
  
11. <span data-ttu-id="3130f-130">プライベート プロセスは、応答メッセージを MessagesToLOB テーブルに配置しが完了し、LOB アプリケーションに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="3130f-130">The private process sends a notification to the LOB application that it put the response message in the MessagesToLOB table, and then is complete.</span></span>  
  
## <a name="handling-of-incorrect-messages"></a><span data-ttu-id="3130f-131">誤ったメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="3130f-131">Handling of Incorrect Messages</span></span>  
 <span data-ttu-id="3130f-132">開始側プライベート プロセスは LOB アプリケーションから正しくないメッセージを受信、プライベート プロセスは、LOB に例外メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="3130f-132">When the initiator private process receives an incorrect message from the LOB application, the private process sends an exception message back to the LOB.</span></span> <span data-ttu-id="3130f-133">ただし、プライベート プロセスには、正しくないメッセージで通知されません、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3130f-133">However, the private process does not post the incorrect message in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk Administration Console.</span></span> <span data-ttu-id="3130f-134">したがって、BizTalk 管理コンソールで、正しくないメッセージを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="3130f-134">Therefore, you are not able to view the incorrect message in BizTalk Administration Console.</span></span> <span data-ttu-id="3130f-135">正しくないメッセージが正しくなかったことを確認するメッセージへのアクセス、例外メッセージを使用しての MessagesFromLOB テーブルに正しくないメッセージにアクセスし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。</span><span class="sxs-lookup"><span data-stu-id="3130f-135">You can use the exception message to access the incorrect message to determine which message was incorrect, and then access the incorrect message in the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span> <span data-ttu-id="3130f-136">ただし、このメッセージができません消費されると、プライベート プロセス メッセージと同じ編集、保存されているプロセスとメッセージの処理に使用するアダプター。</span><span class="sxs-lookup"><span data-stu-id="3130f-136">However, this message may not be the same as the message that the private process consumed, because the stored process and adapter used to process the message edit it.</span></span> <span data-ttu-id="3130f-137">メッセージにルート要素と名前空間を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="3130f-137">They add a root element and namespace to the message.</span></span> <span data-ttu-id="3130f-138">保存されているプロセスとアダプターは、複数のレコードを返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3130f-138">The stored process and adapter possibly return multiple records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3130f-139">参照</span><span class="sxs-lookup"><span data-stu-id="3130f-139">See Also</span></span>  
 <span data-ttu-id="3130f-140">[プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="3130f-140">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="3130f-141">[応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="3130f-141">[Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span></span>  
 <span data-ttu-id="3130f-142">[オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="3130f-142">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="3130f-143">PrivateInitiator サンプル</span><span class="sxs-lookup"><span data-stu-id="3130f-143">PrivateInitiator Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)