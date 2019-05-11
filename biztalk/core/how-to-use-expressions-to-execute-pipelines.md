---
title: パイプラインを実行する式を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ExecuteReceivePipeline() method
- pipelines, schema resolution
- ExecuteSendPipeline() method
- SendPipelineInputMessages class
- pipelines, restrictions
- pipelines, errors
- XLANGPipelineManager class
- receive pipelines, orchestrations
- ReceivePipelineOutputMessages class
- orchestrations, pipelines
- pipelines, component types
- send pipelines, orchestrations
- pipelines, states
- pipelines, executing
- Microsoft.XLANGs.Pipeline namespace
- pipelines, transactional
- pipelines, orchestrations
- Message Assignment shape [Orchestration Designer], pipelines
ms.assetid: f947fa73-526c-4747-8de7-df557a93056c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2da3d12ac8df31fc8f63db69b4611b58c58df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383370"
---
# <a name="how-to-use-expressions-to-execute-pipelines"></a>パイプラインを実行する式を使用する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションからパイプラインを同期的に呼び出す機能があります。 これにより、パイプライン内でカプセル化されたメッセージの処理を活用するためのオーケストレーション (送信または受信) に対して、メッセージング インフラストラクチャを介してそのデータを送信することがなくデータの本体。  
  
 1 つの送信インターチェンジに複数のメッセージを集約するために、送信パイプラインを呼び出すオーケストレーションを有効にするのには、この機能を使用することができます。 逆に、オーケストレーションでは、デコードおよびメッセージ ボックスを通過の処理コストを発生させずに、メッセージング インフラストラクチャの外部で取得されたインターチェンジを逆アセンブルするには、受信パイプラインを呼び出す可能性があります。  
  
## <a name="details"></a>詳細  
 オーケストレーション内のメソッドを使用して、 **XLANGPipelineManager**クラス (で、 **Microsoft.XLANGs.Pipeline**名前空間) を呼び出す送信または受信パイプライン。  受信パイプラインは、1 つのメッセージまたはインターチェンジのいずれかを使用して、パイプラインが受信 BizTalk メッセージ内のメッセージのコンテキストで実行される場合と同様、0 個以上のメッセージが生成されます。 送信パイプラインでは、1 つまたは複数のメッセージを使用をパイプラインが BizTalk メッセージのメッセージ送信のコンテキストで実行される場合と同様、ここでも、1 つのメッセージまたはインターチェンジを生成します。  
  
## <a name="calling-a-receive-pipeline"></a>受信パイプラインの呼び出し  
 アプリケーションがオーケストレーションから受信パイプラインを呼び出すために、 **ExecuteReceivePipeline()** のメソッド、 **XLANGPipelineManager**クラス。  このメソッドは、1 つのインターチェンジを使用し、0 個以上のメッセージのコレクションを返します (のインスタンスに含まれている、 **ReceivePipelineOutputMessages**クラス)。 このメソッドの構文の .NET クラス ライブラリの参照の詳細については、 **XLANGPipelineManager**クラス。  
  
 オーケストレーションから受信パイプラインを実行するための API です。  
  
 `// Execute receive pipeline`  
  
 `static public ReceivePipelineOutputMessages ExecuteReceivePipeline(System.Type receivePipelineType, XLANGMessage msg);`  
  
 受信パイプラインへの呼び出しを行うことが通常、**式**オーケストレーション内の図形。  
  
 オーケストレーションから受信パイプラインを呼び出すために、開発者は、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。 受信パイプラインを呼び出すオーケストレーションの例を次に示します。  
  
 ![受信パイプラインの呼び出し画面](../core/media/callingreceivepipelinefromorchestration.gif "CallingReceivePipelineFromOrchestration")  
  
 詳細な例は、SDK サンプルを参照してください。[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)します。  
  
> [!NOTE]
>  型の変数**ReceivePipelineOutputMessages**オーケストレーションのアトミックのスコープ内でのみ宣言できます。  これは、この型の変数がシリアル化できないし、したがって、オーケストレーションの永続性は失わオーケストレーションがアトミックのスコープ内で実行中に永続化しないためです。  つまり、受信パイプラインは、アトミックのスコープ内でのみ実行できます。  
  
