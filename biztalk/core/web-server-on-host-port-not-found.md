---
title: Web サーバーが見つかりませんホスト ポート |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987147"
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="cad5f-102">ホスト ポートの Web サーバーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="cad5f-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="cad5f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cad5f-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="cad5f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cad5f-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="cad5f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cad5f-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="cad5f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cad5f-106">Event ID</span></span>     |                                         <span data-ttu-id="cad5f-107">0</span><span class="sxs-lookup"><span data-stu-id="cad5f-107">0</span></span>                                          |
|  <span data-ttu-id="cad5f-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cad5f-108">Event Source</span></span>   |                                         <span data-ttu-id="cad5f-109">0</span><span class="sxs-lookup"><span data-stu-id="cad5f-109">0</span></span>                                          |
|    <span data-ttu-id="cad5f-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cad5f-110">Component</span></span>    |                                         <span data-ttu-id="cad5f-111">0</span><span class="sxs-lookup"><span data-stu-id="cad5f-111">0</span></span>                                          |
|  <span data-ttu-id="cad5f-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cad5f-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="cad5f-113">0</span><span class="sxs-lookup"><span data-stu-id="cad5f-113">0</span></span>                                          |
|  <span data-ttu-id="cad5f-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cad5f-114">Message Text</span></span>   |                    <span data-ttu-id="cad5f-115">ホスト上の web サーバー"{0}"ポート{1}が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="cad5f-115">Web server on host "{0}" port {1} not found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="cad5f-116">説明</span><span class="sxs-lookup"><span data-stu-id="cad5f-116">Explanation</span></span>  
 <span data-ttu-id="cad5f-117">このエラーは、World Wide Web (WWW) サービスが実行されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cad5f-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cad5f-118">User Action</span></span>  
 <span data-ttu-id="cad5f-119">World Wide Web サービスを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cad5f-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="cad5f-120">World Wide Web サービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="cad5f-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="cad5f-121">クリックして**開始**、 をクリックして**コントロール パネルの **、 をダブルクリックします**管理ツール**、 をダブルクリックします**サービス。**</span><span class="sxs-lookup"><span data-stu-id="cad5f-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="cad5f-122">[名前] 列で検索**World Wide Web 発行**します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="cad5f-123">状態があることを確認**開始**します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="cad5f-124">戻り、**管理ツール**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cad5f-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="cad5f-125">ダブルクリック**インターネット インフォメーション サービス**します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="cad5f-126">フォルダー領域を展開し、Web サイトを探します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="cad5f-127">状態があることを確認**開始**します。</span><span class="sxs-lookup"><span data-stu-id="cad5f-127">Ensure that the status is **Started**.</span></span>