---
title: メッセージ プロセッサ (BizTalk Server サンプル) で構成されます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a072a889403abd474a31625eba86f9e28a2da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356653"
---
# <a name="composed-message-processor-biztalk-server-sample"></a>構成済みメッセージ プロセッサ (BizTalk Server サンプル)
このサンプルの目的は、個別のアイテムを集計したメッセージを処理する構成済みメッセージ プロセッサ アプリケーションを構築します。  
  
 具体的にはようはオーケストレーション スケジュールを作成します。  
  
1. 複数の購買発注で構成されるバッチ インターチェンジ メッセージを受信します。  
  
2. 個々 の注文書インターチェンジ メッセージを逆アセンブルします。  
  
3. 各ドキュメントの処理: 各購買発注、請求書メッセージに変換します。  
  
4. すべての請求書メッセージをバッチ インターチェンジにアセンブルします。  
  
   手順 3. サンプルの目的で簡単になります。 やなどのより複雑なアプリケーションは、オーケストレーション可能性がありますを異なるバックエンド在庫システムに発注書を逆アセンブルを送信し、すべての応答を収集した後に集計する 1 つのバッチ化された請求書メッセージ。  
  
   構成済みメッセージ プロセッサ パターンの詳細については、[1] を参照してください。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 いずれは、次のセクションで詳しく説明、サンプル ソリューション内の 2 つのプロジェクトがあります。  
  
### <a name="pipelines-and-schemas"></a>パイプラインとスキーマ  
 パイプラインとスキーマのプロジェクトが含まれます。  
  
-   入力注文書インターチェンジと出力請求書インターチェンジのフラット ファイル スキーマです。  
  
-   請求書ドキュメントに注文書ドキュメントを変換するマップです。  
  
-   受信および送信パイプラインです。  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a>入力と出力インターチェンジのフラット ファイル スキーマ  
 サンプル アプリケーションについては、フラット ファイル形式でインターチェンジを作成します。 次には、注文書インターチェンジと請求書インターチェンジの例を示します。  
  
 注文書インターチェンジ (CMPInput.txt):  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
PO1999-10-21  
US    John Dow       123 Elm Street      Mill Valley    CA 90952  
US    July Dow       8 Pine Avenue       Old Town       PA 95819  
Please ship it urgent!  
ITEMS,ITEM398-BB|Tire|4|324.99|Wrap them up nicely,ITEM201-BB|Engine Oil|1|12.99|SAE10W30|1999-05-22  
PO1999-10-23  
US    John Connor    123 Cedar Street    Mill Valley    CA 90952  
US    Sarah Connor   8 Grass Avenue      Old Town       PA 95819  
Use cheapest shipping method.  
ITEMS,ITEM101-TT|Plastic flowers|10|4.99|Fragile handle with care,ITEM202-RR|Fertilizer|1|10.99|Lawn fertilizer,ITEM453-XS|Weed killer|1|5.99|Lawn weed killer|1999-05-25  
```  
  
 インターチェンジ、または購買発注書ドキュメントでは、含まれているドキュメントの種類を識別するヘッダーがあります。  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 このインターチェンジは、次の 3 つの注文書で構成されます。 1 つのインスタンスは、下に表示される情報で構成されます。 ご覧のとおり、課金、および配布および注文したアイテムの一覧のアドレスなどの情報が含まれています。  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 これを生成する請求書インターチェンジは、次のようになります。  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
INVOICE1999-10-21  
BILLTO,US,John Dow,123 Elm Street,Mill Valley,CA,90952  
398-BB    Tire              4    324.99    Wrap them up nicely  
201-BB    Engine Oil        1    12.99     SAE10W30  
INVOICE1999-10-20  
BILLTO,US,John Connor,123 Cedar Street,Mill Valley,CA,90952  
101-TT    Plastic flowers   10   4.99      Fragile handle with care  
202-RR    Fertilizer        1    10.99     Lawn fertilizer  
453-XS    Weed killer       1    5.99      Lawn weed killer  
```  
  
 このインターチェンジには、インターチェンジを購入しても、インターチェンジの形式とヘッダーの形式が異なるが含まれる情報のサブセットが含まれています。  
  
 ヘッダーは次のとおりです。  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 ドキュメント インスタンスが、次が含まれています。  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 最初のフラット ファイル スキーマを作成する必要があります。  
  
