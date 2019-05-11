---
title: InterAct アダプタ サーバー アプリケーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c50b239-0480-449f-aa6d-50bbb892e8a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28af1e636d00b3a1d7b8cd9afead5dbc3285aabf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366633"
---
# <a name="interact-adapter-server-application"></a><span data-ttu-id="7b382-102">InterAct アダプタ サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7b382-102">InterAct Adapter Server Application</span></span>
<span data-ttu-id="7b382-103">このセクションでは、サーバー アプリケーションの要求メッセージのコンポジションの一般的な説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="7b382-103">This section presents a general description of the composition of server application Request messages.</span></span> <span data-ttu-id="7b382-104">これらは、サーバー側 SNL からサーバー アプリケーションに渡される XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="7b382-104">These are the XML documents passed from the server-side SNL to the server application.</span></span> <span data-ttu-id="7b382-105">そのため、これらのメッセージには、サーバー側で実行される SWIFTNet プリミティブの最初の部分の特性が。</span><span class="sxs-lookup"><span data-stu-id="7b382-105">As such, these messages are characteristic of the first part of the SWIFTNet primitives exercised on the server side.</span></span>  
  
 <span data-ttu-id="7b382-106">次の図は、サーバーに要求メッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="7b382-106">The following figure shows the server request message.</span></span>  
  
 <span data-ttu-id="7b382-107">![サーバー要求メッセージ](../../adapters-and-accelerators/fileact-interact/media/05bf7d1b-199c-4806-be91-32ca013e9af8.gif "05bf7d1b-199c-4806-be91-32ca013e9af8")</span><span class="sxs-lookup"><span data-stu-id="7b382-107">![Server request message](../../adapters-and-accelerators/fileact-interact/media/05bf7d1b-199c-4806-be91-32ca013e9af8.gif "05bf7d1b-199c-4806-be91-32ca013e9af8")</span></span>  
  
 <span data-ttu-id="7b382-108">次の図は、SNL と InterAct サーバー アプリケーション間で交換されるメッセージのシーケンスを示します。</span><span class="sxs-lookup"><span data-stu-id="7b382-108">The following figure shows the sequence of messages exchanged between SNL and the InterAct server application.</span></span>  
  
 <span data-ttu-id="7b382-109">![InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/media/33edb889-edfa-4e55-842a-e238950327e6.gif "33edb889-edfa-4e55-842a-e238950327e6")</span><span class="sxs-lookup"><span data-stu-id="7b382-109">![InterAct adapter server application](../../adapters-and-accelerators/fileact-interact/media/33edb889-edfa-4e55-842a-e238950327e6.gif "33edb889-edfa-4e55-842a-e238950327e6")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b382-110">参照</span><span class="sxs-lookup"><span data-stu-id="7b382-110">See Also</span></span>  
 <span data-ttu-id="7b382-111">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-111">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="7b382-112">[InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-112">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="7b382-113">[業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-113">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="7b382-114">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-114">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="7b382-115">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="7b382-116">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="7b382-117">[アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="7b382-118">[InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="7b382-118">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="7b382-119">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="7b382-119">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)