---
title: "シングル サインオン: イベント 10539 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a67f5719-da7c-4ae0-a6fe-ff7b653a184d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ca34f40359b518e1a52b3326dae9917ca4910e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10539"></a><span data-ttu-id="347d2-102">シングル サインオン: イベント 10539</span><span class="sxs-lookup"><span data-stu-id="347d2-102">Single Sign-On: Event 10539</span></span>
## <a name="details"></a><span data-ttu-id="347d2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="347d2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="347d2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="347d2-104">Product Name</span></span>|<span data-ttu-id="347d2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="347d2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="347d2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="347d2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="347d2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="347d2-107">Event ID</span></span>|<span data-ttu-id="347d2-108">10539</span><span class="sxs-lookup"><span data-stu-id="347d2-108">10539</span></span>|  
|<span data-ttu-id="347d2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="347d2-109">Event Source</span></span>|<span data-ttu-id="347d2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="347d2-110">ENTSSO</span></span>|  
|<span data-ttu-id="347d2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="347d2-111">Component</span></span>|<span data-ttu-id="347d2-112">CO</span><span class="sxs-lookup"><span data-stu-id="347d2-112">CO</span></span>|  
|<span data-ttu-id="347d2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="347d2-113">Symbolic Name</span></span>|<span data-ttu-id="347d2-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="347d2-114">SSO_WARN_SSO_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="347d2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="347d2-115">Message Text</span></span>|<span data-ttu-id="347d2-116">SSO システムに対してチケットが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="347d2-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="347d2-117">説明</span><span class="sxs-lookup"><span data-stu-id="347d2-117">Explanation</span></span>  
 <span data-ttu-id="347d2-118">この警告イベントは、SSO チケットの使用が有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="347d2-118">This Warning event indicates that the use of SSO tickets is not enabled.</span></span> <span data-ttu-id="347d2-119">SSO チケットの使用の許可は、SSO システムのオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="347d2-119">Allowing the use of SSO tickets is an optional feature of the SSO system.</span></span> <span data-ttu-id="347d2-120">この機能が SSO システムで有効になっていませんでした。</span><span class="sxs-lookup"><span data-stu-id="347d2-120">This feature has not been enabled on your SSO system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="347d2-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="347d2-121">User Action</span></span>  
 <span data-ttu-id="347d2-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="347d2-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="347d2-123">SSO 管理者に問い合わせて、SSO システムのチケットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="347d2-123">Contact your SSO Administrator to enable tickets for the SSO system.</span></span> <span data-ttu-id="347d2-124">SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="347d2-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="347d2-125">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="347d2-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="347d2-126">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="347d2-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="347d2-127">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="347d2-127">Using SSO</span></span>](../core/using-sso.md)