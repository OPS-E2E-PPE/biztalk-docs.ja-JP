---
title: "メッセージ強化サンプル (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3413345c4e2d0a2ce4cd7ee1cb5ebda50b1dea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a>メッセージ強化サンプル (BizTalk Server サンプル)
このメッセージ強化サンプルでは、X12 ドキュメントおよび EDIFACT ドキュメント用のインターチェンジ ヘッダーをトランザクション セット メッセージに追加する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、EDIFACT 用の UNA、UNB、および UNG ヘッダーと X12 用の ISA ヘッダーをトランザクション セットに追加する方法を示します。 具体的には、このサンプルは以下の処理を行います。  
  
1.  テスト メッセージを \Message Enrichment\In フォルダーにドロップすると、受信ポートがそのメッセージを取得して処理し、MessageBox にドロップします。  
  
2.  MessageEnrichmentOrchestration は、受信図形に対して設定されているフィルター式に基づいてメッセージにサブスクライブするため、このテスト メッセージを MessageBox から取得します。  
  
3.  オーケストレーションは、このメッセージのコンテキスト プロパティからインターチェンジ ヘッダーを読み取ります。  
  
    > [!NOTE]
    >  UNA ヘッダーと UNG ヘッダーは EDIFACT メッセージに含まれている必要がないため、メッセージのコンテキスト プロパティに含まれていない場合があります。  
  
4.  オーケストレーションは、インターチェンジ ヘッダーとメッセージ本文の両方を単一の新規メッセージに書き込みます。  
  
5.  オーケストレーションは、ReceivePortNameCorrelationType 関連付けの種類で設定されている追加のプロパティをメッセージに昇格させます。 これにより、オーケストレーションのユーザーは、サブスクリプションに必要なプロパティの一覧を選択できるようになります。 これらのプロパティは、メッセージの構築図形に書き込まれます。 元のメッセージに書き込まれたすべてのコンテキスト プロパティが新規メッセージに書き込まれるわけではありません。  
  
6.  オーケストレーションは、新規メッセージを MessageBox にドロップします。  
  
7.  送信ポートは、新規メッセージを取得し、ファイル アダプター経由で \Message Enrichment\Out フォルダーに送信します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルに格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\message Enrichment。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Cleanup.bat|サンプル シナリオの展開を解除します。 このファイルが正しく実行されるには、オーケストレーションのアクティブなインスタンスがないことが必要です。 アクティブなインスタンスがある場合、ファイルは正しく実行されません。|  
|MessageEnrichment.sln|MessageEnrichment プロジェクトと MessageEnrichmentLibrary プロジェクトが含まれています。|  
|Setup.bat|受信ポート、送信ポート、およびオーケストレーションから構成されるサンプル シナリオを展開します。|  
|EDIFACT_example.edi|入力 EDIFACT メッセージです。|  
|X12_example.edi|入力 X12 メッセージです。|  
|MessageEnrichment.btproj|MessageEnrichment のオーケストレーションとスキーマが含まれたプロジェクトです。|  
|MessageEnrichmentBindings.xml|オーケストレーション、ポート、およびパーティのバインドが含まれたファイルです。|  
|MessageEnrichmentOrchestration.odx|ヘッダーをメッセージに追加するオーケストレーションです。|  
|MessageEnrichmentOrchestration.odx.cs|ヘッダーをメッセージに追加するオーケストレーション コードです。|  
|EFACT_D98B_APERAK.xsd|入力メッセージの EDIFACT スキーマです。|  
|Enriched_EFACT_D98B_APERAK.xsd|出力メッセージの EDIFACT スキーマです。|  
|X12_00401_864.xsd|入力メッセージの X12 スキーマです。|  
|Enriched_X12_00401_864.xsd|出力メッセージの X12 スキーマです。|  
|Headers.xsd|入力メッセージに追加されるヘッダーのスキーマです。|  
|MessageEnrichmentLibrary.csproj|Headers.cs、OrchestrationUtilities.cs、および ParseHeaders.cs の各ファイルが含まれたプロジェクトです。|  
|Headers.cs|ヘッダー データを表すクラスが含まれています。|  
|OrchestrationUtilities.cs|オーケストレーションによって使用されるユーティリティ メソッドが含まれています。|  
|ParseHeaders.cs|新規メッセージで使用される UNA の既定値が含まれています。 これらの値は、ParseHeaders.cs の SerializeEDIFACTHeaders メソッドから取得されます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、インターチェンジ ヘッダーを EDI トランザクション セット メッセージに追加するために必要なアクションの実行例として使用します。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 Message Enrichment サンプルをビルドして初期化するには、このサンプルの BizTalk プロジェクトをビルドして展開し、受信ポートと受信場所を構成して、2 つの異なる送信ポートを構成する必要があります。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>このサンプルの BizTalk プロジェクトをビルドして展開するには  
  