> [!NOTE]
>  呼び出すときに**PassThruReceive**パイプラインまたはオーケストレーション内からカスタム パイプライン コンポーネントでは、受信メッセージの種類に関係なく System.Xml.XmlDocument が XML か、受信メッセージの変数の型を宣言する必要があります. そのため場合は、受信メッセージがフラット ファイル形式のメッセージなどの XML 以外のメッセージ処理をしようとすると例外が発生する可能性があります。 これは、そのため、オーケストレーション エンジンが上記のシナリオでは受信メッセージの任意の型に System.Xml.XmlDocument を使用する予定です。  
  
## <a name="calling-a-send-pipeline"></a>送信パイプラインの呼び出し  
 アプリケーションがオーケストレーションから送信パイプラインを呼び出す、 **ExecuteSendPipeline()** のメソッド、 **XLANGPipelineManager**クラス。 このメソッドは 1 つまたは複数のメッセージのコレクション (のインスタンスに含まれている、 **SendPipelineInputMessages**クラス) を 1 つのインターチェンジを返します。 このメソッドの構文の .NET クラス ライブラリの参照の詳細については、 **XLANGPipelineManager**クラス。  送信パイプラインの実行を呼び出し、新しいインターチェンジを生成するため、 **ExecuteSendPipeline()** メソッドは、そのメッセージの割り当て図形内で行う必要があります。  
  
 オーケストレーションから送信パイプラインを実行するための API です。  
  
 `// Execute a send pipeline`  
  
 `static public ExecuteSendPipeline(System.Type sendPipelineType, SendPipelineInputMessages inputMsgs, XLANGMessage msg);`  
  
 送信パイプラインの呼び出しを行う必要がある、**メッセージの割り当て**オーケストレーション内の図形。  
  
 オーケストレーションから送信パイプラインを呼び出すために、開発者は、オーケストレーション プロジェクトでパイプライン アセンブリを参照する必要があります。  送信パイプラインを呼び出すオーケストレーションの例:  
  
 ![送信パイプラインの呼び出し画面](../core/media/example-callingsendpipelinefromorchestration.gif "Example_CallingSendPipelineFromOrchestration")  
  
> [!NOTE]
>  既定の XMLTransmit パイプラインを呼び出すときに、メッセージ コンテキスト プロパティ XMLNORM を設定する必要があります。EnvelopeSpecName エンベロープ スキーマの完全修飾名にします。 以下に例を示します。  
>   
>  `MyMessage(XMLNORM.EnvelopeSpecName) = "PipelineSchemas.POEnv, PipelineSchemas, Version=1.0.0.0, Culture=nuetral, PublicKeyToken=12e5cc95621c33e8";`  
  
 詳細な例は、SDK サンプルを参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)します。  
  
## <a name="pipeline-execution---behavioral-differences"></a>パイプラインの実行の動作の違い  
 送信の実行または受信パイプライン、オーケストレーションによって呼び出されたときに大部分がメッセージング インフラストラクチャ内で同じパイプラインを実行するときと同じ (つまりで受信場所または送信ポート)。  ただし、以下で説明されている特定の動作の違いがあります。  
  
### <a name="differences-within-pipeline-stages"></a>パイプラインのステージ内の相違点  
 送信内のステージの実行または受信パイプラインが例外については、ステージで、BizTalk メッセージング インフラストラクチャから呼び出されると、オーケストレーション内から呼び出されたパイプラインがこれらの段階の実行とほぼ同じです以下に。  
  
-   アセンブラー/逆アセンブラー。アセンブラーおよび逆アセンブラー ステージは処理されません**追跡プロファイルの**データ。  
  
-   エンコーダー/デコーダー:MIME エンコーダーは、ホストが関連付けられているホストで構成された証明書を使用してメッセージにデジタル署名します。  SMIME エンコーダーでは、パイプラインに渡されたメッセージのコンテキストで、証明書を使用してメッセージを暗号化します。  
  
### <a name="schema-resolution"></a>スキーマの解決  
 これには、オーケストレーションからパイプラインを実行する場合にサポートされている 2 つのスキーマ検索アルゴリズムがあります。  
  
- 種類による解決  
  
- 名前による解決  
  
  重複するスキーマがデプロイされている場合、適切なスキーマを選択するためのアルゴリズムのロジックは、メッセージング インフラストラクチャのコンテキストで実行するときに使用するのと同じです。  
  
