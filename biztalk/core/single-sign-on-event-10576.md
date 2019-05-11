---
title: シングル サインオン:イベント 10576 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b2d9904-4302-41b7-bced-7db46cc05d7f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8492d2d6e9aee841d60aea305dc6669f7df63efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303472"
---
# <a name="single-sign-on-event-10576"></a><span data-ttu-id="42b1e-102">シングル サインオン:イベント 10576</span><span class="sxs-lookup"><span data-stu-id="42b1e-102">Single Sign-On: Event 10576</span></span>
## <a name="details"></a><span data-ttu-id="42b1e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="42b1e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="42b1e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="42b1e-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="42b1e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="42b1e-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="42b1e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="42b1e-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="42b1e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="42b1e-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="42b1e-108">10576</span><span class="sxs-lookup"><span data-stu-id="42b1e-108">10576</span></span>                                                                                                        |
|  <span data-ttu-id="42b1e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="42b1e-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="42b1e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="42b1e-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="42b1e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42b1e-111">Component</span></span>    |                                                                                                         <span data-ttu-id="42b1e-112">なし</span><span class="sxs-lookup"><span data-stu-id="42b1e-112">N/A</span></span>                                                                                                         |
|  <span data-ttu-id="42b1e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="42b1e-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="42b1e-114">SSO_INFO_CHANGED_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="42b1e-114">SSO_INFO_CHANGED_SSO_ADMIN</span></span>                                                                                              |
|  <span data-ttu-id="42b1e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="42b1e-115">Message Text</span></span>   | <span data-ttu-id="42b1e-116">SSO の更新の管理者 account.%r</span><span class="sxs-lookup"><span data-stu-id="42b1e-116">Updated SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="42b1e-117">新しい SSO 管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="42b1e-117">New SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="42b1e-118">古い SSO 管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="42b1e-118">Old SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="42b1e-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="42b1e-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="42b1e-120">クライアント コンピューターの場合: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="42b1e-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="42b1e-121">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="42b1e-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="42b1e-122">説明</span><span class="sxs-lookup"><span data-stu-id="42b1e-122">Explanation</span></span>  
 <span data-ttu-id="42b1e-123">これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。</span><span class="sxs-lookup"><span data-stu-id="42b1e-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="42b1e-124">このメッセージは、SSO 管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="42b1e-124">This message states that the SSO Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42b1e-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="42b1e-125">User Action</span></span>  
 <span data-ttu-id="42b1e-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="42b1e-126">No user action is required.</span></span>