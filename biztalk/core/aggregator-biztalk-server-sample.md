---
title: アグリゲーター (BizTalk Server サンプル) |Microsoft Docs
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
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127eb496a6949c0bbf3d6756324f38286e127ea3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360088"
---
# <a name="aggregator-biztalk-server-sample"></a>アグリゲーター (BizTalk Server サンプル)
このサンプルでは、オーケストレーションとパイプラインを使用してメッセージ集計機能を構築します。 具体的には行うオーケストレーションを構築します。  
  
1.  一連の関連するメッセージを受信します。 メッセージは宛先パートナーのメッセージのコンテンツから抽出された URI 情報に基づいて関連付けられます。  
  
2.  XML を実行することによって、1 つのインターチェンジ バッチにメッセージを受信した集計は、パイプラインを送信します。  
  
3.  1 分ごとに、XML インターチェンジ メッセージを生成またはと即座に十分なメッセージを集計します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 *\<パスのサンプル\>* \Pipelines\Aggregator  
  
 次の表では、このサンプルのファイルを示します。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Aggregator.sln|サンプルの Visual Studio ソリューション ファイルです。|  
|AggretatorBinding.xml|サンプルのバインド ファイルです。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|Aggregate フォルダー内。<br /><br /> Aggregate.btproj|アグリゲート オーケストレーションの BizTalk プロジェクトです。|  
|Aggregator フォルダー内。<br /><br /> 」の Aggregate.odx|関連付けられたメッセージをまとめて収集しを実行するオーケストレーションは、1 つのインターチェンジにアセンブルするためのパイプラインを送信します。|  
|Aggregate フォルダー内。<br /><br /> SuspendMessage.odx|アグリゲート オーケストレーション内で処理できないメッセージを中断するためのオーケストレーションです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> FFReceivePipeline.btp|受信フラット ファイル逆アセンブラーでは、パイプラインを使用します。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt|サンプルのドキュメント インスタンスです。 Instance1.txt と Instance2.txt は、宛先パートナーのインターチェンジに追加する必要があります [http://www.contoso.com](http://www.contoso.com/) Instance3.txt と Instance4.txt は、宛先パートナーのインターチェンジに追加する必要があります [http://www.northwind.com](http://www.northwind.com/) .|  
|PipelinesAndSchemas フォルダー内: <br /><br /> Invoice.xsd, InvoiceEnvelope.xsd|ドキュメント スキーマと出力インターチェンジのエンベロープ スキーマ。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PipelinesAndSchemas.btproj|スキーマとパイプラインの BizTalk プロジェクトです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PropertySchema.xsd|サンプルのプロパティ スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> XMLAggregatingPipeline.btp|収集されたメッセージを XML インターチェンジにアセンブルするオーケストレーションから実行されるパイプラインを送信します。|  
  
## <a name="building-and-initializing-the-sample"></a>サンプルのビルドおよび初期化  
 次の手順を使用して、ビルドして、アグリゲーターのサンプルを初期化します。  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a>ビルドして、アグリゲーターのサンプルの初期化  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<パスのサンプル\>\Pipelines\Aggregator  
  
2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - 入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。  
  
      \<パスのサンプル\>\Pipelines\Aggregator  
  
   - このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。  
  
   - Aggregator Sample をという新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
   - 参加しオーケストレーションを開始、により、受信場所および送信ポートを開始します。  
  
      開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。  
  
3. このサンプルを実行する前に、ことを確認します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でビルドおよび初期化プロセス中にエラーが報告されません。  
  
    Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 アグリゲーターのサンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-the-aggregator-sample"></a>アグリゲーターのサンプルを実行するには  
  
1.  開いているファイル Instance1.txt と Instance2.txt PipelinesAndSchemas フォルダーにその内容を確認します。  
  
     どちらのファイルも、DestinationPartnerURI 要素に通知には、値が含まれています。 http://www.contoso.comします。 この値は、1 つのインターチェンジに追加できるようにこれら 2 つのメッセージをまとめて関連付けるために使用されます。  
  
     同様に、DestinationPatnerURI 要素に設定のあるファイル Instance3.txt と Instance4.txt http://www.northwind.com します。  
  
     これら 2 つのメッセージが、別の 1 つのインターチェンジに追加されます。  
  
2.  テキスト ファイル Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt のコピーをフォルダーに貼り付けます。  
  
3.  アグリゲート オーケストレーションは、10 個のメッセージを収集するとすぐに、または 1 分のタイムアウト後に、出力インターチェンジを生成します。 そのため、遅延が Out フォルダにファイルがあります。  
  
     タイムアウトを避けるためには、さらに 4 回、アグリゲート オーケストレーションによるインターチェンジの生成をトリガーする 4 つの入力ファイルを貼り付けることができます。  
  
4.  Out フォルダに作成された XML ファイルを確認します。2 つのファイル-宛先パートナー URI ごとに 1 つがあります。  
  
     その内容を確認するファイルのいずれかを開きます。 ファイルは、エンベロープとその中の 2 つの XML ドキュメントで構成される XML インターチェンジに含める必要があります。  
  
    > [!NOTE]
    >  「配信済み、消費されませんでした」が発生する可能性があります、サンプルの実装またはコンボイ シナリオでの高負荷の下で「メッセージを破棄して完了」です。 これは、メッセージの到着、ビジネス プロセスを終了、途中のビジネスへのルートを処理するメッセージがいつや、予期せぬに発生します。  
  
## <a name="see-also"></a>参照  
 [パイプライン (BizTalk Server Samples フォルダー)](../core/pipelines-biztalk-server-samples-folder.md)