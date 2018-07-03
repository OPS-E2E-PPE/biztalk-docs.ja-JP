---
title: 'シングル サインオン: イベント 10579 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e18f6d-9dda-49bf-a901-bb28f4cd9a84
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aab40dded4fc677d86c9c1a4ab21d17434cfa8b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002683"
---
# <a name="single-sign-on-event-10579"></a><span data-ttu-id="b8f4a-102">シングル サインオン: イベント 10579</span><span class="sxs-lookup"><span data-stu-id="b8f4a-102">Single Sign-On: Event 10579</span></span>
## <a name="details"></a><span data-ttu-id="b8f4a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b8f4a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b8f4a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b8f4a-104">Product Name</span></span>   |                                                                                                          <span data-ttu-id="b8f4a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b8f4a-105">Enterprise Single Sign-On</span></span>                                                                                                           |
| <span data-ttu-id="b8f4a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b8f4a-106">Product Version</span></span> |                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                          |
|    <span data-ttu-id="b8f4a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b8f4a-107">Event ID</span></span>     |                                                                                                                    <span data-ttu-id="b8f4a-108">10579</span><span class="sxs-lookup"><span data-stu-id="b8f4a-108">10579</span></span>                                                                                                                     |
|  <span data-ttu-id="b8f4a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b8f4a-109">Event Source</span></span>   |                                                                                                                    <span data-ttu-id="b8f4a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b8f4a-110">ENTSSO</span></span>                                                                                                                    |
|    <span data-ttu-id="b8f4a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b8f4a-111">Component</span></span>    |                                                                                                                     <span data-ttu-id="b8f4a-112">なし</span><span class="sxs-lookup"><span data-stu-id="b8f4a-112">N/A</span></span>                                                                                                                      |
|  <span data-ttu-id="b8f4a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b8f4a-113">Symbolic Name</span></span>  |                                                                                                       <span data-ttu-id="b8f4a-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="b8f4a-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span></span>                                                                                                       |
|  <span data-ttu-id="b8f4a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b8f4a-115">Message Text</span></span>   | <span data-ttu-id="b8f4a-116">アプリケーション管理者アカウントが更新されました。%r</span><span class="sxs-lookup"><span data-stu-id="b8f4a-116">Updated Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="b8f4a-117">新しいアプリケーション管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="b8f4a-117">New Application Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="b8f4a-118">古いアプリケーション管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="b8f4a-118">Old Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="b8f4a-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="b8f4a-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="b8f4a-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="b8f4a-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="b8f4a-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="b8f4a-121">Application Name: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b8f4a-122">説明</span><span class="sxs-lookup"><span data-stu-id="b8f4a-122">Explanation</span></span>  
 <span data-ttu-id="b8f4a-123">これは情報メッセージであり、SSO システム内で発生する重要なセキュリティ関連イベントの追跡に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="b8f4a-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="b8f4a-124">このメッセージは、アプリケーション管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b8f4a-124">This message states that the Application Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8f4a-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b8f4a-125">User Action</span></span>  
 <span data-ttu-id="b8f4a-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="b8f4a-126">No user action is required.</span></span>