1.  Notepad.Exe を使用して開きます[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\messageenrichment\  
    MessageEnrichment\properties\AssemblyInfo.cs し、ファイルの下部にある次の行を追加します。  
  
    ```  
    [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
    ```  
  
2.  変更した AssemblyInfo.cs ファイルを保存し、メモ帳を終了します。  
  
3.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment  
  
4.  実行**Setup.bat**、次の操作を実行します。  
  
    -   受信 (**で**) と送信 (**アウト**) \MessageEnrichment フォルダーに、このサンプル用のフォルダーです。  
  
    -   キーのペアを MessageEnrichmentLibrary\testkey.snk に書き込みます。  
  
    -   MessageEnrichmentLibrary.btproj プロジェクトを構築し、展開します。  
  
    -   MessageEnrichment.btproj プロジェクトを構築して展開します。  
  
    -   MessageEnrichmentBindings.xml のバインド情報を読み取ります。  
  
        > [!NOTE]
        >  このプロジェクトのバインドでは、BizTalk ホストが信頼された認証として設定されていることが必要です。  信頼されていないホストでバインドを使用するためには、MessageEnrichmentBindings.xml で HostTrusted="true" エントリを HostTrusted="false" に変更します。  
  
    -   オーケストレーションのバインドを更新します。  
  
    -   送信ポート、送信ポート グループ、および受信ポートを更新します。  
  
    -   パーティと参加状況を更新します。  
  
    -   送信ポートを開始します。  
  
    -   受信場所を有効にします。  
  
    -   オーケストレーションを登録して開始します。  
  
 BizTalk Server でこのサンプルを使用する準備ができました。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 Message Enrichment サンプルを実行するには、次の手順に従います。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  EDIFACT_examples.edi ファイルを \MessageEnrichment\Instances フォルダーから \MessageEnrichment\In フォルダーにコピーします。  
  
2.  EDIFACT_examples.edi ファイルが \MessageEnrichment\In フォルダーに表示されなくなり、\MessageEnrichment\Out フォルダーに表示されていることを確認します。  
  
3.  \MessageEnrichment\Out フォルダーのファイルを開きます。 ファイルが \MessageEnrichment\Instances フォルダーにある EDIFACT_examples.edi ファイルの XML 表記であることを確認します。また、出力ファイルに EDIFACT UNA、UNB、および UNG の各ヘッダーがあることを除き、ファイルのコンテンツが EDIFACT_examples.edi ファイルと同じであることを確認します。  
  
4.  \MessageEnrichment\Instances フォルダーの X12_examples.edi ファイルに対して手順 1. と 2. を繰り返します。  
  
5.  \MessageEnrichment\Out フォルダーの新規ファイルを開きます。 ファイルが \MessageEnrichment\Instances フォルダーにある X12_examples.edi file ファイルの XML 表記であることを確認します。また、出力ファイルに X12 ISA ヘッダーがあることを除き、ファイルのコンテンツが X12_examples.edi ファイルと同じであることを確認します。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 なし  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 (BizTalk Server Samples フォルダ)](../core/edi-and-as2-biztalk-server-samples-folder.md)