- 購買発注書ドキュメント (PO.xsd)  
  
- 請求書ドキュメント (Invoice.xsd)  
  
- 発注書ヘッダー (POHeader.xsd)  
  
- 請求書ヘッダー (InvoiceHeader.xsd)  
  
  このサンプルでは、フラット ファイル スキーマを作成するプロセスを説明することはしません。 ドキュメント インスタンスからフラット ファイル スキーマを作成する方法については、「ドキュメント インスタンスからフラット ファイル スキーマを作成する」ドキュメントのセクションを参照してください。  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a>請求書ドキュメントに注文書ドキュメントを変換するマップ  
 マップ (PO2Invoice.btm) は、注文書のインスタンスを請求書ドキュメントに変換します。  
  
#### <a name="receive-and-send-pipelines"></a>受信パイプラインと送信  
 受信パイプライン (FFReceivePipeline.btp) には、注文書インターチェンジを処理するために使用するフラット ファイル逆アセンブラー コンポーネントが含まれています。 具体的には、特に CMPInput.txt ファイルで、インターチェンジのインターチェンジ ヘッダーを削除し、3 つの発注書に対応する 3 つの XML ドキュメントを生成します。  
  
 受信パイプラインのフラット ファイル逆アセンブラーが示すように構成されています。  
  
- **ドキュメント スキーマ:** PipelinesAndSchemas.PO  
  
- **ヘッダー スキーマ:** PipelinesAndSchemas.POHeader  
  
- **ヘッダーを保存します。** False  
  
- **回復可能なインターチェンジ:** False  
  
- **トレーラー スキーマ:**(なし)  
  
- **ドキュメント構造を検証します。** False  
  
  送信パイプライン (FFSendPipeline.btp) には、集計請求書インターチェンジを作成するために使用するフラット ファイル アセンブラー コンポーネントが含まれています。  
  
  送信パイプラインのフラット ファイル アセンブラーが示すように構成されています。  
  
- **ドキュメント スキーマ:** PipelinesandSchemas.Invoice  
  
- **ヘッダー スキーマ:** PipelinesAndSchemas.InvoiceHeader  
  
- **バイト オーダー マークを保存します。** False  
  
- **ターゲット文字セット:**(なし)  
  
- **トレーラー スキーマ:**(なし)  
  
### <a name="orchestration-schedule"></a>オーケストレーション スケジュール  
 オーケストレーション スケジュール (CMP.odx) は、すべての主な処理が行われる場所です。 具体的には、次の操作が実行されます。  
  
-   受信パイプラインを実行すると、注文書インターチェンジを逆アセンブル  
  
-   受信パイプラインのすべての出力メッセージを変換します。  
  
-   送信パイプラインを実行して、請求書インターチェンジをアセンブルするには  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a>オーケストレーション スケジュールを作成して、グローバル変数を定義します。  
 オーケストレーションでは、入力としてのフラット ファイル インターチェンジを受信して、出力として、フラット ファイル インターチェンジを送信します。 そのため、型として (それぞれという InputInterchange および OutputInterchange) 入力と出力メッセージを定義する必要があります (つまり System.Xml.XmlDocument 型を持つ) に依存しません。  
  
 また、メッセージを処理しますが、アトミックのスコープを定義する必要があります。 受信パイプラインはアトミックのスコープ内で実行できるために必要です。  
  
#### <a name="executing-receive-pipeline"></a>受信パイプラインの実行  
 次の手順としては、オーケストレーションで受信したメッセージの受信パイプラインを実行するロジックを追加します。 これを行うには、最初に宣言のスコープ内で Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages の種類の変数 (rcvpipeoutput)。 この変数は、順番にパイプライン出力メッセージを受信できるようにする列挙子です。 オーケストレーションからパイプラインの実行の他のすべての種類と、この型にアクセスするために必要です、次のアセンブリへの参照を追加することを確認してください。  
  
