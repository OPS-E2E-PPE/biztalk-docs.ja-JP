---
title: SWIFT 送信アダプターの動的送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 105972fe-9dc0-480a-a4d1-2ec682fa7ad9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5161c47011a5239435739d08783e3da6f2547aaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364191"
---
# <a name="swift-send-adapter-dynamic-send"></a><span data-ttu-id="d8f72-102">SWIFT 送信アダプターの動的送信</span><span class="sxs-lookup"><span data-stu-id="d8f72-102">SWIFT Send Adapter Dynamic Send</span></span>
<span data-ttu-id="d8f72-103">送信アダプターの動的な送信モードでは、キューからメッセージをプルします。</span><span class="sxs-lookup"><span data-stu-id="d8f72-103">The send adapter dynamic send mode pulls messages from the queue.</span></span> <span data-ttu-id="d8f72-104">動的送信のための URI です。</span><span class="sxs-lookup"><span data-stu-id="d8f72-104">The URI for dynamic send is:</span></span>  
  
```  
SWIFT://<queue name>/<Force Acquire>/<Session Mode>/<Order By>/<Recovery mode>  
```  
  
 <span data-ttu-id="d8f72-105">オーケストレーションまたはパイプラインを使用すると、URI を構築します。</span><span class="sxs-lookup"><span data-stu-id="d8f72-105">You can use an orchestration or a pipeline to construct the URI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f72-106">参照</span><span class="sxs-lookup"><span data-stu-id="d8f72-106">See Also</span></span>  
 <span data-ttu-id="d8f72-107">[SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d8f72-107">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 <span data-ttu-id="d8f72-108">[SWIFT 送信アダプターの URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="d8f72-108">[SWIFT Send Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md) </span></span>  
 <span data-ttu-id="d8f72-109">[SWIFT 送信アダプターの初期化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="d8f72-109">[SWIFT Send Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md) </span></span>  
 <span data-ttu-id="d8f72-110">[SWIFT 送信アダプター同期モード](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d8f72-110">[SWIFT Send Adapter Synchronous Mode](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md) </span></span>  
 [<span data-ttu-id="d8f72-111">SWIFT 送信アダプターの終了</span><span class="sxs-lookup"><span data-stu-id="d8f72-111">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)