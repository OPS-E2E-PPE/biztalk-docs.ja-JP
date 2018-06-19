---
title: 'シングル サインオン: イベント 11037 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245b4af07a88c4015048db0ea20fe04b714d0ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276842"
---
# <a name="single-sign-on-event-11037"></a><span data-ttu-id="a7b7d-102">シングル サインオン: イベント 11037</span><span class="sxs-lookup"><span data-stu-id="a7b7d-102">Single Sign-On: Event 11037</span></span>
## <a name="details"></a><span data-ttu-id="a7b7d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a7b7d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7b7d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a7b7d-104">Product Name</span></span>|<span data-ttu-id="a7b7d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a7b7d-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a7b7d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a7b7d-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a7b7d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a7b7d-107">Event ID</span></span>|<span data-ttu-id="a7b7d-108">11037</span><span class="sxs-lookup"><span data-stu-id="a7b7d-108">11037</span></span>|  
|<span data-ttu-id="a7b7d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a7b7d-109">Event Source</span></span>|<span data-ttu-id="a7b7d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a7b7d-110">ENTSSO</span></span>|  
|<span data-ttu-id="a7b7d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a7b7d-111">Component</span></span>|<span data-ttu-id="a7b7d-112">なし</span><span class="sxs-lookup"><span data-stu-id="a7b7d-112">N/A</span></span>|  
|<span data-ttu-id="a7b7d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a7b7d-113">Symbolic Name</span></span>|<span data-ttu-id="a7b7d-114">SSO_INFO_PS_MAPPING_INVALID</span><span class="sxs-lookup"><span data-stu-id="a7b7d-114">SSO_INFO_PS_MAPPING_INVALID</span></span>|  
|<span data-ttu-id="a7b7d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a7b7d-115">Message Text</span></span>|<span data-ttu-id="a7b7d-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="a7b7d-116">External password change.</span></span> <span data-ttu-id="a7b7d-117">マッピングが有効ではなくなっているため、外部アカウントのパスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="a7b7d-117">The password was not changed for the external account because the mapping is no longer valid.%r</span></span><br /><br /> <span data-ttu-id="a7b7d-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a7b7d-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="a7b7d-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a7b7d-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="a7b7d-120">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a7b7d-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="a7b7d-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="a7b7d-121">External Account: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7b7d-122">説明</span><span class="sxs-lookup"><span data-stu-id="a7b7d-122">Explanation</span></span>  
 <span data-ttu-id="a7b7d-123">マッピングがアプリケーション ユーザー グループに含まれなくなっています。</span><span class="sxs-lookup"><span data-stu-id="a7b7d-123">The mapping is no longer a part of the Application Users group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7b7d-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a7b7d-124">User Action</span></span>  
 <span data-ttu-id="a7b7d-125">このメッセージには、外部アカウントとアプリケーションの名前が示されます。</span><span class="sxs-lookup"><span data-stu-id="a7b7d-125">The message lists the name of the external account and application.</span></span> <span data-ttu-id="a7b7d-126">この情報を使用して、マッピングが有効ではなくなった理由を調べます。</span><span class="sxs-lookup"><span data-stu-id="a7b7d-126">You can use this information to find out why the mapping is no longer valid.</span></span>