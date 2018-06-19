---
title: 'シングル サインオン: イベント 10527 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf1785361ad343b3da4c7dc07b6a73a362fa14d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270202"
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="75f99-102">シングル サインオン: イベント 10527</span><span class="sxs-lookup"><span data-stu-id="75f99-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="75f99-103">詳細</span><span class="sxs-lookup"><span data-stu-id="75f99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="75f99-104">製品名</span><span class="sxs-lookup"><span data-stu-id="75f99-104">Product Name</span></span>|<span data-ttu-id="75f99-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="75f99-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="75f99-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="75f99-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="75f99-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="75f99-107">Event ID</span></span>|<span data-ttu-id="75f99-108">10527</span><span class="sxs-lookup"><span data-stu-id="75f99-108">10527</span></span>|  
|<span data-ttu-id="75f99-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="75f99-109">Event Source</span></span>|<span data-ttu-id="75f99-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="75f99-110">ENTSSO</span></span>|  
|<span data-ttu-id="75f99-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="75f99-111">Component</span></span>|<span data-ttu-id="75f99-112">0</span><span class="sxs-lookup"><span data-stu-id="75f99-112">0</span></span>|  
|<span data-ttu-id="75f99-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="75f99-113">Symbolic Name</span></span>|<span data-ttu-id="75f99-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="75f99-114">SSO_ERROR_GET_SECRET_FAILED</span></span>|  
|<span data-ttu-id="75f99-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="75f99-115">Message Text</span></span>|<span data-ttu-id="75f99-116">マスター シークレットの取得要求が失敗しました。%r</span><span class="sxs-lookup"><span data-stu-id="75f99-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="75f99-117">シークレット番号: %1 %r</span><span class="sxs-lookup"><span data-stu-id="75f99-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="75f99-118">クライアント ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="75f99-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="75f99-119">クライアント コンピューターの場合: %3 %r</span><span class="sxs-lookup"><span data-stu-id="75f99-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="75f99-120">追跡 ID: %4 %r</span><span class="sxs-lookup"><span data-stu-id="75f99-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="75f99-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="75f99-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="75f99-122">説明</span><span class="sxs-lookup"><span data-stu-id="75f99-122">Explanation</span></span>  
 <span data-ttu-id="75f99-123">このエラー イベントは、マスター シークレットの取得要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="75f99-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="75f99-124">これらの場合、アプリケーション イベント ログに関連するメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="75f99-124">In these cases there should be related messages in the Application event log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="75f99-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="75f99-125">User Action</span></span>  
 <span data-ttu-id="75f99-126">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="75f99-126">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="75f99-127">関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="75f99-127">Check the Application event log for associated events or errors.</span></span>  
  
 <span data-ttu-id="75f99-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="75f99-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="75f99-129">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="75f99-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="75f99-130">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="75f99-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)