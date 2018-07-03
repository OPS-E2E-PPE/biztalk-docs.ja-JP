---
title: 'シングル サインオン: イベント 10573 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de1ea4e3-5d5f-4d50-8f9a-eff270ac0edb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7b2dffb5bd78a3257a400cf2d3cb93978e1d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980185"
---
# <a name="single-sign-on-event-10573"></a><span data-ttu-id="597ef-102">シングル サインオン: イベント 10573</span><span class="sxs-lookup"><span data-stu-id="597ef-102">Single Sign-On: Event 10573</span></span>
## <a name="details"></a><span data-ttu-id="597ef-103">詳細</span><span class="sxs-lookup"><span data-stu-id="597ef-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="597ef-104">製品名</span><span class="sxs-lookup"><span data-stu-id="597ef-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="597ef-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="597ef-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="597ef-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="597ef-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="597ef-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="597ef-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="597ef-108">10573</span><span class="sxs-lookup"><span data-stu-id="597ef-108">10573</span></span>                                                                                             |
|  <span data-ttu-id="597ef-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="597ef-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="597ef-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="597ef-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="597ef-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="597ef-111">Component</span></span>    |                                                                                             <span data-ttu-id="597ef-112">なし</span><span class="sxs-lookup"><span data-stu-id="597ef-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="597ef-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="597ef-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="597ef-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="597ef-114">SSO_WARN_INVALID_SSO_APP_ADMIN_GROUP</span></span>                                                                             |
|  <span data-ttu-id="597ef-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="597ef-115">Message Text</span></span>   | <span data-ttu-id="597ef-116">SSO 関連管理者アカウントがグローバル情報アダプターに対して無効です。%r</span><span class="sxs-lookup"><span data-stu-id="597ef-116">The SSO Affiliate Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="597ef-117">SSO 関連管理者: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="597ef-117">SSO Affiliate Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="597ef-118">無効なアカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="597ef-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="597ef-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="597ef-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="597ef-120">説明</span><span class="sxs-lookup"><span data-stu-id="597ef-120">Explanation</span></span>  
 <span data-ttu-id="597ef-121">SSO 関連管理者アカウントがグローバル情報アダプターに対して無効です。</span><span class="sxs-lookup"><span data-stu-id="597ef-121">The SSO Affiliate Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="597ef-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="597ef-122">User Action</span></span>  
 <span data-ttu-id="597ef-123">警告メッセージには、SSO 関連管理者アカウントおよび無効なアカウントに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="597ef-123">The warning message contains information regarding the SSO Affiliate Administrators account and the invalid accounts.</span></span> <span data-ttu-id="597ef-124">この情報を確認し、必要に応じて修正を行い、もう一度更新を試行します。</span><span class="sxs-lookup"><span data-stu-id="597ef-124">Review this information, make any necessary corrections, and try the update again.</span></span>