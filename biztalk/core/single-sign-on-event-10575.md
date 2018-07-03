---
title: 'シングル サインオン: イベント 10575 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a691812-433c-42ba-a225-873ad1bfee99
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93ae664da9f4f9a36c82cdec2dea0edeeac6bdeb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968563"
---
# <a name="single-sign-on-event-10575"></a><span data-ttu-id="2f63a-102">シングル サインオン: イベント 10575</span><span class="sxs-lookup"><span data-stu-id="2f63a-102">Single Sign-On: Event 10575</span></span>
## <a name="details"></a><span data-ttu-id="2f63a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2f63a-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2f63a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2f63a-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="2f63a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2f63a-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="2f63a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2f63a-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="2f63a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2f63a-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="2f63a-108">10575</span><span class="sxs-lookup"><span data-stu-id="2f63a-108">10575</span></span>                                                                                               |
|  <span data-ttu-id="2f63a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2f63a-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="2f63a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2f63a-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="2f63a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2f63a-111">Component</span></span>    |                                                                                                <span data-ttu-id="2f63a-112">なし</span><span class="sxs-lookup"><span data-stu-id="2f63a-112">N/A</span></span>                                                                                                |
|  <span data-ttu-id="2f63a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2f63a-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="2f63a-114">SSO_INFO_CHANGED_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="2f63a-114">SSO_INFO_CHANGED_SECRET_SERVER</span></span>                                                                                   |
|  <span data-ttu-id="2f63a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2f63a-115">Message Text</span></span>   | <span data-ttu-id="2f63a-116">シークレット サーバー名を更新しました。%r</span><span class="sxs-lookup"><span data-stu-id="2f63a-116">Updated secret server name.%r</span></span><br /><br /> <span data-ttu-id="2f63a-117">新しいシークレット サーバー: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="2f63a-117">New Secret Server: %1%r</span></span><br /><br /> <span data-ttu-id="2f63a-118">古いシークレット サーバー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="2f63a-118">Old Secret Server: %2%r</span></span><br /><br /> <span data-ttu-id="2f63a-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="2f63a-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="2f63a-120">クライアント コンピューターの場合: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="2f63a-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="2f63a-121">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="2f63a-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2f63a-122">説明</span><span class="sxs-lookup"><span data-stu-id="2f63a-122">Explanation</span></span>  
 <span data-ttu-id="2f63a-123">これは情報メッセージであり、SSO システム内で発生する重要なセキュリティ関連イベントの追跡に役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="2f63a-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="2f63a-124">このメッセージは、シークレット サーバー名が更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2f63a-124">This message states that the secret server name has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2f63a-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2f63a-125">User Action</span></span>  
 <span data-ttu-id="2f63a-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="2f63a-126">No user action is required.</span></span>