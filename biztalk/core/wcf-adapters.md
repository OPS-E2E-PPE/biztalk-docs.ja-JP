---
title: "WCF アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb77124dbad631cd521a285ff4f036e0545ca819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters"></a><span data-ttu-id="9084b-102">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="9084b-102">WCF Adapters</span></span>

## <a name="overview"></a><span data-ttu-id="9084b-103">概要</span><span class="sxs-lookup"><span data-stu-id="9084b-103">Overview</span></span>
<span data-ttu-id="9084b-104">Windows Communication Foundation (WCF) 向け BizTalk アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できます。</span><span class="sxs-lookup"><span data-stu-id="9084b-104">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="9084b-105">BizTalk WCF アダプターは、WCF 定義済みバインドを表す 5 つの物理アダプターを含める-**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-105">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="9084b-106">定義済みバインド用 WCF アダプタの目的は、大半のアプリケーション要件に必要な情報の構成を合理化することです。</span><span class="sxs-lookup"><span data-stu-id="9084b-106">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="9084b-107">BizTalk WCF アダプタには、受信場所と送信ポートに関する WCF バインドと動作情報を自由に構成するために使用される、2 つのアダプタも含まれています。</span><span class="sxs-lookup"><span data-stu-id="9084b-107">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  

## <a name="available-wcf-adapters"></a><span data-ttu-id="9084b-108">使用可能な WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-108">Available WCF adapters</span></span>
    
-   <span data-ttu-id="9084b-109">**Wcf-wshttp アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-109">**WCF-WSHttp adapter**.</span></span> <span data-ttu-id="9084b-110">HTTP トランスポート経由の WS-* 標準をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9084b-110">Provides the WS-* standards support over the HTTP transport.</span></span> <span data-ttu-id="9084b-111">WCF-WSHttp アダプターは、外部アプリケーションと MessageBox データベース間のトランザクション上の対話に WS-Transaction、メッセージ セキュリティと認証に WS-Security という仕様を実装します。</span><span class="sxs-lookup"><span data-stu-id="9084b-111">The WCF-WSHttp adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="9084b-112">トランスポートは HTTP または HTTPS で、メッセージのエンコードは、テキスト エンコードまたは Message Transmission Optimization Mechanism (MTOM) エンコードです。</span><span class="sxs-lookup"><span data-stu-id="9084b-112">The transport is HTTP or HTTPS, and message encoding is a Text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span>  
  
-   <span data-ttu-id="9084b-113">**Wcf-basichttp アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-113">**WCF-BasicHttp adapter**.</span></span> <span data-ttu-id="9084b-114">ASMX ベースの Web サービスとクライアント、および WS-I Basic Profile 1.1 に準拠する他のサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="9084b-114">Communicates with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span> <span data-ttu-id="9084b-115">トランスポートは HTTP または HTTPS で、メッセージ エンコードは Text エンコードです。</span><span class="sxs-lookup"><span data-stu-id="9084b-115">The transport is HTTP or HTTPS, and message encoding is a text encoding.</span></span>  
  
-   <span data-ttu-id="9084b-116">**Wcf-nettcp アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-116">**WCF-NetTcp adapter**.</span></span> <span data-ttu-id="9084b-117">TCP トランスポート経由の WS-* 標準をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9084b-117">Provides the WS-* standards support over the TCP transport.</span></span> <span data-ttu-id="9084b-118">WCF-NetTcp アダプタは、WCF-to-WCF 環境での効率的な通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="9084b-118">The WCF-NetTcp adapter provides efficient communication in a WCF-to-WCF environment.</span></span> <span data-ttu-id="9084b-119">アダプターは、次の仕様を実装して: 外部アプリケーションとメッセージ ボックス データベース、および Ws-security 間は、メッセージ セキュリティと認証の間のやり取りをトランザクションの WS トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="9084b-119">The adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="9084b-120">トランスポートは TCP で、メッセージのエンコードはバイナリ エンコードです。</span><span class="sxs-lookup"><span data-stu-id="9084b-120">The transport is TCP, and message encoding is binary encoding.</span></span>  
  
-   <span data-ttu-id="9084b-121">**Wcf-netmsmq アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-121">**WCF-NetMsmq adapter**.</span></span> <span data-ttu-id="9084b-122">[!INCLUDE[btsCoName](../includes/btsconame-md.md)] メッセージ キュー (MSMQ) をトランスポートとして利用することにより、キューをサポートします。疎結合アプリケーションのサポート、エラーの分離、負荷の平準化、および切断時の操作を可能にします。</span><span class="sxs-lookup"><span data-stu-id="9084b-122">Provides support for queuing by leveraging [!INCLUDE[btsCoName](../includes/btsconame-md.md)] Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling, and disconnected operations.</span></span>  
  
