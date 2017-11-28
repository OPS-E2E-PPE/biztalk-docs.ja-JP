---
title: "シングル サインオン: イベント 10681 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87ce2e50-cf54-4b23-b247-f137ce64ba1d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0f1b6c27f3e77220d4615da1c0b5bb343344de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10681"></a><span data-ttu-id="dec99-102">シングル サインオン: イベント 10681</span><span class="sxs-lookup"><span data-stu-id="dec99-102">Single Sign-On: Event 10681</span></span>
## <a name="details"></a><span data-ttu-id="dec99-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dec99-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dec99-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dec99-104">Product Name</span></span>|<span data-ttu-id="dec99-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="dec99-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="dec99-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dec99-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="dec99-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dec99-107">Event ID</span></span>|<span data-ttu-id="dec99-108">10681</span><span class="sxs-lookup"><span data-stu-id="dec99-108">10681</span></span>|  
|<span data-ttu-id="dec99-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dec99-109">Event Source</span></span>|<span data-ttu-id="dec99-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="dec99-110">ENTSSO</span></span>|  
|<span data-ttu-id="dec99-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dec99-111">Component</span></span>|<span data-ttu-id="dec99-112">N\A</span><span class="sxs-lookup"><span data-stu-id="dec99-112">N\A</span></span>|  
|<span data-ttu-id="dec99-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dec99-113">Symbolic Name</span></span>|<span data-ttu-id="dec99-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="dec99-114">SSO_WARN_NO_WINDOWS_PASSWORD_CHANGE</span></span>|  
|<span data-ttu-id="dec99-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dec99-115">Message Text</span></span>|<span data-ttu-id="dec99-116">外部パスワードが変更されています。</span><span class="sxs-lookup"><span data-stu-id="dec99-116">External password change.</span></span> <span data-ttu-id="dec99-117">1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードは変更されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="dec99-117">The Windows password was not changed because one or more of the external account changes failed.%r</span></span><br /><br /> <span data-ttu-id="dec99-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="dec99-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="dec99-119">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="dec99-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="dec99-120">Windows アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="dec99-120">Windows Account: %3</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dec99-121">説明</span><span class="sxs-lookup"><span data-stu-id="dec99-121">Explanation</span></span>  
 <span data-ttu-id="dec99-122">この警告イベントは、1 つまたは複数の外部アカウント変更が失敗したため、Windows パスワードが変更されなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="dec99-122">This Warning event indicates that the Windows password was not changed because one or more of the external account changes failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dec99-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dec99-123">User Action</span></span>  
 <span data-ttu-id="dec99-124">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="dec99-124">To resolve this warning, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="dec99-125">システムおよびアプリケーション イベント ログで関連するイベントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dec99-125">Check the System and Application Event logs for associated events.</span></span>  
  
-   <span data-ttu-id="dec99-126">SSO 管理ツールを使用してアダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="dec99-126">Verify adapter configuration using the SSO administration tools.</span></span>  
  
-   <span data-ttu-id="dec99-127">外部システムを確認します。</span><span class="sxs-lookup"><span data-stu-id="dec99-127">Verify external systems.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="dec99-128">詳細</span><span class="sxs-lookup"><span data-stu-id="dec99-128">More info</span></span>
  
-   [<span data-ttu-id="dec99-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="dec99-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   <span data-ttu-id="dec99-130">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="dec99-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>