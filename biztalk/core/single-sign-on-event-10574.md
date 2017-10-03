---
title: "シングル サインオン: イベント 10574 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77f2a5aa-3a19-4d7c-9257-89f1567a3c2d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ea4dc3a11a577460e59bf6d910f286e791050e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10574"></a><span data-ttu-id="51243-102">シングル サインオン: イベント 10574</span><span class="sxs-lookup"><span data-stu-id="51243-102">Single Sign-On: Event 10574</span></span>
## <a name="details"></a><span data-ttu-id="51243-103">詳細</span><span class="sxs-lookup"><span data-stu-id="51243-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51243-104">製品名</span><span class="sxs-lookup"><span data-stu-id="51243-104">Product Name</span></span>|<span data-ttu-id="51243-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="51243-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="51243-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="51243-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="51243-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="51243-107">Event ID</span></span>|<span data-ttu-id="51243-108">10574</span><span class="sxs-lookup"><span data-stu-id="51243-108">10574</span></span>|  
|<span data-ttu-id="51243-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="51243-109">Event Source</span></span>|<span data-ttu-id="51243-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="51243-110">ENTSSO</span></span>|  
|<span data-ttu-id="51243-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51243-111">Component</span></span>|<span data-ttu-id="51243-112">なし</span><span class="sxs-lookup"><span data-stu-id="51243-112">N/A</span></span>|  
|<span data-ttu-id="51243-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="51243-113">Symbolic Name</span></span>|<span data-ttu-id="51243-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="51243-114">SSO_WARN_INVALID_SSO_ADMIN_GROUP</span></span>|  
|<span data-ttu-id="51243-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="51243-115">Message Text</span></span>|<span data-ttu-id="51243-116">SSO 管理者アカウントがグローバル情報の更新について有効ではありません。%r</span><span class="sxs-lookup"><span data-stu-id="51243-116">The SSO Administrators account is not valid for global info update.%r</span></span><br /><br /> <span data-ttu-id="51243-117">SSO 管理者: %1 %r</span><span class="sxs-lookup"><span data-stu-id="51243-117">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="51243-118">無効なアカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="51243-118">Invalid accounts: %2%r</span></span><br /><br /> <span data-ttu-id="51243-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="51243-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="51243-120">説明</span><span class="sxs-lookup"><span data-stu-id="51243-120">Explanation</span></span>  
 <span data-ttu-id="51243-121">SSO 管理者アカウントがグローバル情報の更新について有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="51243-121">The SSO Administrators account is not valid for global info update.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51243-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="51243-122">User Action</span></span>  
 <span data-ttu-id="51243-123">この警告メッセージには、SSO 管理者アカウントおよび無効なアカウントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51243-123">The warning message contains information regarding the SSO Administrators account and the invalid accounts.</span></span> <span data-ttu-id="51243-124">この情報を確認し、必要に応じて修正を行い、もう一度更新を試行します。</span><span class="sxs-lookup"><span data-stu-id="51243-124">Review this information, make any necessary corrections, and try the update again.</span></span>