---
title: シングル サインオン:イベント 10615 |Microsoft Docs
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
ms.openlocfilehash: adece23afc79fcff2d4c0168aaee4b38819f5e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397687"
---
# <a name="single-sign-on-event-10615"></a><span data-ttu-id="0e187-102">シングル サインオン:イベント 10615</span><span class="sxs-lookup"><span data-stu-id="0e187-102">Single Sign-On: Event 10615</span></span>
## <a name="details"></a><span data-ttu-id="0e187-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0e187-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e187-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0e187-104">Product Name</span></span>   |                                                                                                                <span data-ttu-id="0e187-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0e187-105">Enterprise Single Sign-On</span></span>                                                                                                                |
| <span data-ttu-id="0e187-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0e187-106">Product Version</span></span> |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    <span data-ttu-id="0e187-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0e187-107">Event ID</span></span>     |                                                                                                                          <span data-ttu-id="0e187-108">10615</span><span class="sxs-lookup"><span data-stu-id="0e187-108">10615</span></span>                                                                                                                          |
|  <span data-ttu-id="0e187-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0e187-109">Event Source</span></span>   |                                                                                                                         <span data-ttu-id="0e187-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e187-110">ENTSSO</span></span>                                                                                                                          |
|    <span data-ttu-id="0e187-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e187-111">Component</span></span>    |                                                                                                                           <span data-ttu-id="0e187-112">なし</span><span class="sxs-lookup"><span data-stu-id="0e187-112">N/A</span></span>                                                                                                                           |
|  <span data-ttu-id="0e187-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0e187-113">Symbolic Name</span></span>  |                                                                                                            <span data-ttu-id="0e187-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e187-114">SSO_WARN_NO_UPDATE_TICKET_TIMEOUT</span></span>                                                                                                            |
|  <span data-ttu-id="0e187-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0e187-115">Message Text</span></span>   | <span data-ttu-id="0e187-116">クライアント ユーザーは application.%r のチケット タイムアウトを変更するには、SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e187-116">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.%r</span></span><br /><br /> <span data-ttu-id="0e187-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="0e187-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="0e187-118">SSO 管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="0e187-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="0e187-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="0e187-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="0e187-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="0e187-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e187-121">説明</span><span class="sxs-lookup"><span data-stu-id="0e187-121">Explanation</span></span>  
 <span data-ttu-id="0e187-122">クライアント ユーザーは、アプリケーションのチケット タイムアウトを変更するには、SSO 管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e187-122">The client user must be a member of the SSO Administrators account to change the ticket time-out for an application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e187-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0e187-123">User Action</span></span>  
 <span data-ttu-id="0e187-124">この変更を行うには、SSO 管理者アカウントのメンバーの検索に役立つ、システム管理者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="0e187-124">Have your system administrator help you find a member of the SSO Administrators account to make this change.</span></span>