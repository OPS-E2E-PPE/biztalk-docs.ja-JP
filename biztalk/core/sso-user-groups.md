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
ms.openlocfilehash: cee8780b645cc6f58c0a75526a695e2148893023
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017290"
---
# <a name="sso-user-groups"></a><span data-ttu-id="b4667-102">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="b4667-102">SSO User Groups</span></span>
<span data-ttu-id="b4667-103">エンタープライズ シングル サインオン (SSO) システムを構成および管理するには、ロールごとに特定の Windows グループとアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4667-103">To configure and manage the Enterprise Single Sign-On (SSO) system, you must create certain Windows groups and accounts for each of these roles.</span></span> <span data-ttu-id="b4667-104">エンタープライズ SSO でアクセス アカウントを構成する際には、各ロールに複数のアカウントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="b4667-104">When configuring the access accounts in Enterprise SSO, you can specify more than one account for each of these roles.</span></span> <span data-ttu-id="b4667-105">このセクションでは、各ロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b4667-105">This section describes these roles.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4667-106">SSO を構成する際には、ドメイン グループを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4667-106">It is strongly recommended that you use domain groups when configuring SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4667-107">セキュリティ上の理由から、SSO システムでは組み込みアカウントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4667-107">For security purposes, the SSO system does not allow built-in accounts.</span></span>  
  
## <a name="single-sign-on-administrators"></a><span data-ttu-id="b4667-108">シングル サインオン管理者</span><span class="sxs-lookup"><span data-stu-id="b4667-108">Single Sign-On Administrators</span></span>  
 <span data-ttu-id="b4667-109">SSO 管理者には、SSO システムで最高レベルのユーザー権利が与えられています。</span><span class="sxs-lookup"><span data-stu-id="b4667-109">SSO administrators have the highest level user rights in the SSO system.</span></span> <span data-ttu-id="b4667-110">SSO 管理者は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b4667-110">They can:</span></span>  
  
- <span data-ttu-id="b4667-111">SSO データベースの作成および管理</span><span class="sxs-lookup"><span data-stu-id="b4667-111">Create and manage the SSO database</span></span>  
  
- <span data-ttu-id="b4667-112">マスタ シークレットの作成および管理</span><span class="sxs-lookup"><span data-stu-id="b4667-112">Create and manage the master secret</span></span>  
  
- <span data-ttu-id="b4667-113">SSO システムの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="b4667-113">Enable and disable the SSO system</span></span>  
  
- <span data-ttu-id="b4667-114">パスワード同期アダプタの作成</span><span class="sxs-lookup"><span data-stu-id="b4667-114">Create password synchronization adapters</span></span>  
  
- <span data-ttu-id="b4667-115">SSO システムでのパスワード同期の有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="b4667-115">Enable and disable password synchronization in the SSO system</span></span>  
  
- <span data-ttu-id="b4667-116">ホスト側開始 SSO の有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="b4667-116">Enable and disable host initiated SSO</span></span>  
  
- <span data-ttu-id="b4667-117">すべての管理作業の実行</span><span class="sxs-lookup"><span data-stu-id="b4667-117">Perform all administration tasks</span></span>  
  
  <span data-ttu-id="b4667-118">SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="b4667-118">The SSO administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="b4667-119">また、ドメインまたはローカルのグループや単独アカウントのいずれかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4667-119">The SSO administrators account can also be either a domain or local group or individual account.</span></span> <span data-ttu-id="b4667-120">単独アカウントを使用すると、このアカウントを別の単独アカウントに変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4667-120">When using an individual account, you cannot change this account to another individual account.</span></span> <span data-ttu-id="b4667-121">そのため、単独アカウントは使用しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4667-121">Therefore, it is recommended that you do not use an individual account.</span></span> <span data-ttu-id="b4667-122">元のアカウントが新しいグループのメンバであれば、単独アカウントをグループ アカウントに変更できます。</span><span class="sxs-lookup"><span data-stu-id="b4667-122">You can change this account to a group account as long as the original account is a member of the new account.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4667-123">エンタープライズ シングル サインオン サービスを実行しているサービス アカウントは、このグループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4667-123">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="b4667-124">環境をセキュリティで保護するために、同じサービス アカウントが他のサービスで使用されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b4667-124">To secure your environment, ensure that no other service is using the same service account.</span></span>  
  
## <a name="single-sign-on-affiliate-administrators"></a><span data-ttu-id="b4667-125">シングル サインオン関連管理者</span><span class="sxs-lookup"><span data-stu-id="b4667-125">Single Sign-On Affiliate Administrators</span></span>  
 <span data-ttu-id="b4667-126">SSO 関連管理者は、SSO システムに含まれる関連アプリケーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4667-126">The SSO affiliate administrator defines the affiliate applications that the SSO system contains.</span></span> <span data-ttu-id="b4667-127">関連アプリケーションとは、SSO を使用して接続するバックエンド システムを表す論理エンティティのことです。</span><span class="sxs-lookup"><span data-stu-id="b4667-127">Affiliate applications are a logical entity that represents the back-end system to which you are connecting using SSO.</span></span> <span data-ttu-id="b4667-128">SSO 関連管理者は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b4667-128">SSO affiliate administrators can:</span></span>  
  
