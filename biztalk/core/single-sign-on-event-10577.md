---
title: 'シングル サインオン: イベント 10577 |Microsoft Docs'
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
ms.openlocfilehash: 769576430df7ac3ce7ec0ec31a3e7b3eea03968c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003059"
---
# <a name="single-sign-on-event-10577"></a><span data-ttu-id="f617e-102">シングル サインオン: イベント 10577</span><span class="sxs-lookup"><span data-stu-id="f617e-102">Single Sign-On: Event 10577</span></span>
## <a name="details"></a><span data-ttu-id="f617e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f617e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f617e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f617e-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="f617e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f617e-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="f617e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f617e-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="f617e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f617e-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="f617e-108">10577</span><span class="sxs-lookup"><span data-stu-id="f617e-108">10577</span></span>                                                                                                                       |
|  <span data-ttu-id="f617e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f617e-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="f617e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f617e-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="f617e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f617e-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="f617e-112">なし</span><span class="sxs-lookup"><span data-stu-id="f617e-112">N/A</span></span>                                                                                                                        |
|  <span data-ttu-id="f617e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f617e-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="f617e-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="f617e-114">SSO_INFO_CHANGED_SSO_AFF_ADMIN</span></span>                                                                                                           |
|  <span data-ttu-id="f617e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f617e-115">Message Text</span></span>   | <span data-ttu-id="f617e-116">SSO 関連管理者アカウントが更新されました。%r</span><span class="sxs-lookup"><span data-stu-id="f617e-116">Updated SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="f617e-117">新しい SSO 関連管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="f617e-117">New SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="f617e-118">古い SSO 関連管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f617e-118">Old SSO Affiliate Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="f617e-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="f617e-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="f617e-120">クライアント コンピューターの場合: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="f617e-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="f617e-121">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="f617e-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f617e-122">説明</span><span class="sxs-lookup"><span data-stu-id="f617e-122">Explanation</span></span>  
 <span data-ttu-id="f617e-123">これは情報メッセージであり、SSO システム内で発生する重要なセキュリティ関連イベントの追跡に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="f617e-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="f617e-124">このメッセージは、SSO 関連管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="f617e-124">This message states that the SSO Affiliate Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f617e-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f617e-125">User Action</span></span>  
 <span data-ttu-id="f617e-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="f617e-126">No user action is required.</span></span>