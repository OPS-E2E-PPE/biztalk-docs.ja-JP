---
title: "TIBCO Rendezvous から BizTalk Server を使用してメッセージを送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, sending
- sending messages
- BizTalk Server, using from TIBCO Rendezvous
ms.assetid: 72057d42-32b5-4748-81e4-5ffb89630f5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4556ce5ca90b3c62f779d2df55e78c4506458d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a><span data-ttu-id="505d6-102">BizTalk Server を TIBCO Rendezvous から使用してメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="505d6-102">Using BizTalk Server from TIBCO Rendezvous to Send Messages</span></span>
<span data-ttu-id="505d6-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、非同期 API (Transport.Send) を使用します。</span><span class="sxs-lookup"><span data-stu-id="505d6-103">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="505d6-104">メッセージ コンテキスト プロパティを使用して、このアダプターが送信するメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="505d6-104">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="505d6-105">**構造化**: アダプターには、BizTalk Server から受信した XML データに基づいて、TIBRVMSG_MSG 構造化されたメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="505d6-105">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="505d6-106">(*)</span><span class="sxs-lookup"><span data-stu-id="505d6-106">(*)</span></span>  
  
 <span data-ttu-id="505d6-107">BizTalk Server が 127 文字を超える名前を持つフィールドのあるメッセージを送信した場合、BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous の最大フィールド名サイズ (127 文字) に名前を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="505d6-107">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="505d6-108">`reply subject name` プロパティが指定されている場合、このプロパティを使用して TIBCO Rendezvous メッセージの返信の件名が設定されます。</span><span class="sxs-lookup"><span data-stu-id="505d6-108">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="505d6-109">受信ポートが応答を待機して BizTalk Server に転送するように設定されているか、その他の TIBCO Rendezvous プログラムが応答を処理すると想定されています。</span><span class="sxs-lookup"><span data-stu-id="505d6-109">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="505d6-110">トリプレット (サービス、デーモン、およびネットワーク) がトランスポートの構成を形成します。</span><span class="sxs-lookup"><span data-stu-id="505d6-110">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="505d6-111">トランスポートの構成が空白の場合 (既定)、メッセージは既定のトランスポート オブジェクトを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="505d6-111">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="505d6-112">コード ページを指定しない場合、このアダプターは UTF-8 エンコーディング (コード ページ 65001) を使用します。</span><span class="sxs-lookup"><span data-stu-id="505d6-112">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="505d6-113">伝送側では、認定済みメッセージはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="505d6-113">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505d6-114">参照</span><span class="sxs-lookup"><span data-stu-id="505d6-114">See Also</span></span>  
 <span data-ttu-id="505d6-115">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="505d6-115">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="505d6-116">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="505d6-116">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)