---
title: "応答側プライベート プロセス |Microsoft ドキュメント"
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
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8ba5ca38eb64859182242c944d260c9db15c880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="responder-private-process"></a><span data-ttu-id="018d0-102">応答側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="018d0-102">Responder Private Process</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="018d0-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]応答側プライベート プロセス (PrivateResponder.odx) を使用して、応答側コンピュータの service content を処理します。</span><span class="sxs-lookup"><span data-stu-id="018d0-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the responder private process (PrivateResponder.odx) to process service content at a responder computer.</span></span> <span data-ttu-id="018d0-104">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="018d0-104">This includes the following:</span></span>  
  
-   <span data-ttu-id="018d0-105">基幹業務 (LOB) アプリケーションへの着信メッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="018d0-105">Routing an incoming message to the line-of-business (LOB) application</span></span>  
  
-   <span data-ttu-id="018d0-106">応答メッセージの Service Content の作成、および応答側コンピューター宛てのメッセージのパブリック プロセスへのルーティング</span><span class="sxs-lookup"><span data-stu-id="018d0-106">Creating the service content of a response message and routing the message to the public process, in route to the responder computer</span></span>  
  
 <span data-ttu-id="018d0-107">プライベート プロセスにより、メタデータの設定と、応答メッセージへの添付ファイルの追加も行われます。</span><span class="sxs-lookup"><span data-stu-id="018d0-107">The private process also sets metadata and adds any attachments to the response message.</span></span> <span data-ttu-id="018d0-108">プライベート プロセスでは、応答側パブリック プロセスに送信メッセージをルーティングします。これによって、RNIF (RosettaNet Implementation Framework) ヘッダーが追加され、メッセージを送信する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="018d0-108">The private process routes outgoing messages to the responder public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="018d0-109">プライベート プロセスは、LOB アプリケーション宛ての着信メッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesToLOB テーブルにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="018d0-109">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
 <span data-ttu-id="018d0-110">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、個々のビジネス プロセスに合わせてカスタマイズ可能な応答側プライベート プロセスのサンプルが 2 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="018d0-110">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two responder private process samples that you can customize for your specific business processes.</span></span> <span data-ttu-id="018d0-111">1 つ目のサンプルは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によってインストールされた応答側プライベート プロセスのコードを含む PrivateResponder プロセスのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="018d0-111">The first is the PrivateResponder process sample that contains the code for the responder private process installed by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="018d0-112">詳細については、次を参照してください。 [PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="018d0-112">For more information, see [PrivateResponder Sample](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md).</span></span>  
  
 <span data-ttu-id="018d0-113">2 つ目のサンプルは、3A2 および 3A4 の PIP (Partner Interface Process) を使用する発注照会/発注プロセスを自動化する PIP3A4PrivateResponder プライベート プロセスのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="018d0-113">The second sample is the PIP3A4PrivateResponder private process sample that automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="018d0-114">他のすべての PIP メッセージも処理します。</span><span class="sxs-lookup"><span data-stu-id="018d0-114">It also handles any other PIP messages.</span></span> <span data-ttu-id="018d0-115">詳細については、次を参照してください。 [3A4 プライベート応答側オーケストレーションを使用して、ビジネス ルール](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。</span><span class="sxs-lookup"><span data-stu-id="018d0-115">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="018d0-116">メッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="018d0-116">Message Flow</span></span>  
 <span data-ttu-id="018d0-117">応答側プライベート プロセスを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="018d0-117">The message flow through the responder private process is as follows:</span></span>  
  
1.  <span data-ttu-id="018d0-118">応答側プライベート プロセスは、開始側コンピューターから発信された元の着信メッセージを応答側パブリック プロセスから受信します。</span><span class="sxs-lookup"><span data-stu-id="018d0-118">The responder private process receives the original incoming message from the responder public process, in route from the initiator computer.</span></span>  
  
2.  <span data-ttu-id="018d0-119">プライベート プロセスは、LOB アプリケーション メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="018d0-119">The private process constructs the LOB application message.</span></span> <span data-ttu-id="018d0-120">これには、LOB メッセージ テンプレートの取得、XML サービス コンテンツのシリアル化、および LOB メッセージへの XML メッセージ部の読み込みが含まれます。</span><span class="sxs-lookup"><span data-stu-id="018d0-120">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
3.  <span data-ttu-id="018d0-121">プライベート プロセスは、バックエンド LOB アプリケーション宛てのメッセージを、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースの MessagesFromLOB テーブルにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="018d0-121">The private process routes the message to the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the back-end LOB application.</span></span>  
  
4.  <span data-ttu-id="018d0-122">元のメッセージに添付ファイルがある場合、プライベート プロセスは AttachmentHelper コンポーネントを呼び出して添付ファイルを処理します。</span><span class="sxs-lookup"><span data-stu-id="018d0-122">If the original message has an attachment, the private process calls the AttachmentHelper component to process the attachment.</span></span>  
  
5.  <span data-ttu-id="018d0-123">プライベート プロセスは、応答メッセージを MessagesToLOB テーブルに保存したことを LOB アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="018d0-123">The private process sends a notification to the LOB application that it saved the response message in the MessagesToLOB table.</span></span>  
  
6.  <span data-ttu-id="018d0-124">シングル アクション メッセージの場合、プライベート プロセスは完了します。</span><span class="sxs-lookup"><span data-stu-id="018d0-124">If the message is a single-action message, the private process is complete.</span></span>  
  
7.  <span data-ttu-id="018d0-125">ダブル アクション メッセージの場合、プライベート プロセスは LOB アプリケーションからの応答をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="018d0-125">If the message is a double-action message, the private process listens for a response from the LOB application.</span></span>  
  
8.  <span data-ttu-id="018d0-126">プライベート プロセスは LOB アプリケーションからの応答を受信すると、応答メッセージを作成してパブリック プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="018d0-126">When the private process receives the response from the LOB application, it constructs a response message, and sends the message to the public process.</span></span>  
  
9. <span data-ttu-id="018d0-127">プライベート プロセスは、パブリック プロセスからのシグナルを待ちます。</span><span class="sxs-lookup"><span data-stu-id="018d0-127">The private process waits for the signal from the public process.</span></span> <span data-ttu-id="018d0-128">シグナルを受信すると、プライベート プロセスは LOB シグナル メッセージを作成して LOB アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="018d0-128">If it receives the signal, it constructs the LOB signal message and sends it to the LOB application.</span></span> <span data-ttu-id="018d0-129">RNIF のバージョンが 1.1 の場合、プライベート プロセスは 2 番目の受信確認シグナルの受信をリッスンし、それを受信すると、LOB シグナル メッセージを作成して LOB アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="018d0-129">If the RNIF version is 1.1, the private process will listen for a second acknowledgement signal, and upon receiving it, will construct the LOB signal message and send it to the LOB application.</span></span> <span data-ttu-id="018d0-130">プライベート プロセスは、各シグナル メッセージを送信した後に LOB アプリケーションに通知します。</span><span class="sxs-lookup"><span data-stu-id="018d0-130">The private process notifies the LOB application after sending each signal message.</span></span>  
  
10. <span data-ttu-id="018d0-131">プライベート プロセスは、開始側から発信されたエラー通知 (NoF) メッセージをパブリック プロセスから受信すると、"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Exception" メッセージを作成して LOB アプリケーションに送信します。</span><span class="sxs-lookup"><span data-stu-id="018d0-131">If the private process receives a Notification of Failure (NoF) message from the public process, in route from the initiator, the private process constructs a "[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Exception" message, and sends it to the LOB application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018d0-132">参照</span><span class="sxs-lookup"><span data-stu-id="018d0-132">See Also</span></span>  
 <span data-ttu-id="018d0-133">[プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="018d0-133">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="018d0-134">[開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="018d0-134">[Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span></span>  
 <span data-ttu-id="018d0-135">[オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="018d0-135">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="018d0-136">PrivateResponder サンプル</span><span class="sxs-lookup"><span data-stu-id="018d0-136">PrivateResponder Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)