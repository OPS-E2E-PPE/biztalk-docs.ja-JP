---
title: 'シングル サインオン: イベント 11059 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3dfab1d020211565df452b6cfaf0bca14e724f0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276802"
---
# <a name="single-sign-on-event-11059"></a><span data-ttu-id="ecb89-102">シングル サインオン: イベント 11059</span><span class="sxs-lookup"><span data-stu-id="ecb89-102">Single Sign-On: Event 11059</span></span>
## <a name="details"></a><span data-ttu-id="ecb89-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ecb89-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecb89-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ecb89-104">Product Name</span></span>|<span data-ttu-id="ecb89-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ecb89-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ecb89-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ecb89-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ecb89-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ecb89-107">Event ID</span></span>|<span data-ttu-id="ecb89-108">11059</span><span class="sxs-lookup"><span data-stu-id="ecb89-108">11059</span></span>|  
|<span data-ttu-id="ecb89-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ecb89-109">Event Source</span></span>|<span data-ttu-id="ecb89-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ecb89-110">ENTSSO</span></span>|  
|<span data-ttu-id="ecb89-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ecb89-111">Component</span></span>|<span data-ttu-id="ecb89-112">なし</span><span class="sxs-lookup"><span data-stu-id="ecb89-112">N/A</span></span>|  
|<span data-ttu-id="ecb89-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ecb89-113">Symbolic Name</span></span>|<span data-ttu-id="ecb89-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span><span class="sxs-lookup"><span data-stu-id="ecb89-114">SSO_INFO_INVALID_USER_NOT_IN_GROUP</span></span>|  
|<span data-ttu-id="ecb89-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ecb89-115">Message Text</span></span>|<span data-ttu-id="ecb89-116">指定されたユーザーが Application Users アカウントのメンバーではないため、マッピングを作成できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="ecb89-116">A mapping could not be created because the specified user is not a member of the Application Users account.%r</span></span><br /><br /> <span data-ttu-id="ecb89-117">Windows アカウント: %1\\%2 %r</span><span class="sxs-lookup"><span data-stu-id="ecb89-117">Windows Account: %1\\%2%r</span></span><br /><br /> <span data-ttu-id="ecb89-118">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="ecb89-118">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="ecb89-119">アプリケーション ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="ecb89-119">Application Users: %4%r</span></span><br /><br /> <span data-ttu-id="ecb89-120">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="ecb89-120">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecb89-121">説明</span><span class="sxs-lookup"><span data-stu-id="ecb89-121">Explanation</span></span>  
 <span data-ttu-id="ecb89-122">指定されたユーザーがアプリケーション ユーザー アカウントのメンバーではないために、マッピングを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ecb89-122">The mapping could not be created because the specified user is not a member of the Application Users account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecb89-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ecb89-123">User Action</span></span>  
 <span data-ttu-id="ecb89-124">アプリケーション ユーザー アカウントのメンバーになる方法については、ENTSSO 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ecb89-124">Contact your ENTSSO Administrator about becoming a member of the Application Users account.</span></span>