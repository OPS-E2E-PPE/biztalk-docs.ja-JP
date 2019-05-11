---
title: シングル サインオン:イベント 11040 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ccdc06-9677-4454-ae2c-8dde78d6f3f8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a071aa4959aaf8668a0713221904a1a612d0a417
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401007"
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="b3196-102">シングル サインオン:イベント 11040</span><span class="sxs-lookup"><span data-stu-id="b3196-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="b3196-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b3196-103">Details</span></span>  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b3196-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b3196-104">Product Name</span></span>   |                                                                  <span data-ttu-id="b3196-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b3196-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="b3196-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b3196-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="b3196-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b3196-107">Event ID</span></span>     |                                                                            <span data-ttu-id="b3196-108">11040</span><span class="sxs-lookup"><span data-stu-id="b3196-108">11040</span></span>                                                                            |
|  <span data-ttu-id="b3196-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b3196-109">Event Source</span></span>   |                                                                           <span data-ttu-id="b3196-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b3196-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="b3196-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b3196-111">Component</span></span>    |                                                                             <span data-ttu-id="b3196-112">なし</span><span class="sxs-lookup"><span data-stu-id="b3196-112">N/A</span></span>                                                                             |
|  <span data-ttu-id="b3196-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b3196-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="b3196-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="b3196-114">SSO_WARN_NETWORK_SERVICE</span></span>                                                                   |
|  <span data-ttu-id="b3196-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b3196-115">Message Text</span></span>   | <span data-ttu-id="b3196-116">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="b3196-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="b3196-117">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="b3196-117">There are some special considerations for this account.</span></span> <span data-ttu-id="b3196-118">詳細については、マニュアルを参照してください。%r</span><span class="sxs-lookup"><span data-stu-id="b3196-118">See your documentation for details.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b3196-119">説明</span><span class="sxs-lookup"><span data-stu-id="b3196-119">Explanation</span></span>  
 <span data-ttu-id="b3196-120">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="b3196-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="b3196-121">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="b3196-121">There are some special considerations for this account.</span></span> <span data-ttu-id="b3196-122">たとえば、ネットワーク サービス アカウントを追加した後は、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3196-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="b3196-123">また、ネットワーク サービス アカウントで実行すると、非常に限定されたシナリオに実行が制限されます。</span><span class="sxs-lookup"><span data-stu-id="b3196-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3196-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b3196-124">User Action</span></span>  
 <span data-ttu-id="b3196-125">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="b3196-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>