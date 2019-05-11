---
title: JD Edwards OneWorld のアーキテクチャ |Microsoft Docs
description: デザイン時および実行時に BizTalk の JD Edwards OneWorld アダプター デザイン時および実行時、および送信イベント受信サービスを説明します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e98b7196077d0754ef067d01a51b49b96dc8f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358987"
---
# <a name="architecture-of-jd-edwards-oneworld"></a><span data-ttu-id="5e134-103">JD Edwards OneWorld のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5e134-103">Architecture of JD Edwards OneWorld</span></span>
<span data-ttu-id="5e134-104">Microsoft の BizTalk Adapter for JD Edwards OneWorld では、JD Edwards OneWorld ビジネス関数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e134-104">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="5e134-105">JD Edwards OneWorld は、独自のメッセージング JDENet と呼ばれるアーキテクチャを使用してクライアントとサーバーのマシン間で通信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-105">JD Edwards OneWorld communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="5e134-106">JDENet は、Connector.jar および Kernel.jar という JAR ファイルを JD Edwards OneWorld コネクタ クラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-106">JDENet is implemented by the JD Edwards OneWorld connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="5e134-107">通信は、既定のポートは 6009 または 6010 トランスポート プロトコルとして TCP/IP を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="5e134-108">この値を設定する場所の説明についてを参照してください[アーティファクトを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e134-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="5e134-109">**BizTalk Adapter for JD Edwards OneWorld のアーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="5e134-109">**Architecture for BizTalk Adapter for JD Edwards OneWorld**</span></span>  
  
 <span data-ttu-id="5e134-110">![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")</span><span class="sxs-lookup"><span data-stu-id="5e134-110">![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")</span></span>  
  
 <span data-ttu-id="5e134-111">JD Edwards OneWorld ビジネス関数の呼び出しでは、2 つのメッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e134-111">Calls to JD Edwards OneWorld business functions require two messages:</span></span>  
  
-   <span data-ttu-id="5e134-112">最初のメッセージは、ビジネス関数を処理するサーバーの場所で応答します。</span><span class="sxs-lookup"><span data-stu-id="5e134-112">The first message responds with the location of the server that processes the business function.</span></span> <span data-ttu-id="5e134-113">これと呼ばれるテーブルのセットでルックアップを実行することによって実現*オブジェクト構成マッピング (OCM)* します。</span><span class="sxs-lookup"><span data-stu-id="5e134-113">This is accomplished by performing a lookup in a set of tables called *object configuration mapping (OCM)*.</span></span>  
  
-   <span data-ttu-id="5e134-114">2 番目のメッセージは、JD Edwards OneWorld との間を適切なサーバーに渡す引数を含む書式設定されたメッセージ バッファーを送信し、応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="5e134-114">The second message sends a formatted message buffer containing the arguments to pass to or from JD Edwards OneWorld to the appropriate server, and waits for a reply.</span></span> <span data-ttu-id="5e134-115">バッファーは、基になるの typedef に従って書式設定C++構造体。</span><span class="sxs-lookup"><span data-stu-id="5e134-115">The buffers are formatted according to the typedefs of the underlying C++ structs.</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="5e134-116">デザイン時に受信サービス</span><span class="sxs-lookup"><span data-stu-id="5e134-116">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="5e134-117">デザイン時にには、アダプターを選択、および、ターゲットの JD Edwards OneWorld サーバーへの接続に資格情報を指定のポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e134-117">At design time, you create your port, select the adapter, and provide credential information to connect to the target JD Edwards OneWorld server.</span></span> <span data-ttu-id="5e134-118">Visual Studio 開発環境では、このポートのデザイン時の情報を要求するためにアダプター フレームワークを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5e134-118">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="5e134-119">BizTalk Adapter for JD Edwards OneWorld では、このポートに対して Browsingagent を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e134-119">BizTalk Adapter for JD Edwards OneWorld uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="5e134-120">デザイン時に、BizTalk Server は、アダプターを呼び出すことで情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="5e134-120">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="5e134-121">Browsingagent は、要求を JD Edwards OneWorld のネイティブ コードに変換し、(コネクタと Kernel.jar で確立された)、ThinNet API 接続を JD Edwards OneWorld に要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-121">The Browsingagent converts the request into native JD Edwards OneWorld code and then transmits the requests to JD Edwards OneWorld through the ThinNet API connection (established in the Connector and Kernel.jars).</span></span>  
  
-   <span data-ttu-id="5e134-122">カスタム ビジネス関数は BTSREL インストールを通じてインストールされます。 マスター ビジネス関数を公開します。</span><span class="sxs-lookup"><span data-stu-id="5e134-122">A custom business function is installed through the BTSREL installation: it exposes the master business functions.</span></span>  
  
