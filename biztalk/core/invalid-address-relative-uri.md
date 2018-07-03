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
ms.openlocfilehash: dd362112a8edff37650aaa83da9c6ab33d0d697a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017400"
---
# <a name="invalid-address-relative-uri"></a><span data-ttu-id="d5e55-102">アドレスが無効です (相対 URI)</span><span class="sxs-lookup"><span data-stu-id="d5e55-102">Invalid address (relative uri)</span></span>
## <a name="details"></a><span data-ttu-id="d5e55-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d5e55-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="d5e55-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d5e55-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="d5e55-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d5e55-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="d5e55-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5e55-106">Event ID</span></span>     |                                        <span data-ttu-id="d5e55-107">000</span><span class="sxs-lookup"><span data-stu-id="d5e55-107">000</span></span>                                         |
|  <span data-ttu-id="d5e55-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d5e55-108">Event Source</span></span>   |                                         <span data-ttu-id="d5e55-109">0</span><span class="sxs-lookup"><span data-stu-id="d5e55-109">0</span></span>                                          |
|    <span data-ttu-id="d5e55-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5e55-110">Component</span></span>    |                                         <span data-ttu-id="d5e55-111">0</span><span class="sxs-lookup"><span data-stu-id="d5e55-111">0</span></span>                                          |
|  <span data-ttu-id="d5e55-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d5e55-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="d5e55-113">0</span><span class="sxs-lookup"><span data-stu-id="d5e55-113">0</span></span>                                          |
|  <span data-ttu-id="d5e55-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d5e55-114">Message Text</span></span>   |                  <span data-ttu-id="d5e55-115">無効なアドレスのスキーム指定してください"{0}"スキーム。</span><span class="sxs-lookup"><span data-stu-id="d5e55-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="d5e55-116">説明</span><span class="sxs-lookup"><span data-stu-id="d5e55-116">Explanation</span></span>  
 <span data-ttu-id="d5e55-117">正しい形式の相対アドレスを使用して WCF 分離受信場所が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d5e55-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="d5e55-118">たとえば、http://localhost/svc相対アドレスとしては機能しません。</span><span class="sxs-lookup"><span data-stu-id="d5e55-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="d5e55-119">WCF 分離受信場所の "アドレス" プロパティを絶対アドレスに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5e55-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5e55-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d5e55-120">User Action</span></span>  
 <span data-ttu-id="d5e55-121">受信場所のアドレスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-121">Use the following procedure to configure the receive location address.</span></span>  
  
#### <a name="to-configure-the-receive-location-address"></a><span data-ttu-id="d5e55-122">受信場所のアドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="d5e55-122">To configure the receive location address</span></span>  
  
1. <span data-ttu-id="d5e55-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="d5e55-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d5e55-124">コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="d5e55-125">アプリケーションと、検索、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-125">Locate your application and the locate your transport.</span></span>  
  
4. <span data-ttu-id="d5e55-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e55-126">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="d5e55-127">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5e55-127">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="d5e55-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-128">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="d5e55-129">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-129">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="d5e55-130">**WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="d5e55-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="d5e55-131">**アドレス (URI)** テキスト ボックスに、スラッシュ (「/」) を開始するようにアドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="d5e55-131">In the **Address (URI)** text box, change the address so that it starts with a forward slash ("/").</span></span>  
  
   <span data-ttu-id="d5e55-132">受信場所の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5e55-132">For additional information on receive locations, see the following resources:</span></span>  
  
-   [<span data-ttu-id="d5e55-133">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d5e55-133">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="d5e55-134">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d5e55-134">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="d5e55-135">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d5e55-135">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)