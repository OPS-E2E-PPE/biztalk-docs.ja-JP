---
title: シングル サインオン:イベント 11012 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 252bedc8-8dc3-4962-b078-465f9b064ead
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3775772225521941f03c213aa5b1d49ff8bcd04f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267284"
---
# <a name="single-sign-on-event-11012"></a><span data-ttu-id="cf9ca-102">シングル サインオン:イベント 11012</span><span class="sxs-lookup"><span data-stu-id="cf9ca-102">Single Sign-On: Event 11012</span></span>
## <a name="details"></a><span data-ttu-id="cf9ca-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cf9ca-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cf9ca-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cf9ca-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="cf9ca-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cf9ca-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="cf9ca-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cf9ca-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="cf9ca-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cf9ca-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="cf9ca-108">11012</span><span class="sxs-lookup"><span data-stu-id="cf9ca-108">11012</span></span>                                                                                                          |
|  <span data-ttu-id="cf9ca-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cf9ca-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="cf9ca-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cf9ca-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="cf9ca-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf9ca-111">Component</span></span>    |                                                                                                          <span data-ttu-id="cf9ca-112">なし</span><span class="sxs-lookup"><span data-stu-id="cf9ca-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="cf9ca-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cf9ca-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="cf9ca-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span><span class="sxs-lookup"><span data-stu-id="cf9ca-114">SSO_WARN_NOT_APP_ADMIN_ADMIN_SAME</span></span>                                                                                            |
|  <span data-ttu-id="cf9ca-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cf9ca-115">Message Text</span></span>   | <span data-ttu-id="cf9ca-116">クライアント ユーザーはアプリケーション管理者 account.%r のメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="cf9ca-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="cf9ca-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cf9ca-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cf9ca-118">クライアント ユーザー: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="cf9ca-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="cf9ca-119">アプリケーション名: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="cf9ca-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="cf9ca-120">アプリケーション管理者: %5</span><span class="sxs-lookup"><span data-stu-id="cf9ca-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cf9ca-121">説明</span><span class="sxs-lookup"><span data-stu-id="cf9ca-121">Explanation</span></span>  
 <span data-ttu-id="cf9ca-122">クライアント ユーザーは、アプリケーション管理者アカウントのメンバーではないです。</span><span class="sxs-lookup"><span data-stu-id="cf9ca-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="cf9ca-123">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf9ca-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf9ca-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cf9ca-124">User Action</span></span>  
 <span data-ttu-id="cf9ca-125">状況を解決するには、アプリケーションの管理者アカウントのメンバー、クライアント ユーザーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf9ca-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="cf9ca-126">この警告を今後表示しないを停止するには、監査レベルを下げることです。</span><span class="sxs-lookup"><span data-stu-id="cf9ca-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>