---
title: アダプターのアーキテクチャの対話 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce7e4b7e-abe4-4db6-b4e0-6f71bd7e5e6f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5634a8ee2bea2e36bcc4d9038a6c89edab56daa3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222834"
---
# <a name="interact-adapter-architecture"></a><span data-ttu-id="136b1-102">アダプターのアーキテクチャを対話します。</span><span class="sxs-lookup"><span data-stu-id="136b1-102">InterAct Adapter Architecture</span></span>
<span data-ttu-id="136b1-103">このセクションでは、対話機能の観点からプリミティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="136b1-103">This section describes the primitives of InterAct from a functional point of view.</span></span> <span data-ttu-id="136b1-104">構造体の詳細な構文、および使用状況、プリミティブを完備 SWIFT の参照し、ここでは繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="136b1-104">The detailed structure, syntax, and usage for the primitives is well-documented in the SWIFT references, and is not repeated here.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="136b1-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="136b1-105">In This Section</span></span>  
  
-   [<span data-ttu-id="136b1-106">InterAct アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="136b1-106">InterAct Adapter Components</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)  
  
-   [<span data-ttu-id="136b1-107">ビジネスの Exchange に対するアダプターのメッセージを相互作用します。</span><span class="sxs-lookup"><span data-stu-id="136b1-107">InterAct Adapter Messages for Business Exchange</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)  
  
-   [<span data-ttu-id="136b1-108">InterAct アダプターのクライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="136b1-108">InterAct Adapter Client Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)  
  
-   [<span data-ttu-id="136b1-109">InterAct アダプタ サーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="136b1-109">InterAct Adapter Server Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)  
  
-   [<span data-ttu-id="136b1-110">アダプター ストア アンド フォワードを対話します。</span><span class="sxs-lookup"><span data-stu-id="136b1-110">InterAct Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)  
  
-   [<span data-ttu-id="136b1-111">アダプターのセキュリティ アーキテクチャを対話します。</span><span class="sxs-lookup"><span data-stu-id="136b1-111">InterAct Adapter Security Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)  
  
-   [<span data-ttu-id="136b1-112">アダプターのエンド ツー エンドの信頼性の高い配信を対話します。</span><span class="sxs-lookup"><span data-stu-id="136b1-112">InterAct Adapter End-to-End Reliable Delivery</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)  
  
-   [<span data-ttu-id="136b1-113">アダプターの状態を操作の監視</span><span class="sxs-lookup"><span data-stu-id="136b1-113">InterAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)  
  
-   [<span data-ttu-id="136b1-114">アダプター否認不可を対話します。</span><span class="sxs-lookup"><span data-stu-id="136b1-114">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)