---
title: "Web ポートでサーバーにホストが見つかりません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dce09ce00a169ad14bbc8ae2ab28fe70c039c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="8f307-102">ホスト ポートの Web サーバーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="8f307-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="8f307-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8f307-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f307-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8f307-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8f307-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8f307-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="8f307-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8f307-106">Event ID</span></span>|<span data-ttu-id="8f307-107">0</span><span class="sxs-lookup"><span data-stu-id="8f307-107">0</span></span>|  
|<span data-ttu-id="8f307-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8f307-108">Event Source</span></span>|<span data-ttu-id="8f307-109">0</span><span class="sxs-lookup"><span data-stu-id="8f307-109">0</span></span>|  
|<span data-ttu-id="8f307-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8f307-110">Component</span></span>|<span data-ttu-id="8f307-111">0</span><span class="sxs-lookup"><span data-stu-id="8f307-111">0</span></span>|  
|<span data-ttu-id="8f307-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8f307-112">Symbolic Name</span></span>|<span data-ttu-id="8f307-113">0</span><span class="sxs-lookup"><span data-stu-id="8f307-113">0</span></span>|  
|<span data-ttu-id="8f307-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8f307-114">Message Text</span></span>|<span data-ttu-id="8f307-115">見つかりません。"{0}"ホスト ポート {1} 上の web サーバー</span><span class="sxs-lookup"><span data-stu-id="8f307-115">Web server on host "{0}" port {1} not found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f307-116">説明</span><span class="sxs-lookup"><span data-stu-id="8f307-116">Explanation</span></span>  
 <span data-ttu-id="8f307-117">このエラーは、World Wide Web (WWW) サービスが実行されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="8f307-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f307-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8f307-118">User Action</span></span>  
 <span data-ttu-id="8f307-119">World Wide Web サービスを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8f307-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="8f307-120">World Wide Web サービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="8f307-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="8f307-121">をクリックして**開始**、 をクリックして**コントロール パネル**をダブルクリックして**管理ツール**、 をダブルクリック**サービス。**</span><span class="sxs-lookup"><span data-stu-id="8f307-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="8f307-122">[名前] 列で探します**World Wide Web Publishing**です。</span><span class="sxs-lookup"><span data-stu-id="8f307-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="8f307-123">状態があることを確認してください。 **Started**です。</span><span class="sxs-lookup"><span data-stu-id="8f307-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="8f307-124">戻り、**管理ツール**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="8f307-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="8f307-125">ダブルクリックして**インターネット インフォメーション サービス**です。</span><span class="sxs-lookup"><span data-stu-id="8f307-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="8f307-126">フォルダー領域を展開し、Web サイトを探します。</span><span class="sxs-lookup"><span data-stu-id="8f307-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="8f307-127">状態があることを確認してください。 **Started**です。</span><span class="sxs-lookup"><span data-stu-id="8f307-127">Ensure that the status is **Started**.</span></span>