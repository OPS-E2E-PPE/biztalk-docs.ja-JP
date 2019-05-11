---
title: シングル サインオン:イベント 11035 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d551083c-a897-4a76-a40c-2254d3a3e52e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b07359061b7e855e8ea53abee64ef567668395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395249"
---
# <a name="single-sign-on-event-11035"></a><span data-ttu-id="27ded-102">シングル サインオン:イベント 11035</span><span class="sxs-lookup"><span data-stu-id="27ded-102">Single Sign-On: Event 11035</span></span>
## <a name="details"></a><span data-ttu-id="27ded-103">詳細</span><span class="sxs-lookup"><span data-stu-id="27ded-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="27ded-104">製品名</span><span class="sxs-lookup"><span data-stu-id="27ded-104">Product Name</span></span>   |                                                                                                                                               <span data-ttu-id="27ded-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="27ded-105">Enterprise Single Sign-On</span></span>                                                                                                                                                |
| <span data-ttu-id="27ded-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="27ded-106">Product Version</span></span> |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    <span data-ttu-id="27ded-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="27ded-107">Event ID</span></span>     |                                                                                                                                                         <span data-ttu-id="27ded-108">11035</span><span class="sxs-lookup"><span data-stu-id="27ded-108">11035</span></span>                                                                                                                                                          |
|  <span data-ttu-id="27ded-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="27ded-109">Event Source</span></span>   |                                                                                                                                                         <span data-ttu-id="27ded-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="27ded-110">ENTSSO</span></span>                                                                                                                                                         |
|    <span data-ttu-id="27ded-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="27ded-111">Component</span></span>    |                                                                                                                                                          <span data-ttu-id="27ded-112">なし</span><span class="sxs-lookup"><span data-stu-id="27ded-112">N/A</span></span>                                                                                                                                                           |
|  <span data-ttu-id="27ded-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="27ded-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="27ded-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="27ded-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span></span>                                                                                                                                            |
|  <span data-ttu-id="27ded-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="27ded-115">Message Text</span></span>   | <span data-ttu-id="27ded-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="27ded-116">Windows password change.</span></span> <span data-ttu-id="27ded-117">この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。%r</span><span class="sxs-lookup"><span data-stu-id="27ded-117">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.%r</span></span><br /><br /> <span data-ttu-id="27ded-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="27ded-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="27ded-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="27ded-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="27ded-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="27ded-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="27ded-121">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="27ded-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="27ded-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="27ded-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="27ded-123">説明</span><span class="sxs-lookup"><span data-stu-id="27ded-123">Explanation</span></span>  
 <span data-ttu-id="27ded-124">この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。</span><span class="sxs-lookup"><span data-stu-id="27ded-124">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27ded-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="27ded-125">User Action</span></span>  
 <span data-ttu-id="27ded-126">パスワード同期の構成方法の詳細については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)します。</span><span class="sxs-lookup"><span data-stu-id="27ded-126">For information on configuring Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>