---
title: 'シングル サインオン: イベント 11042 |Microsoft ドキュメント'
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
ms.openlocfilehash: da20346fbf2f73ac2ab64db3c9137394aa5bd366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277058"
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="35f45-102">シングル サインオン: イベント 11042</span><span class="sxs-lookup"><span data-stu-id="35f45-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="35f45-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35f45-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35f45-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35f45-104">Product Name</span></span>|<span data-ttu-id="35f45-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="35f45-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="35f45-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35f45-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="35f45-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35f45-107">Event ID</span></span>|<span data-ttu-id="35f45-108">11042</span><span class="sxs-lookup"><span data-stu-id="35f45-108">11042</span></span>|  
|<span data-ttu-id="35f45-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35f45-109">Event Source</span></span>|<span data-ttu-id="35f45-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="35f45-110">ENTSSO</span></span>|  
|<span data-ttu-id="35f45-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35f45-111">Component</span></span>|<span data-ttu-id="35f45-112">なし</span><span class="sxs-lookup"><span data-stu-id="35f45-112">N/A</span></span>|  
|<span data-ttu-id="35f45-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35f45-113">Symbolic Name</span></span>|<span data-ttu-id="35f45-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="35f45-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>|  
|<span data-ttu-id="35f45-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35f45-115">Message Text</span></span>|<span data-ttu-id="35f45-116">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="35f45-116">Access denied.</span></span><br /><br /> <span data-ttu-id="35f45-117">この機能を実行するには、クライアント ユーザーは次のいずれかのアカウントのメンバーである必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="35f45-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="35f45-118">SSO 管理者: %1 %r</span><span class="sxs-lookup"><span data-stu-id="35f45-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="35f45-119">SSO 関連管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="35f45-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="35f45-120">アプリケーション管理者: %3 %r</span><span class="sxs-lookup"><span data-stu-id="35f45-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="35f45-121">アプリケーション ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="35f45-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="35f45-122">追加データ: %5</span><span class="sxs-lookup"><span data-stu-id="35f45-122">Additional Data: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="35f45-123">説明</span><span class="sxs-lookup"><span data-stu-id="35f45-123">Explanation</span></span>  
 <span data-ttu-id="35f45-124">この機能を実行するには、クライアント ユーザーは警告で示されているいずれかのアカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f45-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35f45-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35f45-125">User Action</span></span>  
 <span data-ttu-id="35f45-126">この機能を実行するには、いずれかのアカウントに加わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f45-126">You must join one of the accounts to perform this function.</span></span>