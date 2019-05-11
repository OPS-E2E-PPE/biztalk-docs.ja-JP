---
title: シングル サインオン:イベント 10575 |Microsoft Docs
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
ms.openlocfilehash: 76cd29d85b700eadb0bce35822a2ab73493755c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295928"
---
# <a name="single-sign-on-event-10575"></a><span data-ttu-id="cc8fc-102">シングル サインオン:イベント 10575</span><span class="sxs-lookup"><span data-stu-id="cc8fc-102">Single Sign-On: Event 10575</span></span>
## <a name="details"></a><span data-ttu-id="cc8fc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cc8fc-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cc8fc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cc8fc-104">Product Name</span></span>   |                                                                                     <span data-ttu-id="cc8fc-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cc8fc-105">Enterprise Single Sign-On</span></span>                                                                                     |
| <span data-ttu-id="cc8fc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cc8fc-106">Product Version</span></span> |                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                     |
|    <span data-ttu-id="cc8fc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cc8fc-107">Event ID</span></span>     |                                                                                               <span data-ttu-id="cc8fc-108">10575</span><span class="sxs-lookup"><span data-stu-id="cc8fc-108">10575</span></span>                                                                                               |
|  <span data-ttu-id="cc8fc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cc8fc-109">Event Source</span></span>   |                                                                                              <span data-ttu-id="cc8fc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cc8fc-110">ENTSSO</span></span>                                                                                               |
|    <span data-ttu-id="cc8fc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cc8fc-111">Component</span></span>    |                                                                                                <span data-ttu-id="cc8fc-112">なし</span><span class="sxs-lookup"><span data-stu-id="cc8fc-112">N/A</span></span>                                                                                                |
|  <span data-ttu-id="cc8fc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cc8fc-113">Symbolic Name</span></span>  |                                                                                  <span data-ttu-id="cc8fc-114">SSO_INFO_CHANGED_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="cc8fc-114">SSO_INFO_CHANGED_SECRET_SERVER</span></span>                                                                                   |
|  <span data-ttu-id="cc8fc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cc8fc-115">Message Text</span></span>   | <span data-ttu-id="cc8fc-116">シークレット サーバー name.%r の更新</span><span class="sxs-lookup"><span data-stu-id="cc8fc-116">Updated secret server name.%r</span></span><br /><br /> <span data-ttu-id="cc8fc-117">新しいシークレット サーバー: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="cc8fc-117">New Secret Server: %1%r</span></span><br /><br /> <span data-ttu-id="cc8fc-118">古いシークレット サーバー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="cc8fc-118">Old Secret Server: %2%r</span></span><br /><br /> <span data-ttu-id="cc8fc-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="cc8fc-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="cc8fc-120">クライアント コンピューターの場合: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="cc8fc-120">Client Computer: %4%r</span></span><br /><br /> <span data-ttu-id="cc8fc-121">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="cc8fc-121">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="cc8fc-122">説明</span><span class="sxs-lookup"><span data-stu-id="cc8fc-122">Explanation</span></span>  
 <span data-ttu-id="cc8fc-123">これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="cc8fc-124">このメッセージは、シークレット サーバー名が更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-124">This message states that the secret server name has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc8fc-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cc8fc-125">User Action</span></span>  
 <span data-ttu-id="cc8fc-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="cc8fc-126">No user action is required.</span></span>