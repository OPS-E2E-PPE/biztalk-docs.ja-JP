---
title: カスタム アダプターの開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44765fbb-b24d-43b6-a40c-d28e319b90a5
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c13aba7e378d67523ec755837ac65b26989730a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239914"
---
# <a name="developing-custom-adapters"></a><span data-ttu-id="e3665-102">カスタム アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="e3665-102">Developing Custom Adapters</span></span>
<span data-ttu-id="e3665-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、外部のシステム、アプリケーション、およびエンティティとメッセージを交換するために、アダプターの概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3665-103">To exchange messages with external systems, applications, and entities, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the concept of an adapter.</span></span> <span data-ttu-id="e3665-104">アダプターは、COM または[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]ビジネス エンドユーザーからのメッセージを転送するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e3665-104">Adapters are COM or [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] components that transfer messages to and from business end.</span></span> <span data-ttu-id="e3665-105">さまざまな通信プロトコルを使用して、(ファイル システム、データベース、カスタム ビジネス アプリケーションなど) のポイント。</span><span class="sxs-lookup"><span data-stu-id="e3665-105">points (such as file systems, databases, and custom business applications) by using various communication protocols.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e3665-106">さまざまなプロトコルをサポートするネイティブ アダプターを提供します。</span><span class="sxs-lookup"><span data-stu-id="e3665-106"> provides native adapters that support various protocols.</span></span> <span data-ttu-id="e3665-107">たとえば、次のオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e3665-107">These include:</span></span>  
  
-   <span data-ttu-id="e3665-108">ファイルの場所からのメッセージの送受信をサポートするファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="e3665-108">A File adapter that supports sending and receiving messages from a File location</span></span>  
  
-   <span data-ttu-id="e3665-109">EDI、FTP、HTTP、MSMQ、SMTP、POP3、および SOAP プロトコルのアダプター</span><span class="sxs-lookup"><span data-stu-id="e3665-109">Adapters for EDI, FTP, HTTP, MSMQ, SMTP, POP3, and SOAP protocols</span></span>  
  
-   <span data-ttu-id="e3665-110">[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] のアダプター</span><span class="sxs-lookup"><span data-stu-id="e3665-110">An adapter for [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span></span>  
  
 <span data-ttu-id="e3665-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はメッセージを特定のカスタム アプリケーションに送信したり、ネイティブ アダプターが存在しないプロトコルを使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3665-111">In some cases [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may need to transport messages to a specific custom application or use a protocol for which a native adapter does not exist.</span></span> <span data-ttu-id="e3665-112">サードパーティの企業は、追加のプロトコルをサポートするアダプターを作成しています。</span><span class="sxs-lookup"><span data-stu-id="e3665-112">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="e3665-113">カスタム アダプターの作成を決定する前に、プロトコルに対するアダプターが存在するかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3665-113">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="e3665-114">アダプターと関連するベンダーの一覧については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140)です。</span><span class="sxs-lookup"><span data-stu-id="e3665-114">For a list of adapters and associated vendors see [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140).</span></span> <span data-ttu-id="e3665-115">通信要件をサポートするためのアダプターが見つからない場合は、独自のカスタム アダプターを開発できます。</span><span class="sxs-lookup"><span data-stu-id="e3665-115">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  
  
 <span data-ttu-id="e3665-116">カスタム アダプターの作成は、難しい作業になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e3665-116">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="e3665-117">このプロセスを簡略化するために、マイクロソフトはアダプター フレームワークと呼ばれる基礎を開発しました。</span><span class="sxs-lookup"><span data-stu-id="e3665-117">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="e3665-118">このフレームワークを、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のサンプルのアダプター ソース コードと共に開発の基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3665-118">You can use this framework as a basis for your development along with sample adapter source code in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="e3665-119">このセクションのトピックでは、カスタム アダプターの開発のヒントや推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="e3665-119">The topics in this section present custom adapter development tips and recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e3665-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e3665-120">In This Section</span></span>  
  
-   [<span data-ttu-id="e3665-121">アダプター フレームワークとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="e3665-121">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)  
  
-   [<span data-ttu-id="e3665-122">BizTalk Server にアダプターがインスタンス化する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-122">How BizTalk Server Instantiates an Adapter</span></span>](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [<span data-ttu-id="e3665-123">メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="e3665-123">Message Batches</span></span>](../core/message-batches.md)  
  
-   [<span data-ttu-id="e3665-124">トランザクション メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="e3665-124">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)  
  
-   [<span data-ttu-id="e3665-125">開発、受信アダプター</span><span class="sxs-lookup"><span data-stu-id="e3665-125">Developing a Receive Adapter</span></span>](../core/developing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="e3665-126">送信アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="e3665-126">Developing a Send Adapter</span></span>](../core/developing-a-send-adapter.md)  
  
-   [<span data-ttu-id="e3665-127">分離アダプターをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="e3665-127">Instantiating Isolated Adapters</span></span>](../core/instantiating-isolated-adapters.md)  
  
-   [<span data-ttu-id="e3665-128">アダプターのデザインに関する問題</span><span class="sxs-lookup"><span data-stu-id="e3665-128">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)  
  
-   [<span data-ttu-id="e3665-129">アダプターがサイズの大きいメッセージを処理する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-129">How Adapters Handle Large Messages</span></span>](../core/how-adapters-handle-large-messages.md)  
  
-   [<span data-ttu-id="e3665-130">アダプターの障害を処理する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-130">How to Handle Adapter Failures</span></span>](../core/how-to-handle-adapter-failures.md)  
  
-   [<span data-ttu-id="e3665-131">アダプターを終了する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-131">How to Terminate an Adapter</span></span>](../core/how-to-terminate-an-adapter.md)  
  
-   [<span data-ttu-id="e3665-132">パフォーマンスの高いアダプターを設計する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-132">How to Design a Performant Adapter</span></span>](../core/how-to-design-a-performant-adapter.md)  
  
-   [<span data-ttu-id="e3665-133">カスタム アダプターを展開する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-133">How to Deploy a Custom Adapter</span></span>](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [<span data-ttu-id="e3665-134">テストおよびアダプターをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="e3665-134">How to Test and Debug an Adapter</span></span>](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [<span data-ttu-id="e3665-135">アダプター メタデータを BizTalk プロジェクトに追加する方法</span><span class="sxs-lookup"><span data-stu-id="e3665-135">How to Add Adapter Metadata to a BizTalk Project</span></span>](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [<span data-ttu-id="e3665-136">アダプターのローカリゼーションの問題</span><span class="sxs-lookup"><span data-stu-id="e3665-136">Adapter Localization Issues</span></span>](../core/adapter-localization-issues.md)  
  
-   [<span data-ttu-id="e3665-137">アダプターのデザインに関するヒント</span><span class="sxs-lookup"><span data-stu-id="e3665-137">Tips for Designing Your Adapter</span></span>](../core/tips-for-designing-your-adapter.md)  
  
-   [<span data-ttu-id="e3665-138">アダプター デザイン時の構成</span><span class="sxs-lookup"><span data-stu-id="e3665-138">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3665-139">参照</span><span class="sxs-lookup"><span data-stu-id="e3665-139">See Also</span></span>  
 [<span data-ttu-id="e3665-140">カスタム コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="e3665-140">Developing Custom Components</span></span>](../core/developing-custom-components.md)