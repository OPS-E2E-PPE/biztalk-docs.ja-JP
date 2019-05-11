---
title: シングル サインオン:イベント 11017 |Microsoft Docs
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
ms.openlocfilehash: 41b28506409bb68190f7dfe07f025d19c99dc47c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267143"
---
# <a name="single-sign-on-event-11017"></a><span data-ttu-id="39fae-102">シングル サインオン:イベント 11017</span><span class="sxs-lookup"><span data-stu-id="39fae-102">Single Sign-On: Event 11017</span></span>
## <a name="details"></a><span data-ttu-id="39fae-103">詳細</span><span class="sxs-lookup"><span data-stu-id="39fae-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="39fae-104">製品名</span><span class="sxs-lookup"><span data-stu-id="39fae-104">Product Name</span></span>   |                                                                                                                               <span data-ttu-id="39fae-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="39fae-105">Enterprise Single Sign-On</span></span>                                                                                                                                |
| <span data-ttu-id="39fae-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="39fae-106">Product Version</span></span> |                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                               |
|    <span data-ttu-id="39fae-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="39fae-107">Event ID</span></span>     |                                                                                                                                         <span data-ttu-id="39fae-108">11017</span><span class="sxs-lookup"><span data-stu-id="39fae-108">11017</span></span>                                                                                                                                          |
|  <span data-ttu-id="39fae-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="39fae-109">Event Source</span></span>   |                                                                                                                                         <span data-ttu-id="39fae-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="39fae-110">ENTSSO</span></span>                                                                                                                                         |
|    <span data-ttu-id="39fae-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="39fae-111">Component</span></span>    |                                                                                                                                          <span data-ttu-id="39fae-112">なし</span><span class="sxs-lookup"><span data-stu-id="39fae-112">N/A</span></span>                                                                                                                                           |
|  <span data-ttu-id="39fae-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="39fae-113">Symbolic Name</span></span>  |                                                                                                                           <span data-ttu-id="39fae-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span><span class="sxs-lookup"><span data-stu-id="39fae-114">SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK</span></span>                                                                                                                           |
|  <span data-ttu-id="39fae-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="39fae-115">Message Text</span></span>   | <span data-ttu-id="39fae-116">アプリケーションのアプリケーション ユーザー アカウントに Windows アカウントがないために、マッピングは無効です。</span><span class="sxs-lookup"><span data-stu-id="39fae-116">The mapping is not valid because the Windows account is not in the Application Users account for the application.</span></span> <span data-ttu-id="39fae-117">マッピングは deleted.%r 削除されました</span><span class="sxs-lookup"><span data-stu-id="39fae-117">The mapping has been deleted.%r</span></span><br /><br /> <span data-ttu-id="39fae-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="39fae-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="39fae-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="39fae-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="39fae-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="39fae-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="39fae-121">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="39fae-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="39fae-122">説明</span><span class="sxs-lookup"><span data-stu-id="39fae-122">Explanation</span></span>  
 <span data-ttu-id="39fae-123">指定された Windows アカウントがこのアプリケーションでのアプリケーション ユーザー アカウントの一部をされなかったか、それが一度に 1 つが変更または削除されました。</span><span class="sxs-lookup"><span data-stu-id="39fae-123">Either the Windows account specified was never a part of the Application Users account for this application, or it was at one time, but has been changed or removed.</span></span> <span data-ttu-id="39fae-124">マッピングが削除されました。</span><span class="sxs-lookup"><span data-stu-id="39fae-124">The mapping has been deleted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39fae-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="39fae-125">User Action</span></span>  
 <span data-ttu-id="39fae-126">お使いのシステム パスワード同期アカウント情報を確認し、情報が有効かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="39fae-126">Check the password sync account information for your system, and make sure your information is valid.</span></span> <span data-ttu-id="39fae-127">次のマッピングを再作成します。</span><span class="sxs-lookup"><span data-stu-id="39fae-127">Then recreate the mapping.</span></span> <span data-ttu-id="39fae-128">無効なマッピング情報のリスクを軽減. マッピングの作成ウィザードを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="39fae-128">Note that using the Create Mapping Wizard reduces the risk of invalid mapping information.</span></span>