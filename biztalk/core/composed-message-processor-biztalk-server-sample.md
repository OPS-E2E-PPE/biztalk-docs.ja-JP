---
title: メッセージ プロセッサ (BizTalk Server サンプル) で構成される |Microsoft ドキュメント
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
ms.openlocfilehash: 3097ef6a0da695c3b07cf68182a374eabed11b5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975280"
---
# <a name="composed-message-processor-biztalk-server-sample"></a>構成済みメッセージ プロセッサ (BizTalk Server サンプル)
このサンプルの目的は、集計メッセージの個別の品目を処理する構成済みメッセージ プロセッサ アプリケーションをビルドすることです。  
  
 具体的には、以下の処理を行うオーケストレーション スケジュールをビルドします。  
  
1.  複数の注文書で構成されるバッチ インターチェンジ メッセージを受信します。  
  
2.  インターチェンジ メッセージを個別の注文書ドキュメントに逆アセンブルします。  
  
3.  各ドキュメントを処理し、各注文書を請求書メッセージに変換します。  
  
4.  すべての請求書メッセージをバッチ インターチェンジにアセンブルします。  
  
 ステップ 3 はサンプル用であるため、簡略化されています。 たとえば、より複雑なアプリケーションの場合、オーケストレーションが逆アセンブルした注文書を異なるバックエンド在庫システムに送信し、すべての応答を収集した後で、応答をバッチ化された 1 つの請求書メッセージに集計することがあります。  
  
 構成済みメッセージ プロセッサのパターンの詳細については、[1] を参照してください。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 サンプル ソリューションには 2 つのプロジェクトがあります。次のセクションで、両方のプロジェクトについて詳しく説明します。  
  
### <a name="pipelines-and-schemas"></a>パイプラインとスキーマ  
 パイプライン、およびスキーマ プロジェクトには以下が含まれています。  
  
-   入力注文書インターチェンジと出力請求書インターチェンジのフラット ファイル スキーム  
  
-   注文書ドキュメントを請求書ドキュメントに変換するマップ  
  
-   受信および送信パイプラインです。  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a>入力インターチェンジと出力インターチェンジのフラット ファイル スキーマ  
 サンプル アプリケーションでは、フラット ファイル形式のインターチェンジを使用します。 注文書インターチェンジと請求書インターチェンジの例を以下に示します。  
  
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
  
 インターチェンジ、または注文書ドキュメントには、そこに含まれるドキュメントの種類を識別するヘッダーがあります。  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 このインターチェンジは、3 つの注文書ドキュメントで構成されています。 1 つのインスタンスを構成する情報は、以下のとおりです。 請求先住所や配送先住所、および注文したアイテムの一覧などの情報が含まれています。  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 ここで生成する請求書インターチェンジは、以下のようになります。  
  
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
  
 このインターチェンジには注文書インターチェンジ内の情報のサブセットが含まれ、さらに、インターチェンジの形式だけでなく、ヘッダーの形式も異なっています。  
  
 ヘッダーは次のとおりです。  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 また、ドキュメント インスタンスには次の情報が含まれます。  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 まず、以下のフラット ファイル スキーマを作成します。  
  
-   注文書ドキュメント (PO.xsd)  
  
-   請求書ドキュメント (Invoice.xsd)  
  
-   注文書ヘッダー (POHeader.xsd)  
  
-   請求書ヘッダー (InvoiceHeader.xsd)  
  
 このサンプルでは、フラット ファイル スキーマの作成プロセスについては説明しません。 ドキュメント インスタンスからフラット ファイル スキーマを作成する方法については、「ドキュメント インスタンスからのフラット ファイル スキーマの作成」ドキュメント セクションを参照してください。  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a>請求書ドキュメントに注文書ドキュメントを変換するマップ  
 マップ (PO2Invoice.btm) は、注文書のインスタンスを請求書ドキュメントに変換します。  
  
#### <a name="receive-and-send-pipelines"></a>受信パイプラインと送信パイプライン  
 受信パイプライン (FFReceivePipeline.btp) には、注文書インターチェンジの処理に使用するフラット ファイル逆アセンブラ コンポーネントが含まれています。 特に CMPInput.txt ファイルのインターチェンジでは、インターチェンジ ヘッダーを削除し、3 つの注文書に対応する 3 つの XML ドキュメントを生成します。  
  
 受信パイプラインのフラット ファイル逆アセンブラは、以下のように構成されます。  
  
-   **ドキュメント スキーマ:** PipelinesAndSchemas.PO  
  
-   **ヘッダー スキーマ:** PipelinesAndSchemas.POHeader  
  
-   **ヘッダーの保存:** False  
  
-   **回復可能なインターチェンジ:** False  
  
-   **トレーラー スキーマ:** (なし)  
  
-   **ドキュメント構造の検証:** False  
  
 送信パイプライン (FFSendPipeline.btp) には、集計請求書インターチェンジの作成に使用するフラット ファイル アセンブラ コンポーネントが含まれています。  
  
 送信パイプラインのフラット ファイルアセンブラは、以下のように構成されます。  
  
-   **ドキュメント スキーマ:** PipelinesandSchemas.Invoice  
  
