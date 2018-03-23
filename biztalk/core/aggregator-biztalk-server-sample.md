---
title: アグリゲーター (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f4d28214a815aca88f214e5efb9cd883e7192
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="aggregator-biztalk-server-sample"></a>アグリゲーター (BizTalk Server サンプル)
このサンプルの目的は、オーケストレーションとパイプラインを使用してメッセージ アグリゲーション機能を構築することです。 特に、以下のことを行うオーケストレーションを構築します。  
  
1.  関連付けられた複数のメッセージを受信します。 各メッセージは、メッセージのコンテンツから取り出した宛先パートナーの URI 情報に基づいて関連付けられます。  
  
2.  XML 送信パイプラインを実行することで、受信したメッセージを単一のインターチェンジ バッチにアグリゲートします。  
  
3.  1 分ごとか、アグリゲートするのに十分なメッセージを受信した場合はすぐに XML インターチェンジ メッセージを生成します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<Samples Path\>*\Pipelines\Aggregator  
  
 次の表に、このサンプルのファイル一覧を示します。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Aggregator.sln|サンプルの Visual Studio ソリューション ファイルです。|  
|AggretatorBinding.xml|サンプルのバインド ファイルです。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|Aggregate フォルダー内:<br /><br /> Aggregate.btproj|オーケストレーションをアグリゲートするための BizTalk プロジェクトです。|  
|Aggregator フォルダー内:<br /><br /> Aggregate.odx|関連付けられているメッセージを 1 か所に集め、送信パイプラインを実行して単一のインターチェンジに組み立てるオーケストレーションです。|  
|Aggregate フォルダー内:<br /><br /> SuspendMessage.odx|アグリゲート オーケストレーション内で処理できない保留メッセージに対して使用するオーケストレーションです。|  
|PipelinesAndSchemas フォルダー内:<br /><br /> FFReceivePipeline.btp|フラット ファイル逆アセンブラーを使用した受信パイプラインです。|  
|PipelinesAndSchemas フォルダー内:<br /><br /> Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt|サンプルのドキュメント インスタンスです。 Instance1.txt と Instance2.txt は、宛先パートナーのインターチェンジに追加する必要があります[ http://www.contoso.com ](http://www.contoso.com/) Instance3.txt と Instance4.txt は、宛先パートナーのインターチェンジに追加する必要があります[ http://www.northwind.com](http://www.northwind.com/).|  
|PipelinesAndSchemas フォルダー内:<br /><br /> Invoice.xsd、InvoiceEnvelope.xsd|出力インターチェンジのドキュメント スキーマとエンベロープ スキーマです。|  
|PipelinesAndSchemas フォルダー内:<br /><br /> PipelinesAndSchemas.btproj|スキーマとパイプラインの BizTalk プロジェクトです。|  
|PipelinesAndSchemas フォルダー内:<br /><br /> PropertySchema.xsd|サンプルのプロパティ スキーマです。|  
|PipelinesAndSchemas フォルダー内:<br /><br /> XMLAggregatingPipeline.btp|収集されたメッセージを XML インターチェンジに組み立てるために、オーケストレーションから実行される送信パイプラインです。|  
  
## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  
 次の手順を使用して、アグリゲーターのサンプルをビルドおよび初期化します。  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a>アグリゲーターのサンプルをビルドおよび初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<パスのサンプル\>\Pipelines\Aggregator  
  
2.  ファイル Setup.bat では、次の操作を実行しますが、実行します。  
  
    -   次のフォルダに、このサンプル用の入力 (In) フォルダと出力 (Out) フォルダを作成します。  
  
         \<パスのサンプル\>\Pipelines\Aggregator  
  
    -   このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。  
  
    -   新しいアプリケーション Aggregator Sample を作成し、そこにサンプル アセンブリを展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
    -   オーケストレーションを参加させて開始し、受信場所を有効化し、送信ポートを開始します。  
  
         開き、Setup.bat ファイルを実行することがなく、このサンプルのプロジェクトをビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアを使用して、生成されたアセンブリの署名に使用します。  
  
3.  このサンプルを実行する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がビルド プロセス中または初期化プロセス中にエラーを報告していないことを確認してください。  
  
     Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 次の手順を使用して、アグリゲーターのサンプルを実行します。  
  
#### <a name="to-run-the-aggregator-sample"></a>アグリゲーターのサンプルを実行するには  
  
1.  PipelinesAndSchemas フォルダーにあるファイル Instance1.txt と Instance2.txt を開き、その内容を確認します。  
  
     どちらのファイルも、DestinationPartnerURI 要素に通知が値を含むhttp://www.contoso.comです。この値は、1 つのインターチェンジに追加できるようにこれら 2 つのメッセージをまとめて関連付けるために使用されます。  
  
     同様にも、DestinationPatnerURI 要素に設定のあるファイル Instance3.txt と Instance4.txthttp://www.northwind.comです。  
  
     これら 2 つのメッセージが、別の 1 つのインターチェンジに追加されます。  
  
2.  テキスト ファイル Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt のコピーを、フォルダー In に貼り付けます。  
  
3.  アグリゲート オーケストレーションにより、10 個のメッセージを収集するか、1 分のタイムアウトが経過した後に、出力インターチェンジが生成されます。 そのため、Out フォルダー内にはファイルが遅れて作成されます。  
  
     タイムアウトを避けるには、4 つの入力ファイルをさらに 4 回貼り付けます。これにより、アグリゲート オーケストレーションによるインターチェンジの生成が起動されます。  
  
4.  フォルダー Out に作成される XML ファイルを参照します。宛先パートナー URI ごとに 1 つ、合計 2 つのファイルが作成されます。  
  
     いずれかのファイルを開いて内容を確認します。 ファイルには XML インターチェンジが 1 つ格納されており、その中には 1 つのエンベロープがあり、さらにその中に 2 つの XML ドキュメントがあります。  
  
    > [!NOTE]
    >  サンプル実装では、コンボイ シナリオにおいて、高負荷時に "配布されましたが、消費されませんでした" または "メッセージを破棄して完了" のエラーが発生します。 これは、メッセージが終了途中のビジネス プロセスにルーティングされた場合や、予期せぬメッセージがビジネス プロセスに到着した場合に必ず発生します。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)