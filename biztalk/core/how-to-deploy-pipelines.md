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
# <a name="how-to-deploy-pipelines"></a>パイプラインをデプロイする方法
パイプラインはコンパイルされ、ソリューションのビルドの一部として展開およびプロセスを展開します。 コンパイラの呼び出し、**検証**各コンポーネントは、これにより、コンポーネントを返すメソッドが構成されている情報にエラーをコンパイルします。 、作成した後、パイプラインは、ソリューションの配置時に、ソリューションの残りの部分で、同じアセンブリに配置されます。  
  
## <a name="per-instance-pipeline-configuration"></a>インスタンスごとのパイプラインの構成  
 インスタンスごとのパイプラインの構成は、送信ポートで、展開済みパイプライン内のパイプライン コンポーネントのプロパティを変更または受信場所のレベルに使用されます。 インスタンスごとのパイプラインの構成は、いくつかのパイプライン コンポーネント プロパティのみがインスタンスごとに変更する必要がある場合に便利です。 たとえばをサポートする必要がある場合の受信場所および 1 つのカスタム XML がある複数の種類別のメッセージの受信パイプライン、インスタンスごとのパイプラインの構成では、パイプラインをデプロイして、(を含む既定の構成をオーバーライドすることができます。指定する別のエンベロープやドキュメントの仕様名)。 BizTalk 管理コンソールで、プログラムで、エクスプ ローラー オブジェクト モデルを通じて、このメカニズムはサポートされています。  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a>インスタンスごとのパイプラインの構成を使用して BizTalk 管理コンソール  
 BizTalk 管理コンソールを使用してインスタンスごとのパイプラインの構成を行うことができます。 カスタム パイプラインをデプロイした後は、受信場所または送信ポートを必要に応じて多くを作成します。 各受信場所または送信ポート、パイプラインの構成 ダイアログ ボックスで既定のプロパティ値をオーバーライドします。 たとえば、別のドキュメント スキーマを指定するのスキーマ名を入力、 **EnvelopeDocSpecNames**プロパティ。  
  
> [!WARNING]
>  構成値の検証は、受信場所の指定など、送信ポートが実行されます。 構成が正しくない場合は、パイプラインを通過するときに実行時にメッセージが失敗します。  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a>エクスプ ローラー オブジェクト モデルを使用してインスタンスごとのパイプラインの構成  
 パイプライン コンポーネントのインスタンスごとの構成を記述する XML ファイルが読み取られるときに、パイプライン ファイルで設定されたプロパティをオーバーライドします。  
  
 インスタンスごとのパイプラインの構成は、BizTalk エクスプローラ オブジェクト モデルを使用して設定されます。 BizTalk エクスプ ローラー オブジェクト モデルを使用する、 **ReceivePipelineData**プロパティを**という**と**ISendPort**の構成を設定するためのインターフェイスパイプライン コンポーネントを受信します。 BizTalk エクスプ ローラー オブジェクト モデルを使用することも、 **SendPipelineData**メソッドを**IReceivePort**と**ISendPort**送信の設定の構成用のインターフェイスパイプライン コンポーネント。  
  
 インスタンスごとのパイプラインの構成には、次をサポートされていません。  
  
- パイプライン内のステージの再構成  
  
- 追加または削除の段階  
  
- ステージ内のコンポーネントの再構成  
  
- 追加またはコンポーネントを削除します。  
  
  パイプライン コンポーネントの構成ではサポートされている変更のみです。 パイプライン コンポーネントのインスタンスごとの構成では、一般的なパイプライン コンポーネントの構成をオーバーライドします。 インスタンスごとのパイプラインの構成でコンポーネントのパラメーターが指定されていない場合は、(パイプライン デザイナーで構成されている) とそのパラメーターの一般的な構成が使用されます。  
  
  次は、インスタンスごとに構成データの例です。  
  
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
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)