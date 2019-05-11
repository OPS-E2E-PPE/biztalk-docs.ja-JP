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
ms.openlocfilehash: adad9ab9e2e5bbe3a23401a4c893a8d581b6c742
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250147"
---
# <a name="web-server-on-host-port-not-found"></a><span data-ttu-id="6fbfd-102">ホスト ポートの Web サーバーが見つかりません</span><span class="sxs-lookup"><span data-stu-id="6fbfd-102">Web server on host port not found</span></span>
## <a name="details"></a><span data-ttu-id="6fbfd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6fbfd-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6fbfd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6fbfd-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6fbfd-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6fbfd-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6fbfd-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6fbfd-106">Event ID</span></span>     |                                         <span data-ttu-id="6fbfd-107">0</span><span class="sxs-lookup"><span data-stu-id="6fbfd-107">0</span></span>                                          |
|  <span data-ttu-id="6fbfd-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6fbfd-108">Event Source</span></span>   |                                         <span data-ttu-id="6fbfd-109">0</span><span class="sxs-lookup"><span data-stu-id="6fbfd-109">0</span></span>                                          |
|    <span data-ttu-id="6fbfd-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6fbfd-110">Component</span></span>    |                                         <span data-ttu-id="6fbfd-111">0</span><span class="sxs-lookup"><span data-stu-id="6fbfd-111">0</span></span>                                          |
|  <span data-ttu-id="6fbfd-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6fbfd-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6fbfd-113">0</span><span class="sxs-lookup"><span data-stu-id="6fbfd-113">0</span></span>                                          |
|  <span data-ttu-id="6fbfd-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6fbfd-114">Message Text</span></span>   |                    <span data-ttu-id="6fbfd-115">ホスト上の web サーバー"{0}"ポート{1}が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-115">Web server on host "{0}" port {1} not found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="6fbfd-116">説明</span><span class="sxs-lookup"><span data-stu-id="6fbfd-116">Explanation</span></span>  
 <span data-ttu-id="6fbfd-117">このエラーは、World Wide Web (WWW) サービスが実行されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-117">This error indicates the World Wide Web (WWW) service is not running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fbfd-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6fbfd-118">User Action</span></span>  
 <span data-ttu-id="6fbfd-119">World Wide Web サービスを開始するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-119">Use the following procedure to start the World Wide Web service.</span></span>  
  
#### <a name="to-start-the-world-wide-web-service"></a><span data-ttu-id="6fbfd-120">World Wide Web サービスを開始するには</span><span class="sxs-lookup"><span data-stu-id="6fbfd-120">To start the World Wide Web service</span></span>  
  
1.  <span data-ttu-id="6fbfd-121">クリックして**開始**、 をクリックして**コントロール パネルの **、 をダブルクリックします**管理ツール**、 をダブルクリックします**サービス。**</span><span class="sxs-lookup"><span data-stu-id="6fbfd-121">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, and double-click **Services.**</span></span>  
  
2.  <span data-ttu-id="6fbfd-122">[名前] 列で検索**World Wide Web 発行**します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-122">In the Name column, locate **World Wide Web Publishing**.</span></span> <span data-ttu-id="6fbfd-123">状態があることを確認**開始**します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-123">Ensure that the status is **Started**.</span></span>  
  
3.  <span data-ttu-id="6fbfd-124">戻り、**管理ツール**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-124">Return to the **Administrative Tools** window.</span></span> <span data-ttu-id="6fbfd-125">ダブルクリック**インターネット インフォメーション サービス**します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-125">Double-click **Internet Information Services**.</span></span>  
  
4.  <span data-ttu-id="6fbfd-126">フォルダーの領域を展開し、web サイトを探します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-126">Expand the folder area and locate the web site.</span></span>  
  
5.  <span data-ttu-id="6fbfd-127">状態があることを確認**開始**します。</span><span class="sxs-lookup"><span data-stu-id="6fbfd-127">Ensure that the status is **Started**.</span></span>