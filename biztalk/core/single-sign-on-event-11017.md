---
title: 'シングル サインオン: イベント 11017 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0883abfd3bc86f6e41fd11e0feafa79b080b13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024192"
---
# <a name="single-sign-on-event-11017"></a><span data-ttu-id="ee895-102">シングル サインオン: イベント 11017</span><span class="sxs-lookup"><span data-stu-id="ee895-102">Single Sign-On: Event 11017</span></span>
## <a name="details"></a><span data-ttu-id="ee895-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ee895-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ee895-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ee895-104">Product Name</span></span>   |                                                                                                                               <span data-ttu-id="ee895-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ee895-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="ee895-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ee895-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    <span data-ttu-id="ee895-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ee895-107">Event ID</span></span>     |                                                                                                                                         <span data-ttu-id="ee895-108">11017</span><span class="sxs-lookup"><span data-stu-id="ee895-108">11017</span></span>                                                                                                                                          |
|  <span data-ttu-id="ee895-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ee895-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="ee895-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ee895-110">ENTSSO</span></span>                                                                                                                                         |
|    <span data-ttu-id="ee895-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ee895-111">Component</span></span>    |                                                                                                                                          <span data-ttu-id="ee895-112">なし</span><span class="sxs-lookup"><span data-stu-id="ee895-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="ee895-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ee895-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="ee895-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span><span class="sxs-lookup"><span data-stu-id="ee895-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span></span>                                                                                                                           |
|  <span data-ttu-id="ee895-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ee895-115">Message Text</span></span>   | <span data-ttu-id="ee895-116">Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントにないため、マッピングは無効です。</span><span class="sxs-lookup"><span data-stu-id="ee895-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="ee895-117">マッピングは削除されました。%r</span><span class="sxs-lookup"><span data-stu-id="ee895-117">The mapping has been deleted.%r</span></span><br /><br /> <span data-ttu-id="ee895-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ee895-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ee895-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ee895-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="ee895-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="ee895-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ee895-121">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="ee895-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ee895-122">説明</span><span class="sxs-lookup"><span data-stu-id="ee895-122">Explanation</span></span>  
 <span data-ttu-id="ee895-123">指定された Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントの一部ではなかったか、一時期はそうだったが変更または削除されました。</span><span class="sxs-lookup"><span data-stu-id="ee895-123">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="ee895-124">マッピングは削除されました。</span><span class="sxs-lookup"><span data-stu-id="ee895-124">The mapping has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ee895-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ee895-125">User Action</span></span>  
 <span data-ttu-id="ee895-126">システムのパスワード同期アカウント情報を確認するか、情報が有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee895-126">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="ee895-127">次にマッピングを再作成します。</span><span class="sxs-lookup"><span data-stu-id="ee895-127">Then recreate the mapping.</span></span> <span data-ttu-id="ee895-128">マッピングの作成ウィザードを使用すると、無効なマッピング情報のリスクが軽減されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ee895-128">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span>