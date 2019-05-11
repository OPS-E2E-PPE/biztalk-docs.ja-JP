---
title: シングル サインオン:イベント 10536 |Microsoft Docs
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
ms.openlocfilehash: 9b66b9a37a92614b10849ac39bd8385d9e850efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262238"
---
# <a name="single-sign-on-event-10536"></a><span data-ttu-id="a23b5-102">シングル サインオン:イベント 10536</span><span class="sxs-lookup"><span data-stu-id="a23b5-102">Single Sign-On: Event 10536</span></span>
## <a name="details"></a><span data-ttu-id="a23b5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a23b5-103">Details</span></span>  

|                 |                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a23b5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a23b5-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="a23b5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a23b5-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="a23b5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a23b5-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="a23b5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a23b5-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="a23b5-108">10536</span><span class="sxs-lookup"><span data-stu-id="a23b5-108">10536</span></span>                                                                                                |
|  <span data-ttu-id="a23b5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a23b5-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="a23b5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a23b5-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="a23b5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a23b5-111">Component</span></span>    |                                                                                                 <span data-ttu-id="a23b5-112">CO</span><span class="sxs-lookup"><span data-stu-id="a23b5-112">CO</span></span>                                                                                                 |
|  <span data-ttu-id="a23b5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a23b5-113">Symbolic Name</span></span>  |                                                                                         <span data-ttu-id="a23b5-114">SSO_WARN_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="a23b5-114">SSO_WARN_API_AUDIT</span></span>                                                                                         |
|  <span data-ttu-id="a23b5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a23b5-115">Message Text</span></span>   | <span data-ttu-id="a23b5-116">SSO の監査 %r</span><span class="sxs-lookup"><span data-stu-id="a23b5-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="a23b5-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a23b5-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="a23b5-118">追跡 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a23b5-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="a23b5-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="a23b5-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="a23b5-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="a23b5-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="a23b5-121">アプリケーション名: % 5% の r</span><span class="sxs-lookup"><span data-stu-id="a23b5-121">Application Name: %5%r</span></span><br /><br /> <span data-ttu-id="a23b5-122">エラー コード: %6</span><span class="sxs-lookup"><span data-stu-id="a23b5-122">Error Code: %6</span></span> |

## <a name="explanation"></a><span data-ttu-id="a23b5-123">説明</span><span class="sxs-lookup"><span data-stu-id="a23b5-123">Explanation</span></span>  
 <span data-ttu-id="a23b5-124">この警告監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="a23b5-124">This Warning Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="a23b5-125">このイベント メッセージは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a23b5-125">This event message includes:</span></span>  

 <span data-ttu-id="a23b5-126">**関数:** 実行中の関数します。</span><span class="sxs-lookup"><span data-stu-id="a23b5-126">**Function:** Function being performed</span></span>  

 <span data-ttu-id="a23b5-127">**追跡 ID:** SSO API が初めて呼び出されたときに生成される一意の GUID。</span><span class="sxs-lookup"><span data-stu-id="a23b5-127">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="a23b5-128">**クライアント コンピューターの場合:** クライアント コンピューターが、関数が発信元であります。</span><span class="sxs-lookup"><span data-stu-id="a23b5-128">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="a23b5-129">**クライアント ユーザー:** 関数を呼び出したユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="a23b5-129">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="a23b5-130">**アプリケーション名:** SSO の名前には、この関数に関連付けられたアプリケーションが関連します。</span><span class="sxs-lookup"><span data-stu-id="a23b5-130">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="a23b5-131">**エラー コード:** エラーの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="a23b5-131">**Error Code:** Unique error identifier.</span></span>  

 <span data-ttu-id="a23b5-132">この種類のイベントは、開発中に問題を診断、トラブルシューティング、またはアプリケーションの実行に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a23b5-132">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="a23b5-133">SSO API 呼び出しが行われるを決定する提供情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a23b5-133">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="a23b5-134">監査レベルを設定することが 0 では 0/1/2/3 – には"none"、1 は「低」には、エラーのみが表示されます、2 は「中」の表示エラーと警告、および 3 はすべての監査メッセージを「高」が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a23b5-134">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="a23b5-135">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a23b5-135">User Action</span></span>  

- <span data-ttu-id="a23b5-136">関連するイベント メッセージは、イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="a23b5-136">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="a23b5-137">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="a23b5-137">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="a23b5-138">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="a23b5-138">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="a23b5-139">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="a23b5-139">Using SSO</span></span>](../core/using-sso.md)
