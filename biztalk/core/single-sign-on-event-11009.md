---
title: "シングル サインオン: イベント 11009 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99308e7a9e709cff5c0e1e15963eeb4769c00f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11009"></a><span data-ttu-id="d6df0-102">シングル サインオン: イベント 11009</span><span class="sxs-lookup"><span data-stu-id="d6df0-102">Single Sign-On: Event 11009</span></span>
## <a name="details"></a><span data-ttu-id="d6df0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d6df0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6df0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d6df0-104">Product Name</span></span>|<span data-ttu-id="d6df0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d6df0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d6df0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d6df0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d6df0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d6df0-107">Event ID</span></span>|<span data-ttu-id="d6df0-108">11009</span><span class="sxs-lookup"><span data-stu-id="d6df0-108">11009</span></span>|  
|<span data-ttu-id="d6df0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d6df0-109">Event Source</span></span>|<span data-ttu-id="d6df0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d6df0-110">ENTSSO</span></span>|  
|<span data-ttu-id="d6df0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d6df0-111">Component</span></span>|<span data-ttu-id="d6df0-112">なし</span><span class="sxs-lookup"><span data-stu-id="d6df0-112">N/A</span></span>|  
|<span data-ttu-id="d6df0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d6df0-113">Symbolic Name</span></span>|<span data-ttu-id="d6df0-114">SSO_WARN_NOT_SSO_ADMIN</span><span class="sxs-lookup"><span data-stu-id="d6df0-114">SSO_WARN_NOT_SSO_ADMIN</span></span>|  
|<span data-ttu-id="d6df0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d6df0-115">Message Text</span></span>|<span data-ttu-id="d6df0-116">クライアント ユーザーが SSO 管理者アカウントのメンバーではありません。%r</span><span class="sxs-lookup"><span data-stu-id="d6df0-116">Client user is not a member of the SSO Administrators account.%r</span></span><br /><br /> <span data-ttu-id="d6df0-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d6df0-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d6df0-118">クライアント ユーザー: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="d6df0-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="d6df0-119">SSO 管理者: %4</span><span class="sxs-lookup"><span data-stu-id="d6df0-119">SSO Administrators: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6df0-120">説明</span><span class="sxs-lookup"><span data-stu-id="d6df0-120">Explanation</span></span>  
 <span data-ttu-id="d6df0-121">クライアント ユーザーが SSO 管理者アカウントのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="d6df0-121">The client user is not a member of the SSO Administrators account.</span></span> <span data-ttu-id="d6df0-122">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6df0-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6df0-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d6df0-123">User Action</span></span>  
 <span data-ttu-id="d6df0-124">この状況を解決するには、クライアント ユーザーを SSO 管理者アカウントのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6df0-124">To remedy the situation, you must make the client user a member of the SSO Administrators account.</span></span> <span data-ttu-id="d6df0-125">今後警告を表示しない場合は、監査レベルを低くします。</span><span class="sxs-lookup"><span data-stu-id="d6df0-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>