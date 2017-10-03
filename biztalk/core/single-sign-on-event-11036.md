---
title: "シングル サインオン: イベント 11036 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63b11005248471c222f63c88439a0e60571b341e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11036"></a><span data-ttu-id="aba55-102">シングル サインオン: イベント 11036</span><span class="sxs-lookup"><span data-stu-id="aba55-102">Single Sign-On: Event 11036</span></span>
## <a name="details"></a><span data-ttu-id="aba55-103">詳細</span><span class="sxs-lookup"><span data-stu-id="aba55-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aba55-104">製品名</span><span class="sxs-lookup"><span data-stu-id="aba55-104">Product Name</span></span>|<span data-ttu-id="aba55-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="aba55-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="aba55-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="aba55-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="aba55-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aba55-107">Event ID</span></span>|<span data-ttu-id="aba55-108">11036</span><span class="sxs-lookup"><span data-stu-id="aba55-108">11036</span></span>|  
|<span data-ttu-id="aba55-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="aba55-109">Event Source</span></span>|<span data-ttu-id="aba55-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="aba55-110">ENTSSO</span></span>|  
|<span data-ttu-id="aba55-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aba55-111">Component</span></span>|<span data-ttu-id="aba55-112">なし</span><span class="sxs-lookup"><span data-stu-id="aba55-112">N/A</span></span>|  
|<span data-ttu-id="aba55-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="aba55-113">Symbolic Name</span></span>|<span data-ttu-id="aba55-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span><span class="sxs-lookup"><span data-stu-id="aba55-114">SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC</span></span>|  
|<span data-ttu-id="aba55-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="aba55-115">Message Text</span></span>|<span data-ttu-id="aba55-116">Windows パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="aba55-116">Windows password change.</span></span> <span data-ttu-id="aba55-117">この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。%r</span><span class="sxs-lookup"><span data-stu-id="aba55-117">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.%r</span></span><br /><br /> <span data-ttu-id="aba55-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="aba55-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="aba55-119">Windows アカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="aba55-119">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="aba55-120">アプリケーション: %3 %r</span><span class="sxs-lookup"><span data-stu-id="aba55-120">Application: %3%r</span></span><br /><br /> <span data-ttu-id="aba55-121">アダプター: %4 %r</span><span class="sxs-lookup"><span data-stu-id="aba55-121">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="aba55-122">クライアント ユーザー: %5</span><span class="sxs-lookup"><span data-stu-id="aba55-122">Client User: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aba55-123">説明</span><span class="sxs-lookup"><span data-stu-id="aba55-123">Explanation</span></span>  
 <span data-ttu-id="aba55-124">この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。</span><span class="sxs-lookup"><span data-stu-id="aba55-124">A mapping for this Windows account has been detected but ignored because the adapter configured for this application does not support password sync to external systems.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aba55-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="aba55-125">User Action</span></span>  
 <span data-ttu-id="aba55-126">アダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="aba55-126">Check your adapter configuration.</span></span>  
  
 <span data-ttu-id="aba55-127">パスワード同期については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)です。</span><span class="sxs-lookup"><span data-stu-id="aba55-127">For information on Password Sync, see [Password Synchronization](../core/password-synchronization2.md).</span></span>