-   **ヘッダー スキーマ:** PipelinesAndSchemas.InvoiceHeader  
  
-   **バイト オーダー マークの保存:** False  
  
-   **文字セットをターゲット:** (なし)  
  
-   **トレーラー スキーマ:** (なし)  
  
### <a name="orchestration-schedule"></a>オーケストレーション スケジュール  
 オーケストレーション スケジュール (CMP.odx) は、すべてのメイン処理が行われる場所です。 具体的には、次のアクションが実行されます。  
  
-   受信パイプラインを実行して、注文書インターチェンジを逆アセンブルする  
  
-   受信パイプラインのすべての出力メッセージを変換する  
  
-   送信パイプラインを実行して、請求書インターチェンジをアセンブルする  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a>オーケストレーション スケジュールの作成とグローバル変数の定義  
 オーケストレーションはフラット ファイル インターチェンジを入力として受信し、フラット ファイル インターチェンジを出力として送信します。 このため、入力メッセージと出力メッセージ (それぞれ InputInterchange および OutputInterchange) を、種類に関係のないメッセージ (System.Xml.XmlDocument 型を持つなど) として定義する必要があります。  
  
 また、メッセージを処理するアトミックのスコープも定義する必要があります。 これが必要なのは、受信パイプラインが、アトミックのスコープ内で実行可能であるためです。  
  
#### <a name="executing-receive-pipeline"></a>受信パイプラインの実行  
 次のステップではロジックを追加して、オーケストレーションで受信したメッセージの受信パイプラインを実行します。 この操作を行うには、まず、スコープ内で Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages の種類の変数 (RcvPipeOutput) を宣言します。 この変数は、受信パイプライン出力メッセージを順番に表示する列挙子です。 この種類、およびパイプラインを実行するその他の種類にオーケストレーションからアクセスするには、次のアセンブリに参照を追加する必要があります。  
  
-   Microsoft.XLANGs.Pipeline.dll  
  
-   Microsoft.BizTalk.Pipeline.dll  
  
 受信パイプラインが常に正常に実行されるという保証はありません。 メッセージの形式が正しくないために、パイプライン処理が失敗することがあります。 オーケストレーションでパイプラインの実行に失敗すると、例外がスローされます。これをキャッチして、エラー処理ロジックを実行することができます。 パイプラインでスローされた例外をキャッチするには、非アトミックなスコープで例外処理を使用して、パイプラインを実行する必要があります。 パイプラインを実行する実際のコードは、そのスコープの式図形から呼び出されます。  
  
 ExecuteRcvPipe 式図形に次のコード行を書き込んで、受信パイプラインを実行します。  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 このコード行を、もう少し詳しく分析しましょう。 この例からわかるとおり、受信パイプラインの種類をパラメータとして使用する静的メソッド ExecuteReceivePipeline を呼び出して、入力メッセージを実行します。 この結果、出力メッセージのセットを持つ列挙子オブジェクトが生成されます。 この結果は、このスコープで以前に定義した ReceivePipelineOutputMessages 型の変数に割り当てられます。  
  
 また、パイプライン実行スコープの例外処理ブロックも含めました。 このブロックでは、XLANGPipelineManagerException 型の例外をキャッチした後、簡単にするために、オーケストレーション インスタンスを終了して、カスタマイズされたエラー メッセージを表示します。  
  
 より複雑なシナリオでは、生成やエラー通知メッセージなどの追加のエラー処理を実行し、電子メールを使用して、それをビジネス ユーザーや管理者に送信することもできます。  
  
#### <a name="transforming-pipeline-output-messages"></a>パイプライン出力メッセージの変換  
 パイプラインを実行した後に、逆アセンブルされたメッセージのセットが生成されたら、各出力メッセージを別の形式に変換する必要があります。  
  
 オーケストレーションで変換を使用するには、変換入力と変換出力の 2 つのメッセージを定義する必要があります。 これらのメッセージをアトミックのスコープ内に定義します。 TmpMessageIn という変換入力メッセージは、PipelinesAndSchemas.PO 型になります。 TmpMessageOut という変換出力メッセージは、PipeliensAndSchemas.Invoice 型になります。 PipelinesAndSchemas プロジェクトで定義したマップ、PO2Invoice.btm を適用します。  
  
 各パイプライン出力メッセージにマップするよう、ループ内で変換を実行する必要があります。 以下の終了条件を持つループ図形を使用します。  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 MoveNext() メソッドは、パイプライン出力メッセージのコレクション内で移動できる IEnumerator .NET インターフェイスの標準メソッドです。 コレクションの最後に達すると、false を返します。  
  
 最初の構築図形を使用して、パイプライン出力メッセージからオーケストレーション メッセージ TmpMessageIn を構築します。  
  
 構築図形のコード :   
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 このコードでは、まず、オーケストレーション メッセージを Null に初期化してから、これをパイプライン出力メッセージ コレクションから現在のメッセージに設定します。  
  
 2 番目の構築図形では、TmpMessageIn の実際の変換が実行され、PipelinesAndSchemas.Invoice 型の TmpMessageOut が構築されます。  
  
