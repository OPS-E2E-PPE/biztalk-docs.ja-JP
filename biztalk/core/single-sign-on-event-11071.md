---
title: 'シングル サインオン: イベント 11071 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bc4793937574cc90021b95b6c1850409d57871
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975891"
---
# <a name="single-sign-on-event-11071"></a><span data-ttu-id="e95e4-102">シングル サインオン: イベント 11071</span><span class="sxs-lookup"><span data-stu-id="e95e4-102">Single Sign-On: Event 11071</span></span>
## <a name="details"></a><span data-ttu-id="e95e4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e95e4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e95e4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e95e4-104">Product Name</span></span>   |                                                                                   <span data-ttu-id="e95e4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e95e4-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="e95e4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e95e4-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    <span data-ttu-id="e95e4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e95e4-107">Event ID</span></span>     |                                                                                             <span data-ttu-id="e95e4-108">11071</span><span class="sxs-lookup"><span data-stu-id="e95e4-108">11071</span></span>                                                                                             |
|  <span data-ttu-id="e95e4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e95e4-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="e95e4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e95e4-110">ENTSSO</span></span>                                                                                             |
|    <span data-ttu-id="e95e4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e95e4-111">Component</span></span>    |                                                                                              <span data-ttu-id="e95e4-112">なし</span><span class="sxs-lookup"><span data-stu-id="e95e4-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="e95e4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e95e4-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="e95e4-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span><span class="sxs-lookup"><span data-stu-id="e95e4-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span></span>                                                                          |
|  <span data-ttu-id="e95e4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e95e4-115">Message Text</span></span>   | <span data-ttu-id="e95e4-116">Windows パスワードの長さが 0 文字であるため、Windows パスワード変更は破棄されました。%r</span><span class="sxs-lookup"><span data-stu-id="e95e4-116">A Windows password change was discarded because the Windows password length is zero characters.%r</span></span><br /><br /> <span data-ttu-id="e95e4-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e95e4-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e95e4-118">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="e95e4-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="e95e4-119">クライアント ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="e95e4-119">Client User: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e95e4-120">説明</span><span class="sxs-lookup"><span data-stu-id="e95e4-120">Explanation</span></span>  
 <span data-ttu-id="e95e4-121">Windows パスワードの長さが 0 文字であるため、Windows パスワード変更は破棄されました。</span><span class="sxs-lookup"><span data-stu-id="e95e4-121">A Windows password change was discarded because the Windows password length is zero characters.</span></span> <span data-ttu-id="e95e4-122">Windows アカウントおよびクライアント ユーザー名は指定されます。</span><span class="sxs-lookup"><span data-stu-id="e95e4-122">The Windows account and client user name are provided.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e95e4-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e95e4-123">User Action</span></span>  
 <span data-ttu-id="e95e4-124">SSO システムで要求される文字の数および種類に従って、もう一度パスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="e95e4-124">Change the password again, using the number and type of characters required by your SSO system.</span></span>