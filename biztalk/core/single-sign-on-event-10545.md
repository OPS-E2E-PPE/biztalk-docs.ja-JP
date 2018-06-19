---
title: 'シングル サインオン: イベント 10545 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270650"
---
# <a name="single-sign-on-event-10545"></a><span data-ttu-id="68bd8-102">シングル サインオン: イベント 10545</span><span class="sxs-lookup"><span data-stu-id="68bd8-102">Single Sign-On: Event 10545</span></span>
## <a name="details"></a><span data-ttu-id="68bd8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68bd8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68bd8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68bd8-104">Product Name</span></span>|<span data-ttu-id="68bd8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="68bd8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="68bd8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68bd8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="68bd8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68bd8-107">Event ID</span></span>|<span data-ttu-id="68bd8-108">10545</span><span class="sxs-lookup"><span data-stu-id="68bd8-108">10545</span></span>|  
|<span data-ttu-id="68bd8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68bd8-109">Event Source</span></span>|<span data-ttu-id="68bd8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="68bd8-110">ENTSSO</span></span>|  
|<span data-ttu-id="68bd8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68bd8-111">Component</span></span>|<span data-ttu-id="68bd8-112">CO</span><span class="sxs-lookup"><span data-stu-id="68bd8-112">CO</span></span>|  
|<span data-ttu-id="68bd8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68bd8-113">Symbolic Name</span></span>|<span data-ttu-id="68bd8-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="68bd8-114">SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="68bd8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68bd8-115">Message Text</span></span>|<span data-ttu-id="68bd8-116">SSO システムに対してチケットが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="68bd8-116">Tickets are not enabled for the SSO system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68bd8-117">説明</span><span class="sxs-lookup"><span data-stu-id="68bd8-117">Explanation</span></span>  
 <span data-ttu-id="68bd8-118">この警告イベントは、チケットが SSO システムについて有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="68bd8-118">This Warning event indicates that tickets are not enabled for the SSO System.</span></span> <span data-ttu-id="68bd8-119">チケットをシステム レベルで無効にすると、関連アプリケーション レベルでもチケットを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="68bd8-119">If ticketing is disabled at the system level, ticketing cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="68bd8-120">チケットをシステム レベルで有効にして、関連アプリケーション レベルで無効にすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="68bd8-120">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68bd8-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68bd8-121">User Action</span></span>  
 <span data-ttu-id="68bd8-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="68bd8-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="68bd8-123">SSO システム レベルでチケットを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68bd8-123">Enable tickets at the SSO System level.</span></span>  
  
 <span data-ttu-id="68bd8-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="68bd8-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="68bd8-125">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="68bd8-125">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="68bd8-126">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="68bd8-126">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)