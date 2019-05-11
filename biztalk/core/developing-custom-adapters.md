---
title: カスタム アダプターの開発 |Microsoft Docs
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
ms.openlocfilehash: 85f0ea739e8ddfe4ee4294f3db33187fecb811b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351121"
---
# <a name="developing-custom-adapters"></a><span data-ttu-id="8aeb6-102">カスタム アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="8aeb6-102">Developing Custom Adapters</span></span>
<span data-ttu-id="8aeb6-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、外部のシステム、アプリケーション、およびエンティティとメッセージを交換するために、アダプターの概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-103">To exchange messages with external systems, applications, and entities, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the concept of an adapter.</span></span> <span data-ttu-id="8aeb6-104">アダプターは、COM または[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]とビジネスの最後のメッセージを転送するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-104">Adapters are COM or [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] components that transfer messages to and from business end.</span></span> <span data-ttu-id="8aeb6-105">さまざまな通信プロトコルを使用して (ファイル システム、データベース、カスタム ビジネス アプリケーションなど) のポイント。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-105">points (such as file systems, databases, and custom business applications) by using various communication protocols.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8aeb6-106">さまざまなプロトコルをサポートするネイティブ アダプターを提供します。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-106">provides native adapters that support various protocols.</span></span> <span data-ttu-id="8aeb6-107">たとえば、次のオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-107">These include:</span></span>  
  
- <span data-ttu-id="8aeb6-108">ファイルの場所からのメッセージの送受信をサポートするファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="8aeb6-108">A File adapter that supports sending and receiving messages from a File location</span></span>  
  
- <span data-ttu-id="8aeb6-109">EDI、FTP、HTTP、MSMQ、SMTP、POP3、および SOAP プロトコルのアダプター</span><span class="sxs-lookup"><span data-stu-id="8aeb6-109">Adapters for EDI, FTP, HTTP, MSMQ, SMTP, POP3, and SOAP protocols</span></span>  
  
- <span data-ttu-id="8aeb6-110">[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] のアダプター</span><span class="sxs-lookup"><span data-stu-id="8aeb6-110">An adapter for [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]</span></span>  
  
  <span data-ttu-id="8aeb6-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はメッセージを特定のカスタム アプリケーションに送信したり、ネイティブ アダプターが存在しないプロトコルを使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-111">In some cases [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may need to transport messages to a specific custom application or use a protocol for which a native adapter does not exist.</span></span> <span data-ttu-id="8aeb6-112">サードパーティの企業は、追加のプロトコルをサポートするアダプターを作成しています。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-112">Third-party companies have written adapters to support additional protocols.</span></span> <span data-ttu-id="8aeb6-113">カスタム アダプターの作成を決定する前に、プロトコルに対するアダプターが存在するかどうかを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-113">You may want to determine if there is an adapter for your protocol before deciding to write a custom adapter.</span></span> <span data-ttu-id="8aeb6-114">アダプターと関連付けられているベンダーの一覧については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140)します。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-114">For a list of adapters and associated vendors see [http://go.microsoft.com/fwlink/?LinkId=47140](http://go.microsoft.com/fwlink/?LinkId=47140).</span></span> <span data-ttu-id="8aeb6-115">通信要件をサポートするためのアダプターが見つからない場合は、独自のカスタム アダプターを開発できます。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-115">If you are unable to locate an adapter to support your communication requirements, you can develop your own custom adapter.</span></span>  
  
  <span data-ttu-id="8aeb6-116">カスタム アダプターの作成は、難しい作業になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-116">Writing a custom adapter can be a challenging exercise.</span></span> <span data-ttu-id="8aeb6-117">このプロセスを簡略化するために、マイクロソフトはアダプター フレームワークと呼ばれる基礎を開発しました。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-117">To simplify this process Microsoft has developed a foundation called the Adapter Framework.</span></span> <span data-ttu-id="8aeb6-118">このフレームワークを、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のサンプルのアダプター ソース コードと共に開発の基礎として使用できます。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-118">You can use this framework as a basis for your development along with sample adapter source code in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
  <span data-ttu-id="8aeb6-119">このセクションのトピックでは、カスタム アダプターの開発のヒントや推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="8aeb6-119">The topics in this section present custom adapter development tips and recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8aeb6-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8aeb6-120">In This Section</span></span>  
  
