---
title: シングル サインオン:イベント 10568 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 266fd09a-c7e6-4a69-ac1c-1834097fa393
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52d5ec7ece58816afd10e44e2bf83d53a35895e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398768"
---
# <a name="single-sign-on-event-10568"></a><span data-ttu-id="db4c2-102">シングル サインオン:イベント 10568</span><span class="sxs-lookup"><span data-stu-id="db4c2-102">Single Sign-On: Event 10568</span></span>
## <a name="details"></a><span data-ttu-id="db4c2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="db4c2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                             |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="db4c2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="db4c2-104">Product Name</span></span>   |                                                                                                  <span data-ttu-id="db4c2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="db4c2-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="db4c2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="db4c2-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                  |
|    <span data-ttu-id="db4c2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="db4c2-107">Event ID</span></span>     |                                                                                                            <span data-ttu-id="db4c2-108">10568</span><span class="sxs-lookup"><span data-stu-id="db4c2-108">10568</span></span>                                                                                                            |
|  <span data-ttu-id="db4c2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="db4c2-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="db4c2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="db4c2-110">ENTSSO</span></span>                                                                                                            |
|    <span data-ttu-id="db4c2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db4c2-111">Component</span></span>    |                                                                                                             <span data-ttu-id="db4c2-112">なし</span><span class="sxs-lookup"><span data-stu-id="db4c2-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="db4c2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="db4c2-113">Symbolic Name</span></span>  |                                                                                              <span data-ttu-id="db4c2-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="db4c2-114">SSO_WARN_INVALID_APP_ADMIN_GROUP</span></span>                                                                                               |
|  <span data-ttu-id="db4c2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="db4c2-115">Message Text</span></span>   | <span data-ttu-id="db4c2-116">アプリケーション管理者アカウントがアプリケーション update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="db4c2-116">The Application Administrators account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="db4c2-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="db4c2-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="db4c2-118">アプリケーション管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="db4c2-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="db4c2-119">無効なアカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="db4c2-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="db4c2-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="db4c2-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="db4c2-121">説明</span><span class="sxs-lookup"><span data-stu-id="db4c2-121">Explanation</span></span>  
 <span data-ttu-id="db4c2-122">無効か、存在しないアプリケーション管理者アカウントを更新しようとしました。</span><span class="sxs-lookup"><span data-stu-id="db4c2-122">You have attempted to update an Application Administrators account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db4c2-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="db4c2-123">User Action</span></span>  
 <span data-ttu-id="db4c2-124">アカウントの名前が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="db4c2-124">Check that the name of the account is correct.</span></span>