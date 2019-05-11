---
title: SSO マッピング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO]
- maps [SSO], creating
- SSO, maps
ms.assetid: b44f7a0c-595c-49dc-9d75-2e76f29dca88
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5debd3e1dcf1ee0e45d421e777006d247a6da84f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258618"
---
# <a name="sso-mappings"></a><span data-ttu-id="3102b-102">SSO マッピング</span><span class="sxs-lookup"><span data-stu-id="3102b-102">SSO Mappings</span></span>
<span data-ttu-id="3102b-103">エンタープライズ シングル サインオン (SSO) 管理者または SSO 関連管理者が関連アプリケーションを定義、管理者を定義できますが、個別のマッピングを持つアプリケーションとして、またはグループ マッピングを使用するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3102b-103">When an Enterprise Single Sign-On (SSO) administrator or an SSO affiliate administrator defines an affiliate application, the administrator can define it either as an application with individual mappings, or as an application with a group mapping.</span></span>  
  
## <a name="individual-mappings"></a><span data-ttu-id="3102b-104">個別のマッピング</span><span class="sxs-lookup"><span data-stu-id="3102b-104">Individual Mappings</span></span>  
 <span data-ttu-id="3102b-105">Windows ユーザーと、対応する非 Windows 資格情報の間の一対一のマッピングを作成するには、管理者とユーザーに個別のマッピングを SSO が有効にします。</span><span class="sxs-lookup"><span data-stu-id="3102b-105">SSO individual mappings enable administrators and users to create a one-to-one mapping between Windows users and their corresponding non-Windows credentials.</span></span> <span data-ttu-id="3102b-106">個別のマッピングを使用する場合、ユーザーは独自のマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-106">When using individual mappings, users can manage their own mappings.</span></span> <span data-ttu-id="3102b-107">SSO システムでは、ユーザーの Windows アカウントとユーザーの Windows 以外の一対一の関係を保持します。</span><span class="sxs-lookup"><span data-stu-id="3102b-107">The SSO system maintains the one-to-one relation for the user's Windows account and the user's non-Windows account.</span></span>  
  
 <span data-ttu-id="3102b-108">Windows エンドユーザーは、作成し、個々 の型のアプリケーションの独自のマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-108">Windows End-users can create and manage their own mappings for individual type applications.</span></span> <span data-ttu-id="3102b-109">同じ関連アプリケーションは、Windows 側開始 SSO とホスト側開始 SSO タイプのアプリケーションとして動作できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-109">The same affiliate application can act as a Windows Initiated SSO and a Host Initiated SSO type application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3102b-110">マッピングは、Windows ドメイン アカウントに対してのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-110">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="3102b-111">ローカル アカウントをマップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3102b-111">Local accounts cannot be mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3102b-112">個々 のユーザーは、個別のマッピングを使用する場合に、個々 のアカウントに資格情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-112">Only individual users can obtain the credentials to their individual accounts when using individual mappings.</span></span>  
  
## <a name="group-mapping"></a><span data-ttu-id="3102b-113">グループ マッピング</span><span class="sxs-lookup"><span data-stu-id="3102b-113">Group Mapping</span></span>  
 <span data-ttu-id="3102b-114">グループ マッピングを SSO 関連アプリケーションの 1 つのアカウントに、複数の Windows ユーザーを含む、Windows グループのマッピングで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3102b-114">SSO group mapping consists of mapping a Windows group, which contains multiple Windows users, to a single account in the affiliate application.</span></span>  
  
 <span data-ttu-id="3102b-115">SSO Application Users ロールに対して複数のアカウントを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3102b-115">You can also specify multiple accounts for the SSO Application Users role.</span></span> <span data-ttu-id="3102b-116">指定する各アカウントは、外部アカウントを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="3102b-116">Each account you specify can be associated with an external account.</span></span> <span data-ttu-id="3102b-117">たとえば、EXTERNALUSER1 と個々 のドメイン アカウントを EXTERNALUSER2 にドメイン グループ アカウントをマップできます。</span><span class="sxs-lookup"><span data-stu-id="3102b-117">For example, you can map a domain group account to EXTERNALUSER1 and an individual domain account to EXTERNALUSER2.</span></span> <span data-ttu-id="3102b-118">同じユーザーには、複数のマッピングがある場合は、SSO Application Users の順序の最初のマッピングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3102b-118">If the same user has more than one mapping, the first mapping in the order of SSO Application Users is used.</span></span>  
  
 <span data-ttu-id="3102b-119">アプリケーション管理者、SSO 関連管理者、または SSO 管理者のみが作成またはグループのマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-119">Only an application administrator, SSO affiliate administrator, or SSO administrator can create or manage a group mapping.</span></span>  
  
 <span data-ttu-id="3102b-120">Windows 用に同じグループ アプリケーション開始 SSO とホスト側開始 SSO を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3102b-120">You cannot specify the same group application for Windows initiated SSO and Host Initiated SSO.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3102b-121">マッピングは、Windows ドメイン アカウントに対してのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-121">Mappings can be created only for Windows domain accounts.</span></span> <span data-ttu-id="3102b-122">ローカル アカウントをマップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3102b-122">Local accounts cannot be mapped.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3102b-123">グループ マッピングを使用すると、グループのメンバーは、グループ マッピングの資格情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3102b-123">When you use group mappings, the members of the group can obtain the credential information for the group mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3102b-124">参照</span><span class="sxs-lookup"><span data-stu-id="3102b-124">See Also</span></span>  
 <span data-ttu-id="3102b-125">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="3102b-125">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="3102b-126">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3102b-126">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)