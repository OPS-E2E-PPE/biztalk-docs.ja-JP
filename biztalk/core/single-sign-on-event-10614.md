---
title: シングル サインオン:イベント 10614 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1f9cd21-3f4b-446f-a4c7-15266973adf1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5fc2758327087d0b312de16b6f7c8ebc6b5bb6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397693"
---
# <a name="single-sign-on-event-10614"></a><span data-ttu-id="6d7d5-102">シングル サインオン:イベント 10614</span><span class="sxs-lookup"><span data-stu-id="6d7d5-102">Single Sign-On: Event 10614</span></span>
## <a name="details"></a><span data-ttu-id="6d7d5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6d7d5-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6d7d5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6d7d5-104">Product Name</span></span>   |                                                                                                        <span data-ttu-id="6d7d5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6d7d5-105">Enterprise Single Sign-On</span></span>                                                                                                        |
| <span data-ttu-id="6d7d5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6d7d5-106">Product Version</span></span> |                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                        |
|    <span data-ttu-id="6d7d5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6d7d5-107">Event ID</span></span>     |                                                                                                                  <span data-ttu-id="6d7d5-108">10614</span><span class="sxs-lookup"><span data-stu-id="6d7d5-108">10614</span></span>                                                                                                                  |
|  <span data-ttu-id="6d7d5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6d7d5-109">Event Source</span></span>   |                                                                                                                 <span data-ttu-id="6d7d5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6d7d5-110">ENTSSO</span></span>                                                                                                                  |
|    <span data-ttu-id="6d7d5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6d7d5-111">Component</span></span>    |                                                                                                                   <span data-ttu-id="6d7d5-112">なし</span><span class="sxs-lookup"><span data-stu-id="6d7d5-112">N/A</span></span>                                                                                                                   |
|  <span data-ttu-id="6d7d5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6d7d5-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="6d7d5-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d7d5-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span></span>                                                                                                     |
|  <span data-ttu-id="6d7d5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6d7d5-115">Message Text</span></span>   | <span data-ttu-id="6d7d5-116">チケットのタイムアウト値がグローバル情報 update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="6d7d5-116">The ticket time-out value is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="6d7d5-117">チケットのタイムアウト: %1 分 %r</span><span class="sxs-lookup"><span data-stu-id="6d7d5-117">Ticket time-out: %1 minutes%r</span></span><br /><br /> <span data-ttu-id="6d7d5-118">最小のチケットのタイムアウト:1 分 %r</span><span class="sxs-lookup"><span data-stu-id="6d7d5-118">Minimum ticket time-out: 1 minute%r</span></span><br /><br /> <span data-ttu-id="6d7d5-119">最大のチケットのタイムアウト: %2 分 %r</span><span class="sxs-lookup"><span data-stu-id="6d7d5-119">Maximum ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="6d7d5-120">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="6d7d5-120">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6d7d5-121">説明</span><span class="sxs-lookup"><span data-stu-id="6d7d5-121">Explanation</span></span>  
 <span data-ttu-id="6d7d5-122">指定したチケットのタイムアウト値が無効です。</span><span class="sxs-lookup"><span data-stu-id="6d7d5-122">The ticket time-out value specified is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d7d5-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6d7d5-123">User Action</span></span>  
 <span data-ttu-id="6d7d5-124">値を修正するのにには、警告メッセージで指定された情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d7d5-124">Use the information supplied in the warning message to fix the value.</span></span>