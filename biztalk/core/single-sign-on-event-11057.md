---
title: シングル サインオン:イベント 11057 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff6e7a5c811c983ebe9f48fc6cdd85ed79f3ee16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400870"
---
# <a name="single-sign-on-event-11057"></a><span data-ttu-id="d7c4d-102">シングル サインオン:イベント 11057</span><span class="sxs-lookup"><span data-stu-id="d7c4d-102">Single Sign-On: Event 11057</span></span>
## <a name="details"></a><span data-ttu-id="d7c4d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d7c4d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d7c4d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d7c4d-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="d7c4d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d7c4d-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="d7c4d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d7c4d-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="d7c4d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d7c4d-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="d7c4d-108">11057</span><span class="sxs-lookup"><span data-stu-id="d7c4d-108">11057</span></span>                                                                                                                          |
|  <span data-ttu-id="d7c4d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d7c4d-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="d7c4d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d7c4d-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="d7c4d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d7c4d-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="d7c4d-112">なし</span><span class="sxs-lookup"><span data-stu-id="d7c4d-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="d7c4d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d7c4d-113">Symbolic Name</span></span>  |                                                                                                        <span data-ttu-id="d7c4d-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="d7c4d-114">SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="d7c4d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d7c4d-115">Message Text</span></span>   | <span data-ttu-id="d7c4d-116">直接パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="d7c4d-116">Direct password change.</span></span> <span data-ttu-id="d7c4d-117">このマッピングのいくつか不足している外部資格情報フィールドを既定 values.%r に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d7c4d-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="d7c4d-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d7c4d-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d7c4d-119">アプリケーション名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d7c4d-119">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="d7c4d-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d7c4d-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="d7c4d-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="d7c4d-121">External Account: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d7c4d-122">説明</span><span class="sxs-lookup"><span data-stu-id="d7c4d-122">Explanation</span></span>  
 <span data-ttu-id="d7c4d-123">直接パスワード同期を使用してパスワードを変更することはできますが、この機能は 1 つの外部資格情報フィールドのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d7c4d-123">While it is possible to change passwords using Direct Password Sync, this feature only supports one external credential field.</span></span> <span data-ttu-id="d7c4d-124">ここで、ENTSSO システムは 1 つ以上の外部資格情報フィールドが発生しましたし、既定 (空白) 値にこれらのフィールドが設定します。</span><span class="sxs-lookup"><span data-stu-id="d7c4d-124">In this case the ENTSSO System has encountered more than one external credential field, and has set those fields to default (blank) values.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d7c4d-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d7c4d-125">User Action</span></span>  
 <span data-ttu-id="d7c4d-126">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d7c4d-126">No user action is necessary.</span></span>