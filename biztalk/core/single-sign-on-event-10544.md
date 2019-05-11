---
title: シングル サインオン:イベント 10544 |Microsoft Docs
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
ms.openlocfilehash: 262a57b44143909b40842eddf7b1aba4049ca130
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243506"
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="8f69c-102">シングル サインオン:イベント 10544</span><span class="sxs-lookup"><span data-stu-id="8f69c-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="8f69c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8f69c-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="8f69c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8f69c-104">Product Name</span></span>   |                 <span data-ttu-id="8f69c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8f69c-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="8f69c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8f69c-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="8f69c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8f69c-107">Event ID</span></span>     |                           <span data-ttu-id="8f69c-108">10544</span><span class="sxs-lookup"><span data-stu-id="8f69c-108">10544</span></span>                            |
|  <span data-ttu-id="8f69c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8f69c-109">Event Source</span></span>   |                           <span data-ttu-id="8f69c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8f69c-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="8f69c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8f69c-111">Component</span></span>    |                             <span data-ttu-id="8f69c-112">CO</span><span class="sxs-lookup"><span data-stu-id="8f69c-112">CO</span></span>                             |
|  <span data-ttu-id="8f69c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8f69c-113">Symbolic Name</span></span>  |                  <span data-ttu-id="8f69c-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="8f69c-114">SSO_WARN_TICKET_EXPIRED</span></span>                   |
|  <span data-ttu-id="8f69c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8f69c-115">Message Text</span></span>   | <span data-ttu-id="8f69c-116">チケットが expired.%r</span><span class="sxs-lookup"><span data-stu-id="8f69c-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="8f69c-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="8f69c-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="8f69c-118">説明</span><span class="sxs-lookup"><span data-stu-id="8f69c-118">Explanation</span></span>  
 <span data-ttu-id="8f69c-119">この警告イベントは、アプリケーション チケットのタイムアウトの期限が切れたことを示します。</span><span class="sxs-lookup"><span data-stu-id="8f69c-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="8f69c-120">システム レベルと、アプリケーション レベルの両方では、チケットのタイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f69c-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="8f69c-121">システム レベルとアプリケーション レベルのタイムアウトの両方が指定されている場合は、アプリケーション レベルのタイムアウトが期限の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f69c-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8f69c-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8f69c-122">User Action</span></span>  
 <span data-ttu-id="8f69c-123">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8f69c-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="8f69c-124">チケットが検証される前に期限切れ理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f69c-124">Determine why the ticket expired before being validated.</span></span>  

- <span data-ttu-id="8f69c-125">チケットのタイムアウト値が引き換えるには、時刻にチケットを発行するときに時間まで存続するのに十分な時間であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f69c-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  

  <span data-ttu-id="8f69c-126">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="8f69c-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="8f69c-127">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="8f69c-127">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="8f69c-128">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8f69c-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
