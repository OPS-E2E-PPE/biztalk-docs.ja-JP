---
title: シングル サインオン:イベント 10585 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfca6095e57936df056558e84ec0ed8ecdb8b002
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530942"
---
# <a name="single-sign-on-event-10585"></a><span data-ttu-id="9589a-102">シングル サインオン:イベント 10585</span><span class="sxs-lookup"><span data-stu-id="9589a-102">Single Sign-On: Event 10585</span></span>
## <a name="details"></a><span data-ttu-id="9589a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9589a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9589a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9589a-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="9589a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9589a-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="9589a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9589a-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="9589a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9589a-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="9589a-108">10585</span><span class="sxs-lookup"><span data-stu-id="9589a-108">10585</span></span>                                                                                           |
|  <span data-ttu-id="9589a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9589a-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="9589a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9589a-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="9589a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9589a-111">Component</span></span>    |                                                                                            <span data-ttu-id="9589a-112">なし</span><span class="sxs-lookup"><span data-stu-id="9589a-112">N/A</span></span>                                                                                            |
|  <span data-ttu-id="9589a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9589a-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="9589a-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span><span class="sxs-lookup"><span data-stu-id="9589a-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span></span>                                                                              |
|  <span data-ttu-id="9589a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9589a-115">Message Text</span></span>   | <span data-ttu-id="9589a-116">チケットのタイムアウト期間の有効期限が切れた後にチケットの引き換えがされています。</span><span class="sxs-lookup"><span data-stu-id="9589a-116">A ticket is being redeemed after the ticket time-out period has expired.</span></span> <span data-ttu-id="9589a-117">この application.%r チケットのタイムアウト値が無効になっているため、これは、許可は、</span><span class="sxs-lookup"><span data-stu-id="9589a-117">This is allowed because the ticket time-out is disabled for this application.%r</span></span><br /><br /> <span data-ttu-id="9589a-118">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="9589a-118">Application Name: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9589a-119">説明</span><span class="sxs-lookup"><span data-stu-id="9589a-119">Explanation</span></span>  
 <span data-ttu-id="9589a-120">チケットのタイムアウトを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9589a-120">Ticket time-out can be enabled or disabled.</span></span> <span data-ttu-id="9589a-121">ここで、チケット引き換えが行われて、タイムアウト期間の有効期限が切れている場合でも、タイムアウトが無効です。</span><span class="sxs-lookup"><span data-stu-id="9589a-121">In this case a ticket is being redeemed even though its time-out period has expired, because the time-out is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9589a-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9589a-122">User Action</span></span>  
 <span data-ttu-id="9589a-123">タイムアウトが無効にすることになって、ユーザーの操作の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9589a-123">If the time-out was supposed to be disabled, no user action is required.</span></span> <span data-ttu-id="9589a-124">ただし、この特定のアプリケーションは、タイムアウトが無効であるが認識されなかった場合は、アプリケーションをチェックことを許可することを確認してすぐに。</span><span class="sxs-lookup"><span data-stu-id="9589a-124">However, if you were not aware that this particular application had its time-out disabled, check the application immediately to be sure you want to allow it.</span></span>