---
title: トランザクションの要求-応答の受信場所はサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37cea795e097596862e14f64b825696511ffbe6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399199"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a><span data-ttu-id="acbd0-102">トランザクションの要求 - 応答の受信場所がサポートされていません</span><span class="sxs-lookup"><span data-stu-id="acbd0-102">Transactional request-response receive location is not supported</span></span>
## <a name="details"></a><span data-ttu-id="acbd0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="acbd0-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="acbd0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="acbd0-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="acbd0-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="acbd0-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="acbd0-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="acbd0-106">Event ID</span></span>     |                                         <span data-ttu-id="acbd0-107">0</span><span class="sxs-lookup"><span data-stu-id="acbd0-107">0</span></span>                                          |
|  <span data-ttu-id="acbd0-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="acbd0-108">Event Source</span></span>   |                                         <span data-ttu-id="acbd0-109">0</span><span class="sxs-lookup"><span data-stu-id="acbd0-109">0</span></span>                                          |
|    <span data-ttu-id="acbd0-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="acbd0-110">Component</span></span>    |                                         <span data-ttu-id="acbd0-111">0</span><span class="sxs-lookup"><span data-stu-id="acbd0-111">0</span></span>                                          |
|  <span data-ttu-id="acbd0-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="acbd0-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="acbd0-113">0</span><span class="sxs-lookup"><span data-stu-id="acbd0-113">0</span></span>                                          |
|  <span data-ttu-id="acbd0-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="acbd0-114">Message Text</span></span>   |         <span data-ttu-id="acbd0-115">トランザクションの要求-応答の受信場所はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="acbd0-115">Transactional request-response receive location is not supported.</span></span>          |

## <a name="explanation"></a><span data-ttu-id="acbd0-116">説明</span><span class="sxs-lookup"><span data-stu-id="acbd0-116">Explanation</span></span>  
 <span data-ttu-id="acbd0-117">このエラーは、WCF 要求-応答の受信場所用に有効にするトランザクションが設定されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-117">This error indicates that the transaction was set to be enabled for a WCF request-response receive location.</span></span> <span data-ttu-id="acbd0-118">トランザクションは、要求-応答の受信、メッセージ ボックス データベースのための場所の BizTalk ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="acbd0-118">Transactions are not supported in BizTalk for a request-response receive location due to the message box database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="acbd0-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="acbd0-119">User Action</span></span>  
 <span data-ttu-id="acbd0-120">標準の WCF アダプターの要求-応答を構成するコードに移動して受信場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-120">For the standard WCF adapters, go to the code configuring the request-response receive location.</span></span> <span data-ttu-id="acbd0-121">いることを確認、 **EnableTransaction**用の XML データ内の要素、 **TransportTypeData**のプロパティ、 **ITransportInfo**に設定されているインターフェイス**False**.</span><span class="sxs-lookup"><span data-stu-id="acbd0-121">Ensure that the **EnableTransaction** element in the XML data for the **TransportTypeData** property of the **ITransportInfo** interface is set to **False**.</span></span>  

 <span data-ttu-id="acbd0-122">Wcf-custom アダプター。</span><span class="sxs-lookup"><span data-stu-id="acbd0-122">For the WCF-Custom adapters:</span></span>  

1. <span data-ttu-id="acbd0-123">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="acbd0-124">コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="acbd0-125">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-125">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="acbd0-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="acbd0-126">Right-click the transport name.</span></span>  

5. <span data-ttu-id="acbd0-127">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="acbd0-127">Click **Properties**.</span></span>  

6. <span data-ttu-id="acbd0-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-128">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="acbd0-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="acbd0-129">Click **Configure**.</span></span>  

8. <span data-ttu-id="acbd0-130">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="acbd0-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="acbd0-131">TransactionFlow プロパティに設定されるように**False**します。</span><span class="sxs-lookup"><span data-stu-id="acbd0-131">Ensure that the transactionFlow property is set to **False**.</span></span>
