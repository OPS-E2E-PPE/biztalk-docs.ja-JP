---
title: シングル サインオン:イベント 11013 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 450836dc-ddeb-4423-9966-69ad173f2c87
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9a59bb13c413489f3b950409fe886c7ddc2e0d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267288"
---
# <a name="single-sign-on-event-11013"></a><span data-ttu-id="bfbe4-102">シングル サインオン:イベント 11013</span><span class="sxs-lookup"><span data-stu-id="bfbe4-102">Single Sign-On: Event 11013</span></span>
## <a name="details"></a><span data-ttu-id="bfbe4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bfbe4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bfbe4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bfbe4-104">Product Name</span></span>   |                                                                                      <span data-ttu-id="bfbe4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bfbe4-105">Enterprise Single Sign-On</span></span>                                                                                       |
| <span data-ttu-id="bfbe4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bfbe4-106">Product Version</span></span> |                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    <span data-ttu-id="bfbe4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bfbe4-107">Event ID</span></span>     |                                                                                                <span data-ttu-id="bfbe4-108">11013</span><span class="sxs-lookup"><span data-stu-id="bfbe4-108">11013</span></span>                                                                                                 |
|  <span data-ttu-id="bfbe4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bfbe4-109">Event Source</span></span>   |                                                                                                <span data-ttu-id="bfbe4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfbe4-110">ENTSSO</span></span>                                                                                                |
|    <span data-ttu-id="bfbe4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfbe4-111">Component</span></span>    |                                                                                                 <span data-ttu-id="bfbe4-112">なし</span><span class="sxs-lookup"><span data-stu-id="bfbe4-112">N/A</span></span>                                                                                                  |
|  <span data-ttu-id="bfbe4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bfbe4-113">Symbolic Name</span></span>  |                                                                                        <span data-ttu-id="bfbe4-114">SSO_WARN_NOT_APP_USER</span><span class="sxs-lookup"><span data-stu-id="bfbe4-114">SSO_WARN_NOT_APP_USER</span></span>                                                                                         |
|  <span data-ttu-id="bfbe4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bfbe4-115">Message Text</span></span>   | <span data-ttu-id="bfbe4-116">クライアント ユーザーがアプリケーション ユーザー account.%r のメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="bfbe4-116">Client user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="bfbe4-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bfbe4-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bfbe4-118">クライアント ユーザー: %2\\% 3 %r</span><span class="sxs-lookup"><span data-stu-id="bfbe4-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="bfbe4-119">アプリケーション名: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="bfbe4-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="bfbe4-120">アプリケーション ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="bfbe4-120">Application Users: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bfbe4-121">説明</span><span class="sxs-lookup"><span data-stu-id="bfbe4-121">Explanation</span></span>  
 <span data-ttu-id="bfbe4-122">クライアント ユーザーは、アプリケーション ユーザー アカウントのメンバーではないです。</span><span class="sxs-lookup"><span data-stu-id="bfbe4-122">The client user is not a member of the Application Users account.</span></span> <span data-ttu-id="bfbe4-123">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfbe4-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfbe4-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bfbe4-124">User Action</span></span>  
 <span data-ttu-id="bfbe4-125">状況を解決するには、アプリケーション ユーザー アカウントのメンバー、クライアント ユーザーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfbe4-125">To remedy the situation, you must make the client user a member of the Application Users account.</span></span> <span data-ttu-id="bfbe4-126">この警告を今後表示しないを停止するには、監査レベルを下げることです。</span><span class="sxs-lookup"><span data-stu-id="bfbe4-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>