---
title: "シングル サインオン: イベント 10518 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 274e29f9-1933-4e40-83c0-2e84c6708315
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27b82d7f0a6bbaf02400679add53851867d728c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10518"></a><span data-ttu-id="9e118-102">シングル サインオン: イベント 10518</span><span class="sxs-lookup"><span data-stu-id="9e118-102">Single Sign-On: Event 10518</span></span>
## <a name="details"></a><span data-ttu-id="9e118-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9e118-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e118-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9e118-104">Product Name</span></span>|<span data-ttu-id="9e118-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9e118-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9e118-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9e118-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9e118-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9e118-107">Event ID</span></span>|<span data-ttu-id="9e118-108">10518</span><span class="sxs-lookup"><span data-stu-id="9e118-108">10518</span></span>|  
|<span data-ttu-id="9e118-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9e118-109">Event Source</span></span>|<span data-ttu-id="9e118-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9e118-110">ENTSSO</span></span>|  
|<span data-ttu-id="9e118-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9e118-111">Component</span></span>|<span data-ttu-id="9e118-112">N\A</span><span class="sxs-lookup"><span data-stu-id="9e118-112">N\A</span></span>|  
|<span data-ttu-id="9e118-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9e118-113">Symbolic Name</span></span>|<span data-ttu-id="9e118-114">SSO_WARN_BAD_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="9e118-114">SSO_WARN_BAD_USER_GROUP</span></span>|  
|<span data-ttu-id="9e118-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9e118-115">Message Text</span></span>|<span data-ttu-id="9e118-116">このアプリケーションのアプリケーション ユーザー アカウントは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="9e118-116">The Application Users account for this application is not valid.</span></span> <span data-ttu-id="9e118-117">これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e118-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="9e118-118">ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="9e118-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="9e118-119">アカウントが有効である場合は、アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e118-119">Enable the application when the account is valid.</span></span> <span data-ttu-id="9e118-120">このコンピューターでこのアプリケーションを使用しない場合、このメッセージは無視して構いません。%r</span><span class="sxs-lookup"><span data-stu-id="9e118-120">You can ignore this message if you are not going to use this application on this computer.%r</span></span><br /><br /> <span data-ttu-id="9e118-121">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9e118-121">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="9e118-122">アプリケーション ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="9e118-122">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="9e118-123">無効なアカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="9e118-123">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="9e118-124">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="9e118-124">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e118-125">説明</span><span class="sxs-lookup"><span data-stu-id="9e118-125">Explanation</span></span>  
 <span data-ttu-id="9e118-126">この警告イベントは、アプリケーション ユーザー グループ アカウントが有効な Windows アカウントではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9e118-126">This Warning event indicates that an Application Users group account is not a valid Windows account.</span></span> <span data-ttu-id="9e118-127">アプリケーション ユーザー アカウント グループは、関連アプリケーションごとに 1 つ存在します。</span><span class="sxs-lookup"><span data-stu-id="9e118-127">There is one Application Users account group for each affiliate application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e118-128">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9e118-128">User Action</span></span>  
 <span data-ttu-id="9e118-129">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="9e118-129">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="9e118-130">指定したアプリケーション ユーザー アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e118-130">Verify the specified Application Users account exists.</span></span>  
  
-   <span data-ttu-id="9e118-131">SSO 管理ユーティリティを使用して、指定した関連アプリケーションが適切なアプリケーション ユーザー アカウントを使用するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e118-131">Use the SSO Administration Utility to verify the specified affiliate application is configured to use the correct application users account.</span></span>  
  
 <span data-ttu-id="9e118-132">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="9e118-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="9e118-133">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="9e118-133">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="9e118-134">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9e118-134">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="9e118-135">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="9e118-135">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)