-   <span data-ttu-id="9084b-123">**Wcf-netnamedpipe アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-123">**WCF-NetNamedPipe adapter**.</span></span> <span data-ttu-id="9084b-124">コンピューター上のプロセス間通信をセキュリティで保護された状態で最適化します。</span><span class="sxs-lookup"><span data-stu-id="9084b-124">Provides secure optimization for on-machine cross-process communication.</span></span> <span data-ttu-id="9084b-125">WCF-NetNamedPipe アダプターはトランスポート セキュリティを使用して、転送時のセキュリティ、メッセージ配信の名前付きパイプ、メッセージのバイナリ エンコードを実現します。</span><span class="sxs-lookup"><span data-stu-id="9084b-125">The WCF-NetNamedPipe adapter uses transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
-   <span data-ttu-id="9084b-126">**WCF カスタム アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-126">**WCF-Custom adapter**.</span></span> <span data-ttu-id="9084b-127">WCF 拡張機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9084b-127">Enables the use of WCF extensibility features.</span></span> <span data-ttu-id="9084b-128">アダプタでは、受信場所および送信ポートに対して、ユーザーが WCF のバインドおよび動作情報を選択し、構成できます。</span><span class="sxs-lookup"><span data-stu-id="9084b-128">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location and send port.</span></span>  
  
-   <span data-ttu-id="9084b-129">**Wcf-customisolated アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9084b-129">**WCF-CustomIsolated adapter**.</span></span> <span data-ttu-id="9084b-130">HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9084b-130">Enables the use of WCF extensibility features over the HTTP transport.</span></span> <span data-ttu-id="9084b-131">このアダプタでは、分離ホストで実行している受信場所に対して、WCF バインドと WCF 動作情報を選択および構成できます。</span><span class="sxs-lookup"><span data-stu-id="9084b-131">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location running in an isolated host.</span></span>  
  
 <span data-ttu-id="9084b-132">さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には BizTalk WCF サービス公開ウィザードと BizTalk WCF サービス使用ウィザードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9084b-132">In addition, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the BizTalk WCF Service Publishing Wizard and the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="9084b-133">BizTalk Web サービス公開ウィザードを使用すると、BizTalk オーケストレーションを WCF サービスとして作成および公開したり、スキーマを WCF サービスとして公開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9084b-133">You can use the BizTalk WCF Service Publishing Wizard to create and publish BizTalk orchestrations as WCF services, and to publish schemas as WCF services.</span></span> <span data-ttu-id="9084b-134">BizTalk WCF サービス使用ウィザードでは、オーケストレーションや種類など、WCF サービスのメタデータ ドキュメントに基づいて WCF サービスを使用するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アイテムを生成します。</span><span class="sxs-lookup"><span data-stu-id="9084b-134">You can use the BizTalk WCF Service Consuming Wizard to generate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts, such as orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span>  
  
 <span data-ttu-id="9084b-135">このセクションでは、WCF アダプタを構成して展開するのに役立つリソースを紹介します。</span><span class="sxs-lookup"><span data-stu-id="9084b-135">This section provides resources to help you configure and deploy the WCF adapters.</span></span>  
  
## <a name="next"></a><span data-ttu-id="9084b-136">Next</span><span class="sxs-lookup"><span data-stu-id="9084b-136">Next</span></span> 
  
-   [<span data-ttu-id="9084b-137">WCF アダプタは?</span><span class="sxs-lookup"><span data-stu-id="9084b-137">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="9084b-138">WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="9084b-138">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="9084b-139">WCF-BasicHttp アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-139">WCF-BasicHttp Adapter</span></span>](../core/wcf-basichttp-adapter.md)  
  
-   [<span data-ttu-id="9084b-140">Wcf-wshttp アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-140">WCF-WSHttp Adapter</span></span>](../core/wcf-wshttp-adapter.md)  
  
-   [<span data-ttu-id="9084b-141">Wcf-nettcp アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-141">WCF-NetTcp Adapter</span></span>](../core/wcf-nettcp-adapter.md)  
  
-   [<span data-ttu-id="9084b-142">Wcf-netmsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-142">WCF-NetMsmq Adapter</span></span>](../core/wcf-netmsmq-adapter.md)  
  
-   [<span data-ttu-id="9084b-143">Wcf-netnamedpipe アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-143">WCF-NetNamedPipe Adapter</span></span>](../core/wcf-netnamedpipe-adapter.md)  
  
-   [<span data-ttu-id="9084b-144">Wcf-custom アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-144">WCF-Custom Adapter</span></span>](../core/wcf-custom-adapter.md)  
  
-   [<span data-ttu-id="9084b-145">Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="9084b-145">WCF-CustomIsolated Adapter</span></span>](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="9084b-146">参照</span><span class="sxs-lookup"><span data-stu-id="9084b-146">See Also</span></span>  
 [<span data-ttu-id="9084b-147">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="9084b-147">Using WCF Services</span></span>](../core/using-wcf-services.md)   