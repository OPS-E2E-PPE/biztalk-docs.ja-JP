---
title: 受信確認処理 |Microsoft Docs
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
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969467"
---
# <a name="acknowledgments-processing"></a><span data-ttu-id="c230d-102">受信確認処理</span><span class="sxs-lookup"><span data-stu-id="c230d-102">Acknowledgments Processing</span></span>
<span data-ttu-id="c230d-103">HL7 仕様では、2 つの形式のメッセージの交換をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c230d-103">The HL7 specification supports exchange of messages in two formats:</span></span>  
  
- <span data-ttu-id="c230d-104">要請されていない更新プログラムとその確認 (ACK)</span><span class="sxs-lookup"><span data-stu-id="c230d-104">Unsolicited update and its acknowledgment (ACK)</span></span>  
  
- <span data-ttu-id="c230d-105">クエリとその応答</span><span class="sxs-lookup"><span data-stu-id="c230d-105">Query and its response</span></span>  
  
  <span data-ttu-id="c230d-106">発信側アプリケーションからのメッセージに対しては、応答側のアプリケーションは、データまたはエラーを示す値を含むメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="c230d-106">In response to a message from an initiating application, the responding application responds with a message that includes data or an error indication.</span></span> <span data-ttu-id="c230d-107">発信側アプリケーションを応答側のアプリケーションでしたメッセージが正しく表示されないことを示す応答側アプリケーションから拒否状態があります。</span><span class="sxs-lookup"><span data-stu-id="c230d-107">The initiating application may receive a reject status from the responder application indicating that the responder application did not receive the message correctly.</span></span> <span data-ttu-id="c230d-108">どちらの場合も、メッセージ交換のプロセスには、2 つのエンティティ、発信側と応答のアプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c230d-108">In both cases, the process of message exchange involves two entities, the initiating and responding applications.</span></span> <span data-ttu-id="c230d-109">各は、送信者とメッセージの受信側の両方です。</span><span class="sxs-lookup"><span data-stu-id="c230d-109">Each is both a sender and receiver of messages.</span></span> <span data-ttu-id="c230d-110">発信側アプリケーションでは、最初に送信し、受信、応答してシステムの受信、送信中。</span><span class="sxs-lookup"><span data-stu-id="c230d-110">The initiating application sends first and then receives, while the responding system receives and then sends.</span></span>  
  
## <a name="unsolicited-updates"></a><span data-ttu-id="c230d-111">要請されていない更新プログラム</span><span class="sxs-lookup"><span data-stu-id="c230d-111">Unsolicited updates</span></span>  
 <span data-ttu-id="c230d-112">要請されていない更新プログラムでは、基幹業務 (LOB) のアプリケーションがメッセージを発行またはトリガー イベントが発生したときに、情報の転送を開始するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c230d-112">An unsolicited update occurs when a line-of-business (LOB) application publishes a message, or initiates a transfer of information when a trigger event occurs.</span></span> <span data-ttu-id="c230d-113">たとえば、患者の実験の結果が使用できる場合は、実験結果を他のいくつかのシステムに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c230d-113">For example, when the laboratory results for a patient are available, there may be a need to send the laboratory results to several other systems.</span></span> <span data-ttu-id="c230d-114">これらの更新プログラムは、ACK が応答する要請されていない更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="c230d-114">These updates are unsolicited updates to which an ACK responds.</span></span>  
  
## <a name="queries"></a><span data-ttu-id="c230d-115">クエリ</span><span class="sxs-lookup"><span data-stu-id="c230d-115">Queries</span></span>  
 <span data-ttu-id="c230d-116">場合は、クエリ情報を必要とするアプリケーションでは、別のアプリケーションにクエリを送信し、受信側アプリケーションがクエリに応答します。</span><span class="sxs-lookup"><span data-stu-id="c230d-116">In the case of a query, an application that requires information sends a query to another application, and the receiving application responds to the query.</span></span> <span data-ttu-id="c230d-117">たとえば、薬局用アプリケーションは注文エントリ (組織) システムの患者の ID 番号を含む要求メッセージの送信し、注文の処理を許可するように、必要なデータを含む応答を受信可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c230d-117">For example, a pharmacy application may send a request message containing the ID number of the patient to the Order Entry (CPOE) system and receive a response containing the necessary data to permit processing of the order.</span></span> <span data-ttu-id="c230d-118">この要求を行ったトランザクションは、クエリであり、要請していない更新プログラムとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c230d-118">This requesting transaction is a query, and is different from an unsolicited update.</span></span> <span data-ttu-id="c230d-119">2 つのアプリケーション間で行われる情報は、応答に含まれます。</span><span class="sxs-lookup"><span data-stu-id="c230d-119">The information that flows between the two applications is contained in the response.</span></span> <span data-ttu-id="c230d-120">応答自体では、4 番目のメッセージの受信確認は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c230d-120">The response itself does not require an acknowledgment with a fourth message.</span></span> <span data-ttu-id="c230d-121">ただし、ACK で応答する一部の環境で変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c230d-121">However, you can modify this in some environments to respond with an ACK.</span></span> <span data-ttu-id="c230d-122">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ように構成されている場合は、ACK で応答します。</span><span class="sxs-lookup"><span data-stu-id="c230d-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responds with an ACK if so configured.</span></span> <span data-ttu-id="c230d-123">クエリ/応答の交換の例は、次を参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="c230d-123">For an example of a query/response exchange, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c230d-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c230d-124">In This Section</span></span>  
  
-   [<span data-ttu-id="c230d-125">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="c230d-125">Validating Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [<span data-ttu-id="c230d-126">ACK メッセージ モード</span><span class="sxs-lookup"><span data-stu-id="c230d-126">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [<span data-ttu-id="c230d-127">ACK プロセス モデル</span><span class="sxs-lookup"><span data-stu-id="c230d-127">ACK Process Model</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)