---
title: 'シングル サインオン: イベント 10742 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abb3acb03e60d1d7a7e705ac8b36aa5157616f6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270986"
---
# <a name="single-sign-on-event-10742"></a><span data-ttu-id="01102-102">シングル サインオン: イベント 10742</span><span class="sxs-lookup"><span data-stu-id="01102-102">Single Sign-On: Event 10742</span></span>
## <a name="details"></a><span data-ttu-id="01102-103">詳細</span><span class="sxs-lookup"><span data-stu-id="01102-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01102-104">製品名</span><span class="sxs-lookup"><span data-stu-id="01102-104">Product Name</span></span>|<span data-ttu-id="01102-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="01102-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="01102-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="01102-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="01102-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="01102-107">Event ID</span></span>|<span data-ttu-id="01102-108">10742</span><span class="sxs-lookup"><span data-stu-id="01102-108">10742</span></span>|  
|<span data-ttu-id="01102-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="01102-109">Event Source</span></span>|<span data-ttu-id="01102-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="01102-110">ENTSSO</span></span>|  
|<span data-ttu-id="01102-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="01102-111">Component</span></span>|<span data-ttu-id="01102-112">N\A</span><span class="sxs-lookup"><span data-stu-id="01102-112">N\A</span></span>|  
|<span data-ttu-id="01102-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="01102-113">Symbolic Name</span></span>|<span data-ttu-id="01102-114">SSO_WARN_NO_UPDATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="01102-114">SSO_WARN_NO_UPDATE_ADAPTER</span></span>|  
|<span data-ttu-id="01102-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="01102-115">Message Text</span></span>|<span data-ttu-id="01102-116">アダプターを更新するには、クライアント ユーザーは SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーであることが必要です。%r</span><span class="sxs-lookup"><span data-stu-id="01102-116">The client user must be a member of the SSO Administrators account or the Application Administrators account to update the adapter.%r</span></span><br /><br /> <span data-ttu-id="01102-117">クライアント ユーザー: %1 %r</span><span class="sxs-lookup"><span data-stu-id="01102-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="01102-118">SSO 管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="01102-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="01102-119">アプリケーション管理者: %3 %r</span><span class="sxs-lookup"><span data-stu-id="01102-119">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="01102-120">アダプター: %4 %r</span><span class="sxs-lookup"><span data-stu-id="01102-120">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="01102-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="01102-121">Error Code: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01102-122">説明</span><span class="sxs-lookup"><span data-stu-id="01102-122">Explanation</span></span>  
 <span data-ttu-id="01102-123">この警告イベントは、指定されたアダプターの更新を試みましたが、使用されたユーザー アカウントが SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーではないために完了できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="01102-123">This Warning event indicates that an attempt to update the specified adapter was made, but could not be completed because the user account used is not a member of the SSO Administrators account or the Application Administrators account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01102-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="01102-124">User Action</span></span>  
 <span data-ttu-id="01102-125">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="01102-125">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="01102-126">SSO 管理者アカウントまたはアプリケーション管理者アカウントにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="01102-126">Add user account to the SSO Administrators account or the Application Administrators account.</span></span>  
  
-   <span data-ttu-id="01102-127">更新を再試行します。</span><span class="sxs-lookup"><span data-stu-id="01102-127">Retry update.</span></span>  
  
 <span data-ttu-id="01102-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="01102-128">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="01102-129">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="01102-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)