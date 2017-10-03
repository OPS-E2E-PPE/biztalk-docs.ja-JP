---
title: "JD Edwards OneWorld のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1daee7d44152817da1ac536dd98cbaf898e2ac7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-jd-edwards-oneworld"></a><span data-ttu-id="965f4-102">JD Edwards OneWorld のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="965f4-102">Architecture of JD Edwards OneWorld</span></span>
<span data-ttu-id="965f4-103">Microsoft BizTalk Adapter for JD Edwards OneWorld を使用すると、JD Edwards OneWorld のビジネス関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="965f4-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="965f4-104">JD Edwards OneWorld は、JDENet と呼ばれる独自のメッセージング アーキテクチャを使用して、クライアント コンピューターとサーバー コンピューター間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="965f4-104">JD Edwards OneWorld communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="965f4-105">JDENet は、JAR ファイルは、Connector.jar および Kernel.jar で JD Edwards OneWorld コネクタ クラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-105">JDENet is implemented by the JD Edwards OneWorld connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="965f4-106">通信は、TCP/IP をトランスポート プロトコルとして使用して実装されており、既定のポートは 6009 または 6010 です。</span><span class="sxs-lookup"><span data-stu-id="965f4-106">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="965f4-107">この値を設定する場所の詳細についてを参照してください[JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="965f4-107">For a description of where this value is set, see [How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md).</span></span>  
  
 <span data-ttu-id="965f4-108">**BizTalk Adapter for JD Edwards OneWorld のアーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="965f4-108">**Architecture for BizTalk Adapter for JD Edwards OneWorld**</span></span>  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 <span data-ttu-id="965f4-109">JD Edwards OneWorld のビジネス関数を呼び出すには、2 つのメッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="965f4-109">Calls to JD Edwards OneWorld business functions require two messages:</span></span>  
  
-   <span data-ttu-id="965f4-110">最初のメッセージは、ビジネス関数を処理するサーバーの場所を返します。</span><span class="sxs-lookup"><span data-stu-id="965f4-110">The first message responds with the location of the server that processes the business function.</span></span> <span data-ttu-id="965f4-111">これを行うと呼ばれるテーブルのセットの検索を実行して*オブジェクト構成マッピング (OCM)*です。</span><span class="sxs-lookup"><span data-stu-id="965f4-111">This is accomplished by performing a lookup in a set of tables called *object configuration mapping (OCM)*.</span></span>  
  
-   <span data-ttu-id="965f4-112">2 番目のメッセージでは、JD Edwards OneWorld から渡す引数または JD Edwards OneWorld に渡す引数が入ったフォーマット済みメッセージ バッファーを適切なサーバーに送信し、応答を待ちます。</span><span class="sxs-lookup"><span data-stu-id="965f4-112">The second message sends a formatted message buffer containing the arguments to pass to or from JD Edwards OneWorld to the appropriate server, and waits for a reply.</span></span> <span data-ttu-id="965f4-113">バッファーは基になる C++ 構造体の Typedef に従ってフォーマットされます。</span><span class="sxs-lookup"><span data-stu-id="965f4-113">The buffers are formatted according to the typedefs of the underlying C++ structs.</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="965f4-114">デザイン時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="965f4-114">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="965f4-115">デザイン時に、ターゲットの JD Edwards OneWorld サーバーに接続するためのポートを作成し、アダプターを選択して、資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="965f4-115">At design time, you create your port, select the adapter, and provide credential information to connect to the target JD Edwards OneWorld server.</span></span> <span data-ttu-id="965f4-116">Visual Studio 開発環境は、アダプター フレームワークを呼び出して、このポートのデザイン時情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="965f4-116">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="965f4-117">BizTalk Adapter for JD Edwards OneWorld ではこのポートに Browsingagent を使用します。</span><span class="sxs-lookup"><span data-stu-id="965f4-117">BizTalk Adapter for JD Edwards OneWorld uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="965f4-118">BizTalk Server は、デザイン時にアダプターを呼び出して情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="965f4-118">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="965f4-119">Browsingagent は、要求を JD Edwards OneWorld のネイティブ コードに変換し、ThinNet API 接続 (Connector.jar および Kernel.jar で確立される) を経由して、変換した要求を JD Edwards OneWorld に送信します。</span><span class="sxs-lookup"><span data-stu-id="965f4-119">The Browsingagent converts the request into native JD Edwards OneWorld code and then transmits the requests to JD Edwards OneWorld through the ThinNet API connection (established in the Connector and Kernel.jars).</span></span>  
  
-   <span data-ttu-id="965f4-120">カスタム ビジネス関数は BTSREL インストールによりインストール: マスター ビジネス関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="965f4-120">A custom business function is installed through the BTSREL installation: it exposes the master business functions.</span></span>  
  
-   <span data-ttu-id="965f4-121">JD Edwards OneWorld のモジュールの一覧が最初に返され、Visual Studio に転送され、アダプター ウィザードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-121">A list of modules in JD Edwards OneWorld is initially returned and transported to Visual Studio, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="965f4-122">階層を展開してライブラリ名とモジュール名を表示できます。</span><span class="sxs-lookup"><span data-stu-id="965f4-122">You can expand the hierarchy to display the library name and module name.</span></span>  
  
-   <span data-ttu-id="965f4-123">特定のモジュールを選択すると、モジュール内のすべての関数のスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-123">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="965f4-124">アダプターは必要な情報を JD Edwards OneWorld から取得し、browsingagent がスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="965f4-124">The adapter obtains the required information from JD Edwards OneWorld, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="965f4-125">スキーマは BizTalk Server プロジェクトのオーケストレーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-125">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="965f4-126">実行時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="965f4-126">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="965f4-127">BizTalk Server は BizTalk Adapter for JD Edwards OneWorld を呼び出し、特定のポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="965f4-127">BizTalk Server calls the BizTalk Adapter for JD Edwards OneWorld to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="965f4-128">ランタイム エージェントは XML を JD Edwards のネイティブ コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="965f4-128">The run-time agent converts the XML into native JD Edwards code.</span></span>  
  
-   <span data-ttu-id="965f4-129">ランタイム エージェントは、ThinNet を経由して、送信ポートのトランスポート プロパティで指定された JD Edwards エンタープライズ システムに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="965f4-129">The run-time agent submits the request through the ThinNet to the JD Edwards enterprise system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="965f4-130">JD Edwards システムでマスター ビジネス関数が実行され、ビジネス関数が返すデータ パラメーターと成功または失敗を示す応答ドキュメントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-130">The master business function is executed on the JD Edwards system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="965f4-131">JD Edwards OneWorld に送信されるメッセージは、単一メッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="965f4-131">The message sent to JD Edwards OneWorld is a single message, single reply architecture.</span></span> <span data-ttu-id="965f4-132">複数のメッセージを同時に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="965f4-132">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="965f4-133">応答ドキュメントが ThinNet を通じて返され、XML に変換されて、BizTalk Server に送られます。</span><span class="sxs-lookup"><span data-stu-id="965f4-133">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="965f4-134">デザイン時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="965f4-134">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="965f4-135">イベント メタデータのシステム的な作成は利用できません。</span><span class="sxs-lookup"><span data-stu-id="965f4-135">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="965f4-136">イベント ドキュメントの FAX を Visual Studio に提供し、スキーマを生成して、ターゲットの名前空間と共にプロジェクトに組み込めるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="965f4-136">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="965f4-137">実行時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="965f4-137">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="965f4-138">JD Edwards エンタープライズ サーバーにファイル転送機構が設定されます。イベントの完了により、生成された XML ドキュメントがそのサーバーのターゲット ディレクトリに転送されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-138">A file transport mechanism is established in the JD Edwards enterprise server to transport the resulting XML document, triggered by the event completion, to the target directory on that server.</span></span>  
  
-   <span data-ttu-id="965f4-139">BizTalk Server コンピューターには、エンタープライズ サーバーのディレクトリに対して割り当てられたドライブがあります。</span><span class="sxs-lookup"><span data-stu-id="965f4-139">The BizTalk Server computer has a mapped drive to the directory on the enterprise server.</span></span>  
  
-   <span data-ttu-id="965f4-140">受信ポートのトランスポート プロパティは、マップされたドライブに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="965f4-140">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="965f4-141">受信ポートではエンタープライズ サーバーによりディレクトリに送信されたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="965f4-141">The receive port receives messages posted to directory by the enterprise server.</span></span>  
  
-   <span data-ttu-id="965f4-142">ターゲットの名前空間を識別することによって、構成されている受信ポートに正しいメッセージが確実にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="965f4-142">The target namespace identification ensures that the correct messages are routed to the configured receive port.</span></span>  
  
-   <span data-ttu-id="965f4-143">受信ポートは、BizTalk Server の XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="965f4-143">The receive port submits the XML document to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="965f4-144">参照</span><span class="sxs-lookup"><span data-stu-id="965f4-144">See Also</span></span>  
 <span data-ttu-id="965f4-145">[JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="965f4-145">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="965f4-146">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="965f4-146">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)