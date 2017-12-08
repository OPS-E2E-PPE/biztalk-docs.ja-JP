---
title: "トランザクション プロトコルをサポートされていません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11fb2497-9971-4e85-b21a-161734f071e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e000c706ca438494f8b07e8ce5dba24cb4f46bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unsupported-transaction-protocol"></a><span data-ttu-id="01d47-102">トランザクション プロトコルがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="01d47-102">Unsupported transaction protocol</span></span>
## <a name="details"></a><span data-ttu-id="01d47-103">詳細</span><span class="sxs-lookup"><span data-stu-id="01d47-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01d47-104">製品名</span><span class="sxs-lookup"><span data-stu-id="01d47-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="01d47-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="01d47-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="01d47-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="01d47-106">Event ID</span></span>|<span data-ttu-id="01d47-107">0</span><span class="sxs-lookup"><span data-stu-id="01d47-107">0</span></span>|  
|<span data-ttu-id="01d47-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="01d47-108">Event Source</span></span>|<span data-ttu-id="01d47-109">0</span><span class="sxs-lookup"><span data-stu-id="01d47-109">0</span></span>|  
|<span data-ttu-id="01d47-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="01d47-110">Component</span></span>|<span data-ttu-id="01d47-111">0</span><span class="sxs-lookup"><span data-stu-id="01d47-111">0</span></span>|  
|<span data-ttu-id="01d47-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="01d47-112">Symbolic Name</span></span>|<span data-ttu-id="01d47-113">0</span><span class="sxs-lookup"><span data-stu-id="01d47-113">0</span></span>|  
|<span data-ttu-id="01d47-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="01d47-114">Message Text</span></span>|<span data-ttu-id="01d47-115">トランザクション プロトコルをサポートされていません: {0}</span><span class="sxs-lookup"><span data-stu-id="01d47-115">Unsupported transaction protocol: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01d47-116">説明</span><span class="sxs-lookup"><span data-stu-id="01d47-116">Explanation</span></span>  
 <span data-ttu-id="01d47-117">このエラーは、受信場所または送信ポートのトランザクション プロトコル プロパティが無効な値に設定されているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="01d47-117">This error occurs when the transaction protocol property of a receive location or send port is set to an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01d47-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="01d47-118">User Action</span></span>  
 <span data-ttu-id="01d47-119">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="01d47-119">To resolve this error, do one or more of the following:</span></span>  
  
1.  <span data-ttu-id="01d47-120">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="01d47-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="01d47-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="01d47-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="01d47-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="01d47-122">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="01d47-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="01d47-123">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="01d47-124">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01d47-124">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="01d47-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="01d47-125">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="01d47-126">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="01d47-126">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="01d47-127">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="01d47-127">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="01d47-128">**トランザクション**セクションで、選択、**トランザクションを有効にする**オプション。</span><span class="sxs-lookup"><span data-stu-id="01d47-128">In the **Transactions** section, choose the **Enable transactions** option.</span></span>  
  
10. <span data-ttu-id="01d47-129">**トランザクション プロトコル**ドロップダウン リストで、いずれかを選択**OleTransactions**または**[wsatomictransactions]**です。</span><span class="sxs-lookup"><span data-stu-id="01d47-129">In the **Transactions protocol** drop-down list, choose either **OleTransactions** or **WSAtomicTransactions**.</span></span>  
  
 <span data-ttu-id="01d47-130">これらの手順が適用されるのは、次のトランスポートの種類のみです。</span><span class="sxs-lookup"><span data-stu-id="01d47-130">These steps only apply to the following transport types:</span></span>  
  
-   <span data-ttu-id="01d47-131">Custom</span><span class="sxs-lookup"><span data-stu-id="01d47-131">Custom</span></span>  
  
-   <span data-ttu-id="01d47-132">CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="01d47-132">CustomIsolated</span></span>  
  
-   <span data-ttu-id="01d47-133">NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="01d47-133">NetNamedPipe</span></span>  
  
-   <span data-ttu-id="01d47-134">NetTcp</span><span class="sxs-lookup"><span data-stu-id="01d47-134">NetTcp</span></span>  
  
-   <span data-ttu-id="01d47-135">WShttp</span><span class="sxs-lookup"><span data-stu-id="01d47-135">WShttp</span></span>