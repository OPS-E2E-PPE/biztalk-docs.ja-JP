---
title: 'シングル サインオン: イベント 10731 |Microsoft Docs'
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
ms.openlocfilehash: d51174c0a7241f7f8bb8b5287cb03b139d6f87c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998515"
---
# <a name="single-sign-on-event-10731"></a><span data-ttu-id="08526-102">シングル サインオン: イベント 10731</span><span class="sxs-lookup"><span data-stu-id="08526-102">Single Sign-On: Event 10731</span></span>
## <a name="details"></a><span data-ttu-id="08526-103">詳細</span><span class="sxs-lookup"><span data-stu-id="08526-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="08526-104">製品名</span><span class="sxs-lookup"><span data-stu-id="08526-104">Product Name</span></span>   |                                                                                                                         <span data-ttu-id="08526-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="08526-105">Enterprise Single Sign-On</span></span>                                                                                                                         |
| <span data-ttu-id="08526-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="08526-106">Product Version</span></span> |                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                         |
|    <span data-ttu-id="08526-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="08526-107">Event ID</span></span>     |                                                                                                                                   <span data-ttu-id="08526-108">10731</span><span class="sxs-lookup"><span data-stu-id="08526-108">10731</span></span>                                                                                                                                   |
|  <span data-ttu-id="08526-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="08526-109">Event Source</span></span>   |                                                                                                                                  <span data-ttu-id="08526-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="08526-110">ENTSSO</span></span>                                                                                                                                   |
|    <span data-ttu-id="08526-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="08526-111">Component</span></span>    |                                                                                                                                    <span data-ttu-id="08526-112">N\A</span><span class="sxs-lookup"><span data-stu-id="08526-112">N\A</span></span>                                                                                                                                    |
|  <span data-ttu-id="08526-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="08526-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="08526-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="08526-114">SSO_WARN_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                                     |
|  <span data-ttu-id="08526-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="08526-115">Message Text</span></span>   | <span data-ttu-id="08526-116">指定されたユーザーが Application Users アカウントのメンバーではないため、マッピングを作成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="08526-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="08526-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="08526-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="08526-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="08526-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="08526-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="08526-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="08526-120">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="08526-120">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="08526-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="08526-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="08526-122">説明</span><span class="sxs-lookup"><span data-stu-id="08526-122">Explanation</span></span>  
 <span data-ttu-id="08526-123">この警告イベントは、指定されたユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="08526-123">This Warning event indicates that a mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  

 <span data-ttu-id="08526-124">アプリケーション ユーザーのグループ アカウントは、関連アプリケーションごとに存在します。</span><span class="sxs-lookup"><span data-stu-id="08526-124">An application user's group account exists for each affiliate application.</span></span> <span data-ttu-id="08526-125">このアカウントのメンバーは、関連アプリケーションで資格情報を検証でき、関連アプリケーションで資格情報のマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="08526-125">Members of this account can verify their credentials in the affiliate application and can manage their credential mappings in the affiliate application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="08526-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="08526-126">User Action</span></span>  
 <span data-ttu-id="08526-127">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="08526-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="08526-128">指定したユーザーを、指定した関連アプリケーションのアプリケーション ユーザーのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="08526-128">Add the specified user to the application user's group for the specified affiliate application.</span></span>  

  <span data-ttu-id="08526-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08526-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="08526-130">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="08526-130">SSO User Groups</span></span>](../core/sso-user-groups.md)  

- [<span data-ttu-id="08526-131">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="08526-131">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)
