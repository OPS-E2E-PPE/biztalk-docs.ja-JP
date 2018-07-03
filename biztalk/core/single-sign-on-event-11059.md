---
title: 'シングル サインオン: イベント 11059 |Microsoft Docs'
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
ms.openlocfilehash: 4a22b2a68acc6cd4be3d5cf854a4d965d897e302
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965779"
---
# <a name="single-sign-on-event-11059"></a><span data-ttu-id="6aa18-102">シングル サインオン: イベント 11059</span><span class="sxs-lookup"><span data-stu-id="6aa18-102">Single Sign-On: Event 11059</span></span>
## <a name="details"></a><span data-ttu-id="6aa18-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6aa18-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                       |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6aa18-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6aa18-104">Product Name</span></span>   |                                                                                                               <span data-ttu-id="6aa18-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6aa18-105">Enterprise Single Sign-On</span></span>                                                                                                               |
| <span data-ttu-id="6aa18-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6aa18-106">Product Version</span></span> |                                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                               |
|    <span data-ttu-id="6aa18-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6aa18-107">Event ID</span></span>     |                                                                                                                         <span data-ttu-id="6aa18-108">11059</span><span class="sxs-lookup"><span data-stu-id="6aa18-108">11059</span></span>                                                                                                                         |
|  <span data-ttu-id="6aa18-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6aa18-109">Event Source</span></span>   |                                                                                                                        <span data-ttu-id="6aa18-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6aa18-110">ENTSSO</span></span>                                                                                                                         |
|    <span data-ttu-id="6aa18-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6aa18-111">Component</span></span>    |                                                                                                                          <span data-ttu-id="6aa18-112">なし</span><span class="sxs-lookup"><span data-stu-id="6aa18-112">N/A</span></span>                                                                                                                          |
|  <span data-ttu-id="6aa18-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6aa18-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="6aa18-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="6aa18-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span></span>                                                                                                           |
|  <span data-ttu-id="6aa18-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6aa18-115">Message Text</span></span>   | <span data-ttu-id="6aa18-116">指定されたユーザーが Application Users アカウントのメンバーではないため、マッピングを作成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="6aa18-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="6aa18-117">Windows アカウント: %1\\% 2 %r</span><span class="sxs-lookup"><span data-stu-id="6aa18-117">Windows Account: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="6aa18-118">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="6aa18-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="6aa18-119">アプリケーション ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="6aa18-119">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="6aa18-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="6aa18-120">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6aa18-121">説明</span><span class="sxs-lookup"><span data-stu-id="6aa18-121">Explanation</span></span>  
 <span data-ttu-id="6aa18-122">指定されたユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6aa18-122">The mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6aa18-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6aa18-123">User Action</span></span>  
 <span data-ttu-id="6aa18-124">アプリケーション ユーザー アカウントのメンバーになる方法については、ENTSSO 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="6aa18-124">Contact your ENTSSO Administrator about becoming a member of the Application Users account.</span></span>