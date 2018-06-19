---
title: 'シングル サインオン: イベント 11010 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22fcd9f3-83bb-44b0-88fc-197c2ef3e72d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f81bef87439c4607a32f2547d5bf44b19491140b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277186"
---
# <a name="single-sign-on-event-11010"></a><span data-ttu-id="0eea2-102">シングル サインオン: イベント 11010</span><span class="sxs-lookup"><span data-stu-id="0eea2-102">Single Sign-On: Event 11010</span></span>
## <a name="details"></a><span data-ttu-id="0eea2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0eea2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0eea2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0eea2-104">Product Name</span></span>|<span data-ttu-id="0eea2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0eea2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0eea2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0eea2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0eea2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0eea2-107">Event ID</span></span>|<span data-ttu-id="0eea2-108">11010</span><span class="sxs-lookup"><span data-stu-id="0eea2-108">11010</span></span>|  
|<span data-ttu-id="0eea2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0eea2-109">Event Source</span></span>|<span data-ttu-id="0eea2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0eea2-110">ENTSSO</span></span>|  
|<span data-ttu-id="0eea2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0eea2-111">Component</span></span>|<span data-ttu-id="0eea2-112">なし</span><span class="sxs-lookup"><span data-stu-id="0eea2-112">N/A</span></span>|  
|<span data-ttu-id="0eea2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0eea2-113">Symbolic Name</span></span>|<span data-ttu-id="0eea2-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span><span class="sxs-lookup"><span data-stu-id="0eea2-114">SSO_WARN_NOT_SSO_AFF_ADMIN</span></span>|  
|<span data-ttu-id="0eea2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0eea2-115">Message Text</span></span>|<span data-ttu-id="0eea2-116">クライアント ユーザーが SSO 関連管理者アカウントのメンバーではありません。%r</span><span class="sxs-lookup"><span data-stu-id="0eea2-116">Client user is not a member of the SSO Affiliate Administrators account.%r</span></span><br /><br /> <span data-ttu-id="0eea2-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0eea2-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0eea2-118">クライアント ユーザー: %2\\%3 %r</span><span class="sxs-lookup"><span data-stu-id="0eea2-118">Client User: %2\\%3%r</span></span><br /><br /> <span data-ttu-id="0eea2-119">SSO 関連管理者: %4</span><span class="sxs-lookup"><span data-stu-id="0eea2-119">SSO Affiliate Administrators: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0eea2-120">説明</span><span class="sxs-lookup"><span data-stu-id="0eea2-120">Explanation</span></span>  
 <span data-ttu-id="0eea2-121">クライアント ユーザーが SSO 関連管理者アカウントのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="0eea2-121">The client user is not a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="0eea2-122">この警告は、監査レベルが高に設定されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="0eea2-122">This warning only appears when the audit levels are set to high.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0eea2-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0eea2-123">User Action</span></span>  
 <span data-ttu-id="0eea2-124">この状況を解決するには、クライアント ユーザーを SSO 関連管理者アカウントのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0eea2-124">To remedy the situation, you must make the client user a member of the SSO Affiliate Administrators account.</span></span> <span data-ttu-id="0eea2-125">今後警告を表示しない場合は、監査レベルを低くします。</span><span class="sxs-lookup"><span data-stu-id="0eea2-125">To stop this warning from appearing in the future, you can lower the audit levels.</span></span>