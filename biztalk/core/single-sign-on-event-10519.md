---
title: 'シングル サインオン: イベント 10519 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e709957e-a690-4a44-a863-07b2a55dae7b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928892ff1d0ee461a26095ddc7a72fd3accecf10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271010"
---
# <a name="single-sign-on-event-10519"></a><span data-ttu-id="ae370-102">シングル サインオン: イベント 10519</span><span class="sxs-lookup"><span data-stu-id="ae370-102">Single Sign-On: Event 10519</span></span>
## <a name="details"></a><span data-ttu-id="ae370-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ae370-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae370-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ae370-104">Product Name</span></span>|<span data-ttu-id="ae370-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ae370-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ae370-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ae370-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ae370-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ae370-107">Event ID</span></span>|<span data-ttu-id="ae370-108">10519</span><span class="sxs-lookup"><span data-stu-id="ae370-108">10519</span></span>|  
|<span data-ttu-id="ae370-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ae370-109">Event Source</span></span>|<span data-ttu-id="ae370-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ae370-110">ENTSSO</span></span>|  
|<span data-ttu-id="ae370-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae370-111">Component</span></span>|<span data-ttu-id="ae370-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ae370-112">N\A</span></span>|  
|<span data-ttu-id="ae370-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ae370-113">Symbolic Name</span></span>|<span data-ttu-id="ae370-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="ae370-114">SSO_WARN_BAD_APP_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="ae370-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ae370-115">Message Text</span></span>|<span data-ttu-id="ae370-116">このアプリケーションのアプリケーション管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="ae370-116">The Application Administrators account for this application is not valid.</span></span> <span data-ttu-id="ae370-117">これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae370-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="ae370-118">ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ae370-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="ae370-119">アカウントが有効である場合は、アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ae370-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="ae370-120">このコンピューターでこのアプリケーションを使用しない場合、このメッセージは無視して構いません。%r</span><span class="sxs-lookup"><span data-stu-id="ae370-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="ae370-121">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ae370-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="ae370-122">アプリケーション管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="ae370-122">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="ae370-123">無効なアカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ae370-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="ae370-124">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="ae370-124">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae370-125">説明</span><span class="sxs-lookup"><span data-stu-id="ae370-125">Explanation</span></span>  
 <span data-ttu-id="ae370-126">この警告イベントは、アプリケーション管理者グループ アカウントが有効な Windows アカウントではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ae370-126">This Warning event indicates that an Application Administrators group account is not a valid Windows account.</span></span> <span data-ttu-id="ae370-127">アプリケーション管理者アカウント グループは、関連アプリケーションごとに 1 つ存在します。</span><span class="sxs-lookup"><span data-stu-id="ae370-127">There is one Application Administraotrs account group for each affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae370-128">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ae370-128">User Action</span></span>  
 <span data-ttu-id="ae370-129">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="ae370-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="ae370-130">指定したアプリケーション管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae370-130">Verify the specified Application Administrators account exists.</span></span>  
  
-   <span data-ttu-id="ae370-131">SSO 管理ユーティリティを使用して、指定した関連アプリケーションが適切なアプリケーション管理者アカウントを使用するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ae370-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application administrators account.</span></span>  
  
 <span data-ttu-id="ae370-132">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="ae370-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="ae370-133">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="ae370-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="ae370-134">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ae370-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="ae370-135">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="ae370-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)