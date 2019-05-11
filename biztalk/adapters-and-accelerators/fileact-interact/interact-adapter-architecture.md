---
title: InterAct アダプターのアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 6c22c68b9167e244e30bd285d2ae39ceaaaa833b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366983"
---
# <a name="interact-adapter-architecture"></a><span data-ttu-id="47618-102">InterAct アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="47618-102">InterAct Adapter Architecture</span></span>
<span data-ttu-id="47618-103">このセクションでは、機能の観点からの対話のプリミティブについて説明します。</span><span class="sxs-lookup"><span data-stu-id="47618-103">This section describes the primitives of InterAct from a functional point of view.</span></span> <span data-ttu-id="47618-104">詳細な構造、構文、およびプリミティブの使用量を SWIFT の参照に記載し、ここでは繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="47618-104">The detailed structure, syntax, and usage for the primitives is well-documented in the SWIFT references, and is not repeated here.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47618-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="47618-105">In This Section</span></span>  
  
-   [<span data-ttu-id="47618-106">InterAct アダプターのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="47618-106">InterAct Adapter Components</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)  
  
-   [<span data-ttu-id="47618-107">業務用 Exchange 用の InterAct アダプターのメッセージ</span><span class="sxs-lookup"><span data-stu-id="47618-107">InterAct Adapter Messages for Business Exchange</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)  
  
-   [<span data-ttu-id="47618-108">InterAct アダプターのクライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47618-108">InterAct Adapter Client Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)  
  
-   [<span data-ttu-id="47618-109">InterAct アダプターのサーバー アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47618-109">InterAct Adapter Server Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)  
  
-   [<span data-ttu-id="47618-110">InterAct アダプターのストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="47618-110">InterAct Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)  
  
-   [<span data-ttu-id="47618-111">InterAct アダプターのセキュリティ アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="47618-111">InterAct Adapter Security Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)  
  
-   [<span data-ttu-id="47618-112">InterAct アダプターのエンド ツー エンドの信頼性の高い配信</span><span class="sxs-lookup"><span data-stu-id="47618-112">InterAct Adapter End-to-End Reliable Delivery</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)  
  
-   [<span data-ttu-id="47618-113">InterAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="47618-113">InterAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)  
  
-   [<span data-ttu-id="47618-114">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="47618-114">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)