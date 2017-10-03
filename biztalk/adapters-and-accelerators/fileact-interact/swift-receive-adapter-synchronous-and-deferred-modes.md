---
title: "SWIFT 受信アダプターの同期および遅延モード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 704def2c-ac82-4cdb-9354-609cc8dc1a0d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f85617a75cfbbb7473874760d99d6c550ab2f8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-synchronous-and-deferred-modes"></a><span data-ttu-id="78094-102">SWIFT 受信アダプターの同期および遅延モード</span><span class="sxs-lookup"><span data-stu-id="78094-102">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>
<span data-ttu-id="78094-103">SWIFTNet リンク (SNL) サーバー アプリケーションは、2 つのモードで動作できます。 同期および遅延モード。</span><span class="sxs-lookup"><span data-stu-id="78094-103">SWIFTNet Link (SNL) server applications can operate in two different modes: synchronous and deferred mode.</span></span> <span data-ttu-id="78094-104">同期モードでは、サーバー アプリケーションは、クライアント アプリケーションへのビジネス応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="78094-104">In synchronous mode, the server application sends a business response back to the client application.</span></span> <span data-ttu-id="78094-105">遅延のモードでは、サーバー アプリケーションは、クライアント アプリケーションに技術確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="78094-105">In deferred mode, the server application sends a technical acknowledgement back to the client application.</span></span>  
  
 <span data-ttu-id="78094-106">次の図は、シーケンスを示します。</span><span class="sxs-lookup"><span data-stu-id="78094-106">The following figure shows the sequence.</span></span>  
  
 <span data-ttu-id="78094-107">![受信アダプターの同期および遅延モード](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span><span class="sxs-lookup"><span data-stu-id="78094-107">![Receive adapter synchronous and deferred mode](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span></span>  
  
 <span data-ttu-id="78094-108">次の図は、受信側の高レベルな表現を示しています。</span><span class="sxs-lookup"><span data-stu-id="78094-108">The following figure shows a high level representation of the receive side.</span></span>  
  
 <span data-ttu-id="78094-109">![受信アダプター シナリオ](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span><span class="sxs-lookup"><span data-stu-id="78094-109">![Receive adapter scenario](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78094-110">参照</span><span class="sxs-lookup"><span data-stu-id="78094-110">See Also</span></span>  
 <span data-ttu-id="78094-111">[SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="78094-111">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="78094-112">[SWIFT 受信アダプター URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="78094-112">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="78094-113">[SWIFT 受信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="78094-113">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="78094-114">[SWIFT 受信アダプター セキュリティ コンテキスト](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="78094-114">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="78094-115">SWIFT 受信アダプター ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="78094-115">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)