---
title: アドレスが無効です (相対 uri) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a953f3e-3768-4e61-8f25-ea958a5a701a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ec013447c0703a9f36469b5d6b452f82c91d8b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381457"
---
# <a name="invalid-address-relative-uri"></a><span data-ttu-id="0763d-102">アドレスが無効です (相対 URI)</span><span class="sxs-lookup"><span data-stu-id="0763d-102">Invalid address (relative uri)</span></span>
## <a name="details"></a><span data-ttu-id="0763d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0763d-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="0763d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0763d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="0763d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0763d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="0763d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0763d-106">Event ID</span></span>     |                                        <span data-ttu-id="0763d-107">000</span><span class="sxs-lookup"><span data-stu-id="0763d-107">000</span></span>                                         |
|  <span data-ttu-id="0763d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0763d-108">Event Source</span></span>   |                                         <span data-ttu-id="0763d-109">0</span><span class="sxs-lookup"><span data-stu-id="0763d-109">0</span></span>                                          |
|    <span data-ttu-id="0763d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0763d-110">Component</span></span>    |                                         <span data-ttu-id="0763d-111">0</span><span class="sxs-lookup"><span data-stu-id="0763d-111">0</span></span>                                          |
|  <span data-ttu-id="0763d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0763d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="0763d-113">0</span><span class="sxs-lookup"><span data-stu-id="0763d-113">0</span></span>                                          |
|  <span data-ttu-id="0763d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0763d-114">Message Text</span></span>   |                  <span data-ttu-id="0763d-115">無効なアドレスのスキーム指定してください"{0}"スキーム。</span><span class="sxs-lookup"><span data-stu-id="0763d-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="0763d-116">説明</span><span class="sxs-lookup"><span data-stu-id="0763d-116">Explanation</span></span>  
 <span data-ttu-id="0763d-117">正しい形式の相対アドレスを使用して WCF 分離受信場所が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="0763d-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="0763d-118">たとえば、 http://localhost/svc 相対アドレスとしては機能しません。</span><span class="sxs-lookup"><span data-stu-id="0763d-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="0763d-119">WCF 分離受信場所の "アドレス" プロパティを絶対アドレスに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0763d-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0763d-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0763d-120">User Action</span></span>  
 <span data-ttu-id="0763d-121">受信場所のアドレスを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0763d-121">Use the following procedure to configure the receive location address.</span></span>  
  
#### <a name="to-configure-the-receive-location-address"></a><span data-ttu-id="0763d-122">受信場所のアドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="0763d-122">To configure the receive location address</span></span>  
  
1. <span data-ttu-id="0763d-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="0763d-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0763d-124">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="0763d-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="0763d-125">アプリケーションと、検索、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="0763d-125">Locate your application and the locate your transport.</span></span>  
  
4. <span data-ttu-id="0763d-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0763d-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="0763d-127">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0763d-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="0763d-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="0763d-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="0763d-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0763d-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="0763d-130">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="0763d-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="0763d-131">**アドレス (URI)** テキスト ボックスに、スラッシュ (「/」) を開始するようにアドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="0763d-131">In the **Address (URI)** text box, change the address so that it starts with a forward slash ("/").</span></span>  
  
   <span data-ttu-id="0763d-132">に関する追加情報については、受信場所を次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0763d-132">For additional information on receive locations, see the following resources:</span></span>  
  
-   [<span data-ttu-id="0763d-133">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0763d-133">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="0763d-134">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0763d-134">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="0763d-135">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0763d-135">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)