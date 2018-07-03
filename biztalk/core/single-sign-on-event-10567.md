---
title: 'シングル サインオン: イベント 10567 |Microsoft Docs'
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
ms.openlocfilehash: 6ac0bed16a9e80860b23738e175b2bdafb883283
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975931"
---
# <a name="single-sign-on-event-10567"></a><span data-ttu-id="c88fc-102">シングル サインオン: イベント 10567</span><span class="sxs-lookup"><span data-stu-id="c88fc-102">Single Sign-On: Event 10567</span></span>
## <a name="details"></a><span data-ttu-id="c88fc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c88fc-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c88fc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c88fc-104">Product Name</span></span>   |                                                                                         <span data-ttu-id="c88fc-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c88fc-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="c88fc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c88fc-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                         |
|    <span data-ttu-id="c88fc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c88fc-107">Event ID</span></span>     |                                                                                                   <span data-ttu-id="c88fc-108">10567</span><span class="sxs-lookup"><span data-stu-id="c88fc-108">10567</span></span>                                                                                                   |
|  <span data-ttu-id="c88fc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c88fc-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="c88fc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c88fc-110">ENTSSO</span></span>                                                                                                   |
|    <span data-ttu-id="c88fc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c88fc-111">Component</span></span>    |                                                                                                    <span data-ttu-id="c88fc-112">なし</span><span class="sxs-lookup"><span data-stu-id="c88fc-112">N/A</span></span>                                                                                                    |
|  <span data-ttu-id="c88fc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c88fc-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="c88fc-114">SSO_WARN_INVALID_APP_USER_GROUP</span><span class="sxs-lookup"><span data-stu-id="c88fc-114">SSO_WARN_INVALID_APP_USER_GROUP</span></span>                                                                                      |
|  <span data-ttu-id="c88fc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c88fc-115">Message Text</span></span>   | <span data-ttu-id="c88fc-116">アプリケーション ユーザー アカウントがアプリケーションの更新について有効ではありません。%r</span><span class="sxs-lookup"><span data-stu-id="c88fc-116">The Application Users account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="c88fc-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c88fc-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="c88fc-118">アプリケーション ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c88fc-118">Application Users: %2%r</span></span><br /><br /> <span data-ttu-id="c88fc-119">無効なアカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="c88fc-119">Invalid accounts: %3%r</span></span><br /><br /> <span data-ttu-id="c88fc-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="c88fc-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c88fc-121">説明</span><span class="sxs-lookup"><span data-stu-id="c88fc-121">Explanation</span></span>  
 <span data-ttu-id="c88fc-122">無効であるか、または存在しないアプリケーション ユーザー アカウントを更新しようとしました。</span><span class="sxs-lookup"><span data-stu-id="c88fc-122">You have attempted to update an Application Users account which is either invalid or does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c88fc-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c88fc-123">User Action</span></span>  
 <span data-ttu-id="c88fc-124">アカウントの名前が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c88fc-124">Check that the name of the account is correct.</span></span>