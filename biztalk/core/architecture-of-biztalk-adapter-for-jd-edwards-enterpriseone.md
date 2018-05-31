---
title: BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ |Microsoft ドキュメント
description: デザイン時および実行時に BizTalk の JD Edwards EnterpriseOne アダプター デザイン時および実行時に、および送信イベント受信サービスを説明します。
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
ms.openlocfilehash: b495ee9a34cf464bd5cc11caed53c5df54948a49
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013761"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="c2d2d-103">BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c2d2d-103">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="c2d2d-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を使用すると、JD Edwards EnterpriseOne のビジネス関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="c2d2d-105">JD Edwards EnterpriseOne は、JDENet と呼ばれる独自のメッセージング アーキテクチャを使用して、クライアント コンピューターとサーバー コンピューター間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-105">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="c2d2d-106">JDENet は、Connector.jar および Kernel.jar という JAR ファイルにある JD Edwards EnterpriseOne コネクタ クラスによって実装されています。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-106">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="c2d2d-107">通信は、TCP/IP をトランスポート プロトコルとして使用して実装されており、既定のポートは 6009 または 6010 です。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="c2d2d-108">この値を設定する場所の詳細についてを参照してください[アイテムを BizTalk 管理コンソールに追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="c2d2d-109">次の図は、BizTalk Adapter for JD Edwards EnterpriseOne のアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-109">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="c2d2d-110">デザイン時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="c2d2d-110">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="c2d2d-111">デザイン時に、ターゲットの JD Edwards EnterpriseOne サーバーに接続するためのポートを作成し、アダプターを選択して、資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-111">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="c2d2d-112">Visual Studio 開発環境は、アダプター フレームワークを呼び出して、このポートのデザイン時情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-112">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="c2d2d-113">アダプターはこのポートに対して Browsingagent を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-113">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="c2d2d-114">BizTalk Server は、デザイン時にアダプターを呼び出して情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-114">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="c2d2d-115">Browsingagent は、要求を JD Edwards EnterpriseOne のネイティブ コードに変換し、ThinNet API 接続 (Connector.jar および Kernel.jar で確立される) を経由して、変換した要求を JD Edwards EnterpriseOne に送信します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-115">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="c2d2d-116">JD Edwards EnterpriseOne のモジュールの一覧が最初に取得され、Visual Studio 開発環境に送信されて、アダプター ウィザードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-116">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="c2d2d-117">ライブラリ名を表示し、次にモジュール名を表示して階層を展開できます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-117">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="c2d2d-118">特定のモジュールを選択すると、モジュール内のすべての関数のスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-118">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="c2d2d-119">アダプターは必要な情報を JD Edwards EnterpriseOne から取得し、browsingagent がスキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-119">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="c2d2d-120">スキーマは BizTalk Server プロジェクトのオーケストレーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-120">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="c2d2d-121">実行時の受信サービス</span><span class="sxs-lookup"><span data-stu-id="c2d2d-121">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="c2d2d-122">BizTalk Server は特定のポートでアダプターを呼び出してメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-122">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="c2d2d-123">ランタイム エージェントは XML を JDE のネイティブ コードに変換します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-123">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="c2d2d-124">ランタイム エージェントは ThinNet を経由して、送信ポートのトランスポート プロパティで指定された JD Edwards EnterpriseOne システムに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-124">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="c2d2d-125">データだけでなく、成功または失敗を示す応答ドキュメントを生成する、JD Edwards EnterpriseOne システムでマスター ビジネス関数が実行されるビジネス関数によって返されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-125">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="c2d2d-126">JD Edwards EnterpriseOne に送信されるメッセージは、単一メッセージ、単一応答のアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-126">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="c2d2d-127">複数のメッセージを同時に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-127">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="c2d2d-128">応答ドキュメントが ThinNet を通じて返され、XML に変換されて、BizTalk Server に送られます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-128">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="c2d2d-129">デザイン時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="c2d2d-129">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="c2d2d-130">イベント メタデータのシステム的な作成は利用できません。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-130">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="c2d2d-131">イベント ドキュメントの FAX を Visual Studio に提供し、スキーマを生成して、ターゲットの名前空間と共にプロジェクトに組み込めるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-131">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="c2d2d-132">実行時の送信イベント</span><span class="sxs-lookup"><span data-stu-id="c2d2d-132">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="c2d2d-133">ファイル トランスポート機構がそのコンピューター上のターゲット ディレクトリに、イベントの完了によってトリガーされる結果の XML ドキュメントのトランスポートを JD Edwards EnterpriseOne サーバーで確立されます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-133">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="c2d2d-134">BizTalk Server コンピューターには、EnterpriseOne サーバー上のディレクトリに対して割り当てられたドライブがあります。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-134">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="c2d2d-135">受信ポートのトランスポート プロパティは、マップされたドライブに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-135">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="c2d2d-136">受信ポートでは EnterpriseOne サーバーによりディレクトリに送信されたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-136">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="c2d2d-137">ターゲット名前空間の識別に正しいメッセージがルーティングされることを確認、構成された受信ポート</span><span class="sxs-lookup"><span data-stu-id="c2d2d-137">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="c2d2d-138">受信ポートは BizTalk Server に XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-138">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="c2d2d-139">便利な機能</span><span class="sxs-lookup"><span data-stu-id="c2d2d-139">More good stuff</span></span>
[<span data-ttu-id="c2d2d-140">BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c2d2d-140">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="c2d2d-141">アプリケーションのアイテムを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2d2d-141">Create the application artifacts</span></span>](../core/developing-applications2.md)  
[<span data-ttu-id="c2d2d-142">インポート、JD Edwards EnterpriseOne アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c2d2d-142">Import your JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="c2d2d-143">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="c2d2d-143">Use BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)  
<span data-ttu-id="c2d2d-144">[[トラブルシューティング]](../core/troubleshooting-jd-edwards-enterpriseone.md)</span><span class="sxs-lookup"><span data-stu-id="c2d2d-144">[Troubleshoot](../core/troubleshooting-jd-edwards-enterpriseone.md)</span></span>  
