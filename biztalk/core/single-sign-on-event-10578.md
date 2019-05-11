---
title: シングル サインオン:イベント 10578 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4693bc25-d4d5-4cc7-b9bd-42d3471b2b0c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcf04e49efa17d3e796905c45833a02ace81b1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398713"
---
# <a name="single-sign-on-event-10578"></a><span data-ttu-id="797b2-102">シングル サインオン:イベント 10578</span><span class="sxs-lookup"><span data-stu-id="797b2-102">Single Sign-On: Event 10578</span></span>
## <a name="details"></a><span data-ttu-id="797b2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="797b2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="797b2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="797b2-104">Product Name</span></span>   |                                                                                             <span data-ttu-id="797b2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="797b2-105">Enterprise Single Sign-On</span></span>                                                                                             |
| <span data-ttu-id="797b2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="797b2-106">Product Version</span></span> |                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    <span data-ttu-id="797b2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="797b2-107">Event ID</span></span>     |                                                                                                       <span data-ttu-id="797b2-108">10578</span><span class="sxs-lookup"><span data-stu-id="797b2-108">10578</span></span>                                                                                                       |
|  <span data-ttu-id="797b2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="797b2-109">Event Source</span></span>   |                                                                                                      <span data-ttu-id="797b2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="797b2-110">ENTSSO</span></span>                                                                                                       |
|    <span data-ttu-id="797b2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="797b2-111">Component</span></span>    |                                                                                                        <span data-ttu-id="797b2-112">なし</span><span class="sxs-lookup"><span data-stu-id="797b2-112">N/A</span></span>                                                                                                        |
|  <span data-ttu-id="797b2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="797b2-113">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="797b2-114">SSO_INFO_CHANGED_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="797b2-114">SSO_INFO_CHANGED_APP_USER_GROUP</span></span>                                                                                          |
|  <span data-ttu-id="797b2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="797b2-115">Message Text</span></span>   | <span data-ttu-id="797b2-116">アプリケーションのユーザーを更新 account.%r</span><span class="sxs-lookup"><span data-stu-id="797b2-116">Updated Application Users account.%r</span></span><br /><br /> <span data-ttu-id="797b2-117">新しいアプリケーション ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="797b2-117">New Application Users: %1%r</span></span><br /><br /> <span data-ttu-id="797b2-118">古いアプリケーション ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="797b2-118">Old Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="797b2-119">追跡 ID: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="797b2-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="797b2-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="797b2-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="797b2-121">アプリケーション名: %5</span><span class="sxs-lookup"><span data-stu-id="797b2-121">Application Name: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="797b2-122">説明</span><span class="sxs-lookup"><span data-stu-id="797b2-122">Explanation</span></span>  
 <span data-ttu-id="797b2-123">これは、情報メッセージであり、SSO システム内でその発生の重要なセキュリティ関連イベントを追跡するために便利です。</span><span class="sxs-lookup"><span data-stu-id="797b2-123">This is an informational message and can be useful for tracking significant security-related events that occurr within the SSO system.</span></span> <span data-ttu-id="797b2-124">このメッセージは、更新されたアプリケーションのユーザー アカウントが更新されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="797b2-124">This message states that the Updated Application Users account has been updated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="797b2-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="797b2-125">User Action</span></span>  
 <span data-ttu-id="797b2-126">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="797b2-126">No user action is required.</span></span>