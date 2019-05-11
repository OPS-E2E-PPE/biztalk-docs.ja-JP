---
title: インストールして、動的解決サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 918b9e5d2f5ad4a3aeb0db54d54cdab943198cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395120"
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a><span data-ttu-id="d379b-102">インストールして、動的解決サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d379b-102">Installing and Running the Dynamic Resolution Sample</span></span>
<span data-ttu-id="d379b-103">動的解決サンプルでは、ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントの一般的な使用シナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="d379b-103">The Dynamic Resolution sample demonstrates typical usage scenarios for the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components.</span></span> <span data-ttu-id="d379b-104">コンポーネントを使用を動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し解決してオーケストレーションを使用しなくても、メッセージング レベルでの Microsoft BizTalk マップを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d379b-104">It demonstrates how you can use the components to dynamically resolve endpoint location, set routing properties, and resolve and execute Microsoft BizTalk maps at the messaging level without using an orchestration.</span></span> <span data-ttu-id="d379b-105">一方向と双方向の両方のメッセージング パターンも示します。</span><span class="sxs-lookup"><span data-stu-id="d379b-105">It also demonstrates both one-way and two-way messaging patterns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d379b-106">内での解決メカニズムをよく理解しておく場合に最適な結果を得るのため、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、実行する必要があります、[をインストールして、リゾルバー サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)動的解決サンプルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="d379b-106">For optimum results when familiarizing yourself with the resolution mechanism within the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you should run the [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md) before you run the Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="d379b-107">サンプル アプリケーションを含む 2 つの受信場所と、動的解決のコンポーネントのユース ケースを複数を示すために、サンプルを使用して 2 つの動的送信ポート。</span><span class="sxs-lookup"><span data-stu-id="d379b-107">The sample application contains two receive locations and two dynamic send ports, which the sample uses to demonstrate multiple use cases for the dynamic resolution components.</span></span> <span data-ttu-id="d379b-108">各ユース ケースでは、競合回避モジュールと解像度でアダプター プロバイダーとの組み合わせで使用する場合に、アダプター プロバイダー フレームワークが疎結合のメッセージング ソリューションのさまざまな基礎を提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d379b-108">Each use case shows how the resolvers and adapter providers in the Resolution and Adapter Provider Framework, when used in combination, can provide the basis for a variety of loosely coupled messaging solutions.</span></span>  
  
## <a name="one-way-messaging-scenarios"></a><span data-ttu-id="d379b-109">一方向メッセージング シナリオ</span><span class="sxs-lookup"><span data-stu-id="d379b-109">One-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="d379b-110">すべて一方向 (を除く、XPATH の競合回避モジュールを使用する 1 つ) のシナリオの使用を \Source\Samples\DynamicResolution\Test\Data フォルダーにあるファイル NAOrderDoc.xml、メッセージング、受信への入力としてという名前の場所 DynamicResolution_FILE します。</span><span class="sxs-lookup"><span data-stu-id="d379b-110">All one-way messaging scenarios (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml, located in the \Source\Samples\DynamicResolution\Test\Data folder, as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="d379b-111">7 つの一方向メッセージングの例は、一意のバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d379b-111">There are seven one-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="two-way-messaging-scenarios"></a><span data-ttu-id="d379b-112">双方向メッセージング シナリオ</span><span class="sxs-lookup"><span data-stu-id="d379b-112">Two-Way Messaging Scenarios</span></span>  
 <span data-ttu-id="d379b-113">すべての双方向メッセージング シナリオでは、ESB のサンプルを使用します。NorthAmericanServices Web サービスがある http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx 要求メッセージを BizTalk に公開します。</span><span class="sxs-lookup"><span data-stu-id="d379b-113">All two-way messaging scenarios use the sample ESB.NorthAmericanServices Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx to publish the request message into BizTalk.</span></span> <span data-ttu-id="d379b-114">Microsoft InfoPath を使用してこの Web サービスを実行するかから使用可能な Storm などのユーティリティを使って[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)します。</span><span class="sxs-lookup"><span data-stu-id="d379b-114">You can execute this Web service using Microsoft InfoPath or through a utility such as the Storm available from [CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409).</span></span>  
  
 <span data-ttu-id="d379b-115">それぞれの例は、ESB のサンプル メッセージを送信するエンドポイントの URL を動的に解決します。CanadianServices Web サービスがある http://localhost/ESB.CanadianServices/SubmitPOService.asmxします。</span><span class="sxs-lookup"><span data-stu-id="d379b-115">Each example dynamically resolves the endpoint URL to submit the message to the sample ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="d379b-116">例を実行するか、 **submitOrder**アクションまたは**submitPurchase**解決プロセスの結果に応じて、アクション。</span><span class="sxs-lookup"><span data-stu-id="d379b-116">The example will execute either the **submitOrder** action or the **submitPurchase** action, depending on the results of the resolution process.</span></span> <span data-ttu-id="d379b-117">双方向メッセージング シナリオの受信場所では、DynamicResolutionReqResp_SOAP です。</span><span class="sxs-lookup"><span data-stu-id="d379b-117">The receive location for two-way messaging scenarios is DynamicResolutionReqResp_SOAP.</span></span> <span data-ttu-id="d379b-118">10 の双方向メッセージングの例は、一意のバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d379b-118">There are 10 two-way messaging examples, all represented by a unique binding file that you must import before you execute each example.</span></span>  
  
