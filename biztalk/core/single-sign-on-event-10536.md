---
title: 'シングル サインオン: イベント 10536 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d493a45b-c4ed-40fc-8803-b3ca12f9795b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49687739fced504c9dccc06969c9eb3e10d9aae4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016132"
---
# <a name="single-sign-on-event-10536"></a><span data-ttu-id="6130b-102">シングル サインオン: イベント 10536</span><span class="sxs-lookup"><span data-stu-id="6130b-102">Single Sign-On: Event 10536</span></span>
## <a name="details"></a><span data-ttu-id="6130b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6130b-103">Details</span></span>  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6130b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6130b-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="6130b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6130b-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="6130b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6130b-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="6130b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6130b-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="6130b-108">10536</span><span class="sxs-lookup"><span data-stu-id="6130b-108">10536</span></span>                                                                                                |
|  <span data-ttu-id="6130b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6130b-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="6130b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6130b-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="6130b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6130b-111">Component</span></span>    |                                                                                                 <span data-ttu-id="6130b-112">CO</span><span class="sxs-lookup"><span data-stu-id="6130b-112">CO</span></span>                                                                                                 |
|  <span data-ttu-id="6130b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6130b-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="6130b-114">SSO_WARN_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="6130b-114">SSO_WARN_API_AUDIT</span></span>                                                                                         |
|  <span data-ttu-id="6130b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6130b-115">Message Text</span></span>   | <span data-ttu-id="6130b-116">SSO の監査%r</span><span class="sxs-lookup"><span data-stu-id="6130b-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="6130b-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6130b-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="6130b-118">追跡 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6130b-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="6130b-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="6130b-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="6130b-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="6130b-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="6130b-121">アプリケーション名: % 5% の r</span><span class="sxs-lookup"><span data-stu-id="6130b-121">Application Name: %5%r</span></span><br /><br /> <span data-ttu-id="6130b-122">エラー コード: %6</span><span class="sxs-lookup"><span data-stu-id="6130b-122">Error Code: %6</span></span> |

## <a name="explanation"></a><span data-ttu-id="6130b-123">説明</span><span class="sxs-lookup"><span data-stu-id="6130b-123">Explanation</span></span>  
 <span data-ttu-id="6130b-124">この警告監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6130b-124">This Warning Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="6130b-125">このイベント メッセージには次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6130b-125">This event message includes:</span></span>  

 <span data-ttu-id="6130b-126">**関数:** 関数が実行されています。</span><span class="sxs-lookup"><span data-stu-id="6130b-126">**Function:** Function being performed</span></span>  

 <span data-ttu-id="6130b-127">**追跡 ID:** SSO API が最初に生成された一意の GUID が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6130b-127">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="6130b-128">**クライアント コンピューターの場合:** 関数が作成されたクライアント コンピューター。</span><span class="sxs-lookup"><span data-stu-id="6130b-128">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="6130b-129">**クライアント ユーザー:** 関数を呼び出したユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="6130b-129">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="6130b-130">**アプリケーション名:** 関連のこの関数に関連付けられているアプリケーションを SSO の名前。</span><span class="sxs-lookup"><span data-stu-id="6130b-130">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="6130b-131">**エラー コード:** エラーの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6130b-131">**Error Code:** Unique error identifier.</span></span>  

 <span data-ttu-id="6130b-132">この種類のイベントは、開発、トラブルシューティング、またはアプリケーションの実行時に発生した問題の診断に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6130b-132">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="6130b-133">表示された情報を使用して、実行中の SSO API 呼び出しを判別できます。</span><span class="sxs-lookup"><span data-stu-id="6130b-133">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="6130b-134">監査レベルは 0/1/2/3 に設定できます。0 は “オフ”、1 は “低“ でエラーのみが表示され、2 は “中” でエラーと警告が表示され、3 は “高” ですべての監査メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6130b-134">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6130b-135">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6130b-135">User Action</span></span>  

- <span data-ttu-id="6130b-136">関連するイベント メッセージについては、イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="6130b-136">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="6130b-137">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="6130b-137">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="6130b-138">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="6130b-138">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="6130b-139">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="6130b-139">Using SSO</span></span>](../core/using-sso.md)
