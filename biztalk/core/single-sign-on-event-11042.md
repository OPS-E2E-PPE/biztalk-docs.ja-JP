---
title: シングル サインオン:イベント 11042 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bef9cdffc7e1b11409491ad27bb195d40c639518
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400981"
---
# <a name="single-sign-on-event-11042"></a><span data-ttu-id="66353-102">シングル サインオン:イベント 11042</span><span class="sxs-lookup"><span data-stu-id="66353-102">Single Sign-On: Event 11042</span></span>
## <a name="details"></a><span data-ttu-id="66353-103">詳細</span><span class="sxs-lookup"><span data-stu-id="66353-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="66353-104">製品名</span><span class="sxs-lookup"><span data-stu-id="66353-104">Product Name</span></span>   |                                                                                                                                                   <span data-ttu-id="66353-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="66353-105">Enterprise Single Sign-On</span></span>                                                                                                                                                   |
| <span data-ttu-id="66353-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="66353-106">Product Version</span></span> |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    <span data-ttu-id="66353-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="66353-107">Event ID</span></span>     |                                                                                                                                                             <span data-ttu-id="66353-108">11042</span><span class="sxs-lookup"><span data-stu-id="66353-108">11042</span></span>                                                                                                                                                             |
|  <span data-ttu-id="66353-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="66353-109">Event Source</span></span>   |                                                                                                                                                            <span data-ttu-id="66353-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="66353-110">ENTSSO</span></span>                                                                                                                                                             |
|    <span data-ttu-id="66353-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="66353-111">Component</span></span>    |                                                                                                                                                              <span data-ttu-id="66353-112">なし</span><span class="sxs-lookup"><span data-stu-id="66353-112">N/A</span></span>                                                                                                                                                              |
|  <span data-ttu-id="66353-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="66353-113">Symbolic Name</span></span>  |                                                                                                                                                <span data-ttu-id="66353-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span><span class="sxs-lookup"><span data-stu-id="66353-114">SSO_WARN_ACCESS_DENIED_ACCOUNTS</span></span>                                                                                                                                                |
|  <span data-ttu-id="66353-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="66353-115">Message Text</span></span>   | <span data-ttu-id="66353-116">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="66353-116">Access denied.</span></span><br /><br /> <span data-ttu-id="66353-117">クライアント ユーザーはこの function.%r を実行するには、次のアカウントのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="66353-117">The client user must be a member of one of the following accounts to perform this function.%r</span></span><br /><br /> <span data-ttu-id="66353-118">SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="66353-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="66353-119">SSO 関連管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="66353-119">SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="66353-120">アプリケーション管理者: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="66353-120">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="66353-121">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="66353-121">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="66353-122">追加データ: %5</span><span class="sxs-lookup"><span data-stu-id="66353-122">Additional Data: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="66353-123">説明</span><span class="sxs-lookup"><span data-stu-id="66353-123">Explanation</span></span>  
 <span data-ttu-id="66353-124">クライアント ユーザーは、この機能を実行する警告の一覧にあるアカウントのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="66353-124">The client user must be a member of one of the accounts listed in the warning to perform this function.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66353-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="66353-125">User Action</span></span>  
 <span data-ttu-id="66353-126">この機能を実行するアカウントのいずれかに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66353-126">You must join one of the accounts to perform this function.</span></span>