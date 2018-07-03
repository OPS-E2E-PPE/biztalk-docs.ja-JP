---
title: 'シングル サインオン: イベント 10569 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25665947921bb316a4d931228016eaf917b4a685
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987203"
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="dfa6d-102">シングル サインオン: イベント 10569</span><span class="sxs-lookup"><span data-stu-id="dfa6d-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="dfa6d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dfa6d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dfa6d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dfa6d-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="dfa6d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="dfa6d-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="dfa6d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dfa6d-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="dfa6d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dfa6d-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="dfa6d-108">10569</span><span class="sxs-lookup"><span data-stu-id="dfa6d-108">10569</span></span>                                                                                                  |
|  <span data-ttu-id="dfa6d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dfa6d-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="dfa6d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dfa6d-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="dfa6d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dfa6d-111">Component</span></span>    |                                                                                                  <span data-ttu-id="dfa6d-112">なし</span><span class="sxs-lookup"><span data-stu-id="dfa6d-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="dfa6d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dfa6d-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="dfa6d-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="dfa6d-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>                                                                                     |
|  <span data-ttu-id="dfa6d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dfa6d-115">Message Text</span></span>   | <span data-ttu-id="dfa6d-116">このアプリケーション管理者アカウントを、アプリケーション管理者が変更することはできません。%r</span><span class="sxs-lookup"><span data-stu-id="dfa6d-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="dfa6d-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="dfa6d-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="dfa6d-118">アプリケーション管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="dfa6d-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="dfa6d-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="dfa6d-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dfa6d-120">説明</span><span class="sxs-lookup"><span data-stu-id="dfa6d-120">Explanation</span></span>  
 <span data-ttu-id="dfa6d-121">このアプリケーション管理者アカウントを、アプリケーション管理者が変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="dfa6d-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfa6d-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dfa6d-122">User Action</span></span>  
 <span data-ttu-id="dfa6d-123">アプリケーション管理者アカウントを変更するには、SSO 関連アプリケーション管理者以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfa6d-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>