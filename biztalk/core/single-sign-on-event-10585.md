---
title: 'シングル サインオン: イベント 10585 |Microsoft Docs'
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
ms.openlocfilehash: a423ae8ca3328b2e3846c953036ae70aa6ff4f05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966835"
---
# <a name="single-sign-on-event-10585"></a><span data-ttu-id="3c93f-102">シングル サインオン: イベント 10585</span><span class="sxs-lookup"><span data-stu-id="3c93f-102">Single Sign-On: Event 10585</span></span>
## <a name="details"></a><span data-ttu-id="3c93f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3c93f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c93f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3c93f-104">Product Name</span></span>   |                                                                                 <span data-ttu-id="3c93f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3c93f-105">Enterprise Single Sign-On</span></span>                                                                                 |
| <span data-ttu-id="3c93f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3c93f-106">Product Version</span></span> |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    <span data-ttu-id="3c93f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3c93f-107">Event ID</span></span>     |                                                                                           <span data-ttu-id="3c93f-108">10585</span><span class="sxs-lookup"><span data-stu-id="3c93f-108">10585</span></span>                                                                                           |
|  <span data-ttu-id="3c93f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3c93f-109">Event Source</span></span>   |                                                                                          <span data-ttu-id="3c93f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c93f-110">ENTSSO</span></span>                                                                                           |
|    <span data-ttu-id="3c93f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3c93f-111">Component</span></span>    |                                                                                            <span data-ttu-id="3c93f-112">なし</span><span class="sxs-lookup"><span data-stu-id="3c93f-112">N/A</span></span>                                                                                            |
|  <span data-ttu-id="3c93f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3c93f-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="3c93f-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span><span class="sxs-lookup"><span data-stu-id="3c93f-114">SSO_WARN_EXPIRED_TICKET_REDEEMED</span></span>                                                                              |
|  <span data-ttu-id="3c93f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3c93f-115">Message Text</span></span>   | <span data-ttu-id="3c93f-116">チケットのタイムアウト期間が経過した後に、チケットの引き換えが行われています。</span><span class="sxs-lookup"><span data-stu-id="3c93f-116">A ticket is being redeemed after the ticket time-out period has expired.</span></span> <span data-ttu-id="3c93f-117">このアプリケーションについてチケットのタイムアウトが無効になっているので、この処理は許可されます。%r</span><span class="sxs-lookup"><span data-stu-id="3c93f-117">This is allowed because the ticket time-out is disabled for this application.%r</span></span><br /><br /> <span data-ttu-id="3c93f-118">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="3c93f-118">Application Name: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3c93f-119">説明</span><span class="sxs-lookup"><span data-stu-id="3c93f-119">Explanation</span></span>  
 <span data-ttu-id="3c93f-120">チケットのタイムアウトは有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3c93f-120">Ticket time-out can be enabled or disabled.</span></span> <span data-ttu-id="3c93f-121">この場合、タイムアウトが無効になっているので、チケットのタイムアウト期間が経過した後でも、チケットの引き換えが実行されています。</span><span class="sxs-lookup"><span data-stu-id="3c93f-121">In this case a ticket is being redeemed even though its time-out period has expired, because the time-out is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c93f-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3c93f-122">User Action</span></span>  
 <span data-ttu-id="3c93f-123">タイムアウトが無効であることが想定されている場合、ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3c93f-123">If the time-out was supposed to be disabled, no user action is required.</span></span> <span data-ttu-id="3c93f-124">ただし、この特定のアプリケーションでタイムアウトが無効であったかどうかがわからない場合は、すぐにアプリケーションを調べてこれを許可することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c93f-124">However, if you were not aware that this particular application had its time-out disabled, check the application immediately to be sure you want to allow it.</span></span>