---
title: InterAct アダプターの状態の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540923098d57fd508e8071daa9febc7b3eeb8c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366616"
---
# <a name="interact-adapter-status-monitoring"></a><span data-ttu-id="0408d-102">InterAct アダプターの状態の監視</span><span class="sxs-lookup"><span data-stu-id="0408d-102">InterAct Adapter Status Monitoring</span></span>
<span data-ttu-id="0408d-103">SWIFTNet リンク (SNL C) は、SWIFTNet ストアとその SNL に獲得前方の (SnF) セッションに関するローカルの状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="0408d-103">SWIFTNet Link (SNL-C) retains a local status about SWIFTNet store and forward (SnF) sessions acquired on that SNL.</span></span> <span data-ttu-id="0408d-104">セッションに関する情報を取得するには、次のプリミティブを SwCall() を使用します。</span><span class="sxs-lookup"><span data-stu-id="0408d-104">To get the information about the session, use SwCall() with the following primitive:</span></span>  
  
 <span data-ttu-id="0408d-105">![セッション情報を取得する](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span><span class="sxs-lookup"><span data-stu-id="0408d-105">![Getting session information](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span></span>  
  
 <span data-ttu-id="0408d-106">AuthorizationContext を提供する必要はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0408d-106">Notice that you are not required to provide an AuthorizationContext.</span></span> <span data-ttu-id="0408d-107">次の図に示すようにローカル SNL に表示される情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="0408d-107">The information seen by the local SNL is returned, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="0408d-108">![セッション状態の情報](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span><span class="sxs-lookup"><span data-stu-id="0408d-108">![Session status information](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0408d-109">参照</span><span class="sxs-lookup"><span data-stu-id="0408d-109">See Also</span></span>  
 <span data-ttu-id="0408d-110">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-110">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="0408d-111">[InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-111">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="0408d-112">[業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-112">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="0408d-113">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-113">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="0408d-114">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-114">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="0408d-115">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="0408d-116">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="0408d-117">[アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="0408d-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 [<span data-ttu-id="0408d-118">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="0408d-118">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)