---
title: シングル サインオン:イベント 11071 |Microsoft Docs
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
ms.openlocfilehash: 43105808e83b06f780736e7168581d3854305439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247485"
---
# <a name="single-sign-on-event-11071"></a><span data-ttu-id="3f37f-102">シングル サインオン:イベント 11071</span><span class="sxs-lookup"><span data-stu-id="3f37f-102">Single Sign-On: Event 11071</span></span>
## <a name="details"></a><span data-ttu-id="3f37f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3f37f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3f37f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3f37f-104">Product Name</span></span>   |                                                                                   <span data-ttu-id="3f37f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3f37f-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="3f37f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3f37f-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    <span data-ttu-id="3f37f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3f37f-107">Event ID</span></span>     |                                                                                             <span data-ttu-id="3f37f-108">11071</span><span class="sxs-lookup"><span data-stu-id="3f37f-108">11071</span></span>                                                                                             |
|  <span data-ttu-id="3f37f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3f37f-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="3f37f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3f37f-110">ENTSSO</span></span>                                                                                             |
|    <span data-ttu-id="3f37f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3f37f-111">Component</span></span>    |                                                                                              <span data-ttu-id="3f37f-112">なし</span><span class="sxs-lookup"><span data-stu-id="3f37f-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="3f37f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3f37f-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="3f37f-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3f37f-114">SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH</span></span>                                                                          |
|  <span data-ttu-id="3f37f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3f37f-115">Message Text</span></span>   | <span data-ttu-id="3f37f-116">Windows パスワードの長さがゼロ characters.%r ために、Windows パスワードの変更は破棄されました。</span><span class="sxs-lookup"><span data-stu-id="3f37f-116">A Windows password change was discarded because the Windows password length is zero characters.%r</span></span><br /><br /> <span data-ttu-id="3f37f-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3f37f-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3f37f-118">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3f37f-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="3f37f-119">クライアント ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="3f37f-119">Client User: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3f37f-120">説明</span><span class="sxs-lookup"><span data-stu-id="3f37f-120">Explanation</span></span>  
 <span data-ttu-id="3f37f-121">Windows パスワードの長さがゼロの文字であるために、Windows パスワードの変更は破棄されました。</span><span class="sxs-lookup"><span data-stu-id="3f37f-121">A Windows password change was discarded because the Windows password length is zero characters.</span></span> <span data-ttu-id="3f37f-122">Windows アカウントとクライアントのユーザー名が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3f37f-122">The Windows account and client user name are provided.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f37f-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3f37f-123">User Action</span></span>  
 <span data-ttu-id="3f37f-124">SSO システムで必要な文字の種類と数を使用して、もう一度パスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="3f37f-124">Change the password again, using the number and type of characters required by your SSO system.</span></span>