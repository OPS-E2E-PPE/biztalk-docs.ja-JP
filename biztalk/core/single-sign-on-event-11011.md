---
title: 'シングル サインオン: イベント 11011 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ef430a-fb3b-4bf7-936f-a866262a6c3a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ba98bf7fb3f57fdf9ce082028f2fff9ea7f618
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972971"
---
# <a name="single-sign-on-event-11011"></a><span data-ttu-id="cddbb-102">シングル サインオン: イベント 11011</span><span class="sxs-lookup"><span data-stu-id="cddbb-102">Single Sign-On: Event 11011</span></span>
## <a name="details"></a><span data-ttu-id="cddbb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cddbb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cddbb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cddbb-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="cddbb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cddbb-105">Enterprise Single Sign-On</span></span>                                                                                                |
| <span data-ttu-id="cddbb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cddbb-106">Product Version</span></span> |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="cddbb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cddbb-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="cddbb-108">11011</span><span class="sxs-lookup"><span data-stu-id="cddbb-108">11011</span></span>                                                                                                          |
|  <span data-ttu-id="cddbb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cddbb-109">Event Source</span></span>   |                                                                                                         <span data-ttu-id="cddbb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cddbb-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="cddbb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cddbb-111">Component</span></span>    |                                                                                                          <span data-ttu-id="cddbb-112">なし</span><span class="sxs-lookup"><span data-stu-id="cddbb-112">N/A</span></span>                                                                                                           |
|  <span data-ttu-id="cddbb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cddbb-113">Symbolic Name</span></span>  |                                                                                                 <span data-ttu-id="cddbb-114">SSO_WARN_NOT_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="cddbb-114">SSO_WARN_NOT_APP_ADMIN</span></span>                                                                                                 |
|  <span data-ttu-id="cddbb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cddbb-115">Message Text</span></span>   | <span data-ttu-id="cddbb-116">クライアント ユーザーはアプリケーション管理者アカウントのメンバーではありません。%r</span><span class="sxs-lookup"><span data-stu-id="cddbb-116">Client user is not a member of the Application Administrators account.%r</span></span><br /><br /> <span data-ttu-id="cddbb-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cddbb-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cddbb-118">クライアント ユーザー: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="cddbb-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="cddbb-119">アプリケーション名: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="cddbb-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="cddbb-120">アプリケーション管理者: %5</span><span class="sxs-lookup"><span data-stu-id="cddbb-120">Application Administrators: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cddbb-121">説明</span><span class="sxs-lookup"><span data-stu-id="cddbb-121">Explanation</span></span>  
 <span data-ttu-id="cddbb-122">クライアント ユーザーはアプリケーション管理者アカウントのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="cddbb-122">The client user is not a member of the Application Administrators account.</span></span> <span data-ttu-id="cddbb-123">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cddbb-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cddbb-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cddbb-124">User Action</span></span>  
 <span data-ttu-id="cddbb-125">この状況に対処するには、クライアント ユーザーをアプリケーション管理者アカウントのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cddbb-125">To remedy the situation, you must make the client user a member of the Application Administrators account.</span></span> <span data-ttu-id="cddbb-126">今後警告を表示しない場合は、監査レベルを低くします。</span><span class="sxs-lookup"><span data-stu-id="cddbb-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>