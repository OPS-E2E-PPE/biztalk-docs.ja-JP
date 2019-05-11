---
title: シングル サインオン:イベント 10569 |Microsoft Docs
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
ms.openlocfilehash: 21e3c6e7650e61af9811cd58542a7a4d2b6204af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398761"
---
# <a name="single-sign-on-event-10569"></a><span data-ttu-id="4a480-102">シングル サインオン:イベント 10569</span><span class="sxs-lookup"><span data-stu-id="4a480-102">Single Sign-On: Event 10569</span></span>
## <a name="details"></a><span data-ttu-id="4a480-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4a480-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4a480-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4a480-104">Product Name</span></span>   |                                                                                       <span data-ttu-id="4a480-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4a480-105">Enterprise Single Sign-On</span></span>                                                                                        |
| <span data-ttu-id="4a480-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4a480-106">Product Version</span></span> |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    <span data-ttu-id="4a480-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4a480-107">Event ID</span></span>     |                                                                                                 <span data-ttu-id="4a480-108">10569</span><span class="sxs-lookup"><span data-stu-id="4a480-108">10569</span></span>                                                                                                  |
|  <span data-ttu-id="4a480-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4a480-109">Event Source</span></span>   |                                                                                                 <span data-ttu-id="4a480-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4a480-110">ENTSSO</span></span>                                                                                                 |
|    <span data-ttu-id="4a480-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4a480-111">Component</span></span>    |                                                                                                  <span data-ttu-id="4a480-112">なし</span><span class="sxs-lookup"><span data-stu-id="4a480-112">N/A</span></span>                                                                                                   |
|  <span data-ttu-id="4a480-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4a480-113">Symbolic Name</span></span>  |                                                                                    <span data-ttu-id="4a480-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span><span class="sxs-lookup"><span data-stu-id="4a480-114">SSO_WARN_NO_UPDATE_BY_APP_ADMIN</span></span>                                                                                     |
|  <span data-ttu-id="4a480-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4a480-115">Message Text</span></span>   | <span data-ttu-id="4a480-116">アプリケーション管理者アカウントは、アプリケーション Administrator.%r 変更ことはできません。</span><span class="sxs-lookup"><span data-stu-id="4a480-116">The Application Administrators account cannot be changed by an Application Administrator.%r</span></span><br /><br /> <span data-ttu-id="4a480-117">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4a480-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="4a480-118">アプリケーション管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="4a480-118">Application Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="4a480-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="4a480-119">Error Code: %3</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4a480-120">説明</span><span class="sxs-lookup"><span data-stu-id="4a480-120">Explanation</span></span>  
 <span data-ttu-id="4a480-121">アプリケーション管理者アカウントには、アプリケーション管理者を変更できません。</span><span class="sxs-lookup"><span data-stu-id="4a480-121">The Application Administrators account cannot be changed by an Application Administrator.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a480-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4a480-122">User Action</span></span>  
 <span data-ttu-id="4a480-123">SSO 関連アプリケーション管理者、またはをアプリケーション管理者アカウントを変更するためにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a480-123">You must be an SSO Affiliate Application Administrator or higher to change the Application Administratos account.</span></span>