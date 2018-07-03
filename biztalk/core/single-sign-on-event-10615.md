---
title: 'シングル サインオン: イベント 10615 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b99f901ba60749386d055ce771beed225e4a18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008467"
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="1a068-102">シングル サインオン: イベント 10615</span><span class="sxs-lookup"><span data-stu-id="1a068-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="1a068-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1a068-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1a068-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1a068-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="1a068-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1a068-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="1a068-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1a068-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="1a068-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1a068-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="1a068-108">10615</span><span class="sxs-lookup"><span data-stu-id="1a068-108">10615</span></span>                                                                                                                          |
|  <span data-ttu-id="1a068-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1a068-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="1a068-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1a068-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="1a068-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1a068-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="1a068-112">なし</span><span class="sxs-lookup"><span data-stu-id="1a068-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="1a068-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1a068-113">Symbolic Name</span></span>  |                                                                                                            <span data-ttu-id="1a068-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a068-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>                                                                                                            |
|  <span data-ttu-id="1a068-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1a068-115">Message Text</span></span>   | <span data-ttu-id="1a068-116">アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。%r</span><span class="sxs-lookup"><span data-stu-id="1a068-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="1a068-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="1a068-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="1a068-118">SSO 管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="1a068-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="1a068-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="1a068-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="1a068-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="1a068-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1a068-121">説明</span><span class="sxs-lookup"><span data-stu-id="1a068-121">Explanation</span></span>  
 <span data-ttu-id="1a068-122">アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a068-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a068-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1a068-123">User Action</span></span>  
 <span data-ttu-id="1a068-124">システム管理者に連絡し、SSO 管理者アカウントのメンバーを探して、この変更を行います。</span><span class="sxs-lookup"><span data-stu-id="1a068-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>