## <a name="binding-files"></a><span data-ttu-id="d379b-119">バインド ファイル</span><span class="sxs-lookup"><span data-stu-id="d379b-119">Binding Files</span></span>  
 <span data-ttu-id="d379b-120">このサンプルのバインド ファイルは \Source\Samples\DynamicResolution\Samples\Release という名前のフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="d379b-120">The binding files for this sample are located in the folder named \Source\Samples\DynamicResolution\Samples\Release.</span></span>  
  
 <span data-ttu-id="d379b-121">すべてのバインド ファイルの名前は、個別に適用する例を示す値を続けて GlobalBank.ESB.DynamicResolution_SubmitOrder_To から始まります。</span><span class="sxs-lookup"><span data-stu-id="d379b-121">The binding file names all start with GlobalBank.ESB.DynamicResolution_SubmitOrder_To, followed by an indication of the individual example to which they apply.</span></span> <span data-ttu-id="d379b-122">たとえば、「ファイルの受信ファイルの送信には、静的リゾルバーを使用して」の例のバインド ファイルには、GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml です。</span><span class="sxs-lookup"><span data-stu-id="d379b-122">For example, the binding file for the "File Inbound to File Outbound using the STATIC Resolver" example is GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml.</span></span>  
  
 <span data-ttu-id="d379b-123">基になる、GlobalBank.ESB BizTalk アプリケーションにファイルが表示されるバインドのいずれかをインポートするたびにサンプル アプリケーション内の位置がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="d379b-123">Every time you import one of the binding files into the GlobalBank.ESB BizTalk application, the underlying receive location within the sample application is reset.</span></span> <span data-ttu-id="d379b-124">受信ポート名に関連付けられている動的送信ポート フィルター。</span><span class="sxs-lookup"><span data-stu-id="d379b-124">The associated dynamic send port filters on the receive port name.</span></span> <span data-ttu-id="d379b-125">そのため、テストを実行するだけのバインド ファイルのいずれかとドロップするか、適切に名前付きのメッセージを (一方向メッセージング シナリオ) の入力フォルダーにインポートか InfoPath、Storm ユーティリティ、またはその他を使用して NorthAmerican Web サービスを呼び出す適切なクライアント。</span><span class="sxs-lookup"><span data-stu-id="d379b-125">Therefore, to execute a test, you just import one of the binding files and either drop the appropriately named message into the input folder (for one-way messaging scenarios) or call the NorthAmerican Web service using InfoPath, the Storm utility, or any other suitable client.</span></span>  
  
## <a name="sample-dependencies"></a><span data-ttu-id="d379b-126">サンプルの依存関係</span><span class="sxs-lookup"><span data-stu-id="d379b-126">Sample Dependencies</span></span>  
 <span data-ttu-id="d379b-127">動的解決サンプル数のコア ESB インストールの一部であるアセンブリに依存しています。</span><span class="sxs-lookup"><span data-stu-id="d379b-127">The Dynamic Resolution sample has dependencies on a number of assemblies that are part of the core ESB installation.</span></span> <span data-ttu-id="d379b-128">これらのアセンブリ、次に示します。</span><span class="sxs-lookup"><span data-stu-id="d379b-128">These assemblies are the following:</span></span>  
  
- <span data-ttu-id="d379b-129">**Microsoft.Practices.ESB.PipelineComponents.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-129">**Microsoft.Practices.ESB.PipelineComponents.dll**.</span></span> <span data-ttu-id="d379b-130">これには、ESB ディスパッチャー パイプライン コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d379b-130">This contains the ESB Dispatcher Pipeline component.</span></span>  
  
