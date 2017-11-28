---
title: "パイプラインを展開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IReceiveLocation interface
- IReceivePort interface
- deploying, pipelines
- pipelines, deploying
- pipelines, compiling
- SendPipelineData method
- pipelines, configuring
- pipelines, code sample
- ReceivePipelineData property
- Validate method
- ISendPort interface
ms.assetid: 7a56c753-a0d4-48ed-a61d-e454bc9cd507
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db6047752c45a2f72b615102e14a4e66839e3e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-pipelines"></a><span data-ttu-id="6dbf1-102">パイプラインを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6dbf1-102">How to Deploy Pipelines</span></span>
<span data-ttu-id="6dbf1-103">ソリューションのビルドおよび展開プロセスの一部として、パイプラインのコンパイルと展開が行われます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-103">Pipelines are compiled and deployed as part of the solution build and deploy process.</span></span> <span data-ttu-id="6dbf1-104">コンパイラの呼び出し、**検証**各コンポーネントは、これにより、コンポーネントを返すメソッドに対してコンパイル エラーは構成済み情報。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-104">The compiler calls the **Validate** method on each component, allowing the components to return compile errors on the configured information.</span></span> <span data-ttu-id="6dbf1-105">ビルドが終了すると、パイプラインはソリューションの展開時に、残りのソリューションと同じアセンブリに展開されます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-105">After building, the pipeline is deployed in the same assembly with the rest of the solution when the solution is deployed.</span></span>  
  
## <a name="per-instance-pipeline-configuration"></a><span data-ttu-id="6dbf1-106">インスタンスごとのパイプラインの構成</span><span class="sxs-lookup"><span data-stu-id="6dbf1-106">Per-instance pipeline configuration</span></span>  
 <span data-ttu-id="6dbf1-107">インスタンスごとのパイプラインの構成は、送信ポートまたは受信場所のレベルで、展開済みパイプライン内のパイプライン コンポーネントのプロパティを変更する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-107">Per-instance pipeline configuration is used to modify properties of pipeline components within a deployed pipeline at the send port or receive location level.</span></span> <span data-ttu-id="6dbf1-108">インスタンスごとのパイプラインの構成は、少数のパイプライン コンポーネント プロパティをインスタンスごとに変更する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-108">Per-instance pipeline configuration is useful when only a few pipeline component properties need to be modified per instance.</span></span> <span data-ttu-id="6dbf1-109">たとえば、複数の受信場所で数種類のメッセージに対応する必要があり、カスタムの XML 受信パイプラインが 1 つである場合、インスタンスごとのパイプラインの構成を使用すると、パイプラインを展開し、既定の構成よりも優先的に使用することができます。また、別のエンベロープやドキュメントの仕様名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-109">For example, if you need to support different message types in multiple receive locations and have a single custom XML receive pipeline, per-instance pipeline configuration enables you to deploy the pipeline and override the default configuration (including specifying different envelope and document spec names).</span></span> <span data-ttu-id="6dbf1-110">インスタンスごとのパイプラインの構成に関するメカニズムは BizTalk 管理コンソールでサポートされており、またエクスプローラー オブジェクト モデルを使ったプログラムを介して利用できます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-110">This mechanism is supported in the BizTalk Management console and programmatically through the Explorer object model.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a><span data-ttu-id="6dbf1-111">BizTalk 管理コンソールを使ったインスタンスごとのパイプラインの構成</span><span class="sxs-lookup"><span data-stu-id="6dbf1-111">Per-Instance Pipeline Configuration Using BizTalk Administration console</span></span>  
 <span data-ttu-id="6dbf1-112">インスタンスごとのパイプラインの構成は、BizTalk 管理コンソールを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-112">You can perform per-instance pipeline configuration using the BizTalk Management console.</span></span> <span data-ttu-id="6dbf1-113">これには、カスタム パイプラインの展開後、受信場所または送信ポートを必要な数だけ作成し、</span><span class="sxs-lookup"><span data-stu-id="6dbf1-113">Once you have deployed your custom pipeline, create as many receive locations or send ports as required.</span></span> <span data-ttu-id="6dbf1-114">次に [パイプラインの構成] ダイアログ ボックスで、各受信場所または送信ポートに対し既定のプロパティ値より優先する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-114">Then for each receive location or send port, override default property values through the Configure Pipeline dialog box.</span></span> <span data-ttu-id="6dbf1-115">たとえば、別のドキュメント スキーマを指定するのスキーマ名を入力、 **EnvelopeDocSpecNames**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-115">For example, to specify a different document schema, enter a schema name for the **EnvelopeDocSpecNames** property.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6dbf1-116">この受信場所または送信ポートに指定された構成値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-116">No validation of the configuration values specified in the receive location or send port will be performed.</span></span> <span data-ttu-id="6dbf1-117">構成が正しくない場合、メッセージは実行時にパイプラインを通過するときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-117">If the configuration is incorrect, messages will fail at runtime when passing through the pipeline.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a><span data-ttu-id="6dbf1-118">エクスプローラー オブジェクト モデルを使ったインスタンスごとのパイプラインの構成</span><span class="sxs-lookup"><span data-stu-id="6dbf1-118">Per-Instance Pipeline Configuration Using the Explorer Object Model</span></span>  
 <span data-ttu-id="6dbf1-119">パイプライン コンポーネントのインスタンスごとの構成を記述する XML ファイルが読み取られると、パイプライン ファイルに設定されたプロパティは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-119">When the XML file describing the per-instance configuration of the pipeline components is read, it overrides the properties set in the pipeline file.</span></span>  
  
 <span data-ttu-id="6dbf1-120">インスタンスごとのパイプラインの構成は、BizTalk エクスプローラー オブジェクト モデルを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-120">Per-instance pipeline configuration is set by using the BizTalk Explorer object model.</span></span> <span data-ttu-id="6dbf1-121">BizTalk エクスプ ローラー オブジェクト モデルを提供、 **ReceivePipelineData**プロパティを**という**と**ISendPort**の構成を設定するためのインターフェイスパイプライン コンポーネントを受信します。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-121">The BizTalk Explorer object model provides the **ReceivePipelineData** property on the **IReceiveLocation** and **ISendPort** interfaces for setting the configuration of receive pipeline components.</span></span> <span data-ttu-id="6dbf1-122">BizTalk エクスプローラ オブジェクト モデルも提供、 **SendPipelineData**メソッドを**IReceivePort**と**ISendPort**送信の設定の構成用のインターフェイスパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-122">The BizTalk Explorer object model also provides the **SendPipelineData** method on the **IReceivePort** and **ISendPort** interfaces for setting configuration of send pipeline components.</span></span>  
  
 <span data-ttu-id="6dbf1-123">インスタンスごとのパイプラインの構成は、次の操作をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-123">Per-instance pipeline configuration does not support the following:</span></span>  
  
