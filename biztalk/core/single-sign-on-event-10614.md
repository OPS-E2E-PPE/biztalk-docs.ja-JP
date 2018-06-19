---
title: 'シングル サインオン: イベント 10614 |Microsoft ドキュメント'
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
ms.openlocfilehash: 66d317e63a66ac05d454a6a5a2612aeaae9244b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270218"
---
# <a name="single-sign-on-event-10614"></a><span data-ttu-id="47b66-102">シングル サインオン: イベント 10614</span><span class="sxs-lookup"><span data-stu-id="47b66-102">Single Sign-On: Event 10614</span></span>
## <a name="details"></a><span data-ttu-id="47b66-103">詳細</span><span class="sxs-lookup"><span data-stu-id="47b66-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47b66-104">製品名</span><span class="sxs-lookup"><span data-stu-id="47b66-104">Product Name</span></span>|<span data-ttu-id="47b66-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="47b66-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="47b66-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="47b66-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="47b66-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="47b66-107">Event ID</span></span>|<span data-ttu-id="47b66-108">10614</span><span class="sxs-lookup"><span data-stu-id="47b66-108">10614</span></span>|  
|<span data-ttu-id="47b66-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="47b66-109">Event Source</span></span>|<span data-ttu-id="47b66-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="47b66-110">ENTSSO</span></span>|  
|<span data-ttu-id="47b66-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="47b66-111">Component</span></span>|<span data-ttu-id="47b66-112">なし</span><span class="sxs-lookup"><span data-stu-id="47b66-112">N/A</span></span>|  
|<span data-ttu-id="47b66-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="47b66-113">Symbolic Name</span></span>|<span data-ttu-id="47b66-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47b66-114">SSO_WARN_INVALID_TICKET_TIMEOUT</span></span>|  
|<span data-ttu-id="47b66-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="47b66-115">Message Text</span></span>|<span data-ttu-id="47b66-116">チケットのタイムアウト値がグローバル情報アダプターに対して無効です。%r</span><span class="sxs-lookup"><span data-stu-id="47b66-116">The ticket time-out value is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="47b66-117">チケットのタイムアウト: %1 分 %r</span><span class="sxs-lookup"><span data-stu-id="47b66-117">Ticket time-out: %1 minutes%r</span></span><br /><br /> <span data-ttu-id="47b66-118">最小のチケットのタイムアウト: 1 分 %r</span><span class="sxs-lookup"><span data-stu-id="47b66-118">Minimum ticket time-out: 1 minute%r</span></span><br /><br /> <span data-ttu-id="47b66-119">最大のチケットのタイムアウト: %2 分 %r</span><span class="sxs-lookup"><span data-stu-id="47b66-119">Maximum ticket time-out: %2 minutes%r</span></span><br /><br /> <span data-ttu-id="47b66-120">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="47b66-120">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47b66-121">説明</span><span class="sxs-lookup"><span data-stu-id="47b66-121">Explanation</span></span>  
 <span data-ttu-id="47b66-122">指定されたチケットのタイムアウト値が無効です。</span><span class="sxs-lookup"><span data-stu-id="47b66-122">The ticket time-out value specified is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47b66-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="47b66-123">User Action</span></span>  
 <span data-ttu-id="47b66-124">警告メッセージで示されている情報を使用して、値を修正します。</span><span class="sxs-lookup"><span data-stu-id="47b66-124">Use the information supplied in the warning message to fix the value.</span></span>