-   <span data-ttu-id="5e134-123">JD Edwards OneWorld のモジュールの一覧が最初に返され、転送先に Visual Studio で、アダプター ウィザードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-123">A list of modules in JD Edwards OneWorld is initially returned and transported to Visual Studio, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="5e134-124">ライブラリ名とモジュール名を表示する階層を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="5e134-124">You can expand the hierarchy to display the library name and module name.</span></span>  
  
-   <span data-ttu-id="5e134-125">特定のモジュールを選択すると、モジュール内のすべての関数のスキーマを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e134-125">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="5e134-126">アダプターは、JD Edwards OneWorld から、必要な情報を取得し、browsingagent がスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e134-126">The adapter obtains the required information from JD Edwards OneWorld, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="5e134-127">スキーマは、BizTalk Server プロジェクトのオーケストレーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-127">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="5e134-128">実行時に受信サービス</span><span class="sxs-lookup"><span data-stu-id="5e134-128">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="5e134-129">BizTalk Server は、BizTalk Adapter for JD Edwards OneWorld の特定のポートでメッセージの送信を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5e134-129">BizTalk Server calls the BizTalk Adapter for JD Edwards OneWorld to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="5e134-130">ランタイム エージェントは、XML を JD Edwards のネイティブ コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="5e134-130">The run-time agent converts the XML into native JD Edwards code.</span></span>  
  
-   <span data-ttu-id="5e134-131">ランタイム エージェントは、送信ポートのトランスポートのプロパティで指定された JD Edwards エンタープライズ システムに ThinNet を通じて要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-131">The run-time agent submits the request through the ThinNet to the JD Edwards enterprise system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="5e134-132">データだけでなく、成功または失敗を示す応答ドキュメントを生成し、JD Edwards システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5e134-132">The master business function is executed on the JD Edwards system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="5e134-133">JD Edwards OneWorld に送信されるメッセージは 1 つのメッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="5e134-133">The message sent to JD Edwards OneWorld is a single message, single reply architecture.</span></span> <span data-ttu-id="5e134-134">同時に複数のメッセージを処理できません。</span><span class="sxs-lookup"><span data-stu-id="5e134-134">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="5e134-135">応答ドキュメントが ThinNet を経由で送信される、XML に変換され、BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-135">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="5e134-136">デザイン時にイベントを送信</span><span class="sxs-lookup"><span data-stu-id="5e134-136">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="5e134-137">イベント メタデータの体系的な作成はありません。</span><span class="sxs-lookup"><span data-stu-id="5e134-137">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="5e134-138">イベント ドキュメントの複製は、スキーマを生成し、ターゲットの名前空間と共にプロジェクトに組み込むように Visual Studio を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e134-138">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="5e134-139">実行時にイベントを送信</span><span class="sxs-lookup"><span data-stu-id="5e134-139">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="5e134-140">ファイル転送機構は、そのサーバー上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards エンタープライズ サーバーで確立されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-140">A file transport mechanism is established in the JD Edwards enterprise server to transport the resulting XML document, triggered by the event completion, to the target directory on that server.</span></span>  
  
-   <span data-ttu-id="5e134-141">BizTalk Server コンピューターには、エンタープライズ サーバー上のディレクトリにマップされたドライブがあります。</span><span class="sxs-lookup"><span data-stu-id="5e134-141">The BizTalk Server computer has a mapped drive to the directory on the enterprise server.</span></span>  
  
-   <span data-ttu-id="5e134-142">受信ポートのトランスポートのプロパティは、マップされたドライブに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="5e134-142">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="5e134-143">受信ポートは、エンタープライズ サーバーによりディレクトリに送信されたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-143">The receive port receives messages posted to directory by the enterprise server.</span></span>  
  
-   <span data-ttu-id="5e134-144">ターゲット名前空間 id によりに正しいメッセージがルーティングされる受信ポートが構成されています。</span><span class="sxs-lookup"><span data-stu-id="5e134-144">The target namespace identification ensures that the correct messages are routed to the configured receive port.</span></span>  
  
-   <span data-ttu-id="5e134-145">受信ポートは、BizTalk Server に XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="5e134-145">The receive port submits the XML document to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e134-146">参照</span><span class="sxs-lookup"><span data-stu-id="5e134-146">See Also</span></span>  
 <span data-ttu-id="5e134-147">[BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="5e134-147">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="5e134-148">計画および設計</span><span class="sxs-lookup"><span data-stu-id="5e134-148">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)