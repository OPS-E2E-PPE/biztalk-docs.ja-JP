---
title: "シングル サインオン: イベント 11021 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e246ac3d0bbab4e991b17c091567b4b59131b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11021"></a><span data-ttu-id="c8885-102">シングル サインオン: イベント 11021</span><span class="sxs-lookup"><span data-stu-id="c8885-102">Single Sign-On: Event 11021</span></span>
## <a name="details"></a><span data-ttu-id="c8885-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c8885-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8885-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c8885-104">Product Name</span></span>|<span data-ttu-id="c8885-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c8885-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c8885-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c8885-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c8885-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c8885-107">Event ID</span></span>|<span data-ttu-id="c8885-108">11021</span><span class="sxs-lookup"><span data-stu-id="c8885-108">11021</span></span>|  
|<span data-ttu-id="c8885-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c8885-109">Event Source</span></span>|<span data-ttu-id="c8885-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c8885-110">ENTSSO</span></span>|  
|<span data-ttu-id="c8885-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c8885-111">Component</span></span>|<span data-ttu-id="c8885-112">なし</span><span class="sxs-lookup"><span data-stu-id="c8885-112">N/A</span></span>|  
|<span data-ttu-id="c8885-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c8885-113">Symbolic Name</span></span>|<span data-ttu-id="c8885-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="c8885-114">SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="c8885-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c8885-115">Message Text</span></span>|<span data-ttu-id="c8885-116">外部パスワード変更によって、別の外部アカウントが変更されます。%r</span><span class="sxs-lookup"><span data-stu-id="c8885-116">An external password change will cause a different external account to be changed.%r</span></span><br /><br /> <span data-ttu-id="c8885-117">この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r</span><span class="sxs-lookup"><span data-stu-id="c8885-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="c8885-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c8885-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c8885-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="c8885-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c8885-120">Windows アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="c8885-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="c8885-121">外部アカウント 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="c8885-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="c8885-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="c8885-122">External Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c8885-123">説明</span><span class="sxs-lookup"><span data-stu-id="c8885-123">Explanation</span></span>  
 <span data-ttu-id="c8885-124">これは、外部パスワード変更によって、別の外部アカウントが変更されることを示す情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="c8885-124">This is an informational message stating that an external password change will cause a different external account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c8885-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c8885-125">User Action</span></span>  
 <span data-ttu-id="c8885-126">この変更が、管理者の理解と認可の下に行われたものであることを直ちに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8885-126">You should confirm immediately that this change was made with your knowledge and authorization.</span></span> <span data-ttu-id="c8885-127">そうである場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8885-127">If so, no action is required.</span></span> <span data-ttu-id="c8885-128">そうでなかった場合は、この変更がどこで行われたのかを調べ、システム内の安全な場所であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c8885-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>