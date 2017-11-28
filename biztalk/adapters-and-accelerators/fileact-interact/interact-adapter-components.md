---
title: "InterAct アダプター コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-components"></a><span data-ttu-id="1f595-102">InterAct アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f595-102">InterAct Adapter Components</span></span>
<span data-ttu-id="1f595-103">InterAct アダプターには、クライアントとサーバー コンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="1f595-103">The InterAct adapter has a client and a server component.</span></span> <span data-ttu-id="1f595-104">含まれていること、A4SWIFT の (最小) インストール SWIFT Alliance ゲートウェイ (SAG) と同じコンピューターに Windows Server が実行されている場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f595-104">Note that there may be an A4SWIFT (minimal) installation on the same computer as the SWIFT Alliance Gateway (SAG) if it is running Windows Server.</span></span> <span data-ttu-id="1f595-105">SWIFTNet リンク (SNL) が、SAG から別のコンピューターにする可能性があるにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="1f595-105">Also note that the SWIFTNet Link (SNL) may be on a separate computer from the SAG.</span></span> <span data-ttu-id="1f595-106">プログラミング インターフェイス (API) のホスト アダプター SWIFT によって提供されるリモート アプリケーションは、コンポーネントの場所に関係なく、SAG A4SWIFT から通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f595-106">The remote application programming interface (API) host adapter provided by SWIFT is used to communicate from A4SWIFT to the SAG, regardless of the location of the components.</span></span>  
  
 <span data-ttu-id="1f595-107">次の図は、InterAct アダプターに関連する全体のアダプターとの通信のチェーンを構成するには、コンポーネントが存在する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="1f595-107">The figure below shows where the components comprising the entire adapter and communications chain related to the InterAct adapter reside.</span></span>  
  
 <span data-ttu-id="1f595-108">![InterAct コンポーネント](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span><span class="sxs-lookup"><span data-stu-id="1f595-108">![InterAct components](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span></span>  
  
 <span data-ttu-id="1f595-109">次の図では、クライアント アプリケーションは、A4SWIFT および InterAct アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f595-109">In the following figure, the client application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="1f595-110">BizTalk Server は、ミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信する、します。</span><span class="sxs-lookup"><span data-stu-id="1f595-110">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="1f595-111">![InterAct クライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span><span class="sxs-lookup"><span data-stu-id="1f595-111">![InterAct client application](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span></span>  
  
 <span data-ttu-id="1f595-112">次の図では、サーバー アプリケーションは、A4SWIFT および InterAct アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f595-112">In the following figure, the server application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="1f595-113">BizTalk Server は、ミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信する、します。</span><span class="sxs-lookup"><span data-stu-id="1f595-113">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="1f595-114">![InterAct サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span><span class="sxs-lookup"><span data-stu-id="1f595-114">![InterAct server application](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f595-115">参照</span><span class="sxs-lookup"><span data-stu-id="1f595-115">See Also</span></span>  
 <span data-ttu-id="1f595-116">[アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-116">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="1f595-117">[ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-117">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="1f595-118">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-118">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="1f595-119">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-119">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="1f595-120">[アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-120">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="1f595-121">[アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-121">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="1f595-122">[アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-122">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="1f595-123">[アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="1f595-123">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="1f595-124">アダプター否認不可を対話します。</span><span class="sxs-lookup"><span data-stu-id="1f595-124">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)