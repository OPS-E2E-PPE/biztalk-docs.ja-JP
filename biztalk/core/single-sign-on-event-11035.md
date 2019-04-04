---
title: 'シングル サインオン: イベント 11035 |Microsoft Docs'
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
ms.openlocfilehash: 194d3069f0b74022e6b16a28de1c7f81ae3030f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001723"
---
# <a name="single-sign-on-event-11035"></a><span data-ttu-id="9c3be-102">シングル サインオン: イベント 11035</span><span class="sxs-lookup"><span data-stu-id="9c3be-102">Single Sign-On: Event 11035</span></span>
## <a name="details"></a><span data-ttu-id="9c3be-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9c3be-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c3be-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9c3be-104">Product Name</span></span>   |                                                                                                                                               <span data-ttu-id="9c3be-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9c3be-105">Enterprise Single Sign-On</span></span>                                                                                                                                                |
| <span data-ttu-id="9c3be-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9c3be-106">Product Version</span></span> |                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                               |
|    <span data-ttu-id="9c3be-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9c3be-107">Event ID</span></span>     |                                                                                                                                                         <span data-ttu-id="9c3be-108">11035</span><span class="sxs-lookup"><span data-stu-id="9c3be-108">11035</span></span>                                                                                                                                                          |
|  <span data-ttu-id="9c3be-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9c3be-109">Event Source</span></span>   |                                                                                                                                                         <span data-ttu-id="9c3be-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9c3be-110">ENTSSO</span></span>                                                                                                                                                         |
|    <span data-ttu-id="9c3be-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9c3be-111">Component</span></span>    |                                                                                                                                                          <span data-ttu-id="9c3be-112">なし</span><span class="sxs-lookup"><span data-stu-id="9c3be-112">N/A</span></span>                                                                                                                                                           |
|  <span data-ttu-id="9c3be-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9c3be-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="9c3be-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="9c3be-114">SSO_INFO_PS_WIN_CHANGE_NO_ADAPTER</span></span>                                                                                                                                            |
|  <span data-ttu-id="9c3be-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9c3be-115">Message Text</span></span>   | <span data-ttu-id="9c3be-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="9c3be-116">Windows password change.</span></span> <span data-ttu-id="9c3be-117">この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。%r</span><span class="sxs-lookup"><span data-stu-id="9c3be-117">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.%r</span></span><br /><br /> <span data-ttu-id="9c3be-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9c3be-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9c3be-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="9c3be-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="9c3be-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="9c3be-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="9c3be-121">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="9c3be-121">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="9c3be-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="9c3be-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9c3be-123">説明</span><span class="sxs-lookup"><span data-stu-id="9c3be-123">Explanation</span></span>  
 <span data-ttu-id="9c3be-124">この Windows アカウントに対するマッピングが検出されましたが、このアプリケーションに対してはパスワード同期が構成されていないため無視されました。</span><span class="sxs-lookup"><span data-stu-id="9c3be-124">A mapping for this Windows account has been detected but ignored because password sync is not configured for this application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c3be-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9c3be-125">User Action</span></span>  
 <span data-ttu-id="9c3be-126">パスワード同期の構成方法の詳細については、[パスワード同期](../core/password-synchronization2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c3be-126">For information on configuring Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>