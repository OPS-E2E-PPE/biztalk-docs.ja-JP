---
title: 'シングル サインオン: イベント 10578 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4693bc25-d4d5-4cc7-b9bd-42d3471b2b0c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6ffb086106f8aa73c268cf3938be28e46b49354
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982643"
---
# <a name="single-sign-on-event-10578"></a><span data-ttu-id="c93b3-102">シングル サインオン: イベント 10578</span><span class="sxs-lookup"><span data-stu-id="c93b3-102">Single Sign-On: Event 10578</span></span>
## <a name="details"></a><span data-ttu-id="c93b3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c93b3-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c93b3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c93b3-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="c93b3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c93b3-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="c93b3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c93b3-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="c93b3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c93b3-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="c93b3-108">10578</span><span class="sxs-lookup"><span data-stu-id="c93b3-108">10578</span></span>                                                                                                       |
|  <span data-ttu-id="c93b3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c93b3-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="c93b3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c93b3-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="c93b3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c93b3-111">Component</span></span>    |                                                                                                        <span data-ttu-id="c93b3-112">なし</span><span class="sxs-lookup"><span data-stu-id="c93b3-112">N/A</span></span>                                                                                                        |
|  <span data-ttu-id="c93b3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c93b3-113">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="c93b3-114">SSO_INFO_CHANGED_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="c93b3-114">SSO_INFO_CHANGED_APP_USER_GROUP</span></span>                                                                                          |
|  <span data-ttu-id="c93b3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c93b3-115">Message Text</span></span>   | <span data-ttu-id="c93b3-116">アプリケーション ユーザー アカウントが更新されました。%r</span><span class="sxs-lookup"><span data-stu-id="c93b3-116">Updated Application Users account.%r</span></span><br /><br /> <span data-ttu-id="c93b3-117">新しいアプリケーション ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="c93b3-117">New Application Users: %1%r</span></span><br /><br /> <span data-ttu-id="c93b3-118">古いアプリケーション ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c93b3-118">Old Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="c93b3-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="c93b3-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="c93b3-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="c93b3-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="c93b3-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="c93b3-121">Application Name: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c93b3-122">説明</span><span class="sxs-lookup"><span data-stu-id="c93b3-122">Explanation</span></span>  
 <span data-ttu-id="c93b3-123">これは情報メッセージであり、SSO システム内で発生する重要なセキュリティ関連イベントの追跡に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="c93b3-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="c93b3-124">このメッセージは、アプリケーション ユーザー アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c93b3-124">This message states that the Updated Application Users account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c93b3-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c93b3-125">User Action</span></span>  
 <span data-ttu-id="c93b3-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="c93b3-126">No user action is required.</span></span>