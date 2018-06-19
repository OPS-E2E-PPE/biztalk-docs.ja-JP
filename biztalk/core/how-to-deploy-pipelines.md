---
title: パイプラインを展開する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: db6047752c45a2f72b615102e14a4e66839e3e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249602"
---
# <a name="how-to-deploy-pipelines"></a>パイプラインを展開する方法
ソリューションのビルドおよび展開プロセスの一部として、パイプラインのコンパイルと展開が行われます。 コンパイラの呼び出し、**検証**各コンポーネントは、これにより、コンポーネントを返すメソッドに対してコンパイル エラーは構成済み情報。 ビルドが終了すると、パイプラインはソリューションの展開時に、残りのソリューションと同じアセンブリに展開されます。  
  
## <a name="per-instance-pipeline-configuration"></a>インスタンスごとのパイプラインの構成  
 インスタンスごとのパイプラインの構成は、送信ポートまたは受信場所のレベルで、展開済みパイプライン内のパイプライン コンポーネントのプロパティを変更する場合に使用されます。 インスタンスごとのパイプラインの構成は、少数のパイプライン コンポーネント プロパティをインスタンスごとに変更する場合に役立ちます。 たとえば、複数の受信場所で数種類のメッセージに対応する必要があり、カスタムの XML 受信パイプラインが 1 つである場合、インスタンスごとのパイプラインの構成を使用すると、パイプラインを展開し、既定の構成よりも優先的に使用することができます。また、別のエンベロープやドキュメントの仕様名を指定することもできます。 インスタンスごとのパイプラインの構成に関するメカニズムは BizTalk 管理コンソールでサポートされており、またエクスプローラー オブジェクト モデルを使ったプログラムを介して利用できます。  
  
### <a name="per-instance-pipeline-configuration-using-biztalk-administration-console"></a>BizTalk 管理コンソールを使ったインスタンスごとのパイプラインの構成  
 インスタンスごとのパイプラインの構成は、BizTalk 管理コンソールを使用して実行できます。 これには、カスタム パイプラインの展開後、受信場所または送信ポートを必要な数だけ作成し、 次に [パイプラインの構成] ダイアログ ボックスで、各受信場所または送信ポートに対し既定のプロパティ値より優先する値を指定します。 たとえば、別のドキュメント スキーマを指定するのスキーマ名を入力、 **EnvelopeDocSpecNames**プロパティです。  
  
> [!WARNING]
>  この受信場所または送信ポートに指定された構成値は検証されません。 構成が正しくない場合、メッセージは実行時にパイプラインを通過するときに失敗します。  
  
### <a name="per-instance-pipeline-configuration-using-the-explorer-object-model"></a>エクスプローラー オブジェクト モデルを使ったインスタンスごとのパイプラインの構成  
 パイプライン コンポーネントのインスタンスごとの構成を記述する XML ファイルが読み取られると、パイプライン ファイルに設定されたプロパティは上書きされます。  
  
 インスタンスごとのパイプラインの構成は、BizTalk エクスプローラー オブジェクト モデルを使用して設定できます。 BizTalk エクスプ ローラー オブジェクト モデルを提供、 **ReceivePipelineData**プロパティを**という**と**ISendPort**の構成を設定するためのインターフェイスパイプライン コンポーネントを受信します。 BizTalk エクスプローラ オブジェクト モデルも提供、 **SendPipelineData**メソッドを**IReceivePort**と**ISendPort**送信の設定の構成用のインターフェイスパイプライン コンポーネントです。  
  
 インスタンスごとのパイプラインの構成は、次の操作をサポートしていません。  
  
-   パイプライン内のステージの再構成  
  
-   ステージの追加または削除  
  
-   ステージ内のコンポーネントの再構成  
  
-   コンポーネントの追加または削除  
  
 サポートされている変更は、パイプライン コンポーネントの構成内の変更のみです。 パイプライン コンポーネントのインスタンスごとの構成は、パイプライン コンポーネントの共通の構成を上書きします。 インスタンスごとのパイプラインの構成でコンポーネントのパラメーターが指定されていない場合、そのパラメーターの共通の構成 (パイプライン デザイナーで構成) が使用されます。  
  
 次に、インスタンスごとの構成データの例を示します。  
  
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