- Microsoft.XLANGs.Pipeline.dll  
  
- Microsoft.biztalk.pipeline.dll 内  
  
  常に、受信パイプラインは正常に実行される保証はありません。 メッセージあります不適切な形式では、パイプライン処理の失敗が発生します。 パイプラインには、オーケストレーションでの実行が失敗するとスローされる例外をキャッチできますが、エラー処理ロジックを実行できます。 パイプラインによってスローされる例外をキャッチするためには、例外処理を使用する非アトミックのスコープ内のパイプラインを実行する必要があります。 パイプラインを実行する実際のコードは、そのスコープ内で式図形から呼び出されます。  
  
  ExecuteRcvPipe 式図形で、受信パイプラインを実行するコードの次の行に記述します。  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 この行のコードの詳細を分析してみましょう。 ご覧のように、静的メソッド ExecuteReceivePipeline をパラメーターとして受信パイプラインを実行して、入力メッセージの種類を呼び出します。 その結果、出力メッセージのセットを持つ列挙子オブジェクトを生成します。 結果は、前にこのスコープで定義した ReceivePipelineOutputMessages 型の変数に割り当てられます。  
  
 例外処理パイプラインの実行スコープのブロックも含めました。 このブロックは、XLANGPipelineManagerException 型の例外をキャッチし、簡単にするためにカスタマイズされたエラー メッセージがオーケストレーション インスタンスを終了します。  
  
 複雑なシナリオは、追加のエラー処理を実行できますここでは、生成など、エラー通知メッセージと、ビジネス ユーザーや電子メールを使用して管理者に送信します。  
  
#### <a name="transforming-pipeline-output-messages"></a>変換のパイプライン出力メッセージ  
 パイプラインが実行されているし、逆アセンブルされたメッセージのセットが生成されて、各出力メッセージを別の形式に変換する必要があります。  
  
 オーケストレーションで変換を使用するには、変換入力し、出力-2 つのメッセージを定義する必要があります。 アトミックのスコープ内でのメッセージを定義します。 TmpMessageIn という変換入力メッセージは、PipelinesAndSchemas.PO 型になります。 TmpMessageOut という変換出力メッセージは、PipeliensAndSchemas.Invoice 型になります。 マップ、PO2Invoice.btm PipelinesAndSchemas プロジェクトで定義されているが適用されます。  
  
 各パイプライン出力メッセージにマップするため、ループ内で変換を実行する必要があります。 ここでは、ループ図形を以下の終了条件を使います。  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 MoveNext() メソッドは、パイプライン出力メッセージのコレクション内で移動できる IEnumerator .NET インターフェイスの標準的な方法です。 コレクションの末尾に達すると false を返します。  
  
 最初の構築図形は、パイプライン出力メッセージから、オーケストレーション メッセージ TmpMessageIn を構築に使用されます。  
  
 構築図形内のコード:  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 このコードではオーケストレーションのメッセージを null に設定し、パイプライン出力メッセージ コレクションから現在のメッセージに設定を最初に初期化します。  
  
 2 番目の構築図形、TmpMessageIn の実際の変換が行われると型の TmpMessageOut PipelinesAndSchemas.Invoice が構築されます。  
  
