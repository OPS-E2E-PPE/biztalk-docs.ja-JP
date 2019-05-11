---
title: シングル サインオン:イベント 10517 |Microsoft Docs
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
ms.openlocfilehash: a9febc85f554b8736d75c9315a37214c8a81ca16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279807"
---
# <a name="single-sign-on-event-10517"></a><span data-ttu-id="68afb-102">シングル サインオン:イベント 10517</span><span class="sxs-lookup"><span data-stu-id="68afb-102">Single Sign-On: Event 10517</span></span>
## <a name="details"></a><span data-ttu-id="68afb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68afb-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="68afb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68afb-104">Product Name</span></span>   |                                                                                                                                                  <span data-ttu-id="68afb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="68afb-105">Enterprise Single Sign-On</span></span>                                                                                                                                                  |
| <span data-ttu-id="68afb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68afb-106">Product Version</span></span> |                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                  |
|    <span data-ttu-id="68afb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68afb-107">Event ID</span></span>     |                                                                                                                                                            <span data-ttu-id="68afb-108">10517</span><span class="sxs-lookup"><span data-stu-id="68afb-108">10517</span></span>                                                                                                                                                            |
|  <span data-ttu-id="68afb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68afb-109">Event Source</span></span>   |                                                                                                                                                           <span data-ttu-id="68afb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="68afb-110">ENTSSO</span></span>                                                                                                                                                            |
|    <span data-ttu-id="68afb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68afb-111">Component</span></span>    |                                                                                                                                                             <span data-ttu-id="68afb-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="68afb-112">N\A</span></span>                                                                                                                                                             |
|  <span data-ttu-id="68afb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68afb-113">Symbolic Name</span></span>  |                                                                                                                                                   <span data-ttu-id="68afb-114">SSO_ERROR_BAD_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="68afb-114">SSO_ERROR_BAD_SSO_ADMIN</span></span>                                                                                                                                                   |
|  <span data-ttu-id="68afb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68afb-115">Message Text</span></span>   | <span data-ttu-id="68afb-116">SSO 管理者アカウントが無効です。</span><span class="sxs-lookup"><span data-stu-id="68afb-116">The SSO Administrators account is not valid.</span></span> <span data-ttu-id="68afb-117">このアカウントは、サーバーに存在するローカル アカウント チェックの場合。</span><span class="sxs-lookup"><span data-stu-id="68afb-117">If it is a local account check that this account exists on the server.</span></span> <span data-ttu-id="68afb-118">場合はドメイン アカウントには、ドメイン管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="68afb-118">If it is a domain account contact your domain administrator.</span></span> <span data-ttu-id="68afb-119">アカウントが valid.%r 場合は、SSO を有効にします。</span><span class="sxs-lookup"><span data-stu-id="68afb-119">Enable SSO when the account is valid.%r</span></span><br /><br /> <span data-ttu-id="68afb-120">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="68afb-120">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="68afb-121">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="68afb-121">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="68afb-122">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="68afb-122">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="68afb-123">説明</span><span class="sxs-lookup"><span data-stu-id="68afb-123">Explanation</span></span>  
 <span data-ttu-id="68afb-124">このエラー イベントは、エンタープライズ シングル サインオン用に指定された SSO 管理者アカウントが有効な Windows アカウントではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="68afb-124">This Error event indicates that the SSO Administrators account specified for Enterprise Single Sign-On is not a valid Windows account.</span></span> <span data-ttu-id="68afb-125">エンタープライズ シングル サインオン サービスを実行するサービス アカウントは、このアカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="68afb-125">The service account running the Enterprise Single Sign-On service must be a member of this account.</span></span> <span data-ttu-id="68afb-126">SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="68afb-126">The SSO Administrators account can be either a Windows group account or an individual account.</span></span> <span data-ttu-id="68afb-127">SSO 管理者アカウントは、ドメインまたはローカル グループ アカウントにもできます。</span><span class="sxs-lookup"><span data-stu-id="68afb-127">The SSO Administrators account can also be either a domain or local group account.</span></span> <span data-ttu-id="68afb-128">個々 のアカウントを使用する場合は、別の単独アカウントをこのアカウントを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="68afb-128">When using an individual account, you cannot change this account to another individual account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="68afb-129">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68afb-129">User Action</span></span>  
 <span data-ttu-id="68afb-130">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68afb-130">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="68afb-131">SSO 管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="68afb-131">Verify the SSO Administrators account exists.</span></span>  

  <span data-ttu-id="68afb-132">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="68afb-132">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="68afb-133">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="68afb-133">SSO User Groups</span></span>](../core/sso-user-groups.md)
