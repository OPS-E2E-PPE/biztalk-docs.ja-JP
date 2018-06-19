---
title: 'シングル サインオン: イベント 10579 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e18f6d-9dda-49bf-a901-bb28f4cd9a84
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85d6860e47fc6a1faf62229a721ab570d0ddd0fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270842"
---
# <a name="single-sign-on-event-10579"></a><span data-ttu-id="c1e1b-102">シングル サインオン: イベント 10579</span><span class="sxs-lookup"><span data-stu-id="c1e1b-102">Single Sign-On: Event 10579</span></span>
## <a name="details"></a><span data-ttu-id="c1e1b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c1e1b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1e1b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c1e1b-104">Product Name</span></span>|<span data-ttu-id="c1e1b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c1e1b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c1e1b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c1e1b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c1e1b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c1e1b-107">Event ID</span></span>|<span data-ttu-id="c1e1b-108">10579</span><span class="sxs-lookup"><span data-stu-id="c1e1b-108">10579</span></span>|  
|<span data-ttu-id="c1e1b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c1e1b-109">Event Source</span></span>|<span data-ttu-id="c1e1b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c1e1b-110">ENTSSO</span></span>|  
|<span data-ttu-id="c1e1b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c1e1b-111">Component</span></span>|<span data-ttu-id="c1e1b-112">なし</span><span class="sxs-lookup"><span data-stu-id="c1e1b-112">N/A</span></span>|  
|<span data-ttu-id="c1e1b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c1e1b-113">Symbolic Name</span></span>|<span data-ttu-id="c1e1b-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="c1e1b-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="c1e1b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c1e1b-115">Message Text</span></span>|<span data-ttu-id="c1e1b-116">アプリケーション管理者アカウントが更新されました。%r</span><span class="sxs-lookup"><span data-stu-id="c1e1b-116">Updated Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="c1e1b-117">新しいアプリケーション管理者: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c1e1b-117">New Application Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="c1e1b-118">古いアプリケーション管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c1e1b-118">Old Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="c1e1b-119">追跡 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c1e1b-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="c1e1b-120">クライアント ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c1e1b-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="c1e1b-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="c1e1b-121">Application Name: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c1e1b-122">説明</span><span class="sxs-lookup"><span data-stu-id="c1e1b-122">Explanation</span></span>  
 <span data-ttu-id="c1e1b-123">これは情報メッセージであり、SSO システム内で発生する重要なセキュリティ関連イベントの追跡に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="c1e1b-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="c1e1b-124">このメッセージは、アプリケーション管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c1e1b-124">This message states that the Application Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1e1b-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c1e1b-125">User Action</span></span>  
 <span data-ttu-id="c1e1b-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="c1e1b-126">No user action is required.</span></span>