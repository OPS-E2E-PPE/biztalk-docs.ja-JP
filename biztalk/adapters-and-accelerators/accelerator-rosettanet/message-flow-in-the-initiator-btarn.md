---
title: メッセージの開始側 BTARN での流れ |Microsoft ドキュメント
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
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85fed6404627fd8abfa9d50e7d56d98ff7306f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210594"
---
# <a name="message-flow-in-the-initiator-btarn"></a><span data-ttu-id="94ecb-102">開始側 BTARN でのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="94ecb-102">Message Flow in the Initiator BTARN</span></span>
<span data-ttu-id="94ecb-103">開始側コンピューターが、バックエンドの基幹業務 (LOB) アプリケーションから専用形式のメッセージを受信すると、メッセージ フローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="94ecb-103">Message flow on an initiator computer starts with receiving a message from the back-end line-of-business application, in its proprietary format.</span></span> <span data-ttu-id="94ecb-104">メッセージ フローには、受信したメッセージを RNIF (RosettaNet Implementation Framework) に準拠するメッセージに変換して、インターネット経由で応答側コンピューターに送信するタスクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="94ecb-104">It involves converting that message to a RosettaNet Implementation Framework (RNIF)-compliant message, and then sending the message over the Internet to the responder computer.</span></span>  
  
 <span data-ttu-id="94ecb-105">PIP (Partner Interface Process) がシングル アクションの場合の応答は、受信確認のシグナル メッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="94ecb-105">If the Partner Interface Process (PIP) is single-action, the only response is an acknowledgement signal message.</span></span> <span data-ttu-id="94ecb-106">シングル アクションのメッセージ フローの詳細については、後の「開始メッセージのフロー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94ecb-106">For information about single-action message flow, see "Flow of an Initiated Message" later in this topic.</span></span> <span data-ttu-id="94ecb-107">PIP がダブル アクションの場合、開始側はシングル アクションのメッセージ フローに加えて、応答メッセージを受信し、受信確認を返信します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-107">If the PIP is double-action, the initiator will receive a response message, and reply with an acknowledgement, in addition to the single-action message flow.</span></span>  
  
 <span data-ttu-id="94ecb-108">PIP が非同期の場合、インターネットを経由する各メッセージは、個別の HTTP 接続で転送されます。</span><span class="sxs-lookup"><span data-stu-id="94ecb-108">If the PIP is asynchronous, each message transmission over the Internet occurs on a different HTTP connection.</span></span> <span data-ttu-id="94ecb-109">PIP が同期の場合、各メッセージはプロセスが完了するまで HTTP アダプターが保持する接続と同じ接続で転送されます。</span><span class="sxs-lookup"><span data-stu-id="94ecb-109">If the PIP is synchronous, each message transmission occurs on the same connection, which the HTTP adapter holds until the process is complete.</span></span> <span data-ttu-id="94ecb-110">ダブル アクション同期シナリオでは、応答側コンピューターは開始側コンピューターに対して、最初の要求メッセージに応える受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="94ecb-110">In a double-action synchronous scenario, the responder computer does not send an acknowledgement to the initiator computer in response to the initial request message.</span></span> <span data-ttu-id="94ecb-111">応答メッセージが受信確認となります。</span><span class="sxs-lookup"><span data-stu-id="94ecb-111">The response message serves as the acknowledgement.</span></span>  
  
## <a name="btarn-components-on-the-initiator-computer"></a><span data-ttu-id="94ecb-112">開始側コンピューター上の BTARN コンポーネント</span><span class="sxs-lookup"><span data-stu-id="94ecb-112">BTARN Components on the Initiator Computer</span></span>  
 <span data-ttu-id="94ecb-113">メッセージが開始側コンピュータの [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] を流れていく際は、次のコンポーネントがメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-113">As a message flows through [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] on the initiator computer, the following components will process the message:</span></span>  
  
-   <span data-ttu-id="94ecb-114">SQL アダプター</span><span class="sxs-lookup"><span data-stu-id="94ecb-114">SQL adapter</span></span>  
  