### <a name="transactional-pipelines"></a>トランザクション パイプライン  
 パイプラインのステージがトランザクション コンポーネントを呼び出すには、使用可能なトランザクション コンテキストがありません。  すべての呼び出しに**IPipelineContext.GetTransaction()** がスローされます**NotSupportedException**します。  元のオーケストレーションは、このようなパイプラインの実行は上がりますが、パイプラインを検出してこのような状況を処理する必要があることを意味します。  
  
### <a name="message-destination"></a>メッセージの宛先  
 このコンテキストでは、パイプライン コンポーネントによってメッセージ送信先の制御がサポートされていません。  コンテキスト プロパティを設定**MessageDestination**または**SuspendOnRoutingFailure**により、 **XLANGPipelineManagerException**がスローされます。  
  
### <a name="pipeline-component-types"></a>パイプライン コンポーネントの種類  
 パイプライン コンポーネントは、オーケストレーション内から呼び出すためには、次に基づく必要があります。  
  
-   .NET framework v1.1  
  
-   .NET framework v2.0  
  
-   .NET framework バージョン 3.0  
  
-   .NET framework v3.5  
  
-   .NET framework v4.0  
  
-   .NET framework v2.0  
  
-   COM (COM)  
  
## <a name="restrictions"></a>制限  
 次の種類のパイプライン**できません**オーケストレーション内から実行します。  
  
- トランザクション パイプライン  
  
- 回復可能パイプライン。  
  
- BAM インターセプター API を呼び出すパイプライン (、 **NotSupportedException**がスローされます)。  
  
- 同じパイプライン インスタンスは、すべての分岐で同期のスコープに配置されていない限り、並列図形のそれぞれの分岐で実行できません。  
  
- 既存のパイプライン (アセンブリ) に対して構築された、 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] SDK。  
  
## <a name="failure-modes-and-effects"></a>障害モードと効果  
 メッセージが中断が発生した場合、パイプラインの実行でエラーをすべてから BizTalk Server メッセージング インフラストラクチャ内で呼び出すためには、このパイプラインは、例外がスローされる代わりになります。  スローされる例外は、型の**Microsoft.XLANGs.Pipeline.XLANGPipelineManagerException**します。  この例外は、呼び出し元オーケストレーションの catch ブロックで処理できます。  オーケストレーションが、スローされた例外をキャッチしない場合、Xlang エンジンはそのテキストには、スローされた例外での例外情報が含まれています、エラーを報告します。  
  
 例外は、パイプライン コンポーネントによって生成されるエラー メッセージの書式設定を実行します。  
  
 **メッセージ**のプロパティ、 **XLANGPipelineManagerException**クラスには、パイプラインの実行エラーの詳細が含まれています。 この詳細は次の形式です。  
  
- パイプラインの実行中にエラーが発生しました\<型をパイプライン\>します。  エラーの詳細\<形式のエラー メッセージ\>します。  
  
  このメッセージの\<パイプラインの種類\>パイプライン クラスの名前を指定し、\<形式のエラー メッセージ\>パイプラインの実行中に発生した特定のエラーの説明を示します。  
  
  たとえば、オーケストレーションが受信パイプラインを呼び出すし、パイプラインのコンポーネントのいずれも、メッセージの値が認識されるため、パイプラインの実行が失敗した場合、 **XLANGPipelineManagerException**のプロパティにはなります。  
  
|XLANGPipelineManagerException のプロパティ|値|  
|--------------------------------------------|-----------|  
|メッセージ|受信パイプライン"です MyPipelines.ReceivePipeline"を実行中にエラーが発生しました。 エラーの詳細:"逆アセンブル ステージのコンポーネントはデータを認識できません。|  
|コンポーネント|String.Empty|  
  
 オーケストレーションが送信パイプラインを呼び出すし、検証エラー、内のテキストがあるために、パイプラインの実行が失敗した場合、別の例として、**メッセージ**プロパティの**XLANGPipelineManagerException**になります。  
  
|XLANGPipelineManagerException のプロパティ|値|  
|--------------------------------------------|-----------|  
|メッセージ|送信パイプライン"MyPipelines.SendPipeline"を実行中にエラーが発生しました。  エラーの詳細:"ドキュメントの検証に失敗しました。"、\<要素名\>要素が無効です - 値\<要素値\>datatype 'String' - Pattern 制約に失敗しました無効です""。|  
|コンポーネント|“Microsoft.BizTalk.Component.XmlValidator”|