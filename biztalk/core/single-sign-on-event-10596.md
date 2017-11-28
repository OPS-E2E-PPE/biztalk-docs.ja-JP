---
title: "シングル サインオン: イベント 10596 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d70aabcf-aa53-40bf-8937-44f191af1aec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051fdf627edc3f560a8d02026207dc2fe5bb3533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10596"></a><span data-ttu-id="1b71f-102">シングル サインオン: イベント 10596</span><span class="sxs-lookup"><span data-stu-id="1b71f-102">Single Sign-On: Event 10596</span></span>
## <a name="details"></a><span data-ttu-id="1b71f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1b71f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b71f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1b71f-104">Product Name</span></span>|<span data-ttu-id="1b71f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1b71f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1b71f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1b71f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1b71f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1b71f-107">Event ID</span></span>|<span data-ttu-id="1b71f-108">10596</span><span class="sxs-lookup"><span data-stu-id="1b71f-108">10596</span></span>|  
|<span data-ttu-id="1b71f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1b71f-109">Event Source</span></span>|<span data-ttu-id="1b71f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1b71f-110">ENTSSO</span></span>|  
|<span data-ttu-id="1b71f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1b71f-111">Component</span></span>|<span data-ttu-id="1b71f-112">なし</span><span class="sxs-lookup"><span data-stu-id="1b71f-112">N/A</span></span>|  
|<span data-ttu-id="1b71f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1b71f-113">Symbolic Name</span></span>|<span data-ttu-id="1b71f-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="1b71f-114">SSO_WARN_TICKET_USER_NOT_IN_GROUP</span></span>|  
|<span data-ttu-id="1b71f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1b71f-115">Message Text</span></span>|<span data-ttu-id="1b71f-116">チケットの発行対象のユーザーがアプリケーション ユーザー アカウントのメンバーではないため、チケットを引き換えることができません。%r</span><span class="sxs-lookup"><span data-stu-id="1b71f-116">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="1b71f-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1b71f-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="1b71f-118">%2 のチケットの発行先: %r</span><span class="sxs-lookup"><span data-stu-id="1b71f-118">Ticket Issued For: %2%r</span></span><br /><br /> <span data-ttu-id="1b71f-119">アプリケーション ユーザー: %3</span><span class="sxs-lookup"><span data-stu-id="1b71f-119">Application Users: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1b71f-120">説明</span><span class="sxs-lookup"><span data-stu-id="1b71f-120">Explanation</span></span>  
 <span data-ttu-id="1b71f-121">チケットの発行対象のユーザーがアプリケーション ユーザー アカウントのメンバーではないため、チケットを引き換えることができません。</span><span class="sxs-lookup"><span data-stu-id="1b71f-121">The ticket cannot be redeemed because the user for whom the ticket was issued is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b71f-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1b71f-122">User Action</span></span>  
 <span data-ttu-id="1b71f-123">アプリケーション ユーザー アカウントのメンバーであるユーザーにチケットを再発行します。</span><span class="sxs-lookup"><span data-stu-id="1b71f-123">Reissue the ticket to a user who is a member of the Application Users account.</span></span>