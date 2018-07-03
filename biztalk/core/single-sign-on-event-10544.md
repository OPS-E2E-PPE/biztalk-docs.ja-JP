---
title: 'シングル サインオン: イベント 10544 |Microsoft Docs'
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
ms.openlocfilehash: f476e664d50d05a57f42006ec08aa03d901e9f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983931"
---
# <a name="single-sign-on-event-10544"></a><span data-ttu-id="a1410-102">シングル サインオン: イベント 10544</span><span class="sxs-lookup"><span data-stu-id="a1410-102">Single Sign-On: Event 10544</span></span>
## <a name="details"></a><span data-ttu-id="a1410-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a1410-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="a1410-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a1410-104">Product Name</span></span>   |                 <span data-ttu-id="a1410-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a1410-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="a1410-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a1410-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="a1410-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a1410-107">Event ID</span></span>     |                           <span data-ttu-id="a1410-108">10544</span><span class="sxs-lookup"><span data-stu-id="a1410-108">10544</span></span>                            |
|  <span data-ttu-id="a1410-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a1410-109">Event Source</span></span>   |                           <span data-ttu-id="a1410-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a1410-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="a1410-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a1410-111">Component</span></span>    |                             <span data-ttu-id="a1410-112">CO</span><span class="sxs-lookup"><span data-stu-id="a1410-112">CO</span></span>                             |
|  <span data-ttu-id="a1410-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a1410-113">Symbolic Name</span></span>  |                  <span data-ttu-id="a1410-114">SSO_WARN_TICKET_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="a1410-114">SSO_WARN_TICKET_EXPIRED</span></span>                   |
|  <span data-ttu-id="a1410-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a1410-115">Message Text</span></span>   | <span data-ttu-id="a1410-116">チケットの有効期限が切れました。%r</span><span class="sxs-lookup"><span data-stu-id="a1410-116">The ticket has expired.%r</span></span><br /><br /> <span data-ttu-id="a1410-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="a1410-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="a1410-118">説明</span><span class="sxs-lookup"><span data-stu-id="a1410-118">Explanation</span></span>  
 <span data-ttu-id="a1410-119">この警告イベントは、アプリケーション チケットのタイムアウトの期限が切れたことを示します。</span><span class="sxs-lookup"><span data-stu-id="a1410-119">This Warning event indicates that an application ticket timeout has expired.</span></span> <span data-ttu-id="a1410-120">システム レベルと、アプリケーション レベルの両方では、チケットのタイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a1410-120">Ticket timeout can be specified at both the system level and the application level.</span></span> <span data-ttu-id="a1410-121">システム レベルとアプリケーション レベルの両方でタイムアウトが指定されている場合、アプリケーション レベルのタイムアウトが有効期限の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1410-121">If both system level and the application level timeout are specified, the application level timeout is used to determine the expiry time.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a1410-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a1410-122">User Action</span></span>  
 <span data-ttu-id="a1410-123">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="a1410-123">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="a1410-124">チケットが検証される前に期限切れになった理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="a1410-124">Determine why the ticket expired before being validated.</span></span>  

- <span data-ttu-id="a1410-125">チケットのタイムアウト値がチケットの発行時からチケットの引き換え時まで存続するのに十分な長さであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1410-125">Ensure that the Ticket timeout value is long enough to last between the time when the ticket is issued to the time that it is redeemed.</span></span>  

  <span data-ttu-id="a1410-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="a1410-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a1410-127">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="a1410-127">SSO Tickets</span></span>](../core/sso-tickets.md)  

- [<span data-ttu-id="a1410-128">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a1410-128">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)
