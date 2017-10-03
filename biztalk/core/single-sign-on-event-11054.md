---
title: "シングル サインオン: イベント 11054 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59dc801d-fc78-4561-8a26-9d815c86d842
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c4d71bc77f36231ddec939faf5e904e45017614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11054"></a><span data-ttu-id="89655-102">シングル サインオン: イベント 11054</span><span class="sxs-lookup"><span data-stu-id="89655-102">Single Sign-On: Event 11054</span></span>
## <a name="details"></a><span data-ttu-id="89655-103">詳細</span><span class="sxs-lookup"><span data-stu-id="89655-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89655-104">製品名</span><span class="sxs-lookup"><span data-stu-id="89655-104">Product Name</span></span>|<span data-ttu-id="89655-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="89655-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="89655-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="89655-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="89655-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="89655-107">Event ID</span></span>|<span data-ttu-id="89655-108">11054</span><span class="sxs-lookup"><span data-stu-id="89655-108">11054</span></span>|  
|<span data-ttu-id="89655-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="89655-109">Event Source</span></span>|<span data-ttu-id="89655-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="89655-110">ENTSSO</span></span>|  
|<span data-ttu-id="89655-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="89655-111">Component</span></span>|<span data-ttu-id="89655-112">なし</span><span class="sxs-lookup"><span data-stu-id="89655-112">N/A</span></span>|  
|<span data-ttu-id="89655-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="89655-113">Symbolic Name</span></span>|<span data-ttu-id="89655-114">SSO_WARN_APP_USERS_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="89655-114">SSO_WARN_APP_USERS_NOT_GROUP</span></span>|  
|<span data-ttu-id="89655-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="89655-115">Message Text</span></span>|<span data-ttu-id="89655-116">アプリケーション ユーザー アカウントには、1 つまたは複数の単独 (グループではない) アカウントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89655-116">The Application Users account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="89655-117">これらの単独アカウントが Active Directory またはローカル コンピューターから削除された場合は、そのアカウントを直ちに SSO システムから削除する必要があります。削除しない場合、セキュリティ リスクになるおそれがあります。%r</span><span class="sxs-lookup"><span data-stu-id="89655-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="89655-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="89655-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="89655-119">アプリケーション ユーザー: %2 %r</span><span class="sxs-lookup"><span data-stu-id="89655-119">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="89655-120">個々 のアカウント: %3</span><span class="sxs-lookup"><span data-stu-id="89655-120">Individual accounts: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89655-121">説明</span><span class="sxs-lookup"><span data-stu-id="89655-121">Explanation</span></span>  
 <span data-ttu-id="89655-122">単独アカウントを Active Directory またはローカル コンピューターから削除しても、SSO システムからそのアカウントが自動的に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="89655-122">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="89655-123">つまり、アカウント USER1 がローカルで削除され、その後、別のユーザー (新入社員など) が同じ名前でシステムに参加した場合、元の USER1 が持っていたすべてのセキュリティ権限が SSO システムによって新しい USER1 に付与されることになります。</span><span class="sxs-lookup"><span data-stu-id="89655-123">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="89655-124">これにより、セキュリティ上のリスクが発生します。</span><span class="sxs-lookup"><span data-stu-id="89655-124">This poses a security risk.</span></span>  
  
 <span data-ttu-id="89655-125">SSO 管理者アカウントでは Active Directory グループ (単独ではない) アカウントを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89655-125">As a best practice, it is recommended that SSO Administration accounts use Active Directory group (not individual) accounts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89655-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="89655-126">User Action</span></span>  
 <span data-ttu-id="89655-127">単独アカウントが Active Directory またはローカル コンピューターから削除されるまで、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="89655-127">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="89655-128">単独アカウントが削除された時点で、そのアカウントをできるだけ早く SSO システムから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89655-128">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>