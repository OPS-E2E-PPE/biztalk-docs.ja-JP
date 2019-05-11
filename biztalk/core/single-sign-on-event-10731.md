---
title: シングル サインオン:イベント 10731 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 605e77f0-61f2-4a97-9ea0-bdc56344e8d9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 630267c28a4db6b570be4c6efe73218e45f15b2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267518"
---
# <a name="single-sign-on-event-10731"></a><span data-ttu-id="e7679-102">シングル サインオン:イベント 10731</span><span class="sxs-lookup"><span data-stu-id="e7679-102">Single Sign-On: Event 10731</span></span>
## <a name="details"></a><span data-ttu-id="e7679-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e7679-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e7679-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e7679-104">Product Name</span></span>   |                                                                                                                         <span data-ttu-id="e7679-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e7679-105">Enterprise Single Sign-On</span></span>                                                                                                                         |
| <span data-ttu-id="e7679-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e7679-106">Product Version</span></span> |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    <span data-ttu-id="e7679-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e7679-107">Event ID</span></span>     |                                                                                                                                   <span data-ttu-id="e7679-108">10731</span><span class="sxs-lookup"><span data-stu-id="e7679-108">10731</span></span>                                                                                                                                   |
|  <span data-ttu-id="e7679-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e7679-109">Event Source</span></span>   |                                                                                                                                  <span data-ttu-id="e7679-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e7679-110">ENTSSO</span></span>                                                                                                                                   |
|    <span data-ttu-id="e7679-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7679-111">Component</span></span>    |                                                                                                                                    <span data-ttu-id="e7679-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7679-112">N\A</span></span>                                                                                                                                    |
|  <span data-ttu-id="e7679-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e7679-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="e7679-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="e7679-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                                     |
|  <span data-ttu-id="e7679-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e7679-115">Message Text</span></span>   | <span data-ttu-id="e7679-116">指定したユーザーがアプリケーション ユーザー account.%r のメンバーではないために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e7679-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="e7679-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e7679-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="e7679-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="e7679-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="e7679-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="e7679-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="e7679-120">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="e7679-120">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="e7679-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="e7679-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="e7679-122">説明</span><span class="sxs-lookup"><span data-stu-id="e7679-122">Explanation</span></span>  
 <span data-ttu-id="e7679-123">この警告イベントは、指定したユーザーがアプリケーション ユーザー アカウントのメンバーではないためは、マッピングを作成できませんでしたを示します。</span><span class="sxs-lookup"><span data-stu-id="e7679-123">This Warning event indicates that a mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  

 <span data-ttu-id="e7679-124">関連アプリケーションごとに、アプリケーション ユーザーのグループのアカウントが存在します。</span><span class="sxs-lookup"><span data-stu-id="e7679-124">An application user's group account exists for each affiliate application.</span></span> <span data-ttu-id="e7679-125">このアカウントのメンバーでは、関連アプリケーションで資格情報を確認することができ、関連アプリケーションで資格情報マッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e7679-125">Members of this account can verify their credentials in the affiliate application and can manage their credential mappings in the affiliate application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e7679-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e7679-126">User Action</span></span>  
 <span data-ttu-id="e7679-127">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7679-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="e7679-128">指定された関連アプリケーションのアプリケーション ユーザーのグループに指定されたユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e7679-128">Add the specified user to the application user's group for the specified affiliate application.</span></span>  

  <span data-ttu-id="e7679-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7679-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="e7679-130">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="e7679-130">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="e7679-131">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e7679-131">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)
