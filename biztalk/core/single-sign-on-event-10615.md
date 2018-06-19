---
title: 'シングル サインオン: イベント 10615 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9570290f82821a80d22826f41d4ed669e29f5b4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271498"
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="a6353-102">シングル サインオン: イベント 10615</span><span class="sxs-lookup"><span data-stu-id="a6353-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="a6353-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6353-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6353-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6353-104">Product Name</span></span>|<span data-ttu-id="a6353-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a6353-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a6353-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6353-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a6353-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6353-107">Event ID</span></span>|<span data-ttu-id="a6353-108">10615</span><span class="sxs-lookup"><span data-stu-id="a6353-108">10615</span></span>|  
|<span data-ttu-id="a6353-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6353-109">Event Source</span></span>|<span data-ttu-id="a6353-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a6353-110">ENTSSO</span></span>|  
|<span data-ttu-id="a6353-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6353-111">Component</span></span>|<span data-ttu-id="a6353-112">なし</span><span class="sxs-lookup"><span data-stu-id="a6353-112">N/A</span></span>|  
|<span data-ttu-id="a6353-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6353-113">Symbolic Name</span></span>|<span data-ttu-id="a6353-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6353-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>|  
|<span data-ttu-id="a6353-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6353-115">Message Text</span></span>|<span data-ttu-id="a6353-116">アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。%r</span><span class="sxs-lookup"><span data-stu-id="a6353-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="a6353-117">クライアント ユーザー: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a6353-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="a6353-118">SSO 管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a6353-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="a6353-119">アプリケーション名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a6353-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="a6353-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="a6353-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6353-121">説明</span><span class="sxs-lookup"><span data-stu-id="a6353-121">Explanation</span></span>  
 <span data-ttu-id="a6353-122">アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a6353-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6353-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6353-123">User Action</span></span>  
 <span data-ttu-id="a6353-124">システム管理者に連絡し、SSO 管理者アカウントのメンバーを探して、この変更を行います。</span><span class="sxs-lookup"><span data-stu-id="a6353-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>