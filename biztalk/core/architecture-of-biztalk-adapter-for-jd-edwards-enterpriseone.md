---
title: BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ |Microsoft Docs
description: デザイン時および実行時に BizTalk の JD Edwards EnterpriseOne アダプター デザイン時および実行時、および送信イベント受信サービスを説明します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7992262731532f2c9df6b29896f48f5f74e5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359362"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="4f0f5-103">BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="4f0f5-103">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="4f0f5-104">Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、JD Edwards EnterpriseOne のビジネス関数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="4f0f5-105">JD Edwards EnterpriseOne は、独自のメッセージング JDENet と呼ばれるアーキテクチャを使用してクライアントとサーバーのマシン間で通信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-105">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="4f0f5-106">JDENet は、Connector.jar および Kernel.jar という JAR ファイルを JD Edwards EnterpriseOne コネクタ クラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-106">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="4f0f5-107">通信は、既定のポートは 6009 または 6010 トランスポート プロトコルとして TCP/IP を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="4f0f5-108">この値を設定する場所の説明についてを参照してください[アーティファクトを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="4f0f5-109">次の図は、BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-109">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 <span data-ttu-id="4f0f5-110">![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")</span><span class="sxs-lookup"><span data-stu-id="4f0f5-110">![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="4f0f5-111">デザイン時に受信サービス</span><span class="sxs-lookup"><span data-stu-id="4f0f5-111">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="4f0f5-112">、デザイン時にアダプターを選択して、および、ターゲットの JD Edwards EnterpriseOne サーバーへの接続に資格情報を指定するポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-112">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="4f0f5-113">Visual Studio 開発環境では、このポートのデザイン時の情報を要求するためにアダプター フレームワークを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-113">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="4f0f5-114">アダプターは、このポートに Browsingagent を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-114">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="4f0f5-115">デザイン時に、BizTalk Server は、アダプターを呼び出すことで情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-115">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="4f0f5-116">Browsingagent は、要求を JD Edwards EnterpriseOne のネイティブ コードに変換し、JD Edwards EnterpriseOne ThinNet API 接続 (Connector.jar および Kernel.jar で確立された) を介して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-116">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="4f0f5-117">JD Edwards EnterpriseOne のモジュールの一覧が最初に返され、転送先に Visual Studio 開発環境、アダプター ウィザードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-117">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="4f0f5-118">ライブラリ名とモジュール名を表示することによって階層を展開できます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-118">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="4f0f5-119">特定のモジュールを選択すると、モジュール内のすべての関数のスキーマを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-119">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="4f0f5-120">アダプターから JD Edwards EnterpriseOne では、必要な情報を取得し、browsingagent がスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-120">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="4f0f5-121">スキーマは、BizTalk Server プロジェクトのオーケストレーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-121">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="4f0f5-122">実行時に受信サービス</span><span class="sxs-lookup"><span data-stu-id="4f0f5-122">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="4f0f5-123">BizTalk Server では、特定のポートでメッセージを送信するアダプターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-123">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="4f0f5-124">ランタイム エージェントは、XML を JDE のネイティブ コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-124">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="4f0f5-125">実行時のエージェントでは、送信ポートのトランスポートのプロパティで指定された JD Edwards EnterpriseOne システムを ThinNet を通じて要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-125">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="4f0f5-126">データだけでなく、成功または失敗を示す応答ドキュメントを生成し、JD Edwards EnterpriseOne システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-126">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="4f0f5-127">JD Edwards EnterpriseOne に送信されるメッセージは 1 つのメッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-127">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="4f0f5-128">同時に複数のメッセージを処理できません。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-128">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="4f0f5-129">応答ドキュメントが ThinNet を経由で送信される、XML に変換され、BizTalk Server に送信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-129">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="4f0f5-130">デザイン時にイベントを送信</span><span class="sxs-lookup"><span data-stu-id="4f0f5-130">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="4f0f5-131">イベント メタデータの体系的な作成はありません。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-131">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="4f0f5-132">イベント ドキュメントの複製は、スキーマを生成し、ターゲットの名前空間と共にプロジェクトに組み込むように Visual Studio を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-132">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="4f0f5-133">実行時にイベントを送信</span><span class="sxs-lookup"><span data-stu-id="4f0f5-133">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="4f0f5-134">ファイル転送機構は、そのコンピューター上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards EnterpriseOne サーバーで確立されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-134">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="4f0f5-135">BizTalk Server コンピューターには、EnterpriseOne サーバー上のディレクトリにマップされたドライブがあります。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-135">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="4f0f5-136">受信ポートのトランスポートのプロパティは、マップされたドライブに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-136">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="4f0f5-137">受信ポートは、EnterpriseOne サーバーによりディレクトリに送信されたが、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-137">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="4f0f5-138">ターゲット名前空間の id によりに正しいメッセージがルーティングされるようになります、構成された受信ポート</span><span class="sxs-lookup"><span data-stu-id="4f0f5-138">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="4f0f5-139">受信ポートは、BizTalk Server で XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="4f0f5-139">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="4f0f5-140">便利な機能</span><span class="sxs-lookup"><span data-stu-id="4f0f5-140">More good stuff</span></span>
[<span data-ttu-id="4f0f5-141">BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4f0f5-141">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="4f0f5-142">アプリケーション アイテムの作成</span><span class="sxs-lookup"><span data-stu-id="4f0f5-142">Create the application artifacts</span></span>](../core/developing-applications2.md)  
[<span data-ttu-id="4f0f5-143">インポート、JD Edwards EnterpriseOne のアプリ</span><span class="sxs-lookup"><span data-stu-id="4f0f5-143">Import your JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="4f0f5-144">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="4f0f5-144">Use BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)  
<span data-ttu-id="4f0f5-145">[[トラブルシューティング]](../core/troubleshooting-jd-edwards-enterpriseone.md)</span><span class="sxs-lookup"><span data-stu-id="4f0f5-145">[Troubleshoot](../core/troubleshooting-jd-edwards-enterpriseone.md)</span></span>  
