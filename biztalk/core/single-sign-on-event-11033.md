---
title: シングル サインオン:イベント 11033 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed8e984-2b6c-4a9e-8603-175fdcabeb0a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9c77a8d8ea41a12e8b122dc21e4f0b8d3adce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303407"
---
# <a name="single-sign-on-event-11033"></a><span data-ttu-id="6fb4d-102">シングル サインオン:イベント 11033</span><span class="sxs-lookup"><span data-stu-id="6fb4d-102">Single Sign-On: Event 11033</span></span>
## <a name="details"></a><span data-ttu-id="6fb4d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6fb4d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6fb4d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6fb4d-104">Product Name</span></span>   |                                                                                                                                   <span data-ttu-id="6fb4d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6fb4d-105">Enterprise Single Sign-On</span></span>                                                                                                                                   |
| <span data-ttu-id="6fb4d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6fb4d-106">Product Version</span></span> |                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                   |
|    <span data-ttu-id="6fb4d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6fb4d-107">Event ID</span></span>     |                                                                                                                                             <span data-ttu-id="6fb4d-108">11033</span><span class="sxs-lookup"><span data-stu-id="6fb4d-108">11033</span></span>                                                                                                                                             |
|  <span data-ttu-id="6fb4d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6fb4d-109">Event Source</span></span>   |                                                                                                                                            <span data-ttu-id="6fb4d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6fb4d-110">ENTSSO</span></span>                                                                                                                                             |
|    <span data-ttu-id="6fb4d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6fb4d-111">Component</span></span>    |                                                                                                                                              <span data-ttu-id="6fb4d-112">なし</span><span class="sxs-lookup"><span data-stu-id="6fb4d-112">N/A</span></span>                                                                                                                                              |
|  <span data-ttu-id="6fb4d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6fb4d-113">Symbolic Name</span></span>  |                                                                                                                              <span data-ttu-id="6fb4d-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="6fb4d-114">SSO_INFO_PS_WIN_CHANGE_APP_DISABLED</span></span>                                                                                                                              |
|  <span data-ttu-id="6fb4d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6fb4d-115">Message Text</span></span>   | <span data-ttu-id="6fb4d-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="6fb4d-116">Windows password change.</span></span> <span data-ttu-id="6fb4d-117">この Windows アカウントのマッピングが検出されましたので、アプリケーションが disabled.%r は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6fb4d-117">A mapping for this Windows account has been detected but ignored because the application is disabled.%r</span></span><br /><br /> <span data-ttu-id="6fb4d-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6fb4d-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="6fb4d-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="6fb4d-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="6fb4d-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="6fb4d-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="6fb4d-121">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="6fb4d-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="6fb4d-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="6fb4d-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6fb4d-123">説明</span><span class="sxs-lookup"><span data-stu-id="6fb4d-123">Explanation</span></span>  
 <span data-ttu-id="6fb4d-124">この Windows アカウントのマッピングが検出されましたが、アプリケーションが無効になっているため、無視されます。</span><span class="sxs-lookup"><span data-stu-id="6fb4d-124">A mapping for this Windows account has been detected but ignored because the application is disabled.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fb4d-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6fb4d-125">User Action</span></span>  
 <span data-ttu-id="6fb4d-126">アプリケーションを有効にするのを参照してください。[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fb4d-126">To enable the application, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>