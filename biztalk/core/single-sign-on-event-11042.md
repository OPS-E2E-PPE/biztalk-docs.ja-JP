---
title: 'シングル サインオン: イベント 11042 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109678e68c3624cec11c4c9f235063288f342f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985691"
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="a6e8b-102">シングル サインオン: イベント 11042</span><span class="sxs-lookup"><span data-stu-id="a6e8b-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="a6e8b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6e8b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a6e8b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6e8b-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="a6e8b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a6e8b-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="a6e8b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6e8b-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="a6e8b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6e8b-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="a6e8b-108">11042</span><span class="sxs-lookup"><span data-stu-id="a6e8b-108">11042</span></span>                                                                                                                                                             |
|  <span data-ttu-id="a6e8b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6e8b-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="a6e8b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a6e8b-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="a6e8b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6e8b-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="a6e8b-112">なし</span><span class="sxs-lookup"><span data-stu-id="a6e8b-112">N/A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="a6e8b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6e8b-113">Symbolic Name</span></span>  |                                                                                                                                                <span data-ttu-id="a6e8b-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="a6e8b-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>                                                                                                                                                |
|  <span data-ttu-id="a6e8b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6e8b-115">Message Text</span></span>   | <span data-ttu-id="a6e8b-116">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="a6e8b-116">Access denied.</span></span><br /><br /> <span data-ttu-id="a6e8b-117">この機能を実行するには、クライアント ユーザーは次のいずれかのアカウントのメンバーである必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="a6e8b-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="a6e8b-118">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="a6e8b-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="a6e8b-119">SSO 関連管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="a6e8b-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="a6e8b-120">アプリケーション管理者: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="a6e8b-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="a6e8b-121">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="a6e8b-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="a6e8b-122">追加データ: %5</span><span class="sxs-lookup"><span data-stu-id="a6e8b-122">Additional Data: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a6e8b-123">説明</span><span class="sxs-lookup"><span data-stu-id="a6e8b-123">Explanation</span></span>  
 <span data-ttu-id="a6e8b-124">この機能を実行するには、クライアント ユーザーは警告で示されているいずれかのアカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e8b-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6e8b-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6e8b-125">User Action</span></span>  
 <span data-ttu-id="a6e8b-126">この機能を実行するには、いずれかのアカウントに加わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e8b-126">You must join one of the accounts to perform this function.</span></span>