-   <span data-ttu-id="6dbf1-124">パイプライン内のステージの再構成</span><span class="sxs-lookup"><span data-stu-id="6dbf1-124">Rearranging stages within the pipeline</span></span>  
  
-   <span data-ttu-id="6dbf1-125">ステージの追加または削除</span><span class="sxs-lookup"><span data-stu-id="6dbf1-125">Adding or removing stages</span></span>  
  
-   <span data-ttu-id="6dbf1-126">ステージ内のコンポーネントの再構成</span><span class="sxs-lookup"><span data-stu-id="6dbf1-126">Rearranging components within stages</span></span>  
  
-   <span data-ttu-id="6dbf1-127">コンポーネントの追加または削除</span><span class="sxs-lookup"><span data-stu-id="6dbf1-127">Adding or removing components</span></span>  
  
 <span data-ttu-id="6dbf1-128">サポートされている変更は、パイプライン コンポーネントの構成内の変更のみです。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-128">The only supported changes are in the configuration of pipeline components.</span></span> <span data-ttu-id="6dbf1-129">パイプライン コンポーネントのインスタンスごとの構成は、パイプライン コンポーネントの共通の構成を上書きします。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-129">Per-instance configuration of a pipeline component overrides the common pipeline component configuration.</span></span> <span data-ttu-id="6dbf1-130">インスタンスごとのパイプラインの構成でコンポーネントのパラメーターが指定されていない場合、そのパラメーターの共通の構成 (パイプライン デザイナーで構成) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-130">If a parameter of a component is not specified in per-instance pipeline configuration, the common configuration for that parameter (as configured in Pipeline Designer) is used.</span></span>  
  
 <span data-ttu-id="6dbf1-131">次に、インスタンスごとの構成データの例を示します。</span><span class="sxs-lookup"><span data-stu-id="6dbf1-131">The following is an example of per-instance configuration data.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<Root xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
    <Stages>  
        <Stage CategoryId="9d0e4103-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft Microsoft.BizTalk.Component.MIME_SMIME_Decoder>  
                    <Properties>  
                        <AllowNonMIMEMessage vt=11>true</AllowNonMIMEMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e4105-4cce-4536-83fa-4a5040674ad6">  
            <Components>  
                <Component Name=Microsoft.BizTalk.Component.XmlDasmComp>  
                    <Properties>  
                        <EnvelopeSpecNames vt=8>MySchemas.EnvelopeSpecNames</EnvelopeSpecNames>  
                        <AllowUnrecognizedMessage vt=11>false</AllowUnrecognizedMessage>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
        <Stage CategoryId="9d0e410d-4cce-4536-83fa-4a5040674ad6" ExecutionSequence="2">  
            <Components>  
                 <Component Name=Microsoft.BizTalk.Component.XmlValidator >  
                    <Properties>  
                        <DocumentSpecName vt=8>MySchemas.DocspecName</DocumentSpecName>  
                    </Properties>  
                </Component>  
            </Components>  
        </Stage>  
    </Stages>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dbf1-132">参照</span><span class="sxs-lookup"><span data-stu-id="6dbf1-132">See Also</span></span>  
 [<span data-ttu-id="6dbf1-133">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="6dbf1-133">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)