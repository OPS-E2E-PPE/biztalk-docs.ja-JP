---
title: 'シングル サインオン: イベント 10599 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd671aa5-b243-4081-9a4e-87103be9a1d7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 326b94be9c05be6645a21b10f3ea302cf63be8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015683"
---
# <a name="single-sign-on-event-10599"></a><span data-ttu-id="35351-102">シングル サインオン: イベント 10599</span><span class="sxs-lookup"><span data-stu-id="35351-102">Single Sign-On: Event 10599</span></span>
## <a name="details"></a><span data-ttu-id="35351-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35351-103">Details</span></span>  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="35351-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35351-104">Product Name</span></span>   |                                                                             <span data-ttu-id="35351-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="35351-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="35351-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35351-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="35351-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35351-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="35351-108">10599</span><span class="sxs-lookup"><span data-stu-id="35351-108">10599</span></span>                                                                                        |
|  <span data-ttu-id="35351-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35351-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="35351-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="35351-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="35351-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35351-111">Component</span></span>    |                                                                                        <span data-ttu-id="35351-112">なし</span><span class="sxs-lookup"><span data-stu-id="35351-112">N/A</span></span>                                                                                         |
|  <span data-ttu-id="35351-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35351-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="35351-114">SSO_WARN_ENTSSO_IS_ADMIN</span><span class="sxs-lookup"><span data-stu-id="35351-114">SSO_WARN_ENTSSO_IS_ADMIN</span></span>                                                                              |
|  <span data-ttu-id="35351-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35351-115">Message Text</span></span>   | <span data-ttu-id="35351-116">SSO サービスはローカル管理者アカウントで実行しています。</span><span class="sxs-lookup"><span data-stu-id="35351-116">The SSO service is running under a local administrator account.</span></span> <span data-ttu-id="35351-117">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="35351-117">This is not recommended for security reasons.</span></span> <span data-ttu-id="35351-118">Details.%r のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35351-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="35351-119">SSO サービス アカウント: %1</span><span class="sxs-lookup"><span data-stu-id="35351-119">SSO Service Account: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="35351-120">説明</span><span class="sxs-lookup"><span data-stu-id="35351-120">Explanation</span></span>  
 <span data-ttu-id="35351-121">指定された SSO サービスはローカル管理者アカウントで実行しています。</span><span class="sxs-lookup"><span data-stu-id="35351-121">The SSO service specified is running under a local administrator account.</span></span> <span data-ttu-id="35351-122">これは、セキュリティ上の理由により推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="35351-122">This is not recommended for security reasons.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35351-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35351-123">User Action</span></span>  
 <span data-ttu-id="35351-124">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="35351-124">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>