---
title: 'シングル サインオン: イベント 10558 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d9a281d6a6ca20a274db4b3ffe5b2697ff812c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974869"
---
# <a name="single-sign-on-event-10558"></a><span data-ttu-id="405db-102">シングル サインオン: イベント 10558</span><span class="sxs-lookup"><span data-stu-id="405db-102">Single Sign-On: Event 10558</span></span>
## <a name="details"></a><span data-ttu-id="405db-103">詳細</span><span class="sxs-lookup"><span data-stu-id="405db-103">Details</span></span>  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="405db-104">製品名</span><span class="sxs-lookup"><span data-stu-id="405db-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="405db-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="405db-105">Enterprise Single Sign-On</span></span>                                                                                   |
| <span data-ttu-id="405db-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="405db-106">Product Version</span></span> |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="405db-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="405db-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="405db-108">10558</span><span class="sxs-lookup"><span data-stu-id="405db-108">10558</span></span>                                                                                             |
|  <span data-ttu-id="405db-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="405db-109">Event Source</span></span>   |                                                                                            <span data-ttu-id="405db-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="405db-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="405db-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="405db-111">Component</span></span>    |                                                                                             <span data-ttu-id="405db-112">なし</span><span class="sxs-lookup"><span data-stu-id="405db-112">N/A</span></span>                                                                                              |
|  <span data-ttu-id="405db-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="405db-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="405db-114">SSO_WARN_USER_OWN_MAPPINGS</span><span class="sxs-lookup"><span data-stu-id="405db-114">SSO_WARN_USER_OWN_MAPPINGS</span></span>                                                                                  |
|  <span data-ttu-id="405db-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="405db-115">Message Text</span></span>   | <span data-ttu-id="405db-116">アプリケーション ユーザーは各自のマッピングを制御することのみ許可されています。%r</span><span class="sxs-lookup"><span data-stu-id="405db-116">Application Users are only allowed to control their own mappings.%r</span></span><br /><br /> <span data-ttu-id="405db-117">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="405db-117">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="405db-118">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="405db-118">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="405db-119">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="405db-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="405db-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="405db-120">Client User: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="405db-121">説明</span><span class="sxs-lookup"><span data-stu-id="405db-121">Explanation</span></span>  
 <span data-ttu-id="405db-122">アプリケーション ユーザーが他のユーザーのマッピングを制御しようとしました。</span><span class="sxs-lookup"><span data-stu-id="405db-122">An attempt was made by an Application User to control the mappings of a different user.</span></span> <span data-ttu-id="405db-123">これは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="405db-123">This is not allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="405db-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="405db-124">User Action</span></span>  
 <span data-ttu-id="405db-125">マッピングを制御できるのは、その特定のマッピングのアプリケーション ユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="405db-125">Mappings can only be controlled by the Application Users for those specific mappings.</span></span>