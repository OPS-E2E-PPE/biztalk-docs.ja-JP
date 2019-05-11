---
title: シングル サインオン:イベント 10567 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f29c8d9-3da2-4de7-b61f-8c586382b68f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a04443059099694dc60dcb8bf7e33c15d508d273
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398772"
---
# <a name="single-sign-on-event-10567"></a><span data-ttu-id="44374-102">シングル サインオン:イベント 10567</span><span class="sxs-lookup"><span data-stu-id="44374-102">Single Sign-On: Event 10567</span></span>
## <a name="details"></a><span data-ttu-id="44374-103">詳細</span><span class="sxs-lookup"><span data-stu-id="44374-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="44374-104">製品名</span><span class="sxs-lookup"><span data-stu-id="44374-104">Product Name</span></span>   |                                                                                         <span data-ttu-id="44374-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="44374-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="44374-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="44374-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                         |
|    <span data-ttu-id="44374-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="44374-107">Event ID</span></span>     |                                                                                                   <span data-ttu-id="44374-108">10567</span><span class="sxs-lookup"><span data-stu-id="44374-108">10567</span></span>                                                                                                   |
|  <span data-ttu-id="44374-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="44374-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="44374-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="44374-110">ENTSSO</span></span>                                                                                                   |
|    <span data-ttu-id="44374-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="44374-111">Component</span></span>    |                                                                                                    <span data-ttu-id="44374-112">なし</span><span class="sxs-lookup"><span data-stu-id="44374-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="44374-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="44374-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="44374-114">SSO_WARN_INVALID_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="44374-114">SSO_WARN_INVALID_APP_USER_GROUP</span></span>                                                                                      |
|  <span data-ttu-id="44374-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="44374-115">Message Text</span></span>   | <span data-ttu-id="44374-116">アプリケーション ユーザー アカウントがアプリケーション update.%r のため無効です。</span><span class="sxs-lookup"><span data-stu-id="44374-116">The Application Users account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="44374-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="44374-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="44374-118">アプリケーション ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="44374-118">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="44374-119">無効なアカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="44374-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="44374-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="44374-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="44374-121">説明</span><span class="sxs-lookup"><span data-stu-id="44374-121">Explanation</span></span>  
 <span data-ttu-id="44374-122">無効か、存在しないアプリケーション ユーザー アカウントを更新しようとしました。</span><span class="sxs-lookup"><span data-stu-id="44374-122">You have attempted to update an Application Users account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44374-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="44374-123">User Action</span></span>  
 <span data-ttu-id="44374-124">アカウントの名前が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="44374-124">Check that the name of the account is correct.</span></span>