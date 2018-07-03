---
title: 'シングル サインオン: イベント 10517 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c1426b4a45d55985ace0548b8e33bb2637f09c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011403"
---
# <a name="single-sign-on-event-10517"></a><span data-ttu-id="e9872-102">シングル サインオン: イベント 10517</span><span class="sxs-lookup"><span data-stu-id="e9872-102">Single Sign-On: Event 10517</span></span>
## <a name="details"></a><span data-ttu-id="e9872-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e9872-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e9872-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e9872-104">Product Name</span></span>   |                                                                                                                                                  <span data-ttu-id="e9872-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e9872-105">Enterprise Single Sign-On</span></span>                                                                                                                                                  |
| <span data-ttu-id="e9872-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e9872-106">Product Version</span></span> |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    <span data-ttu-id="e9872-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e9872-107">Event ID</span></span>     |                                                                                                                                                            <span data-ttu-id="e9872-108">10517</span><span class="sxs-lookup"><span data-stu-id="e9872-108">10517</span></span>                                                                                                                                                            |
|  <span data-ttu-id="e9872-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e9872-109">Event Source</span></span>   |                                                                                                                                                           <span data-ttu-id="e9872-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e9872-110">ENTSSO</span></span>                                                                                                                                                            |
|    <span data-ttu-id="e9872-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e9872-111">Component</span></span>    |                                                                                                                                                             <span data-ttu-id="e9872-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e9872-112">N\A</span></span>                                                                                                                                                             |
|  <span data-ttu-id="e9872-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e9872-113">Symbolic Name</span></span>  |                                                                                                                                                   <span data-ttu-id="e9872-114">SSO_ERROR_BAD_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="e9872-114">SSO_ERROR_BAD_SSO_ADMIN</span></span>                                                                                                                                                   |
|  <span data-ttu-id="e9872-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e9872-115">Message Text</span></span>   | <span data-ttu-id="e9872-116">SSO 管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="e9872-116">The SSO Administrators account is not valid.</span></span> <span data-ttu-id="e9872-117">これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9872-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="e9872-118">ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="e9872-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="e9872-119">アカウントが有効である場合は SSO を有効にします。%r</span><span class="sxs-lookup"><span data-stu-id="e9872-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="e9872-120">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="e9872-120">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="e9872-121">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="e9872-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="e9872-122">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="e9872-122">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="e9872-123">説明</span><span class="sxs-lookup"><span data-stu-id="e9872-123">Explanation</span></span>  
 <span data-ttu-id="e9872-124">このエラー イベントは、エンタープライズ シングル サインオンについて指定されている SSO 管理者アカウントが、有効な Windows アカウントではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e9872-124">This Error event indicates that the SSO Administrators account specified for Enterprise Single Sign-On is not a valid Windows account.</span></span> <span data-ttu-id="e9872-125">エンタープライズ シングル サインオン サービスを実行しているサービス アカウントは、このグループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9872-125">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="e9872-126">SSO 管理者アカウントには、Windows グループ アカウントまたは単独アカウントのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9872-126">The SSO Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="e9872-127">また、ドメインまたはローカルのグループ アカウントを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9872-127">The SSO Administrators account can also be either a domain or local group account.</span></span> <span data-ttu-id="e9872-128">単独アカウントを使用すると、このアカウントを別の単独アカウントに変更できません。</span><span class="sxs-lookup"><span data-stu-id="e9872-128">When using an individual account, you cannot change this account to another individual account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e9872-129">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e9872-129">User Action</span></span>  
 <span data-ttu-id="e9872-130">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e9872-130">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="e9872-131">SSO 管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9872-131">Verify the SSO Administrators account exists.</span></span>  

  <span data-ttu-id="e9872-132">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="e9872-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e9872-133">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="e9872-133">SSO User Groups</span></span>](../core/sso-user-groups.md)
