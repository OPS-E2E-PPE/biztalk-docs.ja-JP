---
title: シングル サインオン:イベント 10535 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b570b0b-5c45-4be3-80c9-a2c50601b677
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c6fc30ad5b0953ddecaad3266dec787e210429
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262348"
---
# <a name="single-sign-on-event-10535"></a><span data-ttu-id="21f06-102">シングル サインオン:イベント 10535</span><span class="sxs-lookup"><span data-stu-id="21f06-102">Single Sign-On: Event 10535</span></span>
## <a name="details"></a><span data-ttu-id="21f06-103">詳細</span><span class="sxs-lookup"><span data-stu-id="21f06-103">Details</span></span>  

|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="21f06-104">製品名</span><span class="sxs-lookup"><span data-stu-id="21f06-104">Product Name</span></span>   |                                                                       <span data-ttu-id="21f06-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="21f06-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="21f06-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="21f06-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="21f06-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="21f06-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="21f06-108">10535</span><span class="sxs-lookup"><span data-stu-id="21f06-108">10535</span></span>                                                                                 |
|  <span data-ttu-id="21f06-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="21f06-109">Event Source</span></span>   |                                                                                <span data-ttu-id="21f06-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21f06-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="21f06-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21f06-111">Component</span></span>    |                                                                                  <span data-ttu-id="21f06-112">CO</span><span class="sxs-lookup"><span data-stu-id="21f06-112">CO</span></span>                                                                                   |
|  <span data-ttu-id="21f06-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="21f06-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="21f06-114">SSO_INFO_API_AUDIT</span><span class="sxs-lookup"><span data-stu-id="21f06-114">SSO_INFO_API_AUDIT</span></span>                                                                           |
|  <span data-ttu-id="21f06-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="21f06-115">Message Text</span></span>   | <span data-ttu-id="21f06-116">SSO の監査 %r</span><span class="sxs-lookup"><span data-stu-id="21f06-116">SSO AUDIT%r</span></span><br /><br /> <span data-ttu-id="21f06-117">関数: %1 %r</span><span class="sxs-lookup"><span data-stu-id="21f06-117">Function: %1%r</span></span><br /><br /> <span data-ttu-id="21f06-118">追跡 ID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="21f06-118">Tracking ID: %2%r</span></span><br /><br /> <span data-ttu-id="21f06-119">クライアント コンピューターの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="21f06-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="21f06-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="21f06-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="21f06-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="21f06-121">Application Name: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="21f06-122">説明</span><span class="sxs-lookup"><span data-stu-id="21f06-122">Explanation</span></span>  
 <span data-ttu-id="21f06-123">この情報監査イベントは、ユーザー定義の監査レベルを満たすイベントが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="21f06-123">This Information Audit event indicates that an event that meets the user defined audit level has occurred.</span></span> <span data-ttu-id="21f06-124">このイベント メッセージは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21f06-124">This event message includes:</span></span>  

 <span data-ttu-id="21f06-125">**関数:** 実行中の関数します。</span><span class="sxs-lookup"><span data-stu-id="21f06-125">**Function:** Function being performed</span></span>  

 <span data-ttu-id="21f06-126">**追跡 ID:** SSO API が初めて呼び出されたときに生成される一意の GUID。</span><span class="sxs-lookup"><span data-stu-id="21f06-126">**Tracking ID:** Unique GUID generated when an SSO API is first called.</span></span>  

 <span data-ttu-id="21f06-127">**クライアント コンピューターの場合:** クライアント コンピューターが、関数が発信元であります。</span><span class="sxs-lookup"><span data-stu-id="21f06-127">**Client Computer:** Client computer where the function originated.</span></span>  

 <span data-ttu-id="21f06-128">**クライアント ユーザー:** 関数を呼び出したユーザー アカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="21f06-128">**Client User:** The name of the user account that invoked the function.</span></span>  

 <span data-ttu-id="21f06-129">**アプリケーション名:** SSO の名前には、この関数に関連付けられたアプリケーションが関連します。</span><span class="sxs-lookup"><span data-stu-id="21f06-129">**Application Name:** Name of the SSO affiliate application associated with this function.</span></span>  

 <span data-ttu-id="21f06-130">この種類のイベントは、開発中に問題を診断、トラブルシューティング、またはアプリケーションの実行に使用されます。</span><span class="sxs-lookup"><span data-stu-id="21f06-130">This type of event is used for diagnosing problems during development, troubleshooting, or running of an application.</span></span> <span data-ttu-id="21f06-131">SSO API 呼び出しが行われるを決定する提供情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="21f06-131">Information provided can be used to determine the SSO API call being made.</span></span>  

 <span data-ttu-id="21f06-132">監査レベルを設定することが 0 では 0/1/2/3 – には"none"、1 は「低」には、エラーのみが表示されます、2 は「中」の表示エラーと警告、および 3 はすべての監査メッセージを「高」が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21f06-132">The audit level can be set to 0/1/2/3 – 0 means “none”, 1 means “low” displays errors only, 2 means “medium” displays errors and warnings, and 3 means “high” displays all audit messages.</span></span>  

## <a name="user-action"></a><span data-ttu-id="21f06-133">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="21f06-133">User Action</span></span>  

- <span data-ttu-id="21f06-134">関連するイベント メッセージは、イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="21f06-134">Check the event log for associated event messages.</span></span>  

  <span data-ttu-id="21f06-135">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="21f06-135">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="21f06-136">SSO を監査する方法</span><span class="sxs-lookup"><span data-stu-id="21f06-136">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  

- [<span data-ttu-id="21f06-137">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="21f06-137">Using SSO</span></span>](../core/using-sso.md)
