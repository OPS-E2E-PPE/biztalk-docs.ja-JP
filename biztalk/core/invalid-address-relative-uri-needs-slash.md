---
title: アドレスが無効です (相対 uri にスラッシュが必要があります (&quot;-&quot;)) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1376f924-f119-4ba8-9be1-eea7ba5f3eb6
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34b1f5d49bfc34d0498d14ba54c866f2972c9035
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331195"
---
# <a name="invalid-address-relative-uri-needs-slash-quot-quot"></a><span data-ttu-id="bea65-102">アドレスが無効です (相対 uri にスラッシュが必要があります (&quot;-&quot;))</span><span class="sxs-lookup"><span data-stu-id="bea65-102">Invalid address (relative uri needs slash (&quot;-&quot;))</span></span>
## <a name="details"></a><span data-ttu-id="bea65-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bea65-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="bea65-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bea65-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="bea65-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bea65-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="bea65-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bea65-106">Event ID</span></span>     |                                         <span data-ttu-id="bea65-107">0</span><span class="sxs-lookup"><span data-stu-id="bea65-107">0</span></span>                                          |
|  <span data-ttu-id="bea65-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bea65-108">Event Source</span></span>   |                                         <span data-ttu-id="bea65-109">0</span><span class="sxs-lookup"><span data-stu-id="bea65-109">0</span></span>                                          |
|    <span data-ttu-id="bea65-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bea65-110">Component</span></span>    |                                         <span data-ttu-id="bea65-111">0</span><span class="sxs-lookup"><span data-stu-id="bea65-111">0</span></span>                                          |
|  <span data-ttu-id="bea65-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bea65-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="bea65-113">0</span><span class="sxs-lookup"><span data-stu-id="bea65-113">0</span></span>                                          |
|  <span data-ttu-id="bea65-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bea65-114">Message Text</span></span>   |         <span data-ttu-id="bea65-115">アドレスが無効です。スラッシュ (「/」) で始まる相対 uri を指定してください。</span><span class="sxs-lookup"><span data-stu-id="bea65-115">Invalid address; expecting relative uri starting with slash ("/")</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="bea65-116">説明</span><span class="sxs-lookup"><span data-stu-id="bea65-116">Explanation</span></span>  
 <span data-ttu-id="bea65-117">正しい形式の相対アドレスを使用して WCF 分離受信場所が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="bea65-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="bea65-118">たとえば、 http://localhost/svc 相対アドレスとしては機能しません。</span><span class="sxs-lookup"><span data-stu-id="bea65-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="bea65-119">WCF 分離受信場所の "アドレス" プロパティを絶対アドレスに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bea65-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bea65-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bea65-120">User Action</span></span>  
 <span data-ttu-id="bea65-121">アドレスを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bea65-121">Use the following procedure to configure an address.</span></span>  
  
#### <a name="to-configure-an-address"></a><span data-ttu-id="bea65-122">アドレスを構成する</span><span class="sxs-lookup"><span data-stu-id="bea65-122">To configure an address</span></span>  
  
1. <span data-ttu-id="bea65-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="bea65-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bea65-124">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="bea65-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="bea65-125">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="bea65-125">Locate your application and locate your transport.</span></span>  
  
4. <span data-ttu-id="bea65-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="bea65-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="bea65-127">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bea65-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="bea65-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="bea65-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="bea65-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="bea65-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="bea65-130">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="bea65-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="bea65-131">**アドレス (URI)** テキスト ボックスに、アドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="bea65-131">In the **Address (URI)** text box, change the address.</span></span> <span data-ttu-id="bea65-132">整形式の相対アドレスの例は、/path/service.svc です。</span><span class="sxs-lookup"><span data-stu-id="bea65-132">An example of a well-formed relative address is /path/service.svc.</span></span>  
  
   <span data-ttu-id="bea65-133">詳細については受信場所は次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea65-133">For additional information on receive locations, see the following:</span></span>  
  
-   [<span data-ttu-id="bea65-134">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="bea65-134">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="bea65-135">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="bea65-135">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="bea65-136">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="bea65-136">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)