- <span data-ttu-id="b4667-129">関連アプリケーションの作成、管理、および削除</span><span class="sxs-lookup"><span data-stu-id="b4667-129">Create, manage, and delete affiliate applications</span></span>  
  
- <span data-ttu-id="b4667-130">各関連アプリケーションに対するアプリケーション管理者アカウントの指定</span><span class="sxs-lookup"><span data-stu-id="b4667-130">Specify the application administrators account for each affiliate application</span></span>  
  
- <span data-ttu-id="b4667-131">アプリケーション管理者とアプリケーション ユーザーが実行できるすべての管理作業の実行</span><span class="sxs-lookup"><span data-stu-id="b4667-131">Perform all the administration tasks that the application administrators and application users can</span></span>  
  
  <span data-ttu-id="b4667-132">SSO 関連管理者アカウントには、Windows グループ アカウントまたは単独アカウントのいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4667-132">The SSO Affiliate Administrator account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="b4667-133">また、ドメインまたはローカルのグループやアカウントのいずれかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4667-133">The SSO Affiliate Administrator account can also be either a domain or local group or account.</span></span>  
  
## <a name="application-administrators"></a><span data-ttu-id="b4667-134">アプリケーション管理者</span><span class="sxs-lookup"><span data-stu-id="b4667-134">Application Administrators</span></span>  
 <span data-ttu-id="b4667-135">アプリケーション管理者グループは、関連アプリケーションごとに 1 つ存在します。</span><span class="sxs-lookup"><span data-stu-id="b4667-135">There is one application administrators group per affiliate application.</span></span>  
  
 <span data-ttu-id="b4667-136">このグループのメンバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4667-136">Members of this group can:</span></span>  
  
-   <span data-ttu-id="b4667-137">アプリケーション ユーザー グループ アカウントの変更</span><span class="sxs-lookup"><span data-stu-id="b4667-137">Change the application users group account</span></span>  
  
-   <span data-ttu-id="b4667-138">特定の関連アプリケーションのすべてのユーザーに対する資格情報マッピングの作成、削除、および管理</span><span class="sxs-lookup"><span data-stu-id="b4667-138">Create, delete, and manage credential mappings for all users of the specific affiliate application</span></span>  
  
-   <span data-ttu-id="b4667-139">特定の関連アプリケーション ユーザー グループ アカウントのすべてのユーザーに対する資格情報の設定</span><span class="sxs-lookup"><span data-stu-id="b4667-139">Set credentials for any user in that specific affiliate application users group account</span></span>  
  
-   <span data-ttu-id="b4667-140">アプリケーション ユーザーが実行できるすべての管理作業の実行</span><span class="sxs-lookup"><span data-stu-id="b4667-140">Perform all the administration tasks that the application users can</span></span>  
  
## <a name="application-users"></a><span data-ttu-id="b4667-141">アプリケーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="b4667-141">Application Users</span></span>  
 <span data-ttu-id="b4667-142">アプリケーション ユーザー グループは、関連アプリケーションごとに 1 つ存在します。</span><span class="sxs-lookup"><span data-stu-id="b4667-142">There is one application users group account for each affiliate application.</span></span> <span data-ttu-id="b4667-143">このグループには、エンタープライズ シングル サインオン環境に存在するエンド ユーザーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4667-143">This account contains the list of end users in an Enterprise Single Sign-On environment.</span></span> <span data-ttu-id="b4667-144">このグループのメンバは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b4667-144">Members of this account can:</span></span>  
  
-   <span data-ttu-id="b4667-145">関連アプリケーションでの資格情報の検索</span><span class="sxs-lookup"><span data-stu-id="b4667-145">Look up their credentials in the affiliate application</span></span>  
  
-   <span data-ttu-id="b4667-146">関連アプリケーションでの資格情報マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="b4667-146">Manage their credential mappings in the affiliate application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4667-147">グループを割り当てる際には注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4667-147">Remember to be vigilant when assigning groups.</span></span> <span data-ttu-id="b4667-148">たとえば、SSO アプリケーション ユーザー グループに BizTalk Server セキュリティ ユーザー グループを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b4667-148">It is possible, for example, to use a BizTalk Server security user group for the SSO application users group.</span></span> <span data-ttu-id="b4667-149">グループを割り当てる前に、ユーザーに与えられるアクセス権が、そのユーザーに必要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b4667-149">Before you do this, be certain that all users need all access that will then be available to them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4667-150">参照</span><span class="sxs-lookup"><span data-stu-id="b4667-150">See Also</span></span>  
 <span data-ttu-id="b4667-151">[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="b4667-151">[How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="b4667-152">[SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="b4667-152">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 <span data-ttu-id="b4667-153">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="b4667-153">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="b4667-154">SSO について</span><span class="sxs-lookup"><span data-stu-id="b4667-154">Understanding SSO</span></span>](../core/understanding-sso.md)