---
title: 'シングル サインオン: イベント 11025 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df5a733b-3c95-409c-8485-bf3f7feb3c50
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd8c25dc80669b4524c7e9ce848e4b0e28f773f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015899"
---
# <a name="single-sign-on-event-11025"></a><span data-ttu-id="84d5b-102">シングル サインオン: イベント 11025</span><span class="sxs-lookup"><span data-stu-id="84d5b-102">Single Sign-On: Event 11025</span></span>
## <a name="details"></a><span data-ttu-id="84d5b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="84d5b-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="84d5b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="84d5b-104">Product Name</span></span>   |                                                                                                 <span data-ttu-id="84d5b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="84d5b-105">Enterprise Single Sign-On</span></span>                                                                                                  |
| <span data-ttu-id="84d5b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="84d5b-106">Product Version</span></span> |                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                 |
|    <span data-ttu-id="84d5b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="84d5b-107">Event ID</span></span>     |                                                                                                           <span data-ttu-id="84d5b-108">11025</span><span class="sxs-lookup"><span data-stu-id="84d5b-108">11025</span></span>                                                                                                            |
|  <span data-ttu-id="84d5b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="84d5b-109">Event Source</span></span>   |                                                                                                           <span data-ttu-id="84d5b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="84d5b-110">ENTSSO</span></span>                                                                                                           |
|    <span data-ttu-id="84d5b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="84d5b-111">Component</span></span>    |                                                                                                            <span data-ttu-id="84d5b-112">なし</span><span class="sxs-lookup"><span data-stu-id="84d5b-112">N/A</span></span>                                                                                                             |
|  <span data-ttu-id="84d5b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="84d5b-113">Symbolic Name</span></span>  |                                                                                            <span data-ttu-id="84d5b-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84d5b-114">SSO_WARN_INVALID_APP_TICKET_TIMEOUT</span></span>                                                                                             |
|  <span data-ttu-id="84d5b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="84d5b-115">Message Text</span></span>   | <span data-ttu-id="84d5b-116">チケットのタイムアウト値がアプリケーション アダプターに対して無効です。%r</span><span class="sxs-lookup"><span data-stu-id="84d5b-116">The ticket time-out value is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="84d5b-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="84d5b-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="84d5b-118">チケットのタイムアウト: %2 分 %r</span><span class="sxs-lookup"><span data-stu-id="84d5b-118">Ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="84d5b-119">最大のチケットのタイムアウト: %3 分 %r</span><span class="sxs-lookup"><span data-stu-id="84d5b-119">Maximum ticket time-out: %3 minutes%r</span></span><br /><br /> <span data-ttu-id="84d5b-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="84d5b-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="84d5b-121">説明</span><span class="sxs-lookup"><span data-stu-id="84d5b-121">Explanation</span></span>  
 <span data-ttu-id="84d5b-122">チケットのタイムアウト値が無効です。</span><span class="sxs-lookup"><span data-stu-id="84d5b-122">The ticket time-out value is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="84d5b-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="84d5b-123">User Action</span></span>  
 <span data-ttu-id="84d5b-124">チケットのタイムアウトの詳細については、[SSO 関連アプリケーション](../core/sso-affiliate-applications.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d5b-124">For more information on ticket time-outs, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>