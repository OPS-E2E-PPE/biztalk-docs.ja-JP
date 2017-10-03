---
title: "シングル サインオン: イベント 10535 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3f96032c8176a251090453e493487a97d9cf0fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10535"></a><span data-ttu-id="d971e-102">シングル サインオン: イベント 10535</span><span class="sxs-lookup"><span data-stu-id="d971e-102">Single Sign-On: Event 10535</span></span>
## <a name="details"></a><span data-ttu-id="d971e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d971e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d971e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d971e-104">Product Name</span></span>|<span data-ttu-id="d971e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d971e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d971e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d971e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d971e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d971e-107">Event ID</span></span>|<span data-ttu-id="d971e-108">10535</span><span class="sxs-lookup"><span data-stu-id="d971e-108">10535</span></span>|  
|<span data-ttu-id="d971e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d971e-109">Event Source</span></span>|<span data-ttu-id="d971e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d971e-110">ENTSSO</span></span>|  
|<span data-ttu-id="d971e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d971e-111">Component</span></span>|<span data-ttu-id="d971e-112">CO</span><span class="sxs-lookup"><span data-stu-id="d971e-112">CO</span></span>|  
|<span data-ttu-id="d971e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d971e-113">Symbolic Name</span></span>|<span data-ttu-id="d971e-114">SSO_INFO_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="d971e-114">SSO_INFO_API_AUDIT</span></span>|  
|<span data-ttu-id="d971e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d971e-115">Message Text</span></span>|<span data-ttu-id="d971e-116">SSO の監査%r</span><span class="sxs-lookup"><span data-stu-id="d971e-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="d971e-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d971e-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="d971e-118">追跡 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d971e-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="d971e-119">クライアント コンピューターの場合: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d971e-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="d971e-120">クライアント ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="d971e-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="d971e-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="d971e-121">Application Name: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d971e-122">説明</span><span class="sxs-lookup"><span data-stu-id="d971e-122">Explanation</span></span>  
 <span data-ttu-id="d971e-123">この情報監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d971e-123">This Information Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="d971e-124">このイベント メッセージには次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d971e-124">This event message includes:</span></span>  
  
 <span data-ttu-id="d971e-125">**関数:**実行されている関数</span><span class="sxs-lookup"><span data-stu-id="d971e-125">**Function:** Function being performed</span></span>  
  
 <span data-ttu-id="d971e-126">**追跡 ID:** SSO API が最初に生成された一意の GUID が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d971e-126">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  
  
 <span data-ttu-id="d971e-127">**クライアント コンピューター:**関数が開始したクライアント コンピューター。</span><span class="sxs-lookup"><span data-stu-id="d971e-127">**Client Computer:** Client computer where the function originated.</span></span>  
  
 <span data-ttu-id="d971e-128">**クライアント ユーザー:**関数を呼び出したユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="d971e-128">**Client User:** The name of the user account that invoked the function.</span></span>  
  
 <span data-ttu-id="d971e-129">**アプリケーション名:** SSO の名前は、この関数に関連付けられているアプリケーションを関連します。</span><span class="sxs-lookup"><span data-stu-id="d971e-129">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  
  
 <span data-ttu-id="d971e-130">この種類のイベントは、開発、トラブルシューティング、またはアプリケーションの実行時に発生した問題の診断に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d971e-130">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="d971e-131">表示された情報を使用して、実行中の SSO API 呼び出しを判別できます。</span><span class="sxs-lookup"><span data-stu-id="d971e-131">Information provided can be used to determine the SSO API call being made.</span></span>  
  
 <span data-ttu-id="d971e-132">監査レベルは 0/1/2/3 に設定できます。0 は “オフ”、1 は “低“ でエラーのみが表示され、2 は “中” でエラーと警告が表示され、3 は “高” ですべての監査メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d971e-132">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d971e-133">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d971e-133">User Action</span></span>  
  
-   <span data-ttu-id="d971e-134">関連するイベント メッセージについては、イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="d971e-134">Check the event log for associated event messages.</span></span>  
  
 <span data-ttu-id="d971e-135">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="d971e-135">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="d971e-136">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="d971e-136">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="d971e-137">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="d971e-137">Using SSO</span></span>](../core/using-sso.md)