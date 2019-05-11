---
title: シングル サインオン:イベント 10577 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4563567a-9ee3-4c32-a202-c2521fd95b6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10d381ccbeb1809fbd3a668bd8d1e38264a3a5fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303387"
---
# <a name="single-sign-on-event-10577"></a><span data-ttu-id="3edb6-102">シングル サインオン:イベント 10577</span><span class="sxs-lookup"><span data-stu-id="3edb6-102">Single Sign-On: Event 10577</span></span>
## <a name="details"></a><span data-ttu-id="3edb6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3edb6-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3edb6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3edb6-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="3edb6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3edb6-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="3edb6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3edb6-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="3edb6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3edb6-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="3edb6-108">10577</span><span class="sxs-lookup"><span data-stu-id="3edb6-108">10577</span></span>                                                                                                                       |
|  <span data-ttu-id="3edb6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3edb6-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="3edb6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3edb6-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="3edb6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3edb6-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="3edb6-112">なし</span><span class="sxs-lookup"><span data-stu-id="3edb6-112">N/A</span></span>                                                                                                                        |
|  <span data-ttu-id="3edb6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3edb6-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="3edb6-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="3edb6-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span></span>                                                                                                           |
|  <span data-ttu-id="3edb6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3edb6-115">Message Text</span></span>   | <span data-ttu-id="3edb6-116">更新された SSO 関連管理者 account.%r</span><span class="sxs-lookup"><span data-stu-id="3edb6-116">Updated SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="3edb6-117">新しい SSO 関連管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="3edb6-117">New SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="3edb6-118">古い SSO 関連管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3edb6-118">Old SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="3edb6-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="3edb6-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="3edb6-120">クライアント コンピューターの場合: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="3edb6-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="3edb6-121">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="3edb6-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3edb6-122">説明</span><span class="sxs-lookup"><span data-stu-id="3edb6-122">Explanation</span></span>  
 <span data-ttu-id="3edb6-123">これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。</span><span class="sxs-lookup"><span data-stu-id="3edb6-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="3edb6-124">このメッセージは、SSO 関連管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3edb6-124">This message states that the SSO Affiliate Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3edb6-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3edb6-125">User Action</span></span>  
 <span data-ttu-id="3edb6-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="3edb6-126">No user action is required.</span></span>