-   <span data-ttu-id="94ecb-115">XML 受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="94ecb-115">XML receive pipeline</span></span>  
  
-   <span data-ttu-id="94ecb-116">開始側プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="94ecb-116">Initiator private process</span></span>  
  
-   <span data-ttu-id="94ecb-117">開始側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="94ecb-117">Initiator public process</span></span>  
  
-   <span data-ttu-id="94ecb-118">XML 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="94ecb-118">XML send pipeline</span></span>  
  
-   <span data-ttu-id="94ecb-119">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="94ecb-119">HTTP adapter</span></span>  
  
-   <span data-ttu-id="94ecb-120">RNIFSend.aspx ページ</span><span class="sxs-lookup"><span data-stu-id="94ecb-120">RNIFSend.aspx page</span></span>  
  
 <span data-ttu-id="94ecb-121">これらのコンポーネントとメッセージの処理方法の詳細については、次を参照してください。 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)です。</span><span class="sxs-lookup"><span data-stu-id="94ecb-121">For more information about these components, and how they process a message, see [Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md).</span></span>  
  
## <a name="flow-of-an-initiated-message"></a><span data-ttu-id="94ecb-122">開始メッセージのフロー</span><span class="sxs-lookup"><span data-stu-id="94ecb-122">Flow of an Initiated Message</span></span>  
 <span data-ttu-id="94ecb-123">以下の手順は、開始側の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] コンピュータから発信されたメッセージのメッセージ フローを示します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-123">The following steps describe the message flow of an initiated message through the initiator [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] computer.</span></span> <span data-ttu-id="94ecb-124">このプロセスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-124">The following figure shows this process.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1.  <span data-ttu-id="94ecb-125">基幹業務アプリケーションにメッセージを送信する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="94ecb-125">The line-of-business application sends the message to [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="94ecb-126"> が、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] データベースから SQL アダプタにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-126"> sends the message from the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database to the SQL adapter.</span></span>  
  
3.  <span data-ttu-id="94ecb-127">XML 受信パイプラインは、メッセージの単純な XML 検証を行います。</span><span class="sxs-lookup"><span data-stu-id="94ecb-127">The XML receive pipeline does simple XML validation of the message.</span></span>  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="94ecb-128"> が MessageBox データベースにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="94ecb-128"> routes the message to the MessageBox database.</span></span>  
  
5.  <span data-ttu-id="94ecb-129">プライベート プロセスでメッセージの Service Content を処理します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-129">The private process processes the service content of the message.</span></span>  
  
6.  <span data-ttu-id="94ecb-130">パブリック プロセスが、メッセージの RNIF ヘッダーを処理します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-130">The public process processes the RNIF headers of the message.</span></span>  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="94ecb-131"> は、再度 MessageBox データベースにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="94ecb-131"> routes the message back to the MessageBox database.</span></span>  
  
8.  <span data-ttu-id="94ecb-132">送信パイプラインは、メッセージのアセンブリと署名/暗号化/エンコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="94ecb-132">The send pipeline performs assembly and signing/encryption/encoding of the message.</span></span>  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="94ecb-133"> は、HTTP アダプタにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="94ecb-133"> routes the message to the HTTP adapter.</span></span>  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="94ecb-134"> は RNIFSend.aspx ページにメッセージをルーティングし、メッセージはここから送信先にインターネット経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="94ecb-134"> routes the message to the RNIFSend.aspx page, which sends it over the Internet to its destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ecb-135">参照</span><span class="sxs-lookup"><span data-stu-id="94ecb-135">See Also</span></span>  
 <span data-ttu-id="94ecb-136">[BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="94ecb-136">[Message Flow in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md) </span></span>  
 <span data-ttu-id="94ecb-137">[応答側 BTARN でのメッセージ フロー](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="94ecb-137">[Message Flow in the Responder BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md) </span></span>  
 [<span data-ttu-id="94ecb-138">BTARN でのメッセージ処理</span><span class="sxs-lookup"><span data-stu-id="94ecb-138">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)