---
title: "アダプターの状態を操作の監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32cf2f197508c0cd703a05780804c6bc880b5f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-status-monitoring"></a><span data-ttu-id="f048b-102">アダプターの状態を操作の監視</span><span class="sxs-lookup"><span data-stu-id="f048b-102">InterAct Adapter Status Monitoring</span></span>
<span data-ttu-id="f048b-103">SWIFTNet リンク (SNL C) には、SWIFTNet ストアとその SNL に獲得前方の (SnF) セッションに関するローカルの状態が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f048b-103">SWIFTNet Link (SNL-C) retains a local status about SWIFTNet store and forward (SnF) sessions acquired on that SNL.</span></span> <span data-ttu-id="f048b-104">セッションに関する情報を取得するには、するには、次のプリミティブで SwCall() を使用します。</span><span class="sxs-lookup"><span data-stu-id="f048b-104">To get the information about the session, use SwCall() with the following primitive:</span></span>  
  
 <span data-ttu-id="f048b-105">![セッション情報を取得する](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span><span class="sxs-lookup"><span data-stu-id="f048b-105">![Getting session information](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span></span>  
  
 <span data-ttu-id="f048b-106">AuthorizationContext を提供する必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f048b-106">Notice that you are not required to provide an AuthorizationContext.</span></span> <span data-ttu-id="f048b-107">次の図に示すようにローカル SNL に表示される情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="f048b-107">The information seen by the local SNL is returned, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="f048b-108">![セッション状態情報](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span><span class="sxs-lookup"><span data-stu-id="f048b-108">![Session status information](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f048b-109">参照</span><span class="sxs-lookup"><span data-stu-id="f048b-109">See Also</span></span>  
 <span data-ttu-id="f048b-110">[アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-110">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="f048b-111">[InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-111">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="f048b-112">[ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-112">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="f048b-113">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-113">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="f048b-114">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-114">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="f048b-115">[アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="f048b-116">[アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="f048b-117">[アダプターのエンド ツー エンドの信頼性の高い配信を対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="f048b-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 [<span data-ttu-id="f048b-118">アダプター否認不可を対話します。</span><span class="sxs-lookup"><span data-stu-id="f048b-118">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)