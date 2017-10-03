---
title: "シングル サインオン: イベント 10762 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 487fbeb0f077950605432861a9118eacd93f2c89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10762"></a><span data-ttu-id="cf925-102">シングル サインオン: イベント 10762</span><span class="sxs-lookup"><span data-stu-id="cf925-102">Single Sign-On: Event 10762</span></span>
## <a name="details"></a><span data-ttu-id="cf925-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cf925-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf925-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cf925-104">Product Name</span></span>|<span data-ttu-id="cf925-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cf925-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="cf925-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cf925-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="cf925-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cf925-107">Event ID</span></span>|<span data-ttu-id="cf925-108">10762</span><span class="sxs-lookup"><span data-stu-id="cf925-108">10762</span></span>|  
|<span data-ttu-id="cf925-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cf925-109">Event Source</span></span>|<span data-ttu-id="cf925-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cf925-110">ENTSSO</span></span>|  
|<span data-ttu-id="cf925-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf925-111">Component</span></span>|<span data-ttu-id="cf925-112">なし</span><span class="sxs-lookup"><span data-stu-id="cf925-112">N/A</span></span>|  
|<span data-ttu-id="cf925-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cf925-113">Symbolic Name</span></span>|<span data-ttu-id="cf925-114">ENTSSO_E_WRONG_THREAD</span><span class="sxs-lookup"><span data-stu-id="cf925-114">ENTSSO_E_WRONG_THREAD</span></span>|  
|<span data-ttu-id="cf925-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cf925-115">Message Text</span></span>|<span data-ttu-id="cf925-116">SSO クライアント コンポーネントが不適切なスレッドで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="cf925-116">The SSO client component has been called on the wrong thread.</span></span> <span data-ttu-id="cf925-117">コンポーネントにトランザクションがあるため、現在コンポーネントはスレッドにロックされています。</span><span class="sxs-lookup"><span data-stu-id="cf925-117">It is currently locked to a thread because it has a transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cf925-118">説明</span><span class="sxs-lookup"><span data-stu-id="cf925-118">Explanation</span></span>  
 <span data-ttu-id="cf925-119">コンポーネントは、トランザクションがない場合にのみマルチスレッド化することができます。</span><span class="sxs-lookup"><span data-stu-id="cf925-119">Components can only be multi-threaded when they do not have a transaction.</span></span> <span data-ttu-id="cf925-120">このコンポーネントにはトランザクションがあるので、スレッドにロックされています。</span><span class="sxs-lookup"><span data-stu-id="cf925-120">This component has a transaction so it is locked to a thread.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf925-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cf925-121">User Action</span></span>  
 <span data-ttu-id="cf925-122">トランザクションを使用しているときには複数のスレッドで SSO クライアント コンポーネントを呼び出さないようにアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf925-122">Configure your application so that it will not call SSO client components on multiple threads when using transactions.</span></span>