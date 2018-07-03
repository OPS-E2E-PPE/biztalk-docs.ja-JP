---
title: サービスのコンポーネント指向のソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
- service solution tutorial, assemblies
- service solution tutorial, components [BizTalk Server]
- service solution tutorial, client applications
- assemblies, service solutions
- orchestrations, service solutions
- client applications, service solutions
- back-end systems
- service solution tutorial, orchestrations
- service solution tutorial, back-end applications
ms.assetid: 97b7b754-abfb-48f9-87bf-7fe171121166
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 888372550e62e72f21e9d397ac35d17f68c1a187
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017151"
---
# <a name="components-of-the-service-oriented-solution"></a><span data-ttu-id="a6f20-102">サービスのコンポーネント指向のソリューション</span><span class="sxs-lookup"><span data-stu-id="a6f20-102">Components of the Service Oriented Solution</span></span>
<span data-ttu-id="a6f20-103">このセクションでは、サービス指向ソリューションの主な BizTalk Server コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-103">This section describes the major BizTalk Server components of the Service Oriented Solution.</span></span> <span data-ttu-id="a6f20-104">次の図は、ソリューションの主なコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-104">The following diagram shows the major components of the solution:</span></span>  
  
 <span data-ttu-id="a6f20-105">![サービス指向ソリューションのフロー ダイアグラム](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")</span><span class="sxs-lookup"><span data-stu-id="a6f20-105">![Service Oriented Solution Flow Diagram](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")</span></span>  
  
 <span data-ttu-id="a6f20-106">サービス指向ソリューションには、3 つのバージョンのオーケストレーションがあります。</span><span class="sxs-lookup"><span data-stu-id="a6f20-106">The Service Oriented solution has three versions of the orchestrations:</span></span>  
  
- <span data-ttu-id="a6f20-107">3 つのバックエンド アプリケーションのすべてがスタブとして作成されるバージョン</span><span class="sxs-lookup"><span data-stu-id="a6f20-107">A version in which all three of the back-end applications are stubbed out</span></span>  
  
- <span data-ttu-id="a6f20-108">3 つのバックエンド アプリケーションのすべてがインラインで呼び出されるバージョン</span><span class="sxs-lookup"><span data-stu-id="a6f20-108">One in which all three back-end applications are invoked inline</span></span>  
  
