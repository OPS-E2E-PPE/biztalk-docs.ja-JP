---
title: "シングル サインオン: イベント 11020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa6a0d72-ece6-4094-9263-dbf69bb068c8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 444a61beec74a9d7141df79d05d8863cc10d6dc6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11020"></a><span data-ttu-id="04638-102">シングル サインオン: イベント 11020</span><span class="sxs-lookup"><span data-stu-id="04638-102">Single Sign-On: Event 11020</span></span>
## <a name="details"></a><span data-ttu-id="04638-103">詳細</span><span class="sxs-lookup"><span data-stu-id="04638-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04638-104">製品名</span><span class="sxs-lookup"><span data-stu-id="04638-104">Product Name</span></span>|<span data-ttu-id="04638-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="04638-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="04638-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="04638-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="04638-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04638-107">Event ID</span></span>|<span data-ttu-id="04638-108">11020</span><span class="sxs-lookup"><span data-stu-id="04638-108">11020</span></span>|  
|<span data-ttu-id="04638-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="04638-109">Event Source</span></span>|<span data-ttu-id="04638-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="04638-110">ENTSSO</span></span>|  
|<span data-ttu-id="04638-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="04638-111">Component</span></span>|<span data-ttu-id="04638-112">なし</span><span class="sxs-lookup"><span data-stu-id="04638-112">N/A</span></span>|  
|<span data-ttu-id="04638-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="04638-113">Symbolic Name</span></span>|<span data-ttu-id="04638-114">SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="04638-114">SSO_INFO_WINDOWS_TO_WINDOWS_MAPPING_CONFLICT_ALLOWED</span></span>|  
|<span data-ttu-id="04638-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="04638-115">Message Text</span></span>|<span data-ttu-id="04638-116">Windows パスワード変更によって、別の Windows アカウントが変更されます。%r</span><span class="sxs-lookup"><span data-stu-id="04638-116">A Windows password change will cause a different Windows account to be changed.%r</span></span><br /><br /> <span data-ttu-id="04638-117">この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r</span><span class="sxs-lookup"><span data-stu-id="04638-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="04638-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="04638-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="04638-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="04638-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="04638-120">外部アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="04638-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="04638-121">Windows アカウント 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="04638-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="04638-122">Windows アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="04638-122">Windows Account 2: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="04638-123">説明</span><span class="sxs-lookup"><span data-stu-id="04638-123">Explanation</span></span>  
 <span data-ttu-id="04638-124">これは、Windows パスワード変更によって、別の Windows アカウントが変更されることを示す情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="04638-124">This is an informational message stating that a Windows password change will cause a different Windows account to be changed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04638-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="04638-125">User Action</span></span>  
 <span data-ttu-id="04638-126">この変更が、管理者の理解と認可の下に行われたものであることを直ちに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04638-126">You should confirm immediately that this change was made with your knowledge and authorization.</span></span> <span data-ttu-id="04638-127">そうである場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="04638-127">If so, no action is required.</span></span> <span data-ttu-id="04638-128">そうでなかった場合は、この変更がどこで行われたのかを調べ、システム内の安全な場所であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="04638-128">If not, find out where the change initiated, and confirm that it was a location safely within the system.</span></span>