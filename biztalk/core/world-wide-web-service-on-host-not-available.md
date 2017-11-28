---
title: "使用できないホスト上の World Wide Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b14eaae-2158-4aef-9561-610d033998be
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ff3196501fe4192b7b7826a0611be9cf7644098
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="0c94e-102">ホストの World Wide Web サービスを使用できません</span><span class="sxs-lookup"><span data-stu-id="0c94e-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="0c94e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0c94e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c94e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0c94e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0c94e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0c94e-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="0c94e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0c94e-106">Event ID</span></span>|<span data-ttu-id="0c94e-107">0</span><span class="sxs-lookup"><span data-stu-id="0c94e-107">0</span></span>|  
|<span data-ttu-id="0c94e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0c94e-108">Event Source</span></span>|<span data-ttu-id="0c94e-109">0</span><span class="sxs-lookup"><span data-stu-id="0c94e-109">0</span></span>|  
|<span data-ttu-id="0c94e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0c94e-110">Component</span></span>|<span data-ttu-id="0c94e-111">0</span><span class="sxs-lookup"><span data-stu-id="0c94e-111">0</span></span>|  
|<span data-ttu-id="0c94e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0c94e-112">Symbolic Name</span></span>|<span data-ttu-id="0c94e-113">0</span><span class="sxs-lookup"><span data-stu-id="0c94e-113">0</span></span>|  
|<span data-ttu-id="0c94e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0c94e-114">Message Text</span></span>|<span data-ttu-id="0c94e-115">ホスト "{0}" の World Wide Web サービス (W3SVC) を使用できません</span><span class="sxs-lookup"><span data-stu-id="0c94e-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c94e-116">説明</span><span class="sxs-lookup"><span data-stu-id="0c94e-116">Explanation</span></span>  
 <span data-ttu-id="0c94e-117">このエラーは、World Wide Web サービスが実行されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="0c94e-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c94e-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0c94e-118">User Action</span></span>  
 <span data-ttu-id="0c94e-119">World Wide Web サービスを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0c94e-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="0c94e-120">World Wide Web サービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="0c94e-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="0c94e-121">をクリックして**開始**、 をクリックして**コントロール パネル**をダブルクリックして**管理ツール**、 をダブルクリック**サービス**です。</span><span class="sxs-lookup"><span data-stu-id="0c94e-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="0c94e-122">[名前] 列で探します**World Wide Web Publishing**です。</span><span class="sxs-lookup"><span data-stu-id="0c94e-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="0c94e-123">状態があることを確認してください。 **Started**です。</span><span class="sxs-lookup"><span data-stu-id="0c94e-123">Ensure that the status is **Started**.</span></span>