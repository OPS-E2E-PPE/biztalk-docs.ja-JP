---
title: "シングル サインオン: イベント 11040 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9eafbbe1c0cbcb0db96c94d072ed511e69b2d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="393fe-102">シングル サインオン: イベント 11040</span><span class="sxs-lookup"><span data-stu-id="393fe-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="393fe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="393fe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="393fe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="393fe-104">Product Name</span></span>|<span data-ttu-id="393fe-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="393fe-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="393fe-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="393fe-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="393fe-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="393fe-107">Event ID</span></span>|<span data-ttu-id="393fe-108">11040</span><span class="sxs-lookup"><span data-stu-id="393fe-108">11040</span></span>|  
|<span data-ttu-id="393fe-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="393fe-109">Event Source</span></span>|<span data-ttu-id="393fe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="393fe-110">ENTSSO</span></span>|  
|<span data-ttu-id="393fe-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="393fe-111">Component</span></span>|<span data-ttu-id="393fe-112">なし</span><span class="sxs-lookup"><span data-stu-id="393fe-112">N/A</span></span>|  
|<span data-ttu-id="393fe-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="393fe-113">Symbolic Name</span></span>|<span data-ttu-id="393fe-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="393fe-114">SSO_WARN_NETWORK_SERVICE</span></span>|  
|<span data-ttu-id="393fe-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="393fe-115">Message Text</span></span>|<span data-ttu-id="393fe-116">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="393fe-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="393fe-117">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="393fe-117">There are some special considerations for this account.</span></span> <span data-ttu-id="393fe-118">詳細については、マニュアルを参照してください。%r</span><span class="sxs-lookup"><span data-stu-id="393fe-118">See your documentation for details.%r</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="393fe-119">説明</span><span class="sxs-lookup"><span data-stu-id="393fe-119">Explanation</span></span>  
 <span data-ttu-id="393fe-120">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="393fe-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="393fe-121">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="393fe-121">There are some special considerations for this account.</span></span> <span data-ttu-id="393fe-122">たとえば、ネットワーク サービス アカウントを追加した後は、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="393fe-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="393fe-123">また、ネットワーク サービス アカウントで実行すると、非常に限定されたシナリオに実行が制限されます。</span><span class="sxs-lookup"><span data-stu-id="393fe-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="393fe-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="393fe-124">User Action</span></span>  
 <span data-ttu-id="393fe-125">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)です。</span><span class="sxs-lookup"><span data-stu-id="393fe-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>