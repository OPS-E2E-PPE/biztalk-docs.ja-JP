---
title: 'シングル サインオン: イベント 10571 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c590a00-b8c5-41b4-abb3-0a424e8b052d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 638e04802b2d2cbf4b8089616ac29e451291b5d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009843"
---
# <a name="single-sign-on-event-10571"></a><span data-ttu-id="dc221-102">シングル サインオン: イベント 10571</span><span class="sxs-lookup"><span data-stu-id="dc221-102">Single Sign-On: Event 10571</span></span>
## <a name="details"></a><span data-ttu-id="dc221-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dc221-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dc221-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dc221-104">Product Name</span></span>   |                                                                                          <span data-ttu-id="dc221-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="dc221-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="dc221-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dc221-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                          |
|    <span data-ttu-id="dc221-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dc221-107">Event ID</span></span>     |                                                                                                    <span data-ttu-id="dc221-108">10571</span><span class="sxs-lookup"><span data-stu-id="dc221-108">10571</span></span>                                                                                                     |
|  <span data-ttu-id="dc221-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dc221-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="dc221-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dc221-110">ENTSSO</span></span>                                                                                                    |
|    <span data-ttu-id="dc221-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dc221-111">Component</span></span>    |                                                                                                     <span data-ttu-id="dc221-112">なし</span><span class="sxs-lookup"><span data-stu-id="dc221-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="dc221-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dc221-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="dc221-114">SSO_WARN_SSO_NOT_IN_NEW_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="dc221-114">SSO_WARN_SSO_NOT_IN_NEW_SSO_ADMIN</span></span>                                                                                       |
|  <span data-ttu-id="dc221-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dc221-115">Message Text</span></span>   | <span data-ttu-id="dc221-116">SSO 管理者アカウント名を変更するには、SSO サービス アカウントが新しい SSO 管理者アカウントのメンバーである必要があります。%r</span><span class="sxs-lookup"><span data-stu-id="dc221-116">To change the SSO Administrators account name the SSO service account must be a member of the new SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="dc221-117">SSO サービス アカウント: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="dc221-117">SSO Service Account: %1%r</span></span><br /><br /> <span data-ttu-id="dc221-118">新しい SSO 管理者: %2</span><span class="sxs-lookup"><span data-stu-id="dc221-118">New SSO Administrators: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dc221-119">説明</span><span class="sxs-lookup"><span data-stu-id="dc221-119">Explanation</span></span>  
 <span data-ttu-id="dc221-120">SSO 管理者アカウント名を変更するには、SSO サービス アカウントが新しい SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc221-120">To change the SSO Administrators account name the SSO service account must be a member of the new SSO Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc221-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dc221-121">User Action</span></span>  
 <span data-ttu-id="dc221-122">ロールとアカウントの詳細については、[SSO ユーザー グループ](../core/sso-user-groups.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc221-122">For more information on roles and accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>