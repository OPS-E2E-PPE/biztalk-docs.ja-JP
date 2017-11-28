---
title: "シングル サインオン: イベント 10601 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2624025e-b7a8-43b9-aa7e-6811a2fc3278
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c34711cf02711ec0ee2a259cc7d8f8fca9c87b7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10601"></a><span data-ttu-id="28ed5-102">シングル サインオン: イベント 10601</span><span class="sxs-lookup"><span data-stu-id="28ed5-102">Single Sign-On: Event 10601</span></span>
## <a name="details"></a><span data-ttu-id="28ed5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="28ed5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28ed5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="28ed5-104">Product Name</span></span>|<span data-ttu-id="28ed5-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="28ed5-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="28ed5-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="28ed5-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="28ed5-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="28ed5-107">Event ID</span></span>|<span data-ttu-id="28ed5-108">10601</span><span class="sxs-lookup"><span data-stu-id="28ed5-108">10601</span></span>|  
|<span data-ttu-id="28ed5-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="28ed5-109">Event Source</span></span>|<span data-ttu-id="28ed5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="28ed5-110">ENTSSO</span></span>|  
|<span data-ttu-id="28ed5-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="28ed5-111">Component</span></span>|<span data-ttu-id="28ed5-112">なし</span><span class="sxs-lookup"><span data-stu-id="28ed5-112">N/A</span></span>|  
|<span data-ttu-id="28ed5-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="28ed5-113">Symbolic Name</span></span>|<span data-ttu-id="28ed5-114">SSO_WARN_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="28ed5-114">SSO_WARN_INVALID_FLAGS</span></span>|  
|<span data-ttu-id="28ed5-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="28ed5-115">Message Text</span></span>|<span data-ttu-id="28ed5-116">指定されたフラグはこの種類のアプリケーションの作成には無効です。</span><span class="sxs-lookup"><span data-stu-id="28ed5-116">The specified flags are not valid for creating this type of application.</span></span><br /><br /> <span data-ttu-id="28ed5-117">Details.%r のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28ed5-117">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="28ed5-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="28ed5-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="28ed5-119">指定したフラグ: %2 %r</span><span class="sxs-lookup"><span data-stu-id="28ed5-119">Specified Flags: %2%r</span></span><br /><br /> <span data-ttu-id="28ed5-120">許可されるフラグ: %3 %r</span><span class="sxs-lookup"><span data-stu-id="28ed5-120">Allowed Flags: %3%r</span></span><br /><br /> <span data-ttu-id="28ed5-121">許可されていないフラグ: %4</span><span class="sxs-lookup"><span data-stu-id="28ed5-121">Not Allowed Flags: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28ed5-122">説明</span><span class="sxs-lookup"><span data-stu-id="28ed5-122">Explanation</span></span>  
 <span data-ttu-id="28ed5-123">指定されたフラグはこの種類のアプリケーションの作成には無効です。</span><span class="sxs-lookup"><span data-stu-id="28ed5-123">The specified flags are not valid for creating this type of application.</span></span> <span data-ttu-id="28ed5-124">この警告には、関連するアプリケーションと共に、許可されているフラグと許可されていないフラグが示されます。</span><span class="sxs-lookup"><span data-stu-id="28ed5-124">The warning lists the application concerned, as well as the flags that are allowed and those that are not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28ed5-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="28ed5-125">User Action</span></span>  
 <span data-ttu-id="28ed5-126">警告メッセージに示されているガイドラインに従ってアプリケーションを再作成します。</span><span class="sxs-lookup"><span data-stu-id="28ed5-126">Recreate the application following the guidelines outlined in the warning message.</span></span>