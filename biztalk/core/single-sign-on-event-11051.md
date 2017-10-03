---
title: "シングル サインオン: イベント 11051 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe767818-f74e-415c-9287-5b7cc46e358a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a58ee5a4fd842dd292179cea0f7461a5ab0517
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11051"></a><span data-ttu-id="c5fe2-102">シングル サインオン: イベント 11051</span><span class="sxs-lookup"><span data-stu-id="c5fe2-102">Single Sign-On: Event 11051</span></span>
## <a name="details"></a><span data-ttu-id="c5fe2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c5fe2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c5fe2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c5fe2-104">Product Name</span></span>|<span data-ttu-id="c5fe2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c5fe2-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c5fe2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c5fe2-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c5fe2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c5fe2-107">Event ID</span></span>|<span data-ttu-id="c5fe2-108">11051</span><span class="sxs-lookup"><span data-stu-id="c5fe2-108">11051</span></span>|  
|<span data-ttu-id="c5fe2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c5fe2-109">Event Source</span></span>|<span data-ttu-id="c5fe2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c5fe2-110">ENTSSO</span></span>|  
|<span data-ttu-id="c5fe2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5fe2-111">Component</span></span>|<span data-ttu-id="c5fe2-112">なし</span><span class="sxs-lookup"><span data-stu-id="c5fe2-112">N/A</span></span>|  
|<span data-ttu-id="c5fe2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c5fe2-113">Symbolic Name</span></span>|<span data-ttu-id="c5fe2-114">SSO_WARN_SSO_ADMIN_NOT_GROUP</span><span class="sxs-lookup"><span data-stu-id="c5fe2-114">SSO_WARN_SSO_ADMIN_NOT_GROUP</span></span>|  
|<span data-ttu-id="c5fe2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c5fe2-115">Message Text</span></span>|<span data-ttu-id="c5fe2-116">SSO 管理者アカウントに、1 つ以上の単独 (グループではない) アカウントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-116">The SSO Administrators account contains one or more individual (not group) accounts.</span></span> <span data-ttu-id="c5fe2-117">これらの単独アカウントが Active Directory またはローカル コンピューターから削除された場合は、そのアカウントを直ちに SSO システムから削除する必要があります。削除しない場合、セキュリティ リスクになるおそれがあります。%r</span><span class="sxs-lookup"><span data-stu-id="c5fe2-117">If these individual accounts are deleted from Active Directory or the local computer they must be promptly removed from the SSO system or they could become a security risk.%r</span></span><br /><br /> <span data-ttu-id="c5fe2-118">SSO 管理者: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c5fe2-118">SSO Administrators: %1%r</span></span><br /><br /> <span data-ttu-id="c5fe2-119">個々 のアカウント: %2</span><span class="sxs-lookup"><span data-stu-id="c5fe2-119">Individual accounts: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c5fe2-120">説明</span><span class="sxs-lookup"><span data-stu-id="c5fe2-120">Explanation</span></span>  
 <span data-ttu-id="c5fe2-121">単独アカウントを Active Directory またはローカル コンピューターから削除しても、SSO システムからそのアカウントが自動的に削除されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-121">Deleting an individual account from the Active Directory or local computer does not automatically delete that account from the SSO System.</span></span> <span data-ttu-id="c5fe2-122">つまり、アカウント USER1 がローカルで削除され、その後、別のユーザー (新入社員など) が同じ名前でシステムに参加した場合、元の USER1 が持っていたすべてのセキュリティ権限が SSO システムによって新しい USER1 に付与されることになります。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-122">This means that if the account USER1 was deleted locally, and then a different user (for instance, a new employee) joined the system using that same name, the SSO System would grant the new USER1 all security rights possessed by the original USER1.</span></span> <span data-ttu-id="c5fe2-123">これにより、セキュリティ上のリスクが発生します。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-123">This poses a security risk.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c5fe2-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c5fe2-124">User Action</span></span>  
 <span data-ttu-id="c5fe2-125">単独アカウントが Active Directory またはローカル コンピューターから削除されるまで、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-125">No action is necessary until an individual account is deleted from Active Directory or the local computer.</span></span> <span data-ttu-id="c5fe2-126">単独アカウントが削除された時点で、そのアカウントをできるだけ早く SSO システムから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5fe2-126">At that point, you must delete the individual account from the SSO System as soon as possible.</span></span>