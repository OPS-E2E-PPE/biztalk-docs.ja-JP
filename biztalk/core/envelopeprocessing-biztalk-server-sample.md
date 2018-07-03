---
title: EnvelopeProcessing (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, envelopes
- flat files, processing
- examples, flat files
- examples, messages
- examples, envelopes
- envelopes, messages
- flat files, examples
- envelopes, examples
ms.assetid: b4cd979b-c7b4-446c-be29-c9f3169afa1f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4206d46ec3a14d269f14d977133fb7211db694c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994531"
---
# <a name="envelopeprocessing-biztalk-server-sample"></a>EnvelopeProcessing (BizTalk Server サンプル)
EnvelopeProcessing サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプラインでメッセージおよびメッセージ エンベロープを処理する方法を示します。 さらに、フラット ファイル メッセージを XML メッセージに変換する方法も示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、EnvInput フォルダを受信場所として構成します。 このフォルダーにサンプル ファイル EnvelopeProcessing_in.txt のようなファイルを置くと、このファイル内のメッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって次の手順で処理されます。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信場所フォルダー EnvInput からメッセージ ファイルを取得します。  

2. 受信パイプラインで、フラット ファイル逆アセンブラのパイプライン コンポーネントがフラット ファイル メッセージからヘッダーおよびトレーラを削除し、個別のメッセージに解析します。  

3. MessageBox データベースで、メッセージがサブスクリプション フィルタを使用して送信ポートにルーティングされます。  

4. 送信ポートの送信パイプラインで、XML アセンブラ パイプライン コンポーネントがメッセージを XML エンベロープにラップし、送信アダプタ フォルダ EnvOutput に配置します。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルのデザインでは、次の 2 つの基本要件に対応する必要がありました。  

- 1 つ以上の注文書を含むフラット ファイル メッセージを受信して処理する。  

- 1 つの注文書と送信者情報を含む 1 つの XML メッセージをディレクトリに送信し、バックエンド処理システムがメッセージを取得できるようにする。  

  これらの要件を満たすために、フラットファイルおよび XML スキーマとカスタム パイプラインの組み合わせが使用されました。 これらのデザイン要素と他のデザイン要素を次の表にまとめます。  

|デザイン要素|選択理由|  
|--------------------|--------------------------|  
|カスタム受信パイプライン|-受信した注文書の注文メッセージを変換するのに、フラット ファイル逆アセンブラーとフラット ファイル スキーマを使用します。|  
|メッセージ ヘッダー、ボディ、およびトレーラ用フラット ファイル スキーマ|-すべての同じレコードとフィールドの特性 (構造体を含む) として定義 XML スキーマとすべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。<br />ヘッダー、本文、およびトレーラーのスキーマは、本文を処理するための個々 のチャンクに分割に使用されます。|  
|エンベロープ スキーマ|-ヘッダーからの情報の個別の注文をラップするために使用します。|  
|サブスクリプション フィルター|-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。|  
|カスタム送信パイプライン|-インスタンス メッセージを XML 形式に変換するのに XML アセンブラおよびエンベロープとボディ スキーマの組み合わせを使用します。|  

 このサンプルのデザインでは、次の事項を考慮する必要があります。  

-   フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。 これらのファイルは手動で作成できますが、その多くはフラット ファイル ウィザードを使用して生成できます。  

-   注文書 (PO.xsd) フラット ファイル スキーマは、Unqualified の elementFormDefault 値を使用します。 これにより正しい結果が得られますが、結果には予期しない xmlns 修飾が追加されます。 この問題を避けるには、Qualified の elementFormDefault を使用してください。  

-   ヘッダーおよびトレーラ フラット ファイル スキーマは、先頭および末尾のデータをメッセージから分離するために使用します。 フラット ファイル逆アセンブラのヘッダー、ドキュメント、およびトレーラのスキーマ プロパティは、それぞれヘッダー、注文書、およびトレーラ スキーマに設定されていました。  

-   XML エンベロープ スキーマは、ヘッダーと注文書の要素を組み合わせて 1 つの XML メッセージを作成します。 ヘッダー スキーマでは、ソース フィールドを昇格 SourceParty フィールドに、 **BTS.bts_system_properties**名前空間。 エンベロープ スキーマに、送信メッセージに降格する原因となる、同じ値を昇格させます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 `<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                      ファイル                      |                                                                                               説明                                                                                               |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Cleanup.bat                    |    アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。     |
| EnvelopeProcessing.btproj、EnvelopeProcessing.sln |                                                                               このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                               |
|             EnvelopeProcessing_in.txt             |                                                                                           サンプル入力ファイルです。                                                                                            |
|          Header.xsd、PO.xsd、Trailer.xsd          |                                                                      フラット ファイルのヘッダー、ボディ、およびトレーラにそれぞれ対応するスキーマです。                                                                      |
|                  XmlEnvelope.xsd                  |                                                                                    送信 XML エンベロープ用スキーマです。                                                                                    |
|    EnvReceivePipeline.btp、EnvSendPipeline.btp    | フラット ファイル逆アセンブラーおよび XML アセンブラーのパイプライン コンポーネントをそれぞれ含む [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信パイプライン ファイルと送信パイプライン ファイルです。 |
|           EnvelopeProcessingBinding.xml           |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                              |
|                     Setup.bat                     |                                                                                このサンプルをビルドおよび初期化するために使用されます。                                                                                |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、独自のフラット ファイル処理ソリューションの基礎として使用してください。 このサンプルで使用されているデザイン要素の多くは、独自の要件に合うように拡張できます。 いくつかの例を次に示します。  

-   各注文書の XML バージョンに加えてフラット ファイル バージョンを書き込むようにサンプルを強化します。 この操作を行うには、新しいカスタム送信パイプラインを作成し、フラット ファイル アセンブラを使用します。 フラット ファイル アセンブラで、フラット ファイルのヘッダー、注文書、およびトレーラのスキーマを指定します。 送信ポートで使用する場合は、ヘッダーおよびトレーラの情報を含む個別の注文書が作成されます。  

-   注文書の情報を追加してエンベロープを強化します。 追加情報を送信メッセージに書き込むには、クイック昇格を使用して "出荷先" 名または他のフィールドを昇格させ、フィールドをエンベロープに追加し、エンベロープ フィールドを同じフィールドに昇格させます。 アセンブラを経由してメッセージが処理されるとき、昇格したプロパティは降格され、送信メッセージにコピーされます。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a>EnvelopeProcessing サンプルをビルドおよび初期化するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - 次のフォルダに、このサンプルの入力フォルダ (EnvInput) と出力フォルダ (EnvOutput) を作成します。  

      *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

   - このサンプル用に Visual Studio プロジェクトをコンパイルおよび展開します。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

      このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。  

     ```  
     Warning: Receive handler not specified for receive location "EnvelopeProcessing_RL"; updating with first receive handler with matching transport type.  
     Warning: Host not specified for orchestration "EnvelopeProcessing"; updating with first available host.  
     ```  

      これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートを開始します。  

> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
> 
> [!NOTE]
>  開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
> 
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-envelopeprocessing-sample"></a>EnvelopeProcessing サンプルを実行するには  

1.  EnvelopeProcessing_in.txt ファイルを EnvInput フォルダにコピーします。  

2.  3 つの .xml ファイルが EnvOutput フォルダに作成されていることを確認します。 これらの .xml ファイルの名前はメッセージ ID GUID に基づいて付けられます。 これらのファイルには、入力ファイルから抽出され、エンベロープでラップされたメッセージが含まれています。  

## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 Setup.bat および Cleanup.bat の 2 つの構成スクリプトは、次の管理用 Windows Management Instrumentation (WMI) スクリプトに依存しています。  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- Remove Send Port\RemoveSendPort  

  セットアップおよびクリーンアップのバッチ ファイルでは、次のように BTSTask を使用します。  

- **BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには  

- **BTSTask RemoveApp** FlatFileReceiveApplication を削除するには  

## <a name="see-also"></a>参照  
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)