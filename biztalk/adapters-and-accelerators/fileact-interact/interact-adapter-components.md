---
title: InterAct アダプターのコンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28effe3955d273e3164d34eb46f8ad947e798907
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366930"
---
# <a name="interact-adapter-components"></a><span data-ttu-id="55ec9-102">InterAct アダプターのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="55ec9-102">InterAct Adapter Components</span></span>
<span data-ttu-id="55ec9-103">InterAct アダプターには、クライアントとサーバー コンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="55ec9-103">The InterAct adapter has a client and a server component.</span></span> <span data-ttu-id="55ec9-104">含まれていること、A4SWIFT の (最小) インストール SWIFT Alliance ゲートウェイ (SAG) と同じコンピューターに Windows Server が実行されている場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="55ec9-104">Note that there may be an A4SWIFT (minimal) installation on the same computer as the SWIFT Alliance Gateway (SAG) if it is running Windows Server.</span></span> <span data-ttu-id="55ec9-105">また SWIFTNet リンク (SNL) は、SAG から別のコンピューターにありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="55ec9-105">Also note that the SWIFTNet Link (SNL) may be on a separate computer from the SAG.</span></span> <span data-ttu-id="55ec9-106">プログラミング インターフェイス (API) のホスト アダプター SWIFT によって提供されるリモート アプリケーションは、A4SWIFT からコンポーネントの場所に関係なく、SAG への通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="55ec9-106">The remote application programming interface (API) host adapter provided by SWIFT is used to communicate from A4SWIFT to the SAG, regardless of the location of the components.</span></span>  
  
 <span data-ttu-id="55ec9-107">InterAct アダプターに関連する全体のアダプターとの通信のチェーンを構成するコンポーネントが置かれている場所を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="55ec9-107">The figure below shows where the components comprising the entire adapter and communications chain related to the InterAct adapter reside.</span></span>  
  
 <span data-ttu-id="55ec9-108">![InterAct コンポーネント](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span><span class="sxs-lookup"><span data-stu-id="55ec9-108">![InterAct components](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span></span>  
  
 <span data-ttu-id="55ec9-109">次の図では、クライアント アプリケーションは、A4SWIFT と InterAct アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="55ec9-109">In the following figure, the client application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="55ec9-110">BizTalk Server は、このミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信します。</span><span class="sxs-lookup"><span data-stu-id="55ec9-110">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="55ec9-111">![InterAct クライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span><span class="sxs-lookup"><span data-stu-id="55ec9-111">![InterAct client application](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span></span>  
  
 <span data-ttu-id="55ec9-112">次の図では、サーバー アプリケーションは、A4SWIFT と InterAct アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="55ec9-112">In the following figure, the server application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="55ec9-113">BizTalk Server は、このミドルウェアは、TCPIP を介してリモート API ホスト アダプターと通信します。</span><span class="sxs-lookup"><span data-stu-id="55ec9-113">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="55ec9-114">![InterAct サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span><span class="sxs-lookup"><span data-stu-id="55ec9-114">![InterAct server application](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ec9-115">参照</span><span class="sxs-lookup"><span data-stu-id="55ec9-115">See Also</span></span>  
 <span data-ttu-id="55ec9-116">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-116">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="55ec9-117">[業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-117">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="55ec9-118">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-118">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="55ec9-119">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-119">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="55ec9-120">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-120">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="55ec9-121">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-121">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="55ec9-122">[アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-122">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="55ec9-123">[InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="55ec9-123">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="55ec9-124">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="55ec9-124">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)