---
title: メッセージ強化サンプル (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d987164eeb855bfc991e9b4f1b0c8b444b99407b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325119"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a>メッセージ強化サンプル (BizTalk Server サンプル)
メッセージ強化サンプルでは、X12 と EDIFACT ドキュメントのトランザクション セット メッセージにインターチェンジ ヘッダーを追加する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、edifact では、UNA、UNB、および UNG ヘッダーと x12 の場合、ISA ヘッダーをトランザクション セットに追加する方法を示します。 具体的には、このサンプルは以下の処理を行います。  
  
1.  \Message Enrichment\In フォルダーにテスト メッセージをドロップすると、受信ポートは、ピックアップする、処理、および、MessageBox にドロップします。  
  
2.  MessageEnrichmentOrchestration から取得し、テスト メッセージ、メッセージ ボックスでは、受信図形に対して設定するフィルター式に基づいてメッセージをサブスクライブしています。  
  
3.  オーケストレーションは、メッセージのコンテキスト プロパティからインターチェンジ ヘッダーを読み取ります。  
  
    > [!NOTE]
    >  UNA と UNG ヘッダーは、メッセージのコンテキスト プロパティでない可能性がありますので、EDIFACT メッセージのオプションです。  
  
4.  オーケストレーションでは、インターチェンジ ヘッダーとメッセージ本文の両方を 1 つの新しいメッセージに書き込みます。  
  
5.  オーケストレーションは、メッセージには、ReceivePortNameCorrelationType 関連付けの種類に設定されている追加のプロパティを昇格させます。 サブスクリプションに必要なプロパティの一覧を選択するオーケストレーションのユーザーは、します。 これらのプロパティは、メッセージの構築図形で記述されます。 元のメッセージに書き込まれたすべてのコンテキスト プロパティは、新しいメッセージに書き込まれます。  
  
6.  オーケストレーションは、メッセージ ボックスに新しいメッセージを削除します。  
  
7.  送信ポートでは、新しいメッセージを取得して、\Message Enrichment\Out フォルダーにファイル アダプターを経由して送信します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルにある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー。[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Sdk \samples\edi\message Enrichment。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Cleanup.bat|この例のシナリオの展開を解除します。 成功するために必要がありますいないオーケストレーションのアクティブなインスタンス。 それ以外の場合、これは失敗します。|  
|MessageEnrichment.sln|MessageEnrichment と MessageEnrichmentLibrary プロジェクトが含まれています。|  
|Setup.bat|受信ポート、送信ポート、およびオーケストレーションで構成されるシナリオの例をデプロイします。|  
|EDIFACT_example.edi|入力の EDIFACT メッセージです。|  
|X12_example.edi|入力 X12 メッセージ。|  
|MessageEnrichment.btproj|MessageEnrichment のオーケストレーションとスキーマを含むプロジェクト。|  
|MessageEnrichmentBindings.xml|オーケストレーション、ポート、および、パーティのバインドを含んでいるファイルです。|  
|MessageEnrichmentOrchestration.odx|このオーケストレーションは、メッセージにヘッダーを追加します。|  
|MessageEnrichmentOrchestration.odx.cs|メッセージにヘッダーを追加するオーケストレーション コードです。|  
|EFACT_D98B_APERAK.xsd|入力メッセージの EDIFACT スキーマです。|  
|Enriched_EFACT_D98B_APERAK.xsd|出力メッセージの EDIFACT スキーマです。|  
|X12_00401_864.xsd|X12 入力メッセージのスキーマ。|  
|Enriched_X12_00401_864.xsd|X12 出力メッセージのスキーマ。|  
|Headers.xsd|入力メッセージに追加されるヘッダーのスキーマです。|  
|MessageEnrichmentLibrary.csproj|Headers.cs、OrchestrationUtilities.cs、および parseheaders.cs の各ファイルを含むプロジェクトです。|  
|Headers.cs|ヘッダーのデータを表すクラスが含まれています。|  
|OrchestrationUtilities.cs|オーケストレーションによって使用されるユーティリティ メソッドが含まれています。|  
|Parseheaders.cs の各|新しいメッセージで使用される UNA の既定値が含まれています。 これらの値は、parseheaders.cs の SerializeEDIFACTHeaders メソッドから取得されます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 EDI トランザクション セット メッセージにインターチェンジ ヘッダーを追加するために必要なアクションの動作例としては、このサンプルを使用します。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 をビルドし、メッセージ強化サンプルを初期化する必要がありますを構築し、このサンプルでは、BizTalk プロジェクトを配置、場所と受信ポートを構成を 2 つの異なる送信ポートを構成します。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>このサンプルの BizTalk プロジェクト ビルドおよび配置するには  
  
1. Notepad.Exe を使用して開く[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\messageenrichment\  
   MessageEnrichment\properties\AssemblyInfo.cs し、ファイルの下部にある次の行を追加します。  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. 変更した AssemblyInfo.cs ファイルを保存し、メモ帳を終了します。  
  
3. コマンド ウィンドウでは、次のフォルダーに移動します。  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment  
  
4. 実行**Setup.bat**、次の操作を実行します。  
  
   -   受信側を作成します (**で**) と送信 (**アウト**) \MessageEnrichment フォルダーに、このサンプル用のフォルダー。  
  
   -   キーのペアを \testkey.snk に書き込みます  
  
   -   ビルドし、MessageEnrichmentLibrary.btproj プロジェクトをデプロイします。  
  
   -   ビルドし、MessageEnrichment.btproj プロジェクトをデプロイします。  
  
   -   MessageEnrichmentBindings.xml のバインド情報を読み取ります。  
  
       > [!NOTE]
       >  このプロジェクトのバインドでは、BizTalk ホストが信頼されている認証としてマークされている必要があります。  これを使用して、信頼されていないホストで、するには、messageenrichmentbindings.xml し、変更、HostTrusted ="true"のエントリを HostTrusted ="false"。  
  
   -   オーケストレーションのバインドを更新します。  
  
   -   更新プログラムは、送信ポート、送信ポート グループ、および受信ポート。  
  
   -   パーティと参加状況を更新します。  
  
   -   送信ポートを開始します。  
  
   -   受信場所を有効にします。  
  
   -   参加させ、オーケストレーションを開始します。  
  
   BizTalk Server は、このサンプルで動作するようになりました。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 Message Enrichment サンプルを実行するのにには、次の手順を使用します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  EDIFACT_examples.edi ファイルを \MessageEnrichment\Instances フォルダーから \MessageEnrichment\In フォルダーにコピーします。  
  
2.  EDIFACT_examples.edi ファイルが \MessageEnrichment\In フォルダーが表示されなくなり、\MessageEnrichment\Out フォルダーに表示されることを確認します。  
  
3.  \MessageEnrichment\Out フォルダーにファイルを開きます。 \MessageEnrichment\Instances フォルダーにファイルが EDIFACT_examples.edi の XML 表現が出力ファイルに EDIFACT UNA、UNB、および UNG ヘッダーがあることを除き、EDIFACT_examples.edi ファイルと同じ内容があることを確認します。  
  
4.  \MessageEnrichment\Instances フォルダーの X12_examples.edi ファイルには、手順 1. および 2. を繰り返します。  
  
5.  \MessageEnrichment\Out フォルダーに新しいファイルを開きます。 \MessageEnrichment\Instances フォルダーにファイルが X12_examples.edi の XML 表現が X12_examples.edi ファイル、出力ファイルに X12 例外として同じ内容があることを確認 ISA ヘッダー。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 なし  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 (BizTalk Server Samples フォルダー)](../core/edi-and-as2-biztalk-server-samples-folder.md)