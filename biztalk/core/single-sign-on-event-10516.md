---
title: シングル サインオン:イベント 10516 |Microsoft Docs
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
ms.openlocfilehash: 85f7d5069ede9653187c7c3af8bf79bc7bc11ca4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243455"
---
# <a name="single-sign-on-event-10516"></a><span data-ttu-id="67a22-102">シングル サインオン:イベント 10516</span><span class="sxs-lookup"><span data-stu-id="67a22-102">Single Sign-On: Event 10516</span></span>
## <a name="details"></a><span data-ttu-id="67a22-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67a22-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67a22-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67a22-104">Product Name</span></span>   |                                                                                                                                                            <span data-ttu-id="67a22-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="67a22-105">Enterprise Single Sign-On</span></span>                                                                                                                                                            |
| <span data-ttu-id="67a22-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67a22-106">Product Version</span></span> |                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    <span data-ttu-id="67a22-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67a22-107">Event ID</span></span>     |                                                                                                                                                                      <span data-ttu-id="67a22-108">10516</span><span class="sxs-lookup"><span data-stu-id="67a22-108">10516</span></span>                                                                                                                                                                      |
|  <span data-ttu-id="67a22-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67a22-109">Event Source</span></span>   |                                                                                                                                                                     <span data-ttu-id="67a22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67a22-110">ENTSSO</span></span>                                                                                                                                                                      |
|    <span data-ttu-id="67a22-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67a22-111">Component</span></span>    |                                                                                                                                                                       <span data-ttu-id="67a22-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="67a22-112">N\A</span></span>                                                                                                                                                                       |
|  <span data-ttu-id="67a22-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67a22-113">Symbolic Name</span></span>  |                                                                                                                                                           <span data-ttu-id="67a22-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="67a22-114">SSO_ERROR_BAD_SSO_APP_ADMIN</span></span>                                                                                                                                                           |
|  <span data-ttu-id="67a22-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67a22-115">Message Text</span></span>   | <span data-ttu-id="67a22-116">SSO 関連管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="67a22-116">The SSO Affiliate Administrators account is not valid.</span></span> <span data-ttu-id="67a22-117">このアカウントは、サーバーに存在するローカル アカウント チェックの場合。</span><span class="sxs-lookup"><span data-stu-id="67a22-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="67a22-118">場合はドメイン アカウントには、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="67a22-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="67a22-119">アカウントが valid.%r 場合は、SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="67a22-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="67a22-120">SSO 関連管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="67a22-120">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="67a22-121">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="67a22-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="67a22-122">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="67a22-122">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="67a22-123">説明</span><span class="sxs-lookup"><span data-stu-id="67a22-123">Explanation</span></span>  
 <span data-ttu-id="67a22-124">このエラー イベントは、こと、SSO 関連管理者アカウントまたはエンタープライズ シングル サインオンによって作成されたグループが有効な Windows アカウントを示します。</span><span class="sxs-lookup"><span data-stu-id="67a22-124">This Error event indicates that the SSO Affiliate Administrator account or group created by Enterprise Sing Sign-on is not a valid Windows account.</span></span> <span data-ttu-id="67a22-125">SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="67a22-125">The SSO Affiliate Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="67a22-126">SSO 関連管理者アカウントは、ドメインまたはローカル グループ アカウントにもできます。</span><span class="sxs-lookup"><span data-stu-id="67a22-126">The SSO Affiliate Administrator account can also be either a domain or local group account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="67a22-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67a22-127">User Action</span></span>  
 <span data-ttu-id="67a22-128">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67a22-128">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="67a22-129">SSO 関連管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="67a22-129">Verify the SSO Affiliate Administrator account exists.</span></span>  

  <span data-ttu-id="67a22-130">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="67a22-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="67a22-131">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="67a22-131">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="67a22-132">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="67a22-132">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)
