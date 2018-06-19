---
title: 'シングル サインオン: イベント 10516 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b74ca4a47bc62d28b25564bd5843729c56362
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269898"
---
# <a name="single-sign-on-event-10516"></a><span data-ttu-id="1c88b-102">シングル サインオン: イベント 10516</span><span class="sxs-lookup"><span data-stu-id="1c88b-102">Single Sign-On: Event 10516</span></span>
## <a name="details"></a><span data-ttu-id="1c88b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1c88b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c88b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1c88b-104">Product Name</span></span>|<span data-ttu-id="1c88b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1c88b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1c88b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1c88b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1c88b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1c88b-107">Event ID</span></span>|<span data-ttu-id="1c88b-108">10516</span><span class="sxs-lookup"><span data-stu-id="1c88b-108">10516</span></span>|  
|<span data-ttu-id="1c88b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1c88b-109">Event Source</span></span>|<span data-ttu-id="1c88b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1c88b-110">ENTSSO</span></span>|  
|<span data-ttu-id="1c88b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1c88b-111">Component</span></span>|<span data-ttu-id="1c88b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1c88b-112">N\A</span></span>|  
|<span data-ttu-id="1c88b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1c88b-113">Symbolic Name</span></span>|<span data-ttu-id="1c88b-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="1c88b-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span></span>|  
|<span data-ttu-id="1c88b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1c88b-115">Message Text</span></span>|<span data-ttu-id="1c88b-116">SSO 関連管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="1c88b-116">The SSO Affiliate Administrators account is not valid.</span></span> <span data-ttu-id="1c88b-117">これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c88b-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="1c88b-118">ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1c88b-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="1c88b-119">アカウントが有効である場合は SSO を有効にします。%r</span><span class="sxs-lookup"><span data-stu-id="1c88b-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="1c88b-120">SSO 関連管理者: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1c88b-120">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="1c88b-121">無効なアカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1c88b-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="1c88b-122">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="1c88b-122">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1c88b-123">説明</span><span class="sxs-lookup"><span data-stu-id="1c88b-123">Explanation</span></span>  
 <span data-ttu-id="1c88b-124">このエラー イベントは、エンタープライズ シングル サインオンによって作成された SSO 関連管理者アカウントまたはグループが有効な Windows アカウントではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1c88b-124">This Error event indicates that the SSO Affiliate Administrator account or group created by Enterprise Sing Sign-on is not a valid Windows account.</span></span> <span data-ttu-id="1c88b-125">SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="1c88b-125">The SSO Affiliate Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="1c88b-126">また、ドメインまたはローカル グループ アカウントのいずれかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c88b-126">The SSO Affiliate Administrator account can also be either a domain or local group account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1c88b-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1c88b-127">User Action</span></span>  
 <span data-ttu-id="1c88b-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c88b-128">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="1c88b-129">SSO 関連管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1c88b-129">Verify the SSO Affiliate Administrator account exists.</span></span>  
  
 <span data-ttu-id="1c88b-130">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="1c88b-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="1c88b-131">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="1c88b-131">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="1c88b-132">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="1c88b-132">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)