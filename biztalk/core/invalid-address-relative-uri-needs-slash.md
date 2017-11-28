---
title: "アドレスが無効です (相対 uri にスラッシュが必要があります (&quot;-&quot;)) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376f924-f119-4ba8-9be1-eea7ba5f3eb6
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1c43d4a86af788c67ea59c7bf0ca7dea43da39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-relative-uri-needs-slash-quot-quot"></a><span data-ttu-id="be299-102">アドレスが無効です (相対 uri にスラッシュが必要があります (&quot;-&quot;))</span><span class="sxs-lookup"><span data-stu-id="be299-102">Invalid address (relative uri needs slash (&quot;-&quot;))</span></span>
## <a name="details"></a><span data-ttu-id="be299-103">詳細</span><span class="sxs-lookup"><span data-stu-id="be299-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be299-104">製品名</span><span class="sxs-lookup"><span data-stu-id="be299-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="be299-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="be299-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="be299-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="be299-106">Event ID</span></span>|<span data-ttu-id="be299-107">0</span><span class="sxs-lookup"><span data-stu-id="be299-107">0</span></span>|  
|<span data-ttu-id="be299-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="be299-108">Event Source</span></span>|<span data-ttu-id="be299-109">0</span><span class="sxs-lookup"><span data-stu-id="be299-109">0</span></span>|  
|<span data-ttu-id="be299-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be299-110">Component</span></span>|<span data-ttu-id="be299-111">0</span><span class="sxs-lookup"><span data-stu-id="be299-111">0</span></span>|  
|<span data-ttu-id="be299-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="be299-112">Symbolic Name</span></span>|<span data-ttu-id="be299-113">0</span><span class="sxs-lookup"><span data-stu-id="be299-113">0</span></span>|  
|<span data-ttu-id="be299-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="be299-114">Message Text</span></span>|<span data-ttu-id="be299-115">アドレスが無効です。スラッシュ ("/") で始まる相対 URI を指定してください。</span><span class="sxs-lookup"><span data-stu-id="be299-115">Invalid address; expecting relative uri starting with slash ("/")</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be299-116">説明</span><span class="sxs-lookup"><span data-stu-id="be299-116">Explanation</span></span>  
 <span data-ttu-id="be299-117">正しい形式の相対アドレスを使用して WCF 分離受信場所が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="be299-117">You did not provide an isolated WCF receive location with a well-formed relative address.</span></span> <span data-ttu-id="be299-118">たとえば、http://localhost/svc は相対アドレスとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="be299-118">For example, http://localhost/svc will not work as a relative address.</span></span> <span data-ttu-id="be299-119">WCF 分離受信場所の "アドレス" プロパティを絶対アドレスに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="be299-119">You cannot set the Address property of the isolated WCF receive location to a absolute address.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be299-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="be299-120">User Action</span></span>  
 <span data-ttu-id="be299-121">アドレスを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be299-121">Use the following procedure to configure an address.</span></span>  
  
#### <a name="to-configure-an-address"></a><span data-ttu-id="be299-122">アドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="be299-122">To configure an address</span></span>  
  
1.  <span data-ttu-id="be299-123">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="be299-123">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="be299-124">コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="be299-124">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="be299-125">アプリケーションを見つけて、トランスポートを特定します。</span><span class="sxs-lookup"><span data-stu-id="be299-125">Locate your application and locate your transport.</span></span>  
  
4.  <span data-ttu-id="be299-126">トランスポート名を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="be299-126">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="be299-127">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be299-127">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="be299-128">ポート**型**一覧で、適切なポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="be299-128">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="be299-129">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="be299-129">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="be299-130">**WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="be299-130">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="be299-131">**アドレス (URI)**テキスト ボックスに、アドレスを変更します。</span><span class="sxs-lookup"><span data-stu-id="be299-131">In the **Address (URI)** text box, change the address.</span></span> <span data-ttu-id="be299-132">整形式の相対アドレスの一例は /path/service.svc です。</span><span class="sxs-lookup"><span data-stu-id="be299-132">An example of a well-formed relative address is /path/service.svc.</span></span>  
  
 <span data-ttu-id="be299-133">受信場所の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be299-133">For additional information on receive locations, see the following:</span></span>  
  
-   [<span data-ttu-id="be299-134">Wcf-customisolated 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="be299-134">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="be299-135">Wcf-wshttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="be299-135">How to Configure a WCF-WSHttp Receive Location</span></span>](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [<span data-ttu-id="be299-136">Wcf-basichttp 受信場所を構成する方法</span><span class="sxs-lookup"><span data-stu-id="be299-136">How to Configure a WCF-BasicHttp Receive Location</span></span>](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)