---
title: 'シングル サインオン: イベント 11013 |Microsoft ドキュメント'
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
ms.openlocfilehash: 4765f542f7694b8ca5019af9effb8eace1ffbb60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277946"
---
# <a name="single-sign-on-event-11013"></a><span data-ttu-id="55bdf-102">シングル サインオン: イベント 11013</span><span class="sxs-lookup"><span data-stu-id="55bdf-102">Single Sign-On: Event 11013</span></span>
## <a name="details"></a><span data-ttu-id="55bdf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="55bdf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55bdf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="55bdf-104">Product Name</span></span>|<span data-ttu-id="55bdf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="55bdf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="55bdf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="55bdf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="55bdf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="55bdf-107">Event ID</span></span>|<span data-ttu-id="55bdf-108">11013</span><span class="sxs-lookup"><span data-stu-id="55bdf-108">11013</span></span>|  
|<span data-ttu-id="55bdf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="55bdf-109">Event Source</span></span>|<span data-ttu-id="55bdf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="55bdf-110">ENTSSO</span></span>|  
|<span data-ttu-id="55bdf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55bdf-111">Component</span></span>|<span data-ttu-id="55bdf-112">なし</span><span class="sxs-lookup"><span data-stu-id="55bdf-112">N/A</span></span>|  
|<span data-ttu-id="55bdf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="55bdf-113">Symbolic Name</span></span>|<span data-ttu-id="55bdf-114">SSO_WARN_NOT_APP_USER</span><span class="sxs-lookup"><span data-stu-id="55bdf-114">SSO_WARN_NOT_APP_USER</span></span>|  
|<span data-ttu-id="55bdf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="55bdf-115">Message Text</span></span>|<span data-ttu-id="55bdf-116">クライアント ユーザーがアプリケーション ユーザー アカウントのメンバーではありません。%r</span><span class="sxs-lookup"><span data-stu-id="55bdf-116">Client user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="55bdf-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="55bdf-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="55bdf-118">クライアント ユーザー: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="55bdf-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="55bdf-119">アプリケーション名: %4 %r</span><span class="sxs-lookup"><span data-stu-id="55bdf-119">Application Name: %4%r</span></span><br /><br /> <span data-ttu-id="55bdf-120">アプリケーション ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="55bdf-120">Application Users: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55bdf-121">説明</span><span class="sxs-lookup"><span data-stu-id="55bdf-121">Explanation</span></span>  
 <span data-ttu-id="55bdf-122">クライアント ユーザーがアプリケーション ユーザー アカウントのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="55bdf-122">The client user is not a member of the Application Users account.</span></span> <span data-ttu-id="55bdf-123">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="55bdf-123">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55bdf-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="55bdf-124">User Action</span></span>  
 <span data-ttu-id="55bdf-125">この状況を解決するには、クライアント ユーザーをアプリケーション ユーザー アカウントのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55bdf-125">To remedy the situation, you must make the client user a member of the Application Users account.</span></span> <span data-ttu-id="55bdf-126">今後警告を表示しない場合は、監査レベルを低くします。</span><span class="sxs-lookup"><span data-stu-id="55bdf-126">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>