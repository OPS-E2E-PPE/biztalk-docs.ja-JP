---
title: シングル サインオン:イベント 10612 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9d9e6f5-06b8-4989-a0dc-6e2e5980443b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b73a601e883f651b5333224c557a1344d32943c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397712"
---
# <a name="single-sign-on-event-10612"></a><span data-ttu-id="67085-102">シングル サインオン:イベント 10612</span><span class="sxs-lookup"><span data-stu-id="67085-102">Single Sign-On: Event 10612</span></span>
## <a name="details"></a><span data-ttu-id="67085-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67085-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67085-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67085-104">Product Name</span></span>   |                                                                                                                            <span data-ttu-id="67085-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="67085-105">Enterprise Single Sign-On</span></span>                                                                                                                            |
| <span data-ttu-id="67085-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67085-106">Product Version</span></span> |                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                            |
|    <span data-ttu-id="67085-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67085-107">Event ID</span></span>     |                                                                                                                                      <span data-ttu-id="67085-108">10612</span><span class="sxs-lookup"><span data-stu-id="67085-108">10612</span></span>                                                                                                                                      |
|  <span data-ttu-id="67085-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67085-109">Event Source</span></span>   |                                                                                                                                     <span data-ttu-id="67085-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67085-110">ENTSSO</span></span>                                                                                                                                      |
|    <span data-ttu-id="67085-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67085-111">Component</span></span>    |                                                                                                                                       <span data-ttu-id="67085-112">なし</span><span class="sxs-lookup"><span data-stu-id="67085-112">N/A</span></span>                                                                                                                                       |
|  <span data-ttu-id="67085-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67085-113">Symbolic Name</span></span>  |                                                                                                                          <span data-ttu-id="67085-114">SSO_WARN_TRANSACTION_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67085-114">SSO_WARN_TRANSACTION_TIMEOUT</span></span>                                                                                                                           |
|  <span data-ttu-id="67085-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67085-115">Message Text</span></span>   | <span data-ttu-id="67085-116">トランザクションのタイムアウトは、この操作に推奨される最大値を超えています。</span><span class="sxs-lookup"><span data-stu-id="67085-116">The transaction time-out exceeds the recommended maximum for this operation.</span></span> <span data-ttu-id="67085-117">Details.%r のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="67085-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="67085-118">トランザクション ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="67085-118">Transaction ID: %1%r</span></span><br /><br /> <span data-ttu-id="67085-119">トランザクションのタイムアウト: %2 分 (0 には、無限のタイムアウトことを示します) %r</span><span class="sxs-lookup"><span data-stu-id="67085-119">Transaction time-out: %2 minutes (zero indicates an infinite time-out)%r</span></span><br /><br /> <span data-ttu-id="67085-120">推奨される最大値: %3 分</span><span class="sxs-lookup"><span data-stu-id="67085-120">Recommended maximum: %3 minutes</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="67085-121">説明</span><span class="sxs-lookup"><span data-stu-id="67085-121">Explanation</span></span>  
 <span data-ttu-id="67085-122">トランザクションには、非常に大きなタイムアウト値を持つシステムが入力されます。</span><span class="sxs-lookup"><span data-stu-id="67085-122">A transaction has entered the system with an exceedingly large timeout value.</span></span> <span data-ttu-id="67085-123">場合は、ENTSSO システムは、実行時間の長いトランザクションによってロックされている SSO データベースをポーリングし、システムは最終的にオフラインになります。</span><span class="sxs-lookup"><span data-stu-id="67085-123">If the ENTSSO system polls the SSO database while it’s locked by a long-running transaction, the system will eventually go offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67085-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67085-124">User Action</span></span>  
 <span data-ttu-id="67085-125">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="67085-125">No user action is required.</span></span>