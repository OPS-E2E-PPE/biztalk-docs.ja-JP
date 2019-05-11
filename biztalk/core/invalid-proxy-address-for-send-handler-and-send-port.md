---
title: 無効なプロキシ アドレス (送信ハンドラーと送信ポート用) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfa5951ed261d3e8bd63811764595d1b7e3858c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330619"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a><span data-ttu-id="b351c-102">(送信ハンドラーと送信ポート) 用の無効なプロキシ アドレス</span><span class="sxs-lookup"><span data-stu-id="b351c-102">Invalid proxy address (for send handler and send port)</span></span>
## <a name="details"></a><span data-ttu-id="b351c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b351c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="b351c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b351c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="b351c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b351c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="b351c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b351c-106">Event ID</span></span>     |                                         <span data-ttu-id="b351c-107">0</span><span class="sxs-lookup"><span data-stu-id="b351c-107">0</span></span>                                          |
|  <span data-ttu-id="b351c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b351c-108">Event Source</span></span>   |                                         <span data-ttu-id="b351c-109">0</span><span class="sxs-lookup"><span data-stu-id="b351c-109">0</span></span>                                          |
|    <span data-ttu-id="b351c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b351c-110">Component</span></span>    |                                         <span data-ttu-id="b351c-111">0</span><span class="sxs-lookup"><span data-stu-id="b351c-111">0</span></span>                                          |
|  <span data-ttu-id="b351c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b351c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="b351c-113">0</span><span class="sxs-lookup"><span data-stu-id="b351c-113">0</span></span>                                          |
|  <span data-ttu-id="b351c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b351c-114">Message Text</span></span>   |                             <span data-ttu-id="b351c-115">無効なプロキシ アドレス: {0}</span><span class="sxs-lookup"><span data-stu-id="b351c-115">Invalid proxy address: {0}</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="b351c-116">説明</span><span class="sxs-lookup"><span data-stu-id="b351c-116">Explanation</span></span>  
 <span data-ttu-id="b351c-117">WCF 送信ハンドラーまたは WCF 送信ポートが有効なプロキシ アドレスでは提供しませんでした。</span><span class="sxs-lookup"><span data-stu-id="b351c-117">You did not provide a WCF send handler or a WCF send port with a valid proxy address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b351c-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b351c-118">User Action</span></span>  
 <span data-ttu-id="b351c-119">プロキシ アドレスを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b351c-119">Use the following procedure to configure a proxy address.</span></span>  
  
#### <a name="to-configure-a-proxy-address"></a><span data-ttu-id="b351c-120">プロキシ アドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="b351c-120">To configure a proxy address</span></span>  
  
1. <span data-ttu-id="b351c-121">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b351c-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b351c-122">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="b351c-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="b351c-123">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="b351c-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="b351c-124">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="b351c-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="b351c-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b351c-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="b351c-126">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b351c-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="b351c-127">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b351c-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="b351c-128">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**プロキシ**タブ。</span><span class="sxs-lookup"><span data-stu-id="b351c-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Proxy** tab.</span></span>  
  
9. <span data-ttu-id="b351c-129">いることを確認でプロキシ アドレス、**プロキシ設定**セクションが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="b351c-129">Verify that the proxy address in the **Proxy settings** section is configured properly.</span></span>  
  
   <span data-ttu-id="b351c-130">送信ポートと送信ハンドラーの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b351c-130">For additional information on send ports and send handlers, see the following resources:</span></span>  
  
-   [<span data-ttu-id="b351c-131">Wcf-wshttp 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b351c-131">How to Configure a WCF-WSHttp Send Port</span></span>](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [<span data-ttu-id="b351c-132">Wcf-basichttp 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b351c-132">How to Configure a WCF-BasicHttp Send Port</span></span>](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [<span data-ttu-id="b351c-133">Wcf-basichttp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b351c-133">How to Configure a WCF-BasicHttp Send Handler</span></span>](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [<span data-ttu-id="b351c-134">Wcf-wshttp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b351c-134">How to Configure a WCF-WSHttp Send Handler</span></span>](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [<span data-ttu-id="b351c-135">Wcf-custom 送信ポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b351c-135">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)