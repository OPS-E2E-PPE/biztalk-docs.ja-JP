---
title: 受信確認の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b726eb4698eaa9887703d7df01dc0f6cadf5eefc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204562"
---
# <a name="acknowledgments-processing"></a><span data-ttu-id="bb01a-102">受信確認の処理</span><span class="sxs-lookup"><span data-stu-id="bb01a-102">Acknowledgments Processing</span></span>
<span data-ttu-id="bb01a-103">HL7 仕様では、2 つの形式でメッセージの交換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb01a-103">The HL7 specification supports exchange of messages in two formats:</span></span>  
  
-   <span data-ttu-id="bb01a-104">要請されていない更新プログラムとその確認 (ACK)</span><span class="sxs-lookup"><span data-stu-id="bb01a-104">Unsolicited update and its acknowledgment (ACK)</span></span>  
  
-   <span data-ttu-id="bb01a-105">クエリとその応答</span><span class="sxs-lookup"><span data-stu-id="bb01a-105">Query and its response</span></span>  
  
 <span data-ttu-id="bb01a-106">発信側アプリケーションからメッセージに応答して、応答側のアプリケーションはデータや、エラーを示す値を含むメッセージに応答します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-106">In response to a message from an initiating application, the responding application responds with a message that includes data or an error indication.</span></span> <span data-ttu-id="bb01a-107">発信側アプリケーションは、応答側のアプリケーションを受信しなかったこと、メッセージ正常を示す応答側アプリケーションから却下ステータスを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb01a-107">The initiating application may receive a reject status from the responder application indicating that the responder application did not receive the message correctly.</span></span> <span data-ttu-id="bb01a-108">どちらの場合は、メッセージ交換処理には、2 つのエンティティ、発信側と応答側のアプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb01a-108">In both cases, the process of message exchange involves two entities, the initiating and responding applications.</span></span> <span data-ttu-id="bb01a-109">各は送信者とメッセージの受信先の両方です。</span><span class="sxs-lookup"><span data-stu-id="bb01a-109">Each is both a sender and receiver of messages.</span></span> <span data-ttu-id="bb01a-110">発信側アプリケーションでは、最初に送信し、受信、応答のシステムの受信、送信中。</span><span class="sxs-lookup"><span data-stu-id="bb01a-110">The initiating application sends first and then receives, while the responding system receives and then sends.</span></span>  
  
## <a name="unsolicited-updates"></a><span data-ttu-id="bb01a-111">要請されていない更新プログラム</span><span class="sxs-lookup"><span data-stu-id="bb01a-111">Unsolicited updates</span></span>  
 <span data-ttu-id="bb01a-112">要請されていない更新プログラムは、基幹業務 (LOB) アプリケーション、メッセージを公開するか、トリガー イベントが発生したときに情報の転送を開始するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-112">An unsolicited update occurs when a line-of-business (LOB) application publishes a message, or initiates a transfer of information when a trigger event occurs.</span></span> <span data-ttu-id="bb01a-113">たとえば、患者の実験の結果が使用できる場合は、ある可能性がありますテスト結果を他のいくつかのシステムに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb01a-113">For example, when the laboratory results for a patient are available, there may be a need to send the laboratory results to several other systems.</span></span> <span data-ttu-id="bb01a-114">これらは、要請されていない更新プログラムの ACK が応答します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-114">These updates are unsolicited updates to which an ACK responds.</span></span>  
  
## <a name="queries"></a><span data-ttu-id="bb01a-115">クエリ</span><span class="sxs-lookup"><span data-stu-id="bb01a-115">Queries</span></span>  
 <span data-ttu-id="bb01a-116">クエリの場合は、情報を必要とするアプリケーションでは、別のアプリケーションにクエリを送信し、受信側のアプリケーションがクエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-116">In the case of a query, an application that requires information sends a query to another application, and the receiving application responds to the query.</span></span> <span data-ttu-id="bb01a-117">やなどの薬局アプリケーション可能性があります、注文エントリ (組織) のシステムの患者の ID 番号を含む要求メッセージの送信、注文に関する処理を許可するように必要なデータを含む応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-117">For example, a pharmacy application may send a request message containing the ID number of the patient to the Order Entry (CPOE) system and receive a response containing the necessary data to permit processing of the order.</span></span> <span data-ttu-id="bb01a-118">この要求を行ったトランザクションは、クエリであり、要請されていない更新プログラムとは異なる。</span><span class="sxs-lookup"><span data-stu-id="bb01a-118">This requesting transaction is a query, and is different from an unsolicited update.</span></span> <span data-ttu-id="bb01a-119">2 つのアプリケーション間をフローする情報は、応答に含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb01a-119">The information that flows between the two applications is contained in the response.</span></span> <span data-ttu-id="bb01a-120">応答には、4 番目のメッセージの受信確認は不要です。</span><span class="sxs-lookup"><span data-stu-id="bb01a-120">The response itself does not require an acknowledgment with a fourth message.</span></span> <span data-ttu-id="bb01a-121">ただし、ACK で応答する一部の環境で変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bb01a-121">However, you can modify this in some environments to respond with an ACK.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="bb01a-122">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ように構成されている場合は、ACK で応答します。</span><span class="sxs-lookup"><span data-stu-id="bb01a-122"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responds with an ACK if so configured.</span></span> <span data-ttu-id="bb01a-123">クエリ/応答のやり取りの例は、次を参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb01a-123">For an example of a query/response exchange, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb01a-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bb01a-124">In This Section</span></span>  
  
-   [<span data-ttu-id="bb01a-125">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="bb01a-125">Validating Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [<span data-ttu-id="bb01a-126">ACK メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="bb01a-126">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [<span data-ttu-id="bb01a-127">ACK プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="bb01a-127">ACK Process Model</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)