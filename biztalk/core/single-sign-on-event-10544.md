---
title: 'シングル サインオン: イベント 10544 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1a01cda4272e2851f929c35fd2b767c321a9dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270578"
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="0ed1b-102">シングル サインオン: イベント 10544</span><span class="sxs-lookup"><span data-stu-id="0ed1b-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="0ed1b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0ed1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ed1b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0ed1b-104">Product Name</span></span>|<span data-ttu-id="0ed1b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0ed1b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0ed1b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0ed1b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0ed1b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0ed1b-107">Event ID</span></span>|<span data-ttu-id="0ed1b-108">10544</span><span class="sxs-lookup"><span data-stu-id="0ed1b-108">10544</span></span>|  
|<span data-ttu-id="0ed1b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0ed1b-109">Event Source</span></span>|<span data-ttu-id="0ed1b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0ed1b-110">ENTSSO</span></span>|  
|<span data-ttu-id="0ed1b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0ed1b-111">Component</span></span>|<span data-ttu-id="0ed1b-112">CO</span><span class="sxs-lookup"><span data-stu-id="0ed1b-112">CO</span></span>|  
|<span data-ttu-id="0ed1b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0ed1b-113">Symbolic Name</span></span>|<span data-ttu-id="0ed1b-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="0ed1b-114">SSO_WARN_TICKET_EXPIRED</span></span>|  
|<span data-ttu-id="0ed1b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0ed1b-115">Message Text</span></span>|<span data-ttu-id="0ed1b-116">チケットの有効期限が切れました。%r</span><span class="sxs-lookup"><span data-stu-id="0ed1b-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="0ed1b-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="0ed1b-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ed1b-118">説明</span><span class="sxs-lookup"><span data-stu-id="0ed1b-118">Explanation</span></span>  
 <span data-ttu-id="0ed1b-119">この警告イベントは、アプリケーション チケットのタイムアウトの期限が切れたことを示します。</span><span class="sxs-lookup"><span data-stu-id="0ed1b-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="0ed1b-120">チケットのタイムアウトは、システム レベルと、アプリケーション レベルの両方で指定できます。</span><span class="sxs-lookup"><span data-stu-id="0ed1b-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="0ed1b-121">システム レベルとアプリケーション レベルの両方でタイムアウトが指定されている場合、アプリケーション レベルのタイムアウトが有効期限の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ed1b-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ed1b-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0ed1b-122">User Action</span></span>  
 <span data-ttu-id="0ed1b-123">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="0ed1b-123">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="0ed1b-124">チケットが検証される前に期限切れになった理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="0ed1b-124">Determine why the ticket expired before being validated.</span></span>  
  
-   <span data-ttu-id="0ed1b-125">チケットのタイムアウト値がチケットの発行時からチケットの引き換え時まで存続するのに十分な長さであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ed1b-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  
  
 <span data-ttu-id="0ed1b-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="0ed1b-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="0ed1b-127">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="0ed1b-127">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="0ed1b-128">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0ed1b-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)