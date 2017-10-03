---
title: "シングル サインオン: イベント 10745 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="d1ff0-102">シングル サインオン: イベント 10745</span><span class="sxs-lookup"><span data-stu-id="d1ff0-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="d1ff0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d1ff0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1ff0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d1ff0-104">Product Name</span></span>|<span data-ttu-id="d1ff0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d1ff0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d1ff0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d1ff0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d1ff0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d1ff0-107">Event ID</span></span>|<span data-ttu-id="d1ff0-108">10745</span><span class="sxs-lookup"><span data-stu-id="d1ff0-108">10745</span></span>|  
|<span data-ttu-id="d1ff0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d1ff0-109">Event Source</span></span>|<span data-ttu-id="d1ff0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d1ff0-110">ENTSSO</span></span>|  
|<span data-ttu-id="d1ff0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d1ff0-111">Component</span></span>|<span data-ttu-id="d1ff0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d1ff0-112">N\A</span></span>|  
|<span data-ttu-id="d1ff0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d1ff0-113">Symbolic Name</span></span>|<span data-ttu-id="d1ff0-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="d1ff0-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>|  
|<span data-ttu-id="d1ff0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d1ff0-115">Message Text</span></span>|<span data-ttu-id="d1ff0-116">アダプターがオフラインです。%r</span><span class="sxs-lookup"><span data-stu-id="d1ff0-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="d1ff0-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d1ff0-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d1ff0-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d1ff0-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d1ff0-119">エラー メッセージ: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d1ff0-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="d1ff0-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="d1ff0-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1ff0-121">説明</span><span class="sxs-lookup"><span data-stu-id="d1ff0-121">Explanation</span></span>  
 <span data-ttu-id="d1ff0-122">このエラー イベントは、指定されたアダプターがオフラインであることを示します。</span><span class="sxs-lookup"><span data-stu-id="d1ff0-122">This Error event indicates that the specified adapter is offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1ff0-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d1ff0-123">User Action</span></span>  
 <span data-ttu-id="d1ff0-124">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1ff0-124">To resolve this error, do one or more of the following:</span></span>  
  
-   <span data-ttu-id="d1ff0-125">関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1ff0-125">Check the system and application event logs for associated errors.</span></span>  
  
-   <span data-ttu-id="d1ff0-126">外部アダプターでエラーを調べます。</span><span class="sxs-lookup"><span data-stu-id="d1ff0-126">Check the external adapter for errors.</span></span>  
  
 <span data-ttu-id="d1ff0-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ff0-127">For more information, see the following resources:</span></span>  
  
-   [<span data-ttu-id="d1ff0-128">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="d1ff0-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)