- <span data-ttu-id="d379b-131">**Microsoft.Practices.ESB.Resolver.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-131">**Microsoft.Practices.ESB.Resolver.dll**.</span></span> <span data-ttu-id="d379b-132">これは、パイプラインによって呼び出される Resolver Manager を実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-132">This implements the Resolver Manager called by the pipeline.</span></span>  
  
- <span data-ttu-id="d379b-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-133">**Microsoft.Practices.ESB.Resolver.BRE.dll**.</span></span> <span data-ttu-id="d379b-134">これは、ビジネス ルール エンジンのリゾルバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-134">This implements the Business Rules Engine Resolver.</span></span>  
  
- <span data-ttu-id="d379b-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-135">**Microsoft.Practices.ESB.Resolver.STATIC.dll**.</span></span> <span data-ttu-id="d379b-136">これは、静的な競合回避モジュールを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-136">This implements the STATIC Resolver.</span></span>  
  
- <span data-ttu-id="d379b-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-137">**Microsoft.Practices.ESB.Resolver.UDDI.dll**.</span></span> <span data-ttu-id="d379b-138">これは、UDDI リゾルバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-138">This implements the UDDI Resolver.</span></span>  
  
- <span data-ttu-id="d379b-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-139">**Microsoft.Practices.ESB.Resolver.UDDI3.dll**.</span></span> <span data-ttu-id="d379b-140">これは、UDDI3 リゾルバーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-140">This implements the UDDI3 Resolver.</span></span>  
  
- <span data-ttu-id="d379b-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-141">**Microsoft.Practices.ESB.Resolver.XPATH.dll**.</span></span> <span data-ttu-id="d379b-142">これは、XPATH の競合回避モジュールを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-142">This implements the XPATH Resolver.</span></span>  
  
- <span data-ttu-id="d379b-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-143">**Microsoft.Practices.ESB.Resolver.Schemas.dll**.</span></span> <span data-ttu-id="d379b-144">これには、競合回避モジュールのスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d379b-144">This contains the resolver schemas.</span></span>  
  
- <span data-ttu-id="d379b-145">**Microsoft.Practices.ESB.Adapter.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-145">**Microsoft.Practices.ESB.Adapter.dll**.</span></span> <span data-ttu-id="d379b-146">これは、アダプター マネージャーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-146">This implements the adapter manager.</span></span>  
  
- <span data-ttu-id="d379b-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-147">**Microsoft.Practices.ESB.Adapter.FTP.dll**.</span></span> <span data-ttu-id="d379b-148">これは、FTP アダプターのプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-148">This implements the FTP adapter provider.</span></span>  
  
- <span data-ttu-id="d379b-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-149">**Microsoft.Practices.ESB.Adapter.FILE.dll**.</span></span> <span data-ttu-id="d379b-150">これは、ファイル アダプターのプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-150">This implements the FILE adapter provider.</span></span>  
  
- <span data-ttu-id="d379b-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-151">**Microsoft.Practices.ESB.Adapter.MQSeries.dll**.</span></span> <span data-ttu-id="d379b-152">これは、MQSeries アダプターのプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-152">This implements the MQSeries adapter provider.</span></span>  
  
- <span data-ttu-id="d379b-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-153">**Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**.</span></span> <span data-ttu-id="d379b-154">これは、Wcf-basichttp アダプターのプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-154">This implements the WCF-BasicHttp adapter provider.</span></span>  
  
- <span data-ttu-id="d379b-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**します。</span><span class="sxs-lookup"><span data-stu-id="d379b-155">**Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**.</span></span> <span data-ttu-id="d379b-156">これは、Wcf-wshttp アダプターのプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="d379b-156">This implements the WCF-WSHttp adapter provider.</span></span>  
  
  <span data-ttu-id="d379b-157">動的解決サンプルも、上記のリゾルバーとアダプターの適切な構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="d379b-157">The Dynamic Resolution sample is also dependent on correct configuration of the preceding resolvers and adapters.</span></span> <span data-ttu-id="d379b-158">インストールする」の説明に従って、これらの構成のプロセスが完了したことを確認、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d379b-158">Make sure that you complete the process for configuring these, as described in Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
  <span data-ttu-id="d379b-159">このセクションでは、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d379b-159">This section contains the following topics:</span></span>  
  
- [<span data-ttu-id="d379b-160">動的解決サンプルをインストールする</span><span class="sxs-lookup"><span data-stu-id="d379b-160">Installing the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
- [<span data-ttu-id="d379b-161">動的解決サンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="d379b-161">Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/running-the-dynamic-resolution-sample.md)
