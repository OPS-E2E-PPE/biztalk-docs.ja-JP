---
title: "シングル サインオン: イベント 10524 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c79da37aaa54f44daaa39048fcdf58e67064f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10524"></a><span data-ttu-id="24916-102">シングル サインオン: イベント 10524</span><span class="sxs-lookup"><span data-stu-id="24916-102">Single Sign-On: Event 10524</span></span>
## <a name="details"></a><span data-ttu-id="24916-103">詳細</span><span class="sxs-lookup"><span data-stu-id="24916-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24916-104">製品名</span><span class="sxs-lookup"><span data-stu-id="24916-104">Product Name</span></span>|<span data-ttu-id="24916-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="24916-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="24916-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="24916-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="24916-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="24916-107">Event ID</span></span>|<span data-ttu-id="24916-108">10524</span><span class="sxs-lookup"><span data-stu-id="24916-108">10524</span></span>|  
|<span data-ttu-id="24916-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="24916-109">Event Source</span></span>|<span data-ttu-id="24916-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="24916-110">ENTSSO</span></span>|  
|<span data-ttu-id="24916-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="24916-111">Component</span></span>|<span data-ttu-id="24916-112">N\A</span><span class="sxs-lookup"><span data-stu-id="24916-112">N\A</span></span>|  
|<span data-ttu-id="24916-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="24916-113">Symbolic Name</span></span>|<span data-ttu-id="24916-114">SSO_ERROR_RESTORE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="24916-114">SSO_ERROR_RESTORE_SECRET_FAILED</span></span>|  
|<span data-ttu-id="24916-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="24916-115">Message Text</span></span>|<span data-ttu-id="24916-116">マスター シークレットを復元できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="24916-116">Failed to restore the master secrets.%r</span></span><br /><br /> <span data-ttu-id="24916-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="24916-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="24916-118">現在の MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="24916-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="24916-119">以前の MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="24916-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="24916-120">クライアント ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="24916-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="24916-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="24916-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="24916-122">説明</span><span class="sxs-lookup"><span data-stu-id="24916-122">Explanation</span></span>  
 <span data-ttu-id="24916-123">このエラー イベントは、ユーザーがバックアップ ファイルからマスター シークレットを復元しようとしたが、失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="24916-123">This Error event indicates that a user attempt to restore the master secrets from a backup file failed.</span></span> <span data-ttu-id="24916-124">これは、問題がある場合のためのアクセス許可 (マスタ シークレットの復元には、SSO 管理者である必要があります) またはバックアップ ファイルのファイルの破損原因として考えられます。</span><span class="sxs-lookup"><span data-stu-id="24916-124">This might be due to permissions issues (you must be an SSO Administrator to restore the master secret) or possibly due to file corruption of the backup file.</span></span> <span data-ttu-id="24916-125">これらの場合、アプリケーション イベント ログに関連するメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="24916-125">In these cases there should be related messages in the Application event log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="24916-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="24916-126">User Action</span></span>  
 <span data-ttu-id="24916-127">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="24916-127">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="24916-128">関連するイベントまたはエラーについては、アプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="24916-128">Check the Application event log for associated events or errors.</span></span>  
  
-   <span data-ttu-id="24916-129">適切な SSO 管理者のアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24916-129">Check that you have the appropriate SSO Administrator permissions.</span></span>  
  
 <span data-ttu-id="24916-130">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="24916-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="24916-131">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="24916-131">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="24916-132">マスター シークレットをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="24916-132">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="24916-133">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="24916-133">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)