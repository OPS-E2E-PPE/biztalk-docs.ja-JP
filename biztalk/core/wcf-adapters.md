---
title: WCF アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716154cbc315c24f7a6a3cd65f9d26a7dfe2fa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399419"
---
# <a name="wcf-adapters"></a><span data-ttu-id="9de1e-102">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="9de1e-102">WCF Adapters</span></span>

## <a name="overview"></a><span data-ttu-id="9de1e-103">概要</span><span class="sxs-lookup"><span data-stu-id="9de1e-103">Overview</span></span>
<span data-ttu-id="9de1e-104">BizTalk アダプターの Windows Communication Foundation (WCF) を許可する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF ベースのアプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-104">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="9de1e-105">BizTalk WCF アダプタには、WCF 定義済みバインドを表す 5 つの物理アダプタが含まれています —**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-105">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="9de1e-106">定義済みバインド用 WCF アダプタは、ほとんどのアプリケーション要件に必要な情報を簡単に構成するために提供されます。</span><span class="sxs-lookup"><span data-stu-id="9de1e-106">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="9de1e-107">BizTalk WCF アダプターでは、WCF バインドと動作については、受信場所の構成し、送信ポートを自由にするための 2 つのアダプターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="9de1e-107">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  

## <a name="available-wcf-adapters"></a><span data-ttu-id="9de1e-108">使用可能な WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-108">Available WCF adapters</span></span>
    
- <span data-ttu-id="9de1e-109">**Wcf-wshttp アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-109">**WCF-WSHttp adapter**.</span></span> <span data-ttu-id="9de1e-110">Ws-\* 標準 HTTP トランスポート経由でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9de1e-110">Provides the WS-\* standards support over the HTTP transport.</span></span> <span data-ttu-id="9de1e-111">Wcf-wshttp アダプタは、次の仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-111">The WCF-WSHttp adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="9de1e-112">トランスポートは HTTP または HTTPS、およびメッセージのエンコードは、テキストまたは Message Transmission Optimization Mechanism (MTOM) エンコードします。</span><span class="sxs-lookup"><span data-stu-id="9de1e-112">The transport is HTTP or HTTPS, and message encoding is a Text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span>  
  
- <span data-ttu-id="9de1e-113">**Wcf-basichttp アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-113">**WCF-BasicHttp adapter**.</span></span> <span data-ttu-id="9de1e-114">ASMX ベースの Web サービスとクライアント、および、WS に準拠するその他のサービスと通信の基本プロファイル 1.1。</span><span class="sxs-lookup"><span data-stu-id="9de1e-114">Communicates with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span> <span data-ttu-id="9de1e-115">トランスポートは HTTP または HTTPS、およびメッセージのエンコードは text エンコードです。</span><span class="sxs-lookup"><span data-stu-id="9de1e-115">The transport is HTTP or HTTPS, and message encoding is a text encoding.</span></span>  
  
- <span data-ttu-id="9de1e-116">**Wcf-nettcp アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-116">**WCF-NetTcp adapter**.</span></span> <span data-ttu-id="9de1e-117">Ws-\* 標準 TCP トランスポート経由でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9de1e-117">Provides the WS-\* standards support over the TCP transport.</span></span> <span data-ttu-id="9de1e-118">Wcf-nettcp アダプターは、WCF の環境での効率的な通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-118">The WCF-NetTcp adapter provides efficient communication in a WCF-to-WCF environment.</span></span> <span data-ttu-id="9de1e-119">アダプターは、次の仕様を実装します。WS トランザクションの外部アプリケーションとメッセージ ボックス データベースでは、Ws-security とは、メッセージ セキュリティと認証のトランザクション対話を処理します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-119">The adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="9de1e-120">トランスポートは TCP、およびメッセージのエンコードはバイナリ エンコードです。</span><span class="sxs-lookup"><span data-stu-id="9de1e-120">The transport is TCP, and message encoding is binary encoding.</span></span>  
  
- <span data-ttu-id="9de1e-121">**Wcf-netmsmq アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-121">**WCF-NetMsmq adapter**.</span></span> <span data-ttu-id="9de1e-122">使用したキューのサポートを提供します。[!INCLUDE[btsCoName](../includes/btsconame-md.md)]メッセージ キュー (MSMQ) トランスポートと有効が疎結合アプリケーション、エラーの分離のサポートとして負荷平準化、および切断操作。</span><span class="sxs-lookup"><span data-stu-id="9de1e-122">Provides support for queuing by leveraging [!INCLUDE[btsCoName](../includes/btsconame-md.md)] Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling, and disconnected operations.</span></span>  
  
