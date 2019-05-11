---
title: MSMQ アダプターのアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 1445907a98b6e86ae898015d131b0a5f892351a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263643"
---
# <a name="msmq-adapter-architecture"></a><span data-ttu-id="d8e2b-102">MSMQ アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d8e2b-102">MSMQ Adapter Architecture</span></span>
<span data-ttu-id="d8e2b-103">MSMQ アダプターでは、それ以外の場合、BizTalk Server で使用できるはない Microsoft メッセージ キュー (MSMQ とも呼ばれます) 機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-103">The MSMQ adapter lets you take advantage of Microsoft Message Queuing (also known as MSMQ) features that are otherwise unavailable in BizTalk Server.</span></span>  
  
## <a name="adapter-structure"></a><span data-ttu-id="d8e2b-104">アダプターの構造</span><span class="sxs-lookup"><span data-stu-id="d8e2b-104">Adapter Structure</span></span>  
 <span data-ttu-id="d8e2b-105">MSMQ アダプターは、他の BizTalk アダプターと同じ構造を備え、アダプター フレームワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-105">The MSMQ adapter has the same structure as other BizTalk adapters and uses the Adapter Framework.</span></span> <span data-ttu-id="d8e2b-106">これについては、デザイン時コンポーネントと実行時コンポーネントの構成されます。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-106">It is made up of a design-time component and a run-time component.</span></span> <span data-ttu-id="d8e2b-107">実行時コンポーネントには、さらに、メッセージ トランスポートを実装する要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-107">The run-time component, in turn, contains the elements that implement the message transport.</span></span>  
  
 <span data-ttu-id="d8e2b-108">デザイン時コンポーネントを使用して、送信と受信アダプターのプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-108">The design-time component lets you configure the adapter properties for sending and receiving.</span></span>  
  
 <span data-ttu-id="d8e2b-109">実行時コンポーネントでは、デザイン時に定義されたキューにメッセージを送信したり、指定されたキューからメッセージを受信することができます。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-109">The run-time component can send messages to a queue defined at design time or receive messages from a designated queue.</span></span> <span data-ttu-id="d8e2b-110">アダプター ランタイムは、BizTalk Server アプリケーションと同じプロセスで実行され、分離ホストでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-110">The adapter runtime runs in the same process as the BizTalk Server application and does not run in an isolated host.</span></span>  
  
 <span data-ttu-id="d8e2b-111">すべてのメッセージ処理は、ローカル メッセージ キュー サービス、リモート キューにも依存します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-111">All message handling relies on the local Message Queuing service, even for remote queues.</span></span> <span data-ttu-id="d8e2b-112">リモート キューの場合、アダプターはメッセージをローカルのメッセージ キュー サービスに渡します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-112">For remote queues, the adapter hands messages off to the local Message Queuing service.</span></span> <span data-ttu-id="d8e2b-113">さらに、リモート キューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-113">It, in turn, sends the messages to the remote queue.</span></span>  
  
 <span data-ttu-id="d8e2b-114">送信の完全な一覧については、構成プロパティを受信したりを参照してください[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)と[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-114">For a complete list of send and receive configuration properties, see [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) and [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md).</span></span>  
  
 <span data-ttu-id="d8e2b-115">メッセージ キューの詳細については、Microsoft TechNet ライブラリには次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-115">For more information about Message Queuing, see the following topics available in the Microsoft TechNet Library:</span></span>  
  
-   <span data-ttu-id="d8e2b-116">**メッセージ キュー設計ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080)します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-116">**Message Queuing Design Guide** at [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).</span></span>  
  
-   <span data-ttu-id="d8e2b-117">**メッセージ キュー操作ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079)します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-117">**Message Queuing Operations Guide** at [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).</span></span>  
  
-   <span data-ttu-id="d8e2b-118">**メッセージ キュー トラブルシューティング ガイド**で[ http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081)します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-118">**Message Queuing Troubleshooting Guide** at [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).</span></span>  
  
-   <span data-ttu-id="d8e2b-119">**メッセージ キュー テクニカル リファレンス**で[ http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082)します。</span><span class="sxs-lookup"><span data-stu-id="d8e2b-119">**Message Queuing Technical Reference** at [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e2b-120">参照</span><span class="sxs-lookup"><span data-stu-id="d8e2b-120">See Also</span></span>  
 [<span data-ttu-id="d8e2b-121">MSMQ アダプターについて</span><span class="sxs-lookup"><span data-stu-id="d8e2b-121">What Is the MSMQ Adapter?</span></span>](../core/what-is-the-msmq-adapter.md)