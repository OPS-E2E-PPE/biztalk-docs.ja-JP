---
title: SSO ユーザー グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd38c0417c84f7130a40f54fb684b01b6b853623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398950"
---
# <a name="sso-user-groups"></a><span data-ttu-id="7dd17-102">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="7dd17-102">SSO User Groups</span></span>
<span data-ttu-id="7dd17-103">で構成して、エンタープライズ シングル サインオン (SSO) システムを管理するには、これらの各ロールの特定の Windows グループとアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd17-103">To configure and manage the Enterprise Single Sign-On (SSO) system, you must create certain Windows groups and accounts for each of these roles.</span></span> <span data-ttu-id="7dd17-104">エンタープライズ SSO でアクセス アカウントを構成するときに、これらの各ロールの 1 つ以上のアカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-104">When configuring the access accounts in Enterprise SSO, you can specify more than one account for each of these roles.</span></span> <span data-ttu-id="7dd17-105">このセクションでは、これらの役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-105">This section describes these roles.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7dd17-106">SSO を構成するときに、ドメイン グループを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dd17-106">It is strongly recommended that you use domain groups when configuring SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dd17-107">セキュリティのために、SSO システムにビルトイン アカウントはできません。</span><span class="sxs-lookup"><span data-stu-id="7dd17-107">For security purposes, the SSO system does not allow built-in accounts.</span></span>  
  
## <a name="single-sign-on-administrators"></a><span data-ttu-id="7dd17-108">シングル サインオン管理者</span><span class="sxs-lookup"><span data-stu-id="7dd17-108">Single Sign-On Administrators</span></span>  
 <span data-ttu-id="7dd17-109">SSO 管理者では、SSO システムで最高レベルのユーザー権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="7dd17-109">SSO administrators have the highest level user rights in the SSO system.</span></span> <span data-ttu-id="7dd17-110">設定できます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-110">They can:</span></span>  
  
- <span data-ttu-id="7dd17-111">作成し、SSO データベースの管理</span><span class="sxs-lookup"><span data-stu-id="7dd17-111">Create and manage the SSO database</span></span>  
  
- <span data-ttu-id="7dd17-112">作成し、マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="7dd17-112">Create and manage the master secret</span></span>  
  
- <span data-ttu-id="7dd17-113">有効にして、SSO システムを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7dd17-113">Enable and disable the SSO system</span></span>  
  
- <span data-ttu-id="7dd17-114">パスワード同期アダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-114">Create password synchronization adapters</span></span>  
  
- <span data-ttu-id="7dd17-115">有効にして、SSO システムでパスワード同期を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7dd17-115">Enable and disable password synchronization in the SSO system</span></span>  
  
- <span data-ttu-id="7dd17-116">有効にして、ホスト側開始 SSO を無効にします。</span><span class="sxs-lookup"><span data-stu-id="7dd17-116">Enable and disable host initiated SSO</span></span>  
  
- <span data-ttu-id="7dd17-117">すべての管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-117">Perform all administration tasks</span></span>  
  
  <span data-ttu-id="7dd17-118">SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-118">The SSO administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="7dd17-119">SSO 管理者アカウントはドメインまたはローカル グループまたは個々 のアカウントのいずれかにもできます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-119">The SSO administrators account can also be either a domain or local group or individual account.</span></span> <span data-ttu-id="7dd17-120">個々 のアカウントを使用する場合は、別の単独アカウントをこのアカウントを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7dd17-120">When using an individual account, you cannot change this account to another individual account.</span></span> <span data-ttu-id="7dd17-121">そのため、個別のアカウントを使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7dd17-121">Therefore, it is recommended that you do not use an individual account.</span></span> <span data-ttu-id="7dd17-122">元のアカウントが、新しいアカウントのメンバーである限りは、グループ アカウントにこのアカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-122">You can change this account to a group account as long as the original account is a member of the new account.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7dd17-123">エンタープライズ シングル サインオン サービスを実行するサービス アカウントは、このアカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dd17-123">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="7dd17-124">環境をセキュリティで保護するには、他のサービスが、同じサービス アカウントを使用していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-124">To secure your environment, ensure that no other service is using the same service account.</span></span>  
  
## <a name="single-sign-on-affiliate-administrators"></a><span data-ttu-id="7dd17-125">シングル サインオン関連管理者</span><span class="sxs-lookup"><span data-stu-id="7dd17-125">Single Sign-On Affiliate Administrators</span></span>  
 <span data-ttu-id="7dd17-126">SSO 関連管理者は、SSO システムを含む関連アプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-126">The SSO affiliate administrator defines the affiliate applications that the SSO system contains.</span></span> <span data-ttu-id="7dd17-127">関連アプリケーションが接続先 SSO を使用してバックエンド システムを表す論理エンティティです。</span><span class="sxs-lookup"><span data-stu-id="7dd17-127">Affiliate applications are a logical entity that represents the back-end system to which you are connecting using SSO.</span></span> <span data-ttu-id="7dd17-128">SSO 関連管理者は。</span><span class="sxs-lookup"><span data-stu-id="7dd17-128">SSO affiliate administrators can:</span></span>  
  
