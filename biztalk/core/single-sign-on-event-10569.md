---
title: "シングル サインオン: イベント 10569 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f52fe91d7e7ce74d5bdf5766178c12f8c3531aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="d4fbf-102">シングル サインオン: イベント 10569</span><span class="sxs-lookup"><span data-stu-id="d4fbf-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="d4fbf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d4fbf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4fbf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d4fbf-104">Product Name</span></span>|<span data-ttu-id="d4fbf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d4fbf-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d4fbf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d4fbf-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d4fbf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d4fbf-107">Event ID</span></span>|<span data-ttu-id="d4fbf-108">10569</span><span class="sxs-lookup"><span data-stu-id="d4fbf-108">10569</span></span>|  
|<span data-ttu-id="d4fbf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d4fbf-109">Event Source</span></span>|<span data-ttu-id="d4fbf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d4fbf-110">ENTSSO</span></span>|  
|<span data-ttu-id="d4fbf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4fbf-111">Component</span></span>|<span data-ttu-id="d4fbf-112">なし</span><span class="sxs-lookup"><span data-stu-id="d4fbf-112">N/A</span></span>|  
|<span data-ttu-id="d4fbf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d4fbf-113">Symbolic Name</span></span>|<span data-ttu-id="d4fbf-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="d4fbf-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>|  
|<span data-ttu-id="d4fbf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d4fbf-115">Message Text</span></span>|<span data-ttu-id="d4fbf-116">このアプリケーション管理者アカウントを、アプリケーション管理者が変更することはできません。%r</span><span class="sxs-lookup"><span data-stu-id="d4fbf-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="d4fbf-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d4fbf-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="d4fbf-118">アプリケーション管理者: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d4fbf-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="d4fbf-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="d4fbf-119">Error Code: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4fbf-120">説明</span><span class="sxs-lookup"><span data-stu-id="d4fbf-120">Explanation</span></span>  
 <span data-ttu-id="d4fbf-121">このアプリケーション管理者アカウントを、アプリケーション管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4fbf-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4fbf-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d4fbf-122">User Action</span></span>  
 <span data-ttu-id="d4fbf-123">アプリケーション管理者アカウントを変更するには、SSO 関連アプリケーション管理者以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4fbf-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>