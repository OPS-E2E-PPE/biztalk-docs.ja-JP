---
title: シングル サインオン:イベント 11036 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75adfa158082ca2a91c99948c172ef879c83bd13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401052"
---
# <a name="single-sign-on-event-11036"></a><span data-ttu-id="4a5f0-102">シングル サインオン:イベント 11036</span><span class="sxs-lookup"><span data-stu-id="4a5f0-102">Single Sign-On: Event 11036</span></span>
## <a name="details"></a><span data-ttu-id="4a5f0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4a5f0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4a5f0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4a5f0-104">Product Name</span></span>   |                                                                                                                                                                <span data-ttu-id="4a5f0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4a5f0-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                |
| <span data-ttu-id="4a5f0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4a5f0-106">Product Version</span></span> |                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                |
|    <span data-ttu-id="4a5f0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4a5f0-107">Event ID</span></span>     |                                                                                                                                                                          <span data-ttu-id="4a5f0-108">11036</span><span class="sxs-lookup"><span data-stu-id="4a5f0-108">11036</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="4a5f0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4a5f0-109">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="4a5f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4a5f0-110">ENTSSO</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="4a5f0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4a5f0-111">Component</span></span>    |                                                                                                                                                                           <span data-ttu-id="4a5f0-112">なし</span><span class="sxs-lookup"><span data-stu-id="4a5f0-112">N/A</span></span>                                                                                                                                                                           |
|  <span data-ttu-id="4a5f0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4a5f0-113">Symbolic Name</span></span>  |                                                                                                                                                         <span data-ttu-id="4a5f0-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span><span class="sxs-lookup"><span data-stu-id="4a5f0-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span></span>                                                                                                                                                          |
|  <span data-ttu-id="4a5f0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4a5f0-115">Message Text</span></span>   | <span data-ttu-id="4a5f0-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-116">Windows password change.</span></span> <span data-ttu-id="4a5f0-117">この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。%r</span><span class="sxs-lookup"><span data-stu-id="4a5f0-117">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.%r</span></span><br /><br /> <span data-ttu-id="4a5f0-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4a5f0-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="4a5f0-119">Windows アカウント: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="4a5f0-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="4a5f0-120">アプリケーションの場合: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="4a5f0-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="4a5f0-121">アダプター: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="4a5f0-121">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="4a5f0-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="4a5f0-122">Client User: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4a5f0-123">説明</span><span class="sxs-lookup"><span data-stu-id="4a5f0-123">Explanation</span></span>  
 <span data-ttu-id="4a5f0-124">この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-124">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a5f0-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4a5f0-125">User Action</span></span>  
 <span data-ttu-id="4a5f0-126">アダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-126">Check your adapter configuration.</span></span>  
  
 <span data-ttu-id="4a5f0-127">パスワード同期については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a5f0-127">For information on Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>