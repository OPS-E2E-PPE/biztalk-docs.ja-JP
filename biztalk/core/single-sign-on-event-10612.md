---
title: "シングル サインオン: イベント 10612 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85361bf9946efc283683d41ed0d08187e4d8754
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10612"></a><span data-ttu-id="6ba83-102">シングル サインオン: イベント 10612</span><span class="sxs-lookup"><span data-stu-id="6ba83-102">Single Sign-On: Event 10612</span></span>
## <a name="details"></a><span data-ttu-id="6ba83-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6ba83-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ba83-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6ba83-104">Product Name</span></span>|<span data-ttu-id="6ba83-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6ba83-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6ba83-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6ba83-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6ba83-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6ba83-107">Event ID</span></span>|<span data-ttu-id="6ba83-108">10612</span><span class="sxs-lookup"><span data-stu-id="6ba83-108">10612</span></span>|  
|<span data-ttu-id="6ba83-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6ba83-109">Event Source</span></span>|<span data-ttu-id="6ba83-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6ba83-110">ENTSSO</span></span>|  
|<span data-ttu-id="6ba83-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6ba83-111">Component</span></span>|<span data-ttu-id="6ba83-112">なし</span><span class="sxs-lookup"><span data-stu-id="6ba83-112">N/A</span></span>|  
|<span data-ttu-id="6ba83-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6ba83-113">Symbolic Name</span></span>|<span data-ttu-id="6ba83-114">SSO_WARN_TRANSACTION_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ba83-114">SSO_WARN_TRANSACTION_TIMEOUT</span></span>|  
|<span data-ttu-id="6ba83-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6ba83-115">Message Text</span></span>|<span data-ttu-id="6ba83-116">トランザクションのタイムアウト値が、この操作で推奨される最大値を超えています。</span><span class="sxs-lookup"><span data-stu-id="6ba83-116">The transaction time-out exceeds the recommended maximum for this operation.</span></span> <span data-ttu-id="6ba83-117">Details.%r のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ba83-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="6ba83-118">トランザクション ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6ba83-118">Transaction ID: %1%r</span></span><br /><br /> <span data-ttu-id="6ba83-119">トランザクションのタイムアウト: %2 分 (0 は、無限のタイムアウトを示します) %r</span><span class="sxs-lookup"><span data-stu-id="6ba83-119">Transaction time-out: %2 minutes (zero indicates an infinite time-out)%r</span></span><br /><br /> <span data-ttu-id="6ba83-120">推奨される最大値: %3 分</span><span class="sxs-lookup"><span data-stu-id="6ba83-120">Recommended maximum: %3 minutes</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6ba83-121">説明</span><span class="sxs-lookup"><span data-stu-id="6ba83-121">Explanation</span></span>  
 <span data-ttu-id="6ba83-122">非常に大きなタイムアウト値が設定されたトランザクションがシステムで処理されています。</span><span class="sxs-lookup"><span data-stu-id="6ba83-122">A transaction has entered the system with an exceedingly large timeout value.</span></span> <span data-ttu-id="6ba83-123">実行時間の長いトランザクションによってロックされているときに ENTSSO システムが SSO データベースをポーリングした場合、システムは最終的にはオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="6ba83-123">If the ENTSSO system polls the SSO database while it’s locked by a long-running transaction, the system will eventually go offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6ba83-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6ba83-124">User Action</span></span>  
 <span data-ttu-id="6ba83-125">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="6ba83-125">No user action is required.</span></span>