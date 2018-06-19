---
title: 'シングル サインオン: イベント 10540 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec48afebfa36411594c28908a233409311e32df9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270994"
---
# <a name="single-sign-on-event-10540"></a><span data-ttu-id="55684-102">シングル サインオン: イベント 10540</span><span class="sxs-lookup"><span data-stu-id="55684-102">Single Sign-On: Event 10540</span></span>
## <a name="details"></a><span data-ttu-id="55684-103">詳細</span><span class="sxs-lookup"><span data-stu-id="55684-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55684-104">製品名</span><span class="sxs-lookup"><span data-stu-id="55684-104">Product Name</span></span>|<span data-ttu-id="55684-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="55684-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="55684-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="55684-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="55684-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="55684-107">Event ID</span></span>|<span data-ttu-id="55684-108">10540</span><span class="sxs-lookup"><span data-stu-id="55684-108">10540</span></span>|  
|<span data-ttu-id="55684-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="55684-109">Event Source</span></span>|<span data-ttu-id="55684-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="55684-110">ENTSSO</span></span>|  
|<span data-ttu-id="55684-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55684-111">Component</span></span>|<span data-ttu-id="55684-112">CO</span><span class="sxs-lookup"><span data-stu-id="55684-112">CO</span></span>|  
|<span data-ttu-id="55684-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="55684-113">Symbolic Name</span></span>|<span data-ttu-id="55684-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="55684-114">SSO_WARN_APP_TICKETS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="55684-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="55684-115">Message Text</span></span>|<span data-ttu-id="55684-116">チケットはこのアプリケーションに対して有効になっていません。%r</span><span class="sxs-lookup"><span data-stu-id="55684-116">Tickets are not enabled for this application.%r</span></span><br /><br /> <span data-ttu-id="55684-117">アプリケーション名: %1</span><span class="sxs-lookup"><span data-stu-id="55684-117">Application Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="55684-118">説明</span><span class="sxs-lookup"><span data-stu-id="55684-118">Explanation</span></span>  
 <span data-ttu-id="55684-119">この警告イベントは、チケット機能がこのアプリケーションで有効になっていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="55684-119">This Warning event indicates that the tickets feature has not been enabled for this application.</span></span> <span data-ttu-id="55684-120">SSO チケットの使用は、SSO アプリケーションごとのオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="55684-120">The use of SSO tickets is an optional feature for each SSO application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="55684-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="55684-121">User Action</span></span>  
 <span data-ttu-id="55684-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="55684-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="55684-123">アプリケーション管理者に連絡し、この SSO アプリケーションのチケットを有効にしてもらいます。</span><span class="sxs-lookup"><span data-stu-id="55684-123">Contact your Application Administrator to enable tickets for this SSO application.</span></span> <span data-ttu-id="55684-124">SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55684-124">This can be done using the SSO administration tools (GUI or command line).</span></span>  
  
 <span data-ttu-id="55684-125">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="55684-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="55684-126">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="55684-126">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="55684-127">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="55684-127">How to List the Properties of an Affiliate Application</span></span>](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [<span data-ttu-id="55684-128">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="55684-128">How to Update the Properties of an Affiliate Application</span></span>](../core/how-to-update-the-properties-of-an-affiliate-application.md)