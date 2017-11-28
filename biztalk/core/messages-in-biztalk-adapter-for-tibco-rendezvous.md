---
title: "BizTalk Adapter for TIBCO Rendezvous のメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passing messages
- TIBCO Rendezvous
- messages
- message passing
- messages, passing
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc1eadbefdeb5c59df9a1b999ffdd3e530587a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="95714-102">BizTalk Adapter for TIBCO Rendezvous のメッセージ</span><span class="sxs-lookup"><span data-stu-id="95714-102">Messages in BizTalk Adapter for TIBCO Rendezvous</span></span>
<span data-ttu-id="95714-103">BizTalk Adapter for TIBCO Rendezvous は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と TIBCO Rendezvous 間に双方向の接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="95714-103">BizTalk Adapter for TIBCO Rendezvous provides bi-directional connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and TIBCO Rendezvous.</span></span> <span data-ttu-id="95714-104">このアダプターは、TIBCO Rendezvous API と BizTalk Adapter Framework API の両方を使用して、緊密な統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="95714-104">This adapter uses both the TIBCO Rendezvous API and the BizTalk Adapter Framework API to provide tight integration.</span></span>  
  
## <a name="about-tibco-rendezvous"></a><span data-ttu-id="95714-105">TIBCO Rendezvous について</span><span class="sxs-lookup"><span data-stu-id="95714-105">About TIBCO Rendezvous</span></span>  
 <span data-ttu-id="95714-106">TIBCO Rendezvous は、エンタープライズ アプリケーション統合 (EAI) のメッセージ バスを提供するソフトウェア製品です。</span><span class="sxs-lookup"><span data-stu-id="95714-106">TIBCO Rendezvous is a software product that provides a message bus for enterprise application integration (EAI).</span></span> <span data-ttu-id="95714-107">TIBCO では、C、C++、Java、Visual Basic および Microsoft Office Excel ワークシートにデータ フィードとその他の任意のアプリケーションを受信する Microsoft .NET Framework のメッセージング Api を提供します。</span><span class="sxs-lookup"><span data-stu-id="95714-107">TIBCO provides messaging APIs in C, C++, Java, Visual Basic and for the Microsoft .NET Framework to receive data feeds on Microsoft Office Excel worksheets and other applications of choice.</span></span> <span data-ttu-id="95714-108">詳細については、次を参照してください。 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)です。</span><span class="sxs-lookup"><span data-stu-id="95714-108">For more information, see [TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md).</span></span>  
  
### <a name="message-passing"></a><span data-ttu-id="95714-109">メッセージ パッシング</span><span class="sxs-lookup"><span data-stu-id="95714-109">Message Passing</span></span>  
 <span data-ttu-id="95714-110">メッセージを渡す概念はとても簡単です。</span><span class="sxs-lookup"><span data-stu-id="95714-110">The basic concept of message passing is fairly simple:</span></span>  
  
-   <span data-ttu-id="95714-111">メッセージには、ピリオドで区切られた要素で構成される 1 つのサブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="95714-111">A message has a single subject composed of elements separated by periods.</span></span> <span data-ttu-id="95714-112">メッセージは 1 つの Rendezous デーモンに送信されますが、最終的に他の複数のデーモンに配信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="95714-112">A message is sent to a single Rendezvous daemon, although it might eventually be broadcast onto other daemons.</span></span>  
  
-   <span data-ttu-id="95714-113">リスナーは、待機しているサブジェクトを (基本的なワイルドカード機能を使用して) デーモンに通知します。</span><span class="sxs-lookup"><span data-stu-id="95714-113">A listener announces its subjects of interest to a daemon (with a basic wildcard facility).</span></span> <span data-ttu-id="95714-114">2 つのデーモンが相互に接続されている場合、または 2 つのデーモンが実際には同一のデーモンである場合は、一致するサブジェクトを持つメッセージがリスナーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="95714-114">Messages that have matching subjects are delivered to it if the two daemons are connected to each other, or are indeed the same daemon.</span></span>  
  
 <span data-ttu-id="95714-115">必要に応じて、この上に重要な "エンタープライズ" 機能を配置できます。そのためには、指定可能なフォールト トレランス、信頼性、または認定済みのオプションを使用します。すべてのオプションは基礎になる基本メッセージをとおして実装されます。</span><span class="sxs-lookup"><span data-stu-id="95714-115">Significant "Enterprise" functionality is layered onto this if desired--with Fault Tolerance/Reliable or Certified options possible--all implemented through the underlying basic messages.</span></span>  
  
 <span data-ttu-id="95714-116">メッセージ自体は、型指定された名前と値のフィールドまたは数字と値のフィールドとして表示できます (1 つのメッセージで 2 つの識別メカニズムを混在させ、特定の制約と照合できます)。</span><span class="sxs-lookup"><span data-stu-id="95714-116">The messages themselves can be viewed as typed name-value fields or number-value fields (the two identification mechanisms in a message can mix and match with certain restrictions).</span></span> <span data-ttu-id="95714-117">メッセージはサブメッセージを含むことができ、そのサブメッセージがサブメッセージを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="95714-117">A message itself can contain sub-messages, which can contain sub-messages.</span></span>  
  
 <span data-ttu-id="95714-118">サブジェクト名は、ドット記号 (ピリオド) で区切った 1 つ以上の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="95714-118">Subject names consist of one or more elements separated by dot characters (periods).</span></span> <span data-ttu-id="95714-119">それらの要素は、アプリケーション システム内の情報の構造を反映したサブジェクト名階層を実装します。</span><span class="sxs-lookup"><span data-stu-id="95714-119">The elements implement a subject name hierarchy that reflects the structure of information in an application system.</span></span> <span data-ttu-id="95714-120">次の文字列は有効なサブジェクト名の例です。</span><span class="sxs-lookup"><span data-stu-id="95714-120">The following strings are examples of valid subject names:</span></span>  
  
