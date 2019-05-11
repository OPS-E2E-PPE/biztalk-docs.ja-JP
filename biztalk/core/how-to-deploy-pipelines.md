---
title: パイプラインをデプロイする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edc30a99c0a037d23bc7d1ef7476edfdf159a339
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385293"
---
# <a name="how-to-deploy-pipelines"></a><span data-ttu-id="d20ae-102">パイプラインをデプロイする方法</span><span class="sxs-lookup"><span data-stu-id="d20ae-102">How to Deploy Pipelines</span></span>
<span data-ttu-id="d20ae-103">パイプラインはコンパイルされ、ソリューションのビルドの一部として展開およびプロセスを展開します。</span><span class="sxs-lookup"><span data-stu-id="d20ae-103">Pipelines are compiled and deployed as part of the solution build and deploy process.</span></span> <span data-ttu-id="d20ae-104">コンパイラの呼び出し、**検証**各コンポーネントは、これにより、コンポーネントを返すメソッドが構成されている情報にエラーをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d20ae-104">The compiler calls the **Validate** method on each component, allowing the components to return compile errors on the configured information.</span></span> <span data-ttu-id="d20ae-105">、作成した後、パイプラインは、ソリューションの配置時に、ソリューションの残りの部分で、同じアセンブリに配置されます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-105">After building, the pipeline is deployed in the same assembly with the rest of the solution when the solution is deployed.</span></span>  
  
## <a name="per-instance-pipeline-configuration"></a><span data-ttu-id="d20ae-106">インスタンスごとのパイプラインの構成</span><span class="sxs-lookup"><span data-stu-id="d20ae-106">Per-instance pipeline configuration</span></span>  
 <span data-ttu-id="d20ae-107">インスタンスごとのパイプラインの構成は、送信ポートで、展開済みパイプライン内のパイプライン コンポーネントのプロパティを変更または受信場所のレベルに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-107">Per-instance pipeline configuration is used to modify properties of pipeline components within a deployed pipeline at the send port or receive location level.</span></span> <span data-ttu-id="d20ae-108">インスタンスごとのパイプラインの構成は、いくつかのパイプライン コンポーネント プロパティのみがインスタンスごとに変更する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d20ae-108">Per-instance pipeline configuration is useful when only a few pipeline component properties need to be modified per instance.</span></span> <span data-ttu-id="d20ae-109">たとえばをサポートする必要がある場合の受信場所および 1 つのカスタム XML がある複数の種類別のメッセージの受信パイプライン、インスタンスごとのパイプラインの構成では、パイプラインをデプロイして、(を含む既定の構成をオーバーライドすることができます。指定する別のエンベロープやドキュメントの仕様名)。</span><span class="sxs-lookup"><span data-stu-id="d20ae-109">For example, if you need to support different message types in multiple receive locations and have a single custom XML receive pipeline, per-instance pipeline configuration enables you to deploy the pipeline and override the default configuration (including specifying different envelope and document spec names).</span></span> <span data-ttu-id="d20ae-110">BizTalk 管理コンソールで、プログラムで、エクスプ ローラー オブジェクト モデルを通じて、このメカニズムはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d20ae-110">This mechanism is supported in the BizTalk Management console and programmatically through the Explorer object model.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a><span data-ttu-id="d20ae-111">インスタンスごとのパイプラインの構成を使用して BizTalk 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="d20ae-111">Per-Instance Pipeline Configuration Using BizTalk Administration console</span></span>  
 <span data-ttu-id="d20ae-112">BizTalk 管理コンソールを使用してインスタンスごとのパイプラインの構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-112">You can perform per-instance pipeline configuration using the BizTalk Management console.</span></span> <span data-ttu-id="d20ae-113">カスタム パイプラインをデプロイした後は、受信場所または送信ポートを必要に応じて多くを作成します。</span><span class="sxs-lookup"><span data-stu-id="d20ae-113">Once you have deployed your custom pipeline, create as many receive locations or send ports as required.</span></span> <span data-ttu-id="d20ae-114">各受信場所または送信ポート、パイプラインの構成 ダイアログ ボックスで既定のプロパティ値をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d20ae-114">Then for each receive location or send port, override default property values through the Configure Pipeline dialog box.</span></span> <span data-ttu-id="d20ae-115">たとえば、別のドキュメント スキーマを指定するのスキーマ名を入力、 **EnvelopeDocSpecNames**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d20ae-115">For example, to specify a different document schema, enter a schema name for the **EnvelopeDocSpecNames** property.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d20ae-116">構成値の検証は、受信場所の指定など、送信ポートが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-116">No validation of the configuration values specified in the receive location or send port will be performed.</span></span> <span data-ttu-id="d20ae-117">構成が正しくない場合は、パイプラインを通過するときに実行時にメッセージが失敗します。</span><span class="sxs-lookup"><span data-stu-id="d20ae-117">If the configuration is incorrect, messages will fail at runtime when passing through the pipeline.</span></span>  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a><span data-ttu-id="d20ae-118">エクスプ ローラー オブジェクト モデルを使用してインスタンスごとのパイプラインの構成</span><span class="sxs-lookup"><span data-stu-id="d20ae-118">Per-Instance Pipeline Configuration Using the Explorer Object Model</span></span>  
 <span data-ttu-id="d20ae-119">パイプライン コンポーネントのインスタンスごとの構成を記述する XML ファイルが読み取られるときに、パイプライン ファイルで設定されたプロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d20ae-119">When the XML file describing the per-instance configuration of the pipeline components is read, it overrides the properties set in the pipeline file.</span></span>  
  
 <span data-ttu-id="d20ae-120">インスタンスごとのパイプラインの構成は、BizTalk エクスプローラ オブジェクト モデルを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-120">Per-instance pipeline configuration is set by using the BizTalk Explorer object model.</span></span> <span data-ttu-id="d20ae-121">BizTalk エクスプ ローラー オブジェクト モデルを使用する、 **ReceivePipelineData**プロパティを**という**と**ISendPort**の構成を設定するためのインターフェイスパイプライン コンポーネントを受信します。</span><span class="sxs-lookup"><span data-stu-id="d20ae-121">The BizTalk Explorer object model provides the **ReceivePipelineData** property on the **IReceiveLocation** and **ISendPort** interfaces for setting the configuration of receive pipeline components.</span></span> <span data-ttu-id="d20ae-122">BizTalk エクスプ ローラー オブジェクト モデルを使用することも、 **SendPipelineData**メソッドを**IReceivePort**と**ISendPort**送信の設定の構成用のインターフェイスパイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d20ae-122">The BizTalk Explorer object model also provides the **SendPipelineData** method on the **IReceivePort** and **ISendPort** interfaces for setting configuration of send pipeline components.</span></span>  
  
 <span data-ttu-id="d20ae-123">インスタンスごとのパイプラインの構成には、次をサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d20ae-123">Per-instance pipeline configuration does not support the following:</span></span>  
  
