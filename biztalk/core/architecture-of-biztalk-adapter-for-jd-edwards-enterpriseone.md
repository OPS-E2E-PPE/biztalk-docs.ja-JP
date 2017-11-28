---
title: "BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 828d0ed6affc44edbf49beb204cd4afe21196747
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="e9877-102">BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e9877-102">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="e9877-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を使用すると、JD Edwards EnterpriseOne のビジネス関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e9877-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="e9877-104">JD Edwards EnterpriseOne は、JDENet と呼ばれる独自のメッセージング アーキテクチャを使用して、クライアント コンピューターとサーバー コンピューター間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="e9877-104">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="e9877-105">JDENet は、Connector.jar および Kernel.jar という JAR ファイルにある JD Edwards EnterpriseOne コネクタ クラスによって実装されています。</span><span class="sxs-lookup"><span data-stu-id="e9877-105">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="e9877-106">通信は、TCP/IP をトランスポート プロトコルとして使用して実装されており、既定のポートは 6009 または 6010 です。</span><span class="sxs-lookup"><span data-stu-id="e9877-106">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="e9877-107">この値を設定する場所の詳細についてを参照してください[JD Edwards OneWorld トランスポートのプロパティを設定する方法](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e9877-107">For a description of where this value is set, see [How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md).</span></span>  
  
 <span data-ttu-id="e9877-108">次の図は、BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="e9877-108">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="e9877-109">デザイン時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="e9877-109">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="e9877-110">デザイン時に、ターゲットの JD Edwards EnterpriseOne サーバーに接続するためのポートを作成し、アダプターを選択して、資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="e9877-110">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="e9877-111">Visual Studio 開発環境は、アダプター フレームワークを呼び出して、このポートのデザイン時情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="e9877-111">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="e9877-112">アダプターはこのポートに対して Browsingagent を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9877-112">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="e9877-113">BizTalk Server は、デザイン時にアダプターを呼び出して情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="e9877-113">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="e9877-114">Browsingagent は、要求を JD Edwards EnterpriseOne のネイティブ コードに変換し、ThinNet API 接続 (Connector.jar および Kernel.jar で確立される) を経由して、変換した要求を JD Edwards EnterpriseOne に送信します。</span><span class="sxs-lookup"><span data-stu-id="e9877-114">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="e9877-115">JD Edwards EnterpriseOne のモジュールの一覧が最初に取得され、Visual Studio 開発環境に送信されて、アダプター ウィザードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e9877-115">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="e9877-116">ライブラリ名を表示し、次にモジュール名を表示して階層を展開できます。</span><span class="sxs-lookup"><span data-stu-id="e9877-116">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="e9877-117">特定のモジュールを選択すると、モジュール内のすべての関数のスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9877-117">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="e9877-118">アダプターは必要な情報を JD Edwards EnterpriseOne から取得し、browsingagent がスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9877-118">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="e9877-119">スキーマは BizTalk Server プロジェクトのオーケストレーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e9877-119">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="e9877-120">実行時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="e9877-120">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="e9877-121">BizTalk Server は特定のポートでアダプターを呼び出してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e9877-121">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="e9877-122">ランタイム エージェントは XML を JDE のネイティブ コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="e9877-122">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="e9877-123">ランタイム エージェントは ThinNet を経由して、送信ポートのトランスポート プロパティで指定された JD Edwards EnterpriseOne システムに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="e9877-123">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="e9877-124">データだけでなく、成功または失敗を示す応答ドキュメントを生成する、JD Edwards EnterpriseOne システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="e9877-124">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="e9877-125">JD Edwards EnterpriseOne に送信されるメッセージは、単一メッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="e9877-125">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="e9877-126">複数のメッセージを同時に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9877-126">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="e9877-127">応答ドキュメントが ThinNet を通じて返され、XML に変換されて、BizTalk Server に送られます。</span><span class="sxs-lookup"><span data-stu-id="e9877-127">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="e9877-128">デザイン時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="e9877-128">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="e9877-129">イベント メタデータのシステム的な作成は利用できません。</span><span class="sxs-lookup"><span data-stu-id="e9877-129">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="e9877-130">イベント ドキュメントの FAX を Visual Studio に提供し、スキーマを生成して、ターゲットの名前空間と共にプロジェクトに組み込めるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9877-130">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="e9877-131">実行時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="e9877-131">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="e9877-132">ファイル トランスポート機構がそのコンピューター上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards EnterpriseOne サーバーで確立されます。</span><span class="sxs-lookup"><span data-stu-id="e9877-132">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="e9877-133">BizTalk Server コンピューターには、EnterpriseOne サーバー上のディレクトリに対して割り当てられたドライブがあります。</span><span class="sxs-lookup"><span data-stu-id="e9877-133">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="e9877-134">受信ポートのトランスポート プロパティは、マップされたドライブに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="e9877-134">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="e9877-135">受信ポートでは EnterpriseOne サーバーによりディレクトリに送信されたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="e9877-135">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="e9877-136">ターゲット名前空間の識別に正しいメッセージがルーティングされることを確認、構成された受信ポート</span><span class="sxs-lookup"><span data-stu-id="e9877-136">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="e9877-137">受信ポートは BizTalk Server に XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="e9877-137">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9877-138">参照</span><span class="sxs-lookup"><span data-stu-id="e9877-138">See Also</span></span>  
 [<span data-ttu-id="e9877-139">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e9877-139">Planning and Architecture</span></span>](../core/planning-and-architecture8.md)