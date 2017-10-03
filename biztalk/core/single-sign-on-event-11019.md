---
title: "シングル サインオン: イベント 11019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec07b00-d567-4518-89eb-340e4f92429b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb4b2d2494a404566c7350a9e9988d429a3e335c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11019"></a><span data-ttu-id="688cf-102">シングル サインオン: イベント 11019</span><span class="sxs-lookup"><span data-stu-id="688cf-102">Single Sign-On: Event 11019</span></span>
## <a name="details"></a><span data-ttu-id="688cf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="688cf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="688cf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="688cf-104">Product Name</span></span>|<span data-ttu-id="688cf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="688cf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="688cf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="688cf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="688cf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="688cf-107">Event ID</span></span>|<span data-ttu-id="688cf-108">11019</span><span class="sxs-lookup"><span data-stu-id="688cf-108">11019</span></span>|  
|<span data-ttu-id="688cf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="688cf-109">Event Source</span></span>|<span data-ttu-id="688cf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="688cf-110">ENTSSO</span></span>|  
|<span data-ttu-id="688cf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="688cf-111">Component</span></span>|<span data-ttu-id="688cf-112">なし</span><span class="sxs-lookup"><span data-stu-id="688cf-112">N/A</span></span>|  
|<span data-ttu-id="688cf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="688cf-113">Symbolic Name</span></span>|<span data-ttu-id="688cf-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED</span><span class="sxs-lookup"><span data-stu-id="688cf-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED</span></span>|  
|<span data-ttu-id="688cf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="688cf-115">Message Text</span></span>|<span data-ttu-id="688cf-116">Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントにないため、マッピングは無効です。</span><span class="sxs-lookup"><span data-stu-id="688cf-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="688cf-117">マッピングを削除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="688cf-117">Failed to delete the mapping.</span></span> <span data-ttu-id="688cf-118">マッピングは無視されます。%r</span><span class="sxs-lookup"><span data-stu-id="688cf-118">The mapping will be ignored.%r</span></span><br /><br /> <span data-ttu-id="688cf-119">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="688cf-119">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="688cf-120">Windows アカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="688cf-120">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="688cf-121">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="688cf-121">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="688cf-122">アプリケーション ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="688cf-122">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="688cf-123">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="688cf-123">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="688cf-124">説明</span><span class="sxs-lookup"><span data-stu-id="688cf-124">Explanation</span></span>  
 <span data-ttu-id="688cf-125">指定された Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントの一部ではなかったか、一時期はそうだったが変更または削除されました。</span><span class="sxs-lookup"><span data-stu-id="688cf-125">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="688cf-126">マッピングは削除されませんでした。</span><span class="sxs-lookup"><span data-stu-id="688cf-126">The mapping has not been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="688cf-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="688cf-127">User Action</span></span>  
 <span data-ttu-id="688cf-128">システムのパスワード同期アカウント情報を確認するか、情報が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="688cf-128">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="688cf-129">次にマッピングを再作成します。</span><span class="sxs-lookup"><span data-stu-id="688cf-129">Then recreate the mapping.</span></span> <span data-ttu-id="688cf-130">マッピングの作成ウィザードを使用すると、無効なマッピング情報のリスクが軽減されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="688cf-130">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span> <span data-ttu-id="688cf-131">失敗したマッピングを削除できます。</span><span class="sxs-lookup"><span data-stu-id="688cf-131">You can delete the failed mapping.</span></span> <span data-ttu-id="688cf-132">削除しない場合、失敗したマッピングは無視されます。</span><span class="sxs-lookup"><span data-stu-id="688cf-132">If you do not delete it, it will be ignored.</span></span>