- <span data-ttu-id="d20ae-124">パイプライン内のステージの再構成</span><span class="sxs-lookup"><span data-stu-id="d20ae-124">Rearranging stages within the pipeline</span></span>  
  
- <span data-ttu-id="d20ae-125">追加または削除の段階</span><span class="sxs-lookup"><span data-stu-id="d20ae-125">Adding or removing stages</span></span>  
  
- <span data-ttu-id="d20ae-126">ステージ内のコンポーネントの再構成</span><span class="sxs-lookup"><span data-stu-id="d20ae-126">Rearranging components within stages</span></span>  
  
- <span data-ttu-id="d20ae-127">追加またはコンポーネントを削除します。</span><span class="sxs-lookup"><span data-stu-id="d20ae-127">Adding or removing components</span></span>  
  
  <span data-ttu-id="d20ae-128">パイプライン コンポーネントの構成ではサポートされている変更のみです。</span><span class="sxs-lookup"><span data-stu-id="d20ae-128">The only supported changes are in the configuration of pipeline components.</span></span> <span data-ttu-id="d20ae-129">パイプライン コンポーネントのインスタンスごとの構成では、一般的なパイプライン コンポーネントの構成をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d20ae-129">Per-instance configuration of a pipeline component overrides the common pipeline component configuration.</span></span> <span data-ttu-id="d20ae-130">インスタンスごとのパイプラインの構成でコンポーネントのパラメーターが指定されていない場合は、(パイプライン デザイナーで構成されている) とそのパラメーターの一般的な構成が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d20ae-130">If a parameter of a component is not specified in per-instance pipeline configuration, the common configuration for that parameter (as configured in Pipeline Designer) is used.</span></span>  
  
  <span data-ttu-id="d20ae-131">次は、インスタンスごとに構成データの例です。</span><span class="sxs-lookup"><span data-stu-id="d20ae-131">The following is an example of per-instance configuration data.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d20ae-132">参照</span><span class="sxs-lookup"><span data-stu-id="d20ae-132">See Also</span></span>  
 [<span data-ttu-id="d20ae-133">カスタム パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="d20ae-133">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)