#### <a name="executing-send-pipeline"></a>送信パイプラインの実行  
 オーケストレーションの最後の処理手順では、すべての変換後の xml メッセージを 1 つのフラット ファイル インターチェンジにアセンブルするフラット ファイル送信パイプラインを実行します。  
  
 送信を実行するためには、パイプライン Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 型の変数を使用する必要がありますには、送信パイプラインで処理する必要があるオーケストレーション メッセージのコレクションを保持しなければが呼び出されます。  
  
 変換を実行したループの最後の式では、送信パイプラインのメッセージのコレクションに変換された各メッセージを追加するコードを書き込みます。  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 実行する部分と同様には、送信パイプラインの実行のコードが例外処理ブロックと共に非アトミックのスコープ内に配置パイプラインが表示されます。 送信パイプラインの実行コードは、構築ブロックのメッセージの割り当て図形にあります。  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 型を構築するコンス トラクター ブロックが使用される依存しない (System.Xml.XmlDocument など) パイプライン出力メッセージ outputinterchange を構築します。 メッセージの割り当て図形では、新しく構築されたメッセージは null に初期化されます。 その後、送信パイプラインを実行する静的メソッドの ExecuteSendPipeline が呼び出されます。 このメソッドは、入力メッセージ、およびパイプラインの出力を格納する出力メッセージへの参照を実行する送信パイプラインの種類をパラメーターとして受け取ります。  
  
 同様に、受信パイプラインの実行、ここでもある例外処理パイプラインの実行スコープのブロック。 このブロックは、XLANGPipelineManagerException 型の例外をキャッチし、簡単にするためにカスタマイズされたエラー メッセージがオーケストレーション インスタンスを終了します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次の表では、このサンプルのファイルを示します。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。<br /><br /> 送信ポートと受信ポートが削除されます。<br /><br /> 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|ComposedMessageProcessor.sln|サンプルの Visual Studio ソリューション ファイルです。|  
|ComposedMessageProcessorBinding.xml|サンプルのバインド ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|Orchestration フォルダー。<br /><br /> CMP.odx|逆アセンブラーのメッセージを受信パイプラインを実行しているオーケストレーションが逆アセンブルされた各メッセージを変換し、し、送信メッセージをインターチェンジにアセンブルするパイプラインを実行します。|  
|Orchestration フォルダー。<br /><br /> Orchestration.btproj|オーケストレーションの BizTalk プロジェクトです。|  
|Orchestration フォルダー。<br /><br /> SuspendMessage.odx|パイプライン処理に失敗したメッセージを中断するためのオーケストレーションです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> CMPInput.xml、CMPOutput.xml|入力と出力はドキュメント、サンプルのインスタンスです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> FFReceivePipeline.btp、FFSendPipeline.btp|受信し、送信パイプラインとフラット ファイル コンポーネント。 これらのパイプラインは、オーケストレーション内で実行されます。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> Invoice.xsd、InvoiceHeader.xsd|出力ドキュメント、およびヘッダーのフラット ファイル スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PO.xsd、POHeader.xsd|入力ドキュメントとヘッダーのフラット ファイル スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PropertySchema.xsd|サンプルのプロパティ スキーマです。|  
  
## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  
 次の手順を使用して、ビルドして、Compose サンプルを初期化します。  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>Compose サンプルをビルドして初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<パスのサンプル\>\Pipelines\ComposedMessageProcessor  
  
2.  ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
    -   入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。  
  
         \<パスのサンプル\>\Pipelines\ComposedMessageProcessor  
  
    -   このサンプルの Visual Studio プロジェクトをコンパイルします。  
  
    -   "CMP Sample"と呼ばれる新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。  
  
    -   作成し、バインド、BizTalk Server 受信場所と送信ポートと受信ポート。  
  
    -   参加しオーケストレーションを開始、により、受信場所および送信ポートを開始します。  
  
         開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。  
  
3.  このサンプルを実行する前に、BizTalk Server がビルドおよび初期化プロセス中にエラーを報告しないことを確認します。  
  
     Setup.bat による変更を元に戻すには、次の操作を行う必要があります。  
  
    1.  停止して、BizTalk Server 管理コンソールからのホスト インスタンスを再起動します。  
  
    2.  Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 ComposedMessageProcessor サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a>ComposedMessageProcessor サンプルを実行するには  
  
1.  PipelinesAndSchemas フォルダー内にある CMPInput.txt テキスト ファイルをコピーします。 このファイルをフォルダーに貼り付けます。  
  
2.  テキスト ファイルが Out フォルダに作成されたことを確認します。このファイルには、CMPInput.txt と同じレコードが含まれていますが、ファイル内のデータの形式が異なります。  
  
     メッセージは、BizTalk Server を通過して、次のようになります。  
  
    1.  メッセージは、逆アセンブルされ、XML メッセージに変換を取得します。 各メッセージは、別の形式にマップされます。  
  
    2.  マップされたすべてのメッセージは一緒にアセンブルし、フラット ファイル形式に変換します。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)