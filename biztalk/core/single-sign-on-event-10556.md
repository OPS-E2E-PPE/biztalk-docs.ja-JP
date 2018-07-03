---
title: 'シングル サインオン: イベント 10556 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66661a77-e8b0-4972-a3bc-4bb717967699
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79300dc2ff97fe3f410d0e8b06cdfbebd4782a48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011763"
---
# <a name="single-sign-on-event-10556"></a><span data-ttu-id="d0097-102">シングル サインオン: イベント 10556</span><span class="sxs-lookup"><span data-stu-id="d0097-102">Single Sign-On: Event 10556</span></span>
## <a name="details"></a><span data-ttu-id="d0097-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d0097-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d0097-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d0097-104">Product Name</span></span>   |                                                                                                                             <span data-ttu-id="d0097-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d0097-105">Enterprise Single Sign-On</span></span>                                                                                                                             |
| <span data-ttu-id="d0097-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d0097-106">Product Version</span></span> |                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                             |
|    <span data-ttu-id="d0097-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d0097-107">Event ID</span></span>     |                                                                                                                                       <span data-ttu-id="d0097-108">10556</span><span class="sxs-lookup"><span data-stu-id="d0097-108">10556</span></span>                                                                                                                                       |
|  <span data-ttu-id="d0097-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d0097-109">Event Source</span></span>   |                                                                                                                                      <span data-ttu-id="d0097-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d0097-110">ENTSSO</span></span>                                                                                                                                       |
|    <span data-ttu-id="d0097-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d0097-111">Component</span></span>    |                                                                                                                                        <span data-ttu-id="d0097-112">なし</span><span class="sxs-lookup"><span data-stu-id="d0097-112">N/A</span></span>                                                                                                                                        |
|  <span data-ttu-id="d0097-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d0097-113">Symbolic Name</span></span>  |                                                                                                                            <span data-ttu-id="d0097-114">SSO_WARN_INVALID_GROUP_USER</span><span class="sxs-lookup"><span data-stu-id="d0097-114">SSO_WARN_INVALID_GROUP_USER</span></span>                                                                                                                            |
|  <span data-ttu-id="d0097-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d0097-115">Message Text</span></span>   | <span data-ttu-id="d0097-116">グループ アプリケーションについて指定されたマッピングが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0097-116">The mapping specified for a Group application is not valid.</span></span> <span data-ttu-id="d0097-117">このアプリケーションでは、マッピングでいずれかのアプリケーション ユーザー アカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0097-117">The mapping must specify one of the Application Users accounts for this application.%r</span></span><br /><br /> <span data-ttu-id="d0097-118">ドメイン名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d0097-118">Domain Name: %1%r</span></span><br /><br /> <span data-ttu-id="d0097-119">ユーザー名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d0097-119">User Name: %2%r</span></span><br /><br /> <span data-ttu-id="d0097-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d0097-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="d0097-121">アプリケーション ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="d0097-121">Application Users: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d0097-122">説明</span><span class="sxs-lookup"><span data-stu-id="d0097-122">Explanation</span></span>  
 <span data-ttu-id="d0097-123">マッピングが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0097-123">The mapping is not valid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0097-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d0097-124">User Action</span></span>  
 <span data-ttu-id="d0097-125">このアプリケーションについて、マッピングでいずれかのアプリケーション ユーザー アカウントが指定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0097-125">Check that the mapping specifies one of the Application User accounts for this application.</span></span>