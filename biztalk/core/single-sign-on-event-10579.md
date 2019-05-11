---
title: シングル サインオン:イベント 10579 |Microsoft Docs
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
ms.openlocfilehash: 15a1ab9bc79e04c3e87a5db7b09770e3f87edd95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303441"
---
# <a name="single-sign-on-event-10579"></a><span data-ttu-id="66e9f-102">シングル サインオン:イベント 10579</span><span class="sxs-lookup"><span data-stu-id="66e9f-102">Single Sign-On: Event 10579</span></span>
## <a name="details"></a><span data-ttu-id="66e9f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="66e9f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="66e9f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="66e9f-104">Product Name</span></span>   |                                                                                                          <span data-ttu-id="66e9f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="66e9f-105">Enterprise Single Sign-On</span></span>                                                                                                           |
| <span data-ttu-id="66e9f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="66e9f-106">Product Version</span></span> |                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                          |
|    <span data-ttu-id="66e9f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="66e9f-107">Event ID</span></span>     |                                                                                                                    <span data-ttu-id="66e9f-108">10579</span><span class="sxs-lookup"><span data-stu-id="66e9f-108">10579</span></span>                                                                                                                     |
|  <span data-ttu-id="66e9f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="66e9f-109">Event Source</span></span>   |                                                                                                                    <span data-ttu-id="66e9f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="66e9f-110">ENTSSO</span></span>                                                                                                                    |
|    <span data-ttu-id="66e9f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="66e9f-111">Component</span></span>    |                                                                                                                     <span data-ttu-id="66e9f-112">なし</span><span class="sxs-lookup"><span data-stu-id="66e9f-112">N/A</span></span>                                                                                                                      |
|  <span data-ttu-id="66e9f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="66e9f-113">Symbolic Name</span></span>  |                                                                                                       <span data-ttu-id="66e9f-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="66e9f-114">SSO_INFO_CHANGED_APP_ADMIN_GROUP</span></span>                                                                                                       |
|  <span data-ttu-id="66e9f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="66e9f-115">Message Text</span></span>   | <span data-ttu-id="66e9f-116">アプリケーションの更新の管理者 account.%r</span><span class="sxs-lookup"><span data-stu-id="66e9f-116">Updated Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="66e9f-117">新しいアプリケーション管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="66e9f-117">New Application Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="66e9f-118">古いアプリケーション管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="66e9f-118">Old Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="66e9f-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="66e9f-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="66e9f-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="66e9f-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="66e9f-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="66e9f-121">Application Name: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="66e9f-122">説明</span><span class="sxs-lookup"><span data-stu-id="66e9f-122">Explanation</span></span>  
 <span data-ttu-id="66e9f-123">これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。</span><span class="sxs-lookup"><span data-stu-id="66e9f-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="66e9f-124">このメッセージは、アプリケーション管理者アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="66e9f-124">This message states that the Application Administrators account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66e9f-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="66e9f-125">User Action</span></span>  
 <span data-ttu-id="66e9f-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="66e9f-126">No user action is required.</span></span>