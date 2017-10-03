---
title: "トランザクションの要求-応答の受信場所はサポートされていません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34de32b338a78b598941d4e828c1a0b736dde4e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a><span data-ttu-id="fc6f8-102">トランザクションの要求 - 応答の受信場所がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="fc6f8-102">Transactional request-response receive location is not supported</span></span>
## <a name="details"></a><span data-ttu-id="fc6f8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fc6f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc6f8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fc6f8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="fc6f8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fc6f8-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="fc6f8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fc6f8-106">Event ID</span></span>|<span data-ttu-id="fc6f8-107">0</span><span class="sxs-lookup"><span data-stu-id="fc6f8-107">0</span></span>|  
|<span data-ttu-id="fc6f8-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fc6f8-108">Event Source</span></span>|<span data-ttu-id="fc6f8-109">0</span><span class="sxs-lookup"><span data-stu-id="fc6f8-109">0</span></span>|  
|<span data-ttu-id="fc6f8-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fc6f8-110">Component</span></span>|<span data-ttu-id="fc6f8-111">0</span><span class="sxs-lookup"><span data-stu-id="fc6f8-111">0</span></span>|  
|<span data-ttu-id="fc6f8-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fc6f8-112">Symbolic Name</span></span>|<span data-ttu-id="fc6f8-113">0</span><span class="sxs-lookup"><span data-stu-id="fc6f8-113">0</span></span>|  
|<span data-ttu-id="fc6f8-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fc6f8-114">Message Text</span></span>|<span data-ttu-id="fc6f8-115">トランザクションの要求-応答の受信場所がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-115">Transactional request-response receive location is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fc6f8-116">説明</span><span class="sxs-lookup"><span data-stu-id="fc6f8-116">Explanation</span></span>  
 <span data-ttu-id="fc6f8-117">このエラーは、WCF の要求-応答の受信場所について有効になるようにトランザクションが設定されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-117">This error indicates that the transaction was set to be enabled for a WCF request-response receive location.</span></span> <span data-ttu-id="fc6f8-118">要求-応答の受信場所はメッセージ ボックス データベースのため、BizTalk ではトランザクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-118">Transactions are not supported in BizTalk for a request-response receive location due to the message box database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc6f8-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fc6f8-119">User Action</span></span>  
 <span data-ttu-id="fc6f8-120">標準の WCF アダプターの場合、要求-応答の受信場所を構成するコードを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-120">For the standard WCF adapters, go to the code configuring the request-response receive location.</span></span> <span data-ttu-id="fc6f8-121">いることを確認、 **EnableTransaction**用の XML データ内の要素、 **TransportTypeData**のプロパティ、 **ITransportInfo**に設定されているインターフェイス**False**.</span><span class="sxs-lookup"><span data-stu-id="fc6f8-121">Ensure that the **EnableTransaction** element in the XML data for the **TransportTypeData** property of the **ITransportInfo** interface is set to **False**.</span></span>  
  
 <span data-ttu-id="fc6f8-122">WCF-Custom アダプターの場合</span><span class="sxs-lookup"><span data-stu-id="fc6f8-122">For the WCF-Custom adapters:</span></span>  
  
1.  <span data-ttu-id="fc6f8-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fc6f8-124">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="fc6f8-125">アプリケーションを特定し、次にトランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-125">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="fc6f8-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="fc6f8-127">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="fc6f8-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="fc6f8-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="fc6f8-130">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="fc6f8-131">TransactionFlow プロパティに設定されていることを確認**False**です。</span><span class="sxs-lookup"><span data-stu-id="fc6f8-131">Ensure that the transactionFlow property is set to **False**.</span></span>