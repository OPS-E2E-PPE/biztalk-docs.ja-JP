---
title: シングル サインオン:イベント 11059 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac5b6ce7-8819-4b9d-85f7-f5dfaf940487
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851e468db974456fe5f9eca00dc201fdfe1e12d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258772"
---
# <a name="single-sign-on-event-11059"></a><span data-ttu-id="62316-102">シングル サインオン:イベント 11059</span><span class="sxs-lookup"><span data-stu-id="62316-102">Single Sign-On: Event 11059</span></span>
## <a name="details"></a><span data-ttu-id="62316-103">詳細</span><span class="sxs-lookup"><span data-stu-id="62316-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="62316-104">製品名</span><span class="sxs-lookup"><span data-stu-id="62316-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="62316-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="62316-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="62316-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="62316-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="62316-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="62316-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="62316-108">11059</span><span class="sxs-lookup"><span data-stu-id="62316-108">11059</span></span>                                                                                                                         |
|  <span data-ttu-id="62316-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="62316-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="62316-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="62316-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="62316-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="62316-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="62316-112">なし</span><span class="sxs-lookup"><span data-stu-id="62316-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="62316-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="62316-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="62316-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="62316-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                           |
|  <span data-ttu-id="62316-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="62316-115">Message Text</span></span>   | <span data-ttu-id="62316-116">指定したユーザーがアプリケーション ユーザー account.%r のメンバーではないために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="62316-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="62316-117">Windows アカウント: %1\\% 2 %r</span><span class="sxs-lookup"><span data-stu-id="62316-117">Windows Account: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="62316-118">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="62316-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="62316-119">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="62316-119">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="62316-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="62316-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="62316-121">説明</span><span class="sxs-lookup"><span data-stu-id="62316-121">Explanation</span></span>  
 <span data-ttu-id="62316-122">指定したユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="62316-122">The mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62316-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="62316-123">User Action</span></span>  
 <span data-ttu-id="62316-124">アプリケーション ユーザー アカウントのメンバーになる方法については、ENTSSO 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="62316-124">Contact your ENTSSO Administrator about becoming a member of the Application Users account.</span></span>