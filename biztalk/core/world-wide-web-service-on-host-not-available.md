---
title: 使用できないホスト上の World Wide Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b14eaae-2158-4aef-9561-610d033998be
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad2616191dc146774c9b3d90664322992bb753d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302329"
---
# <a name="world-wide-web-service-on-host-not-available"></a><span data-ttu-id="bb750-102">ホストの World Wide Web サービスを使用できません</span><span class="sxs-lookup"><span data-stu-id="bb750-102">World Wide Web service on host not available</span></span>
## <a name="details"></a><span data-ttu-id="bb750-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bb750-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="bb750-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bb750-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="bb750-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bb750-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="bb750-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bb750-106">Event ID</span></span>     |                                         <span data-ttu-id="bb750-107">0</span><span class="sxs-lookup"><span data-stu-id="bb750-107">0</span></span>                                          |
|  <span data-ttu-id="bb750-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bb750-108">Event Source</span></span>   |                                         <span data-ttu-id="bb750-109">0</span><span class="sxs-lookup"><span data-stu-id="bb750-109">0</span></span>                                          |
|    <span data-ttu-id="bb750-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb750-110">Component</span></span>    |                                         <span data-ttu-id="bb750-111">0</span><span class="sxs-lookup"><span data-stu-id="bb750-111">0</span></span>                                          |
|  <span data-ttu-id="bb750-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bb750-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="bb750-113">0</span><span class="sxs-lookup"><span data-stu-id="bb750-113">0</span></span>                                          |
|  <span data-ttu-id="bb750-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bb750-114">Message Text</span></span>   |             <span data-ttu-id="bb750-115">ホスト上の World Wide Web サービス (W3SVC)"{0}"利用できません</span><span class="sxs-lookup"><span data-stu-id="bb750-115">World Wide Web service (W3SVC) on host "{0}" not available</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="bb750-116">説明</span><span class="sxs-lookup"><span data-stu-id="bb750-116">Explanation</span></span>  
 <span data-ttu-id="bb750-117">このエラーは、World Wide Web サービスが実行されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bb750-117">This error indicates the World Wide Web service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb750-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bb750-118">User Action</span></span>  
 <span data-ttu-id="bb750-119">World Wide Web サービスを開始するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb750-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="bb750-120">World Wide Web サービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="bb750-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="bb750-121">をクリックして**開始**、 をクリックして**コントロール パネルの **、 をダブルクリックします**管理ツール**、 をダブルクリックします**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="bb750-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services**.</span></span>  
  
2.  <span data-ttu-id="bb750-122">[名前] 列で検索**World Wide Web 発行**します。</span><span class="sxs-lookup"><span data-stu-id="bb750-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="bb750-123">状態があることを確認**開始**します。</span><span class="sxs-lookup"><span data-stu-id="bb750-123">Ensure that the status is **Started**.</span></span>