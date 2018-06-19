---
title: 'シングル サインオン: イベント 10549 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a18eb63-700c-4f49-acc4-890abe2a00ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a59feecdcf5daeef7013dd99eca1e778d49278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270466"
---
# <a name="single-sign-on-event-10549"></a><span data-ttu-id="a6317-102">シングル サインオン: イベント 10549</span><span class="sxs-lookup"><span data-stu-id="a6317-102">Single Sign-On: Event 10549</span></span>
## <a name="details"></a><span data-ttu-id="a6317-103">詳細</span><span class="sxs-lookup"><span data-stu-id="a6317-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6317-104">製品名</span><span class="sxs-lookup"><span data-stu-id="a6317-104">Product Name</span></span>|<span data-ttu-id="a6317-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="a6317-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="a6317-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="a6317-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="a6317-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="a6317-107">Event ID</span></span>|<span data-ttu-id="a6317-108">10549</span><span class="sxs-lookup"><span data-stu-id="a6317-108">10549</span></span>|  
|<span data-ttu-id="a6317-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="a6317-109">Event Source</span></span>|<span data-ttu-id="a6317-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a6317-110">ENTSSO</span></span>|  
|<span data-ttu-id="a6317-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a6317-111">Component</span></span>|<span data-ttu-id="a6317-112">CO</span><span class="sxs-lookup"><span data-stu-id="a6317-112">CO</span></span>|  
|<span data-ttu-id="a6317-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="a6317-113">Symbolic Name</span></span>|<span data-ttu-id="a6317-114">SSO_ERROR_CREATE_DATABASE_FAILED</span><span class="sxs-lookup"><span data-stu-id="a6317-114">SSO_ERROR_CREATE_DATABASE_FAILED</span></span>|  
|<span data-ttu-id="a6317-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="a6317-115">Message Text</span></span>|<span data-ttu-id="a6317-116">SSO データベースを作成および初期化できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="a6317-116">Creation and initialization of the SSO database failed.%r</span></span><br /><br /> <span data-ttu-id="a6317-117">SQL Server 名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="a6317-117">SQL Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="a6317-118">SSO データベース名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="a6317-118">SSO Database Name: %2%r</span></span><br /><br /> <span data-ttu-id="a6317-119">クライアント ユーザー: %3 %r</span><span class="sxs-lookup"><span data-stu-id="a6317-119">Client User: %3%r</span></span><br /><br /> <span data-ttu-id="a6317-120">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="a6317-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a6317-121">説明</span><span class="sxs-lookup"><span data-stu-id="a6317-121">Explanation</span></span>  
 <span data-ttu-id="a6317-122">このエラーは、SSO データベースを作成および初期化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6317-122">This Error indicates that creation and initialization of the SSO database failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6317-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="a6317-123">User Action</span></span>  
 <span data-ttu-id="a6317-124">このエラーを解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="a6317-124">To resolve this error do the following:</span></span>  
  
-   <span data-ttu-id="a6317-125">システムおよびアプリケーションのイベント ログで関連するメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6317-125">Check the system and application event logs for associated messages.</span></span>  
  
-   <span data-ttu-id="a6317-126">セットアップを再実行します。</span><span class="sxs-lookup"><span data-stu-id="a6317-126">Run Setup again.</span></span>  
  
 <span data-ttu-id="a6317-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="a6317-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="a6317-128">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="a6317-128">Installing SSO</span></span>](../core/installing-sso.md)