-   <span data-ttu-id="95714-121">RUN.HOME</span><span class="sxs-lookup"><span data-stu-id="95714-121">RUN.HOME</span></span>  
  
-   <span data-ttu-id="95714-122">RUN.for.Elected_Office</span><span class="sxs-lookup"><span data-stu-id="95714-122">RUN.for.Elected_Office</span></span>  
  
 <span data-ttu-id="95714-123">BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous SDK を使用して、TIBCO Rendezvous サブジェクトにメッセージを発行し、TIBCO Rendezvous イベントに登録します。</span><span class="sxs-lookup"><span data-stu-id="95714-123">BizTalk Adapter for TIBCO Rendezvous uses the TIBCO Rendezvous SDK to publish messages to TIBCO Rendezvous subjects and to register for TIBCO Rendezvous events.</span></span> <span data-ttu-id="95714-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 関連クラスは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターでホストされます。</span><span class="sxs-lookup"><span data-stu-id="95714-124">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related classes are hosted in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer.</span></span> <span data-ttu-id="95714-125">別のプロセス (ランタイム エージェント) が開始されて Rendezvous プログラムとして機能し、.NET Framework リモート処理を使用して両者間のメッセージ交換が行われます。</span><span class="sxs-lookup"><span data-stu-id="95714-125">A separate process (run-time agent) is started and acts as the Rendezvous program, and .NET Framework remoting is used to exchange messages between the two.</span></span>  
  
-   <span data-ttu-id="95714-126">情報レベル、警告レベル、およびエラー レベルのメッセージが Windows イベント ログに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95714-126">Info-Level, Warning-Level, and Error-level messages are sent to the Windows event log.</span></span>  
  
-   <span data-ttu-id="95714-127">デバッグ レベルを含むすべてのレベルのメッセージが Windows トレース ログに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95714-127">All levels, including Debug-level messages, are sent to the Windows Tracing Log.</span></span>  
  
#### <a name="transmitter"></a><span data-ttu-id="95714-128">送信元</span><span class="sxs-lookup"><span data-stu-id="95714-128">Transmitter</span></span>  
 <span data-ttu-id="95714-129">BizTalk Adapter for TIBCO Rendezvous は、送信ポートごとに 1 つのランタイム エージェントを起動します。</span><span class="sxs-lookup"><span data-stu-id="95714-129">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per send port.</span></span> <span data-ttu-id="95714-130">TIBCO Rendezvous .NET Framework API を使用すると、グローバル スコープで文字エンコードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="95714-130">The TIBCO Rendezvous .NET Framework API only allows setting character encoding at a global scope.</span></span> <span data-ttu-id="95714-131">そのため、ポート構成オプションの 1 つはコード ページ番号です。</span><span class="sxs-lookup"><span data-stu-id="95714-131">Therefore, one of the port configuration options is a code page number.</span></span> <span data-ttu-id="95714-132">コード ページごとに異なるプロセスを開始することによって、アダプターはグローバル化に対して、より優れたサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="95714-132">By starting a different process for each code page, the adapter can provide better support for globalization.</span></span>  
  
#### <a name="receiver"></a><span data-ttu-id="95714-133">受信元</span><span class="sxs-lookup"><span data-stu-id="95714-133">Receiver</span></span>  
 <span data-ttu-id="95714-134">BizTalk Adapter for TIBCO Rendezvous は、受信場所ごとに 1 つのランタイム エージェントを起動します。</span><span class="sxs-lookup"><span data-stu-id="95714-134">BizTalk Adapter for TIBCO Rendezvous launches one run-time agent per receive location.</span></span>  
  
#### <a name="transactions"></a><span data-ttu-id="95714-135">トランザクション</span><span class="sxs-lookup"><span data-stu-id="95714-135">Transactions</span></span>  
 <span data-ttu-id="95714-136">TIBCO Rendezvous 製品はトランザクション対応ではありません。</span><span class="sxs-lookup"><span data-stu-id="95714-136">The TIBCO Rendezvous product is not transactional.</span></span> <span data-ttu-id="95714-137">TIBCO Rendezvous TX という別の製品が必要です。</span><span class="sxs-lookup"><span data-stu-id="95714-137">A separate product, TIBCO Rendezvous TX, is required.</span></span> <span data-ttu-id="95714-138">BizTalk Adapter for TIBCO Rendezvous のこのリリースでは、トランザクションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95714-138">BizTalk Adapter for TIBCO Rendezvous does not support transactions in this release.</span></span>  
  
#### <a name="security"></a><span data-ttu-id="95714-139">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="95714-139">Security</span></span>  
 <span data-ttu-id="95714-140">TIBCO Rendezvous は、TIBCO Rendezvous プログラムとデーモンの間の認証のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="95714-140">TIBCO Rendezvous only supports authentication between TIBCO Rendezvous programs and daemons.</span></span> <span data-ttu-id="95714-141">承認または暗号化は実行しません。</span><span class="sxs-lookup"><span data-stu-id="95714-141">It does not perform authorization or encryption.</span></span> <span data-ttu-id="95714-142">TIBCO Rendezvous DataSecurity という別の製品が必要です。</span><span class="sxs-lookup"><span data-stu-id="95714-142">A separate product, TIBCO Rendezvous DataSecurity, is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95714-143">参照</span><span class="sxs-lookup"><span data-stu-id="95714-143">See Also</span></span>  
 <span data-ttu-id="95714-144">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="95714-144">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="95714-145">作業の開始</span><span class="sxs-lookup"><span data-stu-id="95714-145">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)