- <span data-ttu-id="9de1e-123">**Wcf-netnamedpipe アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-123">**WCF-NetNamedPipe adapter**.</span></span> <span data-ttu-id="9de1e-124">セキュリティで保護されたコンピューター上のプロセス間通信の最適化を提供します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-124">Provides secure optimization for on-machine cross-process communication.</span></span> <span data-ttu-id="9de1e-125">Wcf-netnamedpipe アダプタは、メッセージの配信、およびバイナリ メッセージ エンコーディングの名前付きパイプ、転送セキュリティ用トランスポート セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-125">The WCF-NetNamedPipe adapter uses transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
- <span data-ttu-id="9de1e-126">**WCF カスタム アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-126">**WCF-Custom adapter**.</span></span> <span data-ttu-id="9de1e-127">WCF の拡張機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9de1e-127">Enables the use of WCF extensibility features.</span></span> <span data-ttu-id="9de1e-128">アダプターを使用すると、WCF バインドと動作については、受信場所の構成および送信ポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9de1e-128">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location and send port.</span></span>  
  
- <span data-ttu-id="9de1e-129">**Wcf-customisolated アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-129">**WCF-CustomIsolated adapter**.</span></span> <span data-ttu-id="9de1e-130">HTTP トランスポート経由で WCF 拡張機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9de1e-130">Enables the use of WCF extensibility features over the HTTP transport.</span></span> <span data-ttu-id="9de1e-131">アダプターを選択し、WCF バインドと、分離ホストで実行されている受信場所の動作情報を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9de1e-131">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location running in an isolated host.</span></span>  
  
  <span data-ttu-id="9de1e-132">さらに、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk WCF サービス公開ウィザードと BizTalk WCF サービス使用ウィザードを提供します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-132">In addition, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the BizTalk WCF Service Publishing Wizard and the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="9de1e-133">作成し、BizTalk オーケストレーションを WCF サービスとして公開して、スキーマを WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9de1e-133">You can use the BizTalk WCF Service Publishing Wizard to create and publish BizTalk orchestrations as WCF services, and to publish schemas as WCF services.</span></span> <span data-ttu-id="9de1e-134">BizTalk WCF サービス使用ウィザードを使用して、生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF サービスのメタデータ ドキュメントに基づいてオーケストレーションや種類、WCF サービスを使用するなど、成果物。</span><span class="sxs-lookup"><span data-stu-id="9de1e-134">You can use the BizTalk WCF Service Consuming Wizard to generate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts, such as orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span>  
  
  <span data-ttu-id="9de1e-135">このセクションでは、構成、および WCF アダプタの展開に役立つリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="9de1e-135">This section provides resources to help you configure and deploy the WCF adapters.</span></span>  
  
## <a name="next"></a><span data-ttu-id="9de1e-136">Next</span><span class="sxs-lookup"><span data-stu-id="9de1e-136">Next</span></span> 
  
-   [<span data-ttu-id="9de1e-137">WCF アダプターについて</span><span class="sxs-lookup"><span data-stu-id="9de1e-137">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="9de1e-138">WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="9de1e-138">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="9de1e-139">WCF-BasicHttp アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-139">WCF-BasicHttp Adapter</span></span>](../core/wcf-basichttp-adapter.md)  
  
-   [<span data-ttu-id="9de1e-140">WCF-WSHttp アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-140">WCF-WSHttp Adapter</span></span>](../core/wcf-wshttp-adapter.md)  
  
-   [<span data-ttu-id="9de1e-141">WCF-NetTcp アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-141">WCF-NetTcp Adapter</span></span>](../core/wcf-nettcp-adapter.md)  
  
-   [<span data-ttu-id="9de1e-142">WCF-NetMsmq アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-142">WCF-NetMsmq Adapter</span></span>](../core/wcf-netmsmq-adapter.md)  
  
-   [<span data-ttu-id="9de1e-143">WCF-NetNamedPipe アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-143">WCF-NetNamedPipe Adapter</span></span>](../core/wcf-netnamedpipe-adapter.md)  
  
-   [<span data-ttu-id="9de1e-144">WCF-Custom アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-144">WCF-Custom Adapter</span></span>](../core/wcf-custom-adapter.md)  
  
-   [<span data-ttu-id="9de1e-145">WCF-CustomIsolated アダプター</span><span class="sxs-lookup"><span data-stu-id="9de1e-145">WCF-CustomIsolated Adapter</span></span>](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="9de1e-146">参照</span><span class="sxs-lookup"><span data-stu-id="9de1e-146">See Also</span></span>  
 [<span data-ttu-id="9de1e-147">WCF サービスの使用</span><span class="sxs-lookup"><span data-stu-id="9de1e-147">Using WCF Services</span></span>](../core/using-wcf-services.md)   