- <span data-ttu-id="7dd17-129">作成、管理、および関連アプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="7dd17-129">Create, manage, and delete affiliate applications</span></span>  
  
- <span data-ttu-id="7dd17-130">各関連アプリケーションのアプリケーション管理者アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-130">Specify the application administrators account for each affiliate application</span></span>  
  
- <span data-ttu-id="7dd17-131">アプリケーション管理者およびアプリケーションのユーザーが可能なすべての管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-131">Perform all the administration tasks that the application administrators and application users can</span></span>  
  
  <span data-ttu-id="7dd17-132">SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-132">The SSO Affiliate Administrator account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="7dd17-133">SSO 関連管理者アカウントはドメインまたはローカル グループまたはアカウントのいずれかにもできます。</span><span class="sxs-lookup"><span data-stu-id="7dd17-133">The SSO Affiliate Administrator account can also be either a domain or local group or account.</span></span>  
  
## <a name="application-administrators"></a><span data-ttu-id="7dd17-134">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="7dd17-134">Application Administrators</span></span>  
 <span data-ttu-id="7dd17-135">関連アプリケーションごとに 1 つのアプリケーション管理者グループがあります。</span><span class="sxs-lookup"><span data-stu-id="7dd17-135">There is one application administrators group per affiliate application.</span></span>  
  
 <span data-ttu-id="7dd17-136">このグループのメンバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7dd17-136">Members of this group can:</span></span>  
  
-   <span data-ttu-id="7dd17-137">アプリケーションのユーザー グループ アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-137">Change the application users group account</span></span>  
  
-   <span data-ttu-id="7dd17-138">作成、削除、および特定の関連アプリケーションのすべてのユーザーの資格情報マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="7dd17-138">Create, delete, and manage credential mappings for all users of the specific affiliate application</span></span>  
  
-   <span data-ttu-id="7dd17-139">特定の関連アプリケーション ユーザー グループ アカウントですべてのユーザーの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-139">Set credentials for any user in that specific affiliate application users group account</span></span>  
  
-   <span data-ttu-id="7dd17-140">アプリケーションのユーザーが可能なすべての管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-140">Perform all the administration tasks that the application users can</span></span>  
  
## <a name="application-users"></a><span data-ttu-id="7dd17-141">アプリケーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="7dd17-141">Application Users</span></span>  
 <span data-ttu-id="7dd17-142">関連アプリケーションごとに 1 つのアプリケーション ユーザー グループ アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="7dd17-142">There is one application users group account for each affiliate application.</span></span> <span data-ttu-id="7dd17-143">このアカウントには、エンタープライズ シングル サインオン環境でのエンドユーザーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7dd17-143">This account contains the list of end users in an Enterprise Single Sign-On environment.</span></span> <span data-ttu-id="7dd17-144">このアカウントのメンバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7dd17-144">Members of this account can:</span></span>  
  
-   <span data-ttu-id="7dd17-145">関連アプリケーションでの資格情報の検索します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-145">Look up their credentials in the affiliate application</span></span>  
  
-   <span data-ttu-id="7dd17-146">関連アプリケーションで資格情報マッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="7dd17-146">Manage their credential mappings in the affiliate application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dd17-147">グループを割り当てるときに、警戒してください。</span><span class="sxs-lookup"><span data-stu-id="7dd17-147">Remember to be vigilant when assigning groups.</span></span> <span data-ttu-id="7dd17-148">たとえば、SSO アプリケーション ユーザー グループの BizTalk Server のセキュリティ ユーザー グループを使用するは可能であれば、です。</span><span class="sxs-lookup"><span data-stu-id="7dd17-148">It is possible, for example, to use a BizTalk Server security user group for the SSO application users group.</span></span> <span data-ttu-id="7dd17-149">これを実行する前に、すべてのユーザーが使用可能になるすべてのアクセスを必要があることが確認をしてください。</span><span class="sxs-lookup"><span data-stu-id="7dd17-149">Before you do this, be certain that all users need all access that will then be available to them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd17-150">参照</span><span class="sxs-lookup"><span data-stu-id="7dd17-150">See Also</span></span>  
 <span data-ttu-id="7dd17-151">[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="7dd17-151">[How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="7dd17-152">[SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="7dd17-152">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 <span data-ttu-id="7dd17-153">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="7dd17-153">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="7dd17-154">SSO について</span><span class="sxs-lookup"><span data-stu-id="7dd17-154">Understanding SSO</span></span>](../core/understanding-sso.md)