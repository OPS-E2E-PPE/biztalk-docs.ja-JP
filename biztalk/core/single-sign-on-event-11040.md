---
title: 'シングル サインオン: イベント 11040 |Microsoft Docs'
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
ms.openlocfilehash: eefc6c65e07b430851606ce7779aad3771776a83
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019072"
---
# <a name="single-sign-on-event-11040"></a><span data-ttu-id="1da6c-102">シングル サインオン: イベント 11040</span><span class="sxs-lookup"><span data-stu-id="1da6c-102">Single Sign-On: Event 11040</span></span>
## <a name="details"></a><span data-ttu-id="1da6c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1da6c-103">Details</span></span>  
  
|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1da6c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1da6c-104">Product Name</span></span>   |                                                                  <span data-ttu-id="1da6c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1da6c-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="1da6c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1da6c-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    <span data-ttu-id="1da6c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1da6c-107">Event ID</span></span>     |                                                                            <span data-ttu-id="1da6c-108">11040</span><span class="sxs-lookup"><span data-stu-id="1da6c-108">11040</span></span>                                                                            |
|  <span data-ttu-id="1da6c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1da6c-109">Event Source</span></span>   |                                                                           <span data-ttu-id="1da6c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1da6c-110">ENTSSO</span></span>                                                                            |
|    <span data-ttu-id="1da6c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1da6c-111">Component</span></span>    |                                                                             <span data-ttu-id="1da6c-112">なし</span><span class="sxs-lookup"><span data-stu-id="1da6c-112">N/A</span></span>                                                                             |
|  <span data-ttu-id="1da6c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1da6c-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="1da6c-114">SSO_WARN_NETWORK_SERVICE</span><span class="sxs-lookup"><span data-stu-id="1da6c-114">SSO_WARN_NETWORK_SERVICE</span></span>                                                                   |
|  <span data-ttu-id="1da6c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1da6c-115">Message Text</span></span>   | <span data-ttu-id="1da6c-116">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="1da6c-116">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="1da6c-117">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="1da6c-117">There are some special considerations for this account.</span></span> <span data-ttu-id="1da6c-118">詳細については、マニュアルを参照してください。%r</span><span class="sxs-lookup"><span data-stu-id="1da6c-118">See your documentation for details.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1da6c-119">説明</span><span class="sxs-lookup"><span data-stu-id="1da6c-119">Explanation</span></span>  
 <span data-ttu-id="1da6c-120">SSO サービスは Network Service アカウントで実行されています。</span><span class="sxs-lookup"><span data-stu-id="1da6c-120">The SSO service is running under the Network Service account.</span></span> <span data-ttu-id="1da6c-121">このアカウントについては、特別な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="1da6c-121">There are some special considerations for this account.</span></span> <span data-ttu-id="1da6c-122">たとえば、ネットワーク サービス アカウントを追加した後は、再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="1da6c-122">For example, a reboot is required after adding a Network Service account.</span></span> <span data-ttu-id="1da6c-123">また、ネットワーク サービス アカウントで実行すると、非常に限定されたシナリオに実行が制限されます。</span><span class="sxs-lookup"><span data-stu-id="1da6c-123">Also, running under a Network Service account restricts you to running in very limited scenarios.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1da6c-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1da6c-124">User Action</span></span>  
 <span data-ttu-id="1da6c-125">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="1da6c-125">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>