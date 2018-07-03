---
title: トランザクション プロトコルがサポートされていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11fb2497-9971-4e85-b21a-161734f071e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dde6df3360a7b4581964f26e395448d15f3de73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022360"
---
# <a name="unsupported-transaction-protocol"></a><span data-ttu-id="c67f7-102">トランザクション プロトコルがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="c67f7-102">Unsupported transaction protocol</span></span>
## <a name="details"></a><span data-ttu-id="c67f7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c67f7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="c67f7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c67f7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="c67f7-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c67f7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="c67f7-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c67f7-106">Event ID</span></span>     |                                         <span data-ttu-id="c67f7-107">0</span><span class="sxs-lookup"><span data-stu-id="c67f7-107">0</span></span>                                          |
|  <span data-ttu-id="c67f7-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c67f7-108">Event Source</span></span>   |                                         <span data-ttu-id="c67f7-109">0</span><span class="sxs-lookup"><span data-stu-id="c67f7-109">0</span></span>                                          |
|    <span data-ttu-id="c67f7-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c67f7-110">Component</span></span>    |                                         <span data-ttu-id="c67f7-111">0</span><span class="sxs-lookup"><span data-stu-id="c67f7-111">0</span></span>                                          |
|  <span data-ttu-id="c67f7-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c67f7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="c67f7-113">0</span><span class="sxs-lookup"><span data-stu-id="c67f7-113">0</span></span>                                          |
|  <span data-ttu-id="c67f7-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c67f7-114">Message Text</span></span>   |                       <span data-ttu-id="c67f7-115">サポートされていないトランザクション プロトコル: {0}</span><span class="sxs-lookup"><span data-stu-id="c67f7-115">Unsupported transaction protocol: {0}</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="c67f7-116">説明</span><span class="sxs-lookup"><span data-stu-id="c67f7-116">Explanation</span></span>  
 <span data-ttu-id="c67f7-117">このエラーは、受信場所または送信ポートのトランザクション プロトコル プロパティが無効な値に設定されているときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-117">This error occurs when the transaction protocol property of a receive location or send port is set to an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c67f7-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c67f7-118">User Action</span></span>  
 <span data-ttu-id="c67f7-119">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-119">To resolve this error, do one or more of the following:</span></span>  
  
1. <span data-ttu-id="c67f7-120">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="c67f7-121">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="c67f7-122">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="c67f7-123">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c67f7-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="c67f7-124">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c67f7-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="c67f7-125">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="c67f7-126">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="c67f7-127">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="c67f7-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="c67f7-128">**トランザクション**セクションで、選択、**トランザクションを有効にする**オプション。</span><span class="sxs-lookup"><span data-stu-id="c67f7-128">In the **Transactions** section, choose the **Enable transactions** option.</span></span>  
  
10. <span data-ttu-id="c67f7-129">**トランザクション プロトコル**ドロップダウン リストで、いずれかを選択**OleTransactions**または **[wsatomictransactions]** します。</span><span class="sxs-lookup"><span data-stu-id="c67f7-129">In the **Transactions protocol** drop-down list, choose either **OleTransactions** or **WSAtomicTransactions**.</span></span>  
  
    <span data-ttu-id="c67f7-130">これらの手順が適用されるのは、次のトランスポートの種類のみです。</span><span class="sxs-lookup"><span data-stu-id="c67f7-130">These steps only apply to the following transport types:</span></span>  
  
-   <span data-ttu-id="c67f7-131">Custom</span><span class="sxs-lookup"><span data-stu-id="c67f7-131">Custom</span></span>  
  
-   <span data-ttu-id="c67f7-132">CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="c67f7-132">CustomIsolated</span></span>  
  
-   <span data-ttu-id="c67f7-133">NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="c67f7-133">NetNamedPipe</span></span>  
  
-   <span data-ttu-id="c67f7-134">NetTcp</span><span class="sxs-lookup"><span data-stu-id="c67f7-134">NetTcp</span></span>  
  
-   <span data-ttu-id="c67f7-135">WShttp</span><span class="sxs-lookup"><span data-stu-id="c67f7-135">WShttp</span></span>