-   [<span data-ttu-id="8aeb6-121">アダプター フレームワークについて</span><span class="sxs-lookup"><span data-stu-id="8aeb6-121">What Is the Adapter Framework?</span></span>](../core/what-is-the-adapter-framework.md)  
  
-   [<span data-ttu-id="8aeb6-122">BizTalk Server でのアダプターのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="8aeb6-122">How BizTalk Server Instantiates an Adapter</span></span>](../core/how-biztalk-server-instantiates-an-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-123">メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="8aeb6-123">Message Batches</span></span>](../core/message-batches.md)  
  
-   [<span data-ttu-id="8aeb6-124">トランザクション メッセージ バッチ</span><span class="sxs-lookup"><span data-stu-id="8aeb6-124">Transactional Message Batches</span></span>](../core/transactional-message-batches.md)  
  
-   [<span data-ttu-id="8aeb6-125">受信アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="8aeb6-125">Developing a Receive Adapter</span></span>](../core/developing-a-receive-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-126">送信アダプターの開発</span><span class="sxs-lookup"><span data-stu-id="8aeb6-126">Developing a Send Adapter</span></span>](../core/developing-a-send-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-127">分離アダプターのインスタンス化</span><span class="sxs-lookup"><span data-stu-id="8aeb6-127">Instantiating Isolated Adapters</span></span>](../core/instantiating-isolated-adapters.md)  
  
-   [<span data-ttu-id="8aeb6-128">アダプターのデザインの問題点</span><span class="sxs-lookup"><span data-stu-id="8aeb6-128">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)  
  
-   [<span data-ttu-id="8aeb6-129">アダプターによるサイズの大きなメッセージの処理方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-129">How Adapters Handle Large Messages</span></span>](../core/how-adapters-handle-large-messages.md)  
  
-   [<span data-ttu-id="8aeb6-130">アダプターの障害を処理する方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-130">How to Handle Adapter Failures</span></span>](../core/how-to-handle-adapter-failures.md)  
  
-   [<span data-ttu-id="8aeb6-131">アダプターを終了する方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-131">How to Terminate an Adapter</span></span>](../core/how-to-terminate-an-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-132">パフォーマンスの高いアダプターを設計する方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-132">How to Design a Performant Adapter</span></span>](../core/how-to-design-a-performant-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-133">カスタム アダプターを展開する方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-133">How to Deploy a Custom Adapter</span></span>](../core/how-to-deploy-a-custom-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-134">テスト アダプターをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-134">How to Test and Debug an Adapter</span></span>](../core/how-to-test-and-debug-an-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-135">アダプター メタデータを BizTalk プロジェクトに追加する方法</span><span class="sxs-lookup"><span data-stu-id="8aeb6-135">How to Add Adapter Metadata to a BizTalk Project</span></span>](../core/how-to-add-adapter-metadata-to-a-biztalk-project.md)  
  
-   [<span data-ttu-id="8aeb6-136">アダプターのローカライズに関する問題点</span><span class="sxs-lookup"><span data-stu-id="8aeb6-136">Adapter Localization Issues</span></span>](../core/adapter-localization-issues.md)  
  
-   [<span data-ttu-id="8aeb6-137">アダプターのデザインに関するヒント</span><span class="sxs-lookup"><span data-stu-id="8aeb6-137">Tips for Designing Your Adapter</span></span>](../core/tips-for-designing-your-adapter.md)  
  
-   [<span data-ttu-id="8aeb6-138">アダプターのデザイン時構成</span><span class="sxs-lookup"><span data-stu-id="8aeb6-138">Adapter Design-Time Configuration</span></span>](../core/adapter-design-time-configuration.md)  
  
## <a name="see-also"></a><span data-ttu-id="8aeb6-139">参照</span><span class="sxs-lookup"><span data-stu-id="8aeb6-139">See Also</span></span>  
 [<span data-ttu-id="8aeb6-140">カスタム コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="8aeb6-140">Developing Custom Components</span></span>](../core/developing-custom-components.md)