---
title: MSMQ アダプターのアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd314b6f835568b6336121478268b84381a288ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263050"
---
# <a name="msmq-adapter-architecture"></a><span data-ttu-id="858be-102">MSMQ アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="858be-102">MSMQ Adapter Architecture</span></span>
<span data-ttu-id="858be-103">MSMQ アダプターを使用すると、Microsoft メッセージ キュー (MSMQ) の機能を利用できます。MSMQ の機能は MSMQ アダプターを使用しない限り、BizTalk Server で使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="858be-103">The MSMQ adapter lets you take advantage of Microsoft Message Queuing (also known as MSMQ) features that are otherwise unavailable in BizTalk Server.</span></span>  
  
## <a name="adapter-structure"></a><span data-ttu-id="858be-104">アダプターの構造</span><span class="sxs-lookup"><span data-stu-id="858be-104">Adapter Structure</span></span>  
 <span data-ttu-id="858be-105">MSMQ アダプターは、他の BizTalk アダプターと同じ構造で、アダプター フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="858be-105">The MSMQ adapter has the same structure as other BizTalk adapters and uses the Adapter Framework.</span></span> <span data-ttu-id="858be-106">このアダプターは、デザイン時コンポーネントと実行時コンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="858be-106">It is made up of a design-time component and a run-time component.</span></span> <span data-ttu-id="858be-107">実行時コンポーネントには、メッセージ トランスポートを実装する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="858be-107">The run-time component, in turn, contains the elements that implement the message transport.</span></span>  
  
 <span data-ttu-id="858be-108">デザイン時コンポーネントを使用すると、アダプターのプロパティを送受信用に構成できます。</span><span class="sxs-lookup"><span data-stu-id="858be-108">The design-time component lets you configure the adapter properties for sending and receiving.</span></span>  
  
 <span data-ttu-id="858be-109">実行時コンポーネントは、デザイン時に定義されたキューにメッセージを送信したり、指定されたキューからメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="858be-109">The run-time component can send messages to a queue defined at design time or receive messages from a designated queue.</span></span> <span data-ttu-id="858be-110">アダプター ランタイムは、BizTalk Server アプリケーションと同じプロセスで実行され、分離ホストでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="858be-110">The adapter runtime runs in the same process as the BizTalk Server application and does not run in an isolated host.</span></span>  
  
 <span data-ttu-id="858be-111">すべてのメッセージ処理は、リモート キューの場合でも、ローカルのメッセージ キュー サービスに依存します。</span><span class="sxs-lookup"><span data-stu-id="858be-111">All message handling relies on the local Message Queuing service, even for remote queues.</span></span> <span data-ttu-id="858be-112">リモート キューの場合、アダプターはローカルのメッセージ キュー サービスにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="858be-112">For remote queues, the adapter hands messages off to the local Message Queuing service.</span></span> <span data-ttu-id="858be-113">その次に、そのメッセージをリモート キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="858be-113">It, in turn, sends the messages to the remote queue.</span></span>  
  
 <span data-ttu-id="858be-114">送信の完全な一覧については、構成プロパティを受信したりを参照してください[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)と[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="858be-114">For a complete list of send and receive configuration properties, see [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) and [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md).</span></span>  
  
 <span data-ttu-id="858be-115">メッセージ キューの詳細については、Microsoft TechNet ライブラリで次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="858be-115">For more information about Message Queuing, see the following topics available in the Microsoft TechNet Library:</span></span>  
  
-   <span data-ttu-id="858be-116">**メッセージ キューの設計ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080)です。</span><span class="sxs-lookup"><span data-stu-id="858be-116">**Message Queuing Design Guide** at [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).</span></span>  
  
-   <span data-ttu-id="858be-117">**メッセージ キューの操作ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079)です。</span><span class="sxs-lookup"><span data-stu-id="858be-117">**Message Queuing Operations Guide** at [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).</span></span>  
  
-   <span data-ttu-id="858be-118">**メッセージ キューのトラブルシューティング ガイド**で[http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081)です。</span><span class="sxs-lookup"><span data-stu-id="858be-118">**Message Queuing Troubleshooting Guide** at [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).</span></span>  
  
-   <span data-ttu-id="858be-119">**メッセージ キューのテクニカル リファレンス**で[http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082)です。</span><span class="sxs-lookup"><span data-stu-id="858be-119">**Message Queuing Technical Reference** at [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="858be-120">参照</span><span class="sxs-lookup"><span data-stu-id="858be-120">See Also</span></span>  
 [<span data-ttu-id="858be-121">MSMQ アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="858be-121">What Is the MSMQ Adapter?</span></span>](../core/what-is-the-msmq-adapter.md)