#### <a name="executing-send-pipeline"></a>送信パイプラインの実行  
 オーケストレーションの最後の処理ステップでは、フラット ファイル送信パイプラインを実行して、変換されたすべての xml メッセージを 1 つのフラット ファイル インターチェンジにアセンブルします。  
  
 送信パイプラインを実行するためには、送信パイプラインで処理しなければならないオーケストレーション メッセージのコレクションを保持する、SendPipeInput と呼ばれる Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 型の変数を使用する必要があります。  
  
 変換を実行したループの最後の式で、変換された各メッセージを送信パイプラインのメッセージ コレクションに追加するコードを書き込みます。  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 受信パイプラインを実行する部分と同様に、送信パイプラインの実行コードが、例外処理ブロックと共に非アトミックなスコープ内に配置されます。 送信パイプライン実行コードは、構築ブロックのメッセージの割り当て図形内にあります。  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 構築ブロックを使用して、型に依存しない (System.Xml.XmlDocument など) パイプライン出力メッセージ OutputInterchange を構築します。 次に、メッセージの割り当て図形で、新しく構築されたメッセージが Null に初期化されます。 その後、静的メソッドの ExecuteSendPipeline を呼び出して、送信パイプラインを実行します。 このメソッドは、送信パイプラインの種類をパラメータとして、入力メッセージ、およびパイプライン出力が保存される出力メッセージの参照を実行します。  
  
 受信パイプラインの例外と同様に、ここにもパイプライン実行スコープの例外処理ブロックがあります。 このブロックでは、XLANGPipelineManagerException 型の例外をキャッチした後、簡単にするために、オーケストレーション インスタンスを終了して、カスタマイズされたエラー メッセージを表示します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 次の表に、このサンプルのファイル一覧を示します。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。<br /><br /> 送信ポートと受信ポートが削除されます。<br /><br /> 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|ComposedMessageProcessor.sln|サンプルの Visual Studio ソリューション ファイルです。|  
|ComposedMessageProcessorBinding.xml|サンプルのバインド ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|Orchestration フォルダー: <br /><br /> CMP.odx|受信パイプラインを実行して、メッセージを逆アセンブルし、逆アセンブルされた各メッセージを変換した後に送信パイプラインを実行して、メッセージをインターチェンジにアセンブルするオーケストレーションです。|  
|Orchestration フォルダー: <br /><br /> Orchestration.btproj|オーケストレーションの BizTalk プロジェクトです。|  
|Orchestration フォルダー: <br /><br /> SuspendMessage.odx|パイプライン処理が失敗したメッセージの中断に使用されるオーケストレーションです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> CMPInput.xml、CMPOutput.xml|サンプルの入力ドキュメント インスタンスおよび出力ドキュメント インスタンスです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> FFReceivePipeline.btp、FFSendPipeline.btp|フラット ファイル コンポーネントを持つ受信パイプラインと送信パイプラインです。 これらのパイプラインはオーケストレーション内で実行されます。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> Invoice.xsd、InvoiceHeader.xsd|出力ドキュメント、およびヘッダーのフラット ファイル スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PO.xsd、POHeader.xsd|入力ドキュメント、およびヘッダーのフラット ファイル スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PropertySchema.xsd|サンプルのプロパティ スキーマです。|  
  
## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  
 次の手順を使用して、Compose サンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>Compose サンプルをビルドして初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<パスのサンプル\>\Pipelines\ComposedMessageProcessor  
  
2.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   次のフォルダに、このサンプル用の入力 (In) フォルダと出力 (Out) フォルダを作成します。  
  
         \<パスのサンプル\>\Pipelines\ComposedMessageProcessor  
  
    -   このサンプル用に Visual Studio プロジェクトをコンパイルします。  
  
    -   "CMP Sample" という新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。  
  
    -   BizTalk Server の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
    -   オーケストレーションを参加させて開始し、受信場所を有効化し、送信ポートを開始します。  
  
         開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。  
  
3.  このサンプルを実行する前に、BizTalk Server において、作成プロセスおよび初期化プロセスでエラーが報告されていないことを確認してください。  
  
     Setup.bat による変更を元に戻すには、次の作業を行う必要があります。  
  
    1.  BizTalk Server 管理コンソールでホスト インスタンスを 1 度停止し、再開します。  
  
    2.  Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 次の手順を使用して、ComposedMessageProcessor サンプルを実行します。  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a>ComposedMessageProcessor サンプルを実行するには  
  
1.  PipelinesAndSchemas フォルダーのテキスト ファイル CMPInput.txt をコピーします。 このファイルを In フォルダに貼り付けます。  
  
2.  テキスト ファイルが Out フォルダに作成されることを確認します。このファイルには、CMPInput.txt と同じレコードが含まれますが、ファイルのデータ形式が異なります。  
  
     メッセージが BizTalk Server を通過すると、次のことが行われます。  
  
    1.  メッセージが逆アセンブルされ、XML メッセージに変換されます。 各メッセージが別の形式にマップされます。  
  
    2.  マップされたメッセージは一緒にアセンブルされ、フラット ファイル形式に変換されます。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)