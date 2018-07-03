---
title: 'シングル サインオン: イベント 10674 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97f67258bb1ee9118c6f462d0eded4b8f238707b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996131"
---
# <a name="single-sign-on-event-10674"></a><span data-ttu-id="fd48b-102">シングル サインオン: イベント 10674</span><span class="sxs-lookup"><span data-stu-id="fd48b-102">Single Sign-On: Event 10674</span></span>
## <a name="details"></a><span data-ttu-id="fd48b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fd48b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fd48b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fd48b-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="fd48b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fd48b-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="fd48b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fd48b-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="fd48b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fd48b-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="fd48b-108">10674</span><span class="sxs-lookup"><span data-stu-id="fd48b-108">10674</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="fd48b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fd48b-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="fd48b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fd48b-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="fd48b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fd48b-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="fd48b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="fd48b-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="fd48b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fd48b-113">Symbolic Name</span></span>  |                                                                                                                                                                        <span data-ttu-id="fd48b-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="fd48b-114">SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED</span></span>                                                                                                                                                                        |
|  <span data-ttu-id="fd48b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fd48b-115">Message Text</span></span>   | <span data-ttu-id="fd48b-116">外部パスワード変更によって、複数の Windows アカウントを変更しようとしました。%r</span><span class="sxs-lookup"><span data-stu-id="fd48b-116">An external password change would have caused changes to more than one Windows account.%r</span></span><br /><br /> <span data-ttu-id="fd48b-117">この外部システムのアダプターは、マッピングの競合を許可しないよう構成されているため、実行できません。%r</span><span class="sxs-lookup"><span data-stu-id="fd48b-117">This has been prevented because the adapter for this external system is configured to not allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="fd48b-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fd48b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="fd48b-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="fd48b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="fd48b-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="fd48b-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="fd48b-121">Windows アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="fd48b-121">Windows Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="fd48b-122">Windows アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="fd48b-122">Windows Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="fd48b-123">説明</span><span class="sxs-lookup"><span data-stu-id="fd48b-123">Explanation</span></span>  
 <span data-ttu-id="fd48b-124">この警告イベントは、外部パスワード変更によって、複数の Windows アカウントを変更しようとしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fd48b-124">This Warning event indicates that an external password change would have caused changes to more than one Windows account.</span></span> <span data-ttu-id="fd48b-125">アダプター構成で許可されないため、この変更を実行できません。</span><span class="sxs-lookup"><span data-stu-id="fd48b-125">This change was prevented because the adapter configuration would not allow it.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fd48b-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fd48b-126">User Action</span></span>  
 <span data-ttu-id="fd48b-127">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd48b-127">To resolve this error, do the following:</span></span>  

-   <span data-ttu-id="fd48b-128">マッピングの競合が予想され、許可される場合、は、SSO 管理ツールを使用して、構成する、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="fd48b-128">If mapping conflicts are expected and allowed, use the SSO Admin tools to configure the **Allow Mapping Conflicts** property for the Password Sync Adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="fd48b-129">詳細</span><span class="sxs-lookup"><span data-stu-id="fd48b-129">More info</span></span>

- <span data-ttu-id="fd48b-130">**パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="fd48b-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="fd48b-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="fd48b-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
