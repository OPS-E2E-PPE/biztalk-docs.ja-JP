---
title: "BizTalk Server から TIBCO Rendezvous 送信ポートの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, handling
- message handling
- BizTalk Server, using send ports from
- send ports, using from BizTalk Server
- messages, generating
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04e11657e8e15ac0739124178e85f0c7c5c0a70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-send-ports-from-biztalk-server"></a><span data-ttu-id="d8aa3-102">BizTalk Server からの TIBCO Rendezvous 送信ポートの使用</span><span class="sxs-lookup"><span data-stu-id="d8aa3-102">Using TIBCO Rendezvous Send Ports from BizTalk Server</span></span>
<span data-ttu-id="d8aa3-103">送信ポートはあらゆる種類のメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="d8aa3-104">BizTalk Server で Microsoft BizTalk Adapter for TIBCO Rendezvous を介してメッセージを送信する場合、アダプターはメッセージ コンテキストのプロパティ値に基づいてメッセージを生成するか、既定値を使用して、メッセージを指定されたサブジェクトに送信します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8aa3-105">TIBCO Rendezvous のドキュメントに従って、送信サブジェクト名ではワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="d8aa3-106">メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="d8aa3-106">Message Handling</span></span>  
 <span data-ttu-id="d8aa3-107">アダプターは状態を維持し、それに従って BizTalk Server の受信メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="d8aa3-108">トランスポートのエラーでメッセージを送信できない場合、BizTalk Server に対して後で再送信するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="d8aa3-109">アダプターがまだ初期化中であるためにメッセージを送信できない場合、BizTalk Server メッセージはキューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="d8aa3-110">初期化に失敗した場合、BizTalk Server は後で再送信するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="d8aa3-111">メッセージの生成</span><span class="sxs-lookup"><span data-stu-id="d8aa3-111">Message Generation</span></span>  
 <span data-ttu-id="d8aa3-112">送信アダプターを使用する場合、BizTalk Adapter for TIBCO Rendezvous はメッセージのターゲットの名前空間およびルート要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="d8aa3-113">アダプターがメッセージを送信する場合、アダプターはペイロードをそのまま送信します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="d8aa3-114">アダプターが構造化 TIBCO Rendezvous メッセージを生成する場合、ルート要素の名前は無視されます (メッセージに名前はありません)。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="d8aa3-115">いずれの場合も、アダプターはコンテキスト プロパティを使用して、メッセージを公開するときに使用するサブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="d8aa3-116">詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)と[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8aa3-117">参照</span><span class="sxs-lookup"><span data-stu-id="d8aa3-117">See Also</span></span>  
 <span data-ttu-id="d8aa3-118">[送信ポートの作成](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="d8aa3-118">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="d8aa3-119">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8aa3-119">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)