---
title: "SSO マッピング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98b44a1a9e8be3b275a4dd328c70323d79eb8a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-mappings"></a><span data-ttu-id="ac03a-102">SSO マッピング</span><span class="sxs-lookup"><span data-stu-id="ac03a-102">SSO Mappings</span></span>
<span data-ttu-id="ac03a-103">エンタープライズ シングル サインオン (SSO) 管理者または SSO 関連管理者が関連アプリケーションを定義する場合、その管理者は、個別のマッピングを使用するアプリケーションかグループ マッピングを使用するアプリケーションとして、その関連アプリケーションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-103">When an Enterprise Single Sign-On (SSO) administrator or an SSO affiliate administrator defines an affiliate application, the administrator can define it either as an application with individual mappings, or as an application with a group mapping.</span></span>  
  
## <a name="individual-mappings"></a><span data-ttu-id="ac03a-104">個別のマッピング</span><span class="sxs-lookup"><span data-stu-id="ac03a-104">Individual Mappings</span></span>  
 <span data-ttu-id="ac03a-105">SSO の個別のマッピングを使用すると、管理者とユーザーは、Windows ユーザーとそれに対応する Windows 以外の資格情報との間に一対一のマッピングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-105">SSO individual mappings enable administrators and users to create a one-to-one mapping between Windows users and their corresponding non-Windows credentials.</span></span> <span data-ttu-id="ac03a-106">個別のマッピングを使用する場合、ユーザーは独自のマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-106">When using individual mappings, users can manage their own mappings.</span></span> <span data-ttu-id="ac03a-107">SSO システムでは、ユーザーの Windows アカウントとユーザーの Windows 以外のアカウントとの間で一対一の関係を維持します。</span><span class="sxs-lookup"><span data-stu-id="ac03a-107">The SSO system maintains the one-to-one relation for the user's Windows account and the user's non-Windows account.</span></span>  
  
 <span data-ttu-id="ac03a-108">Windows エンド ユーザーは、単独タイプのアプリケーション用に独自のマッピングを作成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-108">Windows End-users can create and manage their own mappings for individual type applications.</span></span> <span data-ttu-id="ac03a-109">同じ関連アプリケーションを、Windows 側開始 SSO タイプのアプリケーションとホスト側開始 SSO タイプのアプリケーションの両方として機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-109">The same affiliate application can act as a Windows Initiated SSO and a Host Initiated SSO type application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac03a-110">マッピングは、Windows ドメイン アカウントに対してのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-110">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="ac03a-111">ローカル アカウントはマップできません。</span><span class="sxs-lookup"><span data-stu-id="ac03a-111">Local accounts cannot be mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac03a-112">個別のマッピングを使用する場合、個別のアカウントに対応する資格情報を取得できるのは個別のユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="ac03a-112">Only individual users can obtain the credentials to their individual accounts when using individual mappings.</span></span>  
  
## <a name="group-mapping"></a><span data-ttu-id="ac03a-113">グループ マッピング</span><span class="sxs-lookup"><span data-stu-id="ac03a-113">Group Mapping</span></span>  
 <span data-ttu-id="ac03a-114">SSO のグループ マッピングは、複数の Windows ユーザーが含まれた 1 つの Windows グループから関連アプリケーションの 1 つのアカウントへのマッピングで構成されています。</span><span class="sxs-lookup"><span data-stu-id="ac03a-114">SSO group mapping consists of mapping a Windows group, which contains multiple Windows users, to a single account in the affiliate application.</span></span>  
  
 <span data-ttu-id="ac03a-115">SSO Application Users ロールに複数のアカウントを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-115">You can also specify multiple accounts for the SSO Application Users role.</span></span> <span data-ttu-id="ac03a-116">指定する各アカウントは、外部アカウントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-116">Each account you specify can be associated with an external account.</span></span> <span data-ttu-id="ac03a-117">たとえば、ドメイン グループ アカウントを EXTERNALUSER1 にマップし、個別のドメイン アカウントを EXTERNALUSER2 にマップできます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-117">For example, you can map a domain group account to EXTERNALUSER1 and an individual domain account to EXTERNALUSER2.</span></span> <span data-ttu-id="ac03a-118">同じユーザーが複数のマッピングを使用している場合は、SSO Application Users ロールの順番が早い方のマッピングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-118">If the same user has more than one mapping, the first mapping in the order of SSO Application Users is used.</span></span>  
  
 <span data-ttu-id="ac03a-119">アプリケーション管理者、SSO 関連管理者、または SSO 管理者のみが作成またはグループのマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-119">Only an application administrator, SSO affiliate administrator, or SSO administrator can create or manage a group mapping.</span></span>  
  
 <span data-ttu-id="ac03a-120">Windows 側開始 SSO とホスト側開始 SSO に同じグループ アプリケーションを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac03a-120">You cannot specify the same group application for Windows initiated SSO and Host Initiated SSO.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac03a-121">マッピングは、Windows ドメイン アカウントに対してのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-121">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="ac03a-122">ローカル アカウントはマップできません。</span><span class="sxs-lookup"><span data-stu-id="ac03a-122">Local accounts cannot be mapped.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac03a-123">グループ マッピングを使用すると、グループのメンバはそのグループ マッピングの資格情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ac03a-123">When you use group mappings, the members of the group can obtain the credential information for the group mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac03a-124">参照</span><span class="sxs-lookup"><span data-stu-id="ac03a-124">See Also</span></span>  
 <span data-ttu-id="ac03a-125">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="ac03a-125">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="ac03a-126">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ac03a-126">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)