- <span data-ttu-id="a6f20-109">アプリケーションに接続するためにアダプタを使用するバージョン</span><span class="sxs-lookup"><span data-stu-id="a6f20-109">A version that uses adapters to connect to the applications.</span></span>  
  
  <span data-ttu-id="a6f20-110">オーケストレーションのすべてのバージョンは、SDK\Senarios\SO\BTSSoln\Orchestrations ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="a6f20-110">All versions of the orchestrations appear in the SDK\Senarios\SO\BTSSoln\Orchestrations directory.</span></span>  
  
  <span data-ttu-id="a6f20-111">インライン バージョンのオーケストレーションでは、ソリューション内で要求と応答の間の待機時間が最短になります。</span><span class="sxs-lookup"><span data-stu-id="a6f20-111">The inline version of the orchestrations provides the lowest latency time within the solution between requests and responses.</span></span>  
  
  <span data-ttu-id="a6f20-112">ソース ファイルについては、次を参照してください。[サービス指向ソリューションのファイルの在庫](../core/file-inventory-for-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-112">For information about the source files, see [File Inventory for the Service Oriented Solution](../core/file-inventory-for-the-service-oriented-solution.md).</span></span>  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a><span data-ttu-id="a6f20-113">サービス指向ソリューションのオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="a6f20-113">Orchestrations in the Service Oriented Solution</span></span>  
 <span data-ttu-id="a6f20-114">3 つのオーケストレーション**CustomerServiceReceiveSend**、 **CustomerServiceNativeRequestResponse**、および**CustomerService**ソリューションの大部分を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-114">Three orchestrations, **CustomerServiceReceiveSend**, **CustomerServiceNativeRequestResponse**, and **CustomerService** compose the bulk of the solution.</span></span> <span data-ttu-id="a6f20-115">**CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**オーケストレーションが呼び出すフロント エンドとして機能、 **CustomerService**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="a6f20-115">The **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse** orchestrations act as front-ends that call the **CustomerService** orchestration.</span></span> <span data-ttu-id="a6f20-116">**CustomerService**オーケストレーション作業のほとんどでは、バックエンド アプリケーションに要求を送信、返信を収集、1 つのメッセージに返信を結合すること、およびフロント エンドを適切なメッセージを送信します。オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="a6f20-116">The **CustomerService** orchestration does most of the work—sending requests to the back-end applications, gathering the replies, combining the replies into a single message, and sending the message to the appropriate front-end orchestration.</span></span> <span data-ttu-id="a6f20-117">フロント エンド オーケストレーションを呼び出すため、 **CustomerService**オーケストレーション、フロント エンド オーケストレーションまで、 **CustomerService**オーケストレーションが終了します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-117">Because the front-end orchestrations call the **CustomerService** orchestration, the front-end orchestrations wait until the **CustomerService** orchestration finishes.</span></span>  
  
 <span data-ttu-id="a6f20-118">ソリューションが公開、 **CustomerServiceNativeRequestResponse**オーケストレーションを Web サービスとして。</span><span class="sxs-lookup"><span data-stu-id="a6f20-118">The solution exposes the **CustomerServiceNativeRequestResponse** orchestration as a Web service.</span></span> <span data-ttu-id="a6f20-119">**CustomerServiceReceiveSend**オーケストレーションは、MQSeries キューからメッセージを受け取る。</span><span class="sxs-lookup"><span data-stu-id="a6f20-119">The **CustomerServiceReceiveSend** orchestration takes messages from an MQSeries queue.</span></span>  
  
## <a name="back-end-applications"></a><span data-ttu-id="a6f20-120">バックエンド アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a6f20-120">Back-end Applications</span></span>  
 <span data-ttu-id="a6f20-121">サービス指向ソリューションは、3 つのバックエンド アプリケーションと通信します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-121">The Service Oriented solution communicates with three back-end applications:</span></span>  
  
- <span data-ttu-id="a6f20-122">**PaymentTracker**アプリケーションには、最近の支払いのシミュレートされた一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="a6f20-122">The **PaymentTracker** application returns a simulated list of recent payments.</span></span> <span data-ttu-id="a6f20-123">**PaymentTracker** MQSeries キューから要求を読み取り、別の MQSeries キューへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-123">**PaymentTracker** reads the request from an MQSeries queue and sends the response to another MQSeries queue.</span></span>  
  
- <span data-ttu-id="a6f20-124">**PendingTransaction**アプリケーションは、顧客アカウントに対して保留中のトランザクションの合計を報告します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-124">The **PendingTransaction** application reports the sum of transactions pending against the customer account.</span></span> <span data-ttu-id="a6f20-125">このアプリケーションは、Microsoft Host Integration Server (HIS) を使用してメインフレーム コンピュータ上の CICS/COBOL プログラムと通信するWeb サービスです。</span><span class="sxs-lookup"><span data-stu-id="a6f20-125">The application is a Web service that, in turn, uses Microsoft Host Integration Server (HIS) to communicate with a CICS/COBOL program on a mainframe computer.</span></span>  
  
- <span data-ttu-id="a6f20-126">SAP アプリケーションは、顧客の全体的な信用限度額に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-126">The SAP application provides information about the customer's overall credit limit.</span></span> <span data-ttu-id="a6f20-127">ソリューションは Web サービスとして SAP アプリケーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-127">The solution connects to the SAP application as a Web service.</span></span> <span data-ttu-id="a6f20-128">アプリケーションは [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] の SAP アダプターを使用して SAP システムと通信します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-128">The application uses the SAP adapter in [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] to communicate with a SAP system.</span></span>  
  
## <a name="pipelines"></a><span data-ttu-id="a6f20-129">パイプライン</span><span class="sxs-lookup"><span data-stu-id="a6f20-129">Pipelines</span></span>  
 <span data-ttu-id="a6f20-130">サービス指向ソリューションは、2 つの場所で既定のパイプラインを使用して: の受信パイプライン、 **CustomerServiceReceiveSend**オーケストレーション、および**CustomerService**オーケストレーションの送信パイプラインを**PaymentTracker**します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-130">The Service Oriented solution uses default pipelines except in two places: the receive pipeline for the **CustomerServiceReceiveSend** orchestration, and the **CustomerService** orchestration's send pipeline to the **PaymentTracker**.</span></span> <span data-ttu-id="a6f20-131">これらのパイプラインは両方ともカスタム コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-131">Both pipelines use custom components.</span></span>  
  
 <span data-ttu-id="a6f20-132">受信パイプライン**CustomerServiceReceiveSend** 、カスタム パーティの解決コンポーネントを含む**SSO Ticket Issuer Pipeline Component**します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-132">The receive pipeline for **CustomerServiceReceiveSend** includes a custom party resolution component, **SSO Ticket Issuer Pipeline Component**.</span></span> <span data-ttu-id="a6f20-133">メッセージを**CustomerServiceReceiveSend**オーケストレーションが受信資格情報はありません。</span><span class="sxs-lookup"><span data-stu-id="a6f20-133">The messages that the **CustomerServiceReceiveSend** orchestration receives do not have credentials.</span></span> <span data-ttu-id="a6f20-134">このオーケストレーションは、メッセージが音声自動応答装置 (IVR) から送信された場合に行われる処理をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="a6f20-134">This simulates what would happen if the messages came from an Interactive Voice Response system.</span></span> <span data-ttu-id="a6f20-135">カスタム パイプライン コンポーネントが、BizTalk 受信ホストのサービス アカウントを使用して資格情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6f20-135">The custom pipeline component adds credentials using the service account of the BizTalk receive host.</span></span>  
  
 <span data-ttu-id="a6f20-136">これに対して、メッセージ、 **CustomerSericeNativeRequestResponse**オーケストレーションを既に受信資格情報を持っています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-136">In contrast, the messages the **CustomerSericeNativeRequestResponse** orchestration receives already have credentials.</span></span> <span data-ttu-id="a6f20-137">Web サービスの仮想フォルダが統合セキュリティ用に構成され、SOAP の受信場所がエンタープライズ シングル サインオン (SSO) を統合するように構成されているので、SOAP アダプタによってメッセージのチケットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6f20-137">Because the virtual folder for the Web service is configured for integrated security and the SOAP receive location is configured to integrate Enterprise Single Sign-On (SSO), the SOAP adapter generates a ticket for the message.</span></span>  
  
 <span data-ttu-id="a6f20-138">その他のカスタムのパイプラインが表示されます、 **CustomerService**送信パイプライン、 **PaymentTracker**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a6f20-138">The other custom pipeline appears in the **CustomerService** send pipeline to the **PaymentTracker** application.</span></span> <span data-ttu-id="a6f20-139">MQSeries ヘッダー設定パイプライン コンポーネントによって、2 つの MQSeries メッセージ ヘッダー プロパティの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a6f20-139">The component, MQSeries Header Setter Pipeline Component, sets values for two MQSeries message header properties.</span></span> <span data-ttu-id="a6f20-140">コンポーネントが 1 つ目のメッセージのデータ形式を設定 (**MQMD_Format**)、メッセージがの形式であることを示す、 **MQCIH**構造、CICS プログラムと通信するための一般的な。</span><span class="sxs-lookup"><span data-stu-id="a6f20-140">The component sets the first, the Message Data Format (**MQMD_Format**), to indicate the message is in the form of an **MQCIH** structure, a structure commonly used to communicate with CICS programs.</span></span> <span data-ttu-id="a6f20-141">2 番目のデータ自体の形式内で、 **MQCIH**構造 (**MQCIH_Format**) をメッセージが文字列に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-141">The second, the format of the data itself within the **MQCIH** structure (**MQCIH_Format**),is set to show the message is a string.</span></span>  
  
 <span data-ttu-id="a6f20-142">使用して、 **MQCIH**形式を使用すると、ユーザー ID とパスワードを渡す、 **MQCIH**構造体。</span><span class="sxs-lookup"><span data-stu-id="a6f20-142">Using the **MQCIH** format enables you to pass the user ID and password in the **MQCIH** structure.</span></span> <span data-ttu-id="a6f20-143">SSO 関連アプリケーションは、Payment Tracking システムのユーザーに渡された Id に、BizTalk アプリケーションの Windows ユーザー ID をマップ、 **MQCIH**構造体。</span><span class="sxs-lookup"><span data-stu-id="a6f20-143">SSO affiliate applications map the BizTalk application's Windows user ID to the Payment Tracking System's user IDs passed in the **MQCIH** structure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6f20-144">ソリューションのインライン バージョンは、オーケストレーションから同じパイプラインを呼び出して使用するので、</span><span class="sxs-lookup"><span data-stu-id="a6f20-144">The inline version of the solution uses the same pipelines by calling them from the orchestration.</span></span> <span data-ttu-id="a6f20-145">パイプライン コードを再使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a6f20-145">This enables re-use of the pipeline code.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="a6f20-146">クライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a6f20-146">Client Application</span></span>  
 <span data-ttu-id="a6f20-147">ソリューションには、C# で記述されたクライアント アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-147">The solution includes a client application written in C#.</span></span> <span data-ttu-id="a6f20-148">このクライアント アプリケーションを使用して、要求を SOAP または MQSeries メッセージとして送信し、結果を検証できます。</span><span class="sxs-lookup"><span data-stu-id="a6f20-148">You can use the application to send requests as SOAP or MQSeries messages, and examine the results.</span></span>  
  
## <a name="other-assemblies"></a><span data-ttu-id="a6f20-149">その他のアセンブリ</span><span class="sxs-lookup"><span data-stu-id="a6f20-149">Other Assemblies</span></span>  
 <span data-ttu-id="a6f20-150">アプリケーションには、上の概要図に示されていない補助アセンブリがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-150">The application includes several auxiliary assemblies not shown in the summary diagram above.</span></span> <span data-ttu-id="a6f20-151">**ユーティリティ**ソリューションのアセンブリのユーティリティ関数。</span><span class="sxs-lookup"><span data-stu-id="a6f20-151">The **Utilities** assembly utility functions for the solution.</span></span>  
  
 <span data-ttu-id="a6f20-152">**ErrorHelper**アセンブリには、メッセージ、エラー コードに変換し、エラー メッセージをエラー コードに変換するクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-152">The **ErrorHelper** assembly contains classes to translate error codes into messages, and to convert error messages to error codes.</span></span>  
  
 <span data-ttu-id="a6f20-153">**ServiceLevelTracking**アセンブリには、ビジネス アクティビティ監視 (BAM) API を使用して、サービス レベル アグリーメントによってデータを追跡するヘルパー メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6f20-153">The **ServiceLevelTracking** assembly includes helper methods using the Business Activity Monitoring (BAM) API to track service-level agreement data.</span></span>  
  
 <span data-ttu-id="a6f20-154">**ConfigHelper**アセンブリにはからソリューションの構成値を取得するヘルパ メソッドが含まれています、 **SSOConfigStore**アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a6f20-154">The **ConfigHelper** assembly contains helper methods to retrieve configuration values for the solution from the **SSOConfigStore** application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f20-155">参照</span><span class="sxs-lookup"><span data-stu-id="a6f20-155">See Also</span></span>  
 <span data-ttu-id="a6f20-156">[開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="a6f20-156">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="a6f20-157">サービス指向ソリューションのファイルの在庫</span><span class="sxs-lookup"><span data-stu-id="a6f20-157">File Inventory for the Service Oriented Solution</span></span>](../core/file-inventory-for-the-service-oriented-solution.md)