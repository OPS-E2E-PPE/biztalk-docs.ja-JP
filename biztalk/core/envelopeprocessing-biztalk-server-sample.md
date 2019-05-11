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
ms.openlocfilehash: 304a19f0ab775438f01df107baf860962cf89166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349235"
---
# <a name="envelopeprocessing-biztalk-server-sample"></a>EnvelopeProcessing (BizTalk Server サンプル)
EnvelopeProcessing サンプルは、メッセージのメッセージのエンベロープを処理する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプライン。 さらに、XML メッセージにフラット ファイル メッセージを処理する方法を示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、受信場所として、EnvInput フォルダを構成します。 サンプル ファイル EnvelopeProcessing_in.txt、このフォルダーにファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の手順を使用してこのファイル内のメッセージを処理します。  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所フォルダ EnvInput からメッセージ ファイルを取得します。  

2. 受信パイプラインで、フラット ファイル逆アセンブラー パイプライン コンポーネントは、フラット ファイル メッセージからヘッダーおよびトレーラを削除し、個々 のメッセージに解析します。  

3. メッセージ ボックス データベースでは、メッセージは、サブスクリプション フィルターを使用して、送信ポートにルーティングされます。  

4. 送信ポートの送信パイプラインでは、XML アセンブラー パイプライン コンポーネントは、メッセージを XML エンベロープでラップし、送信アダプタ フォルダ EnvOutput に配置します。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルのデザインは、2 つの基本的な要件に対応する必要があります。  

- 受信して、1 つまたは複数の注文書を含むフラット ファイル メッセージを処理します。  

- バックエンド処理システムによって 1 つ購入順序と送信者情報ピックアップ ディレクトリを含む 1 つの XML メッセージを送信します。  

  これらの要件を満たすには、フラットファイルおよび XML スキーマとカスタム パイプラインの組み合わせが使用されました。 これらおよび他のデザイン要素は、次の表にまとめたものです。  

|デザイン要素|選択理由|  
|--------------------|--------------------------|  
|カスタム受信パイプライン|-受信した注文書の注文メッセージを変換するのに、フラット ファイル逆アセンブラーとフラット ファイル スキーマを使用します。|  
|メッセージのヘッダー、ボディ、およびトレーラ用フラット ファイル スキーマ|-すべての同じレコードとフィールドの特性 (構造体を含む) として定義 XML スキーマとすべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。<br />ヘッダー、本文、およびトレーラーのスキーマは、本文を処理するための個々 のチャンクに分割に使用されます。|  
|エンベロープ スキーマ|-ヘッダーからの情報の個別の注文をラップするために使用します。|  
|サブスクリプション フィルター|-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。|  
|カスタム送信パイプライン|-インスタンス メッセージを XML 形式に変換するのに XML アセンブラおよびエンベロープとボディ スキーマの組み合わせを使用します。|  

 このサンプルのデザインに次の考慮事項が適用されます。  

-   フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。 これらのファイルを手動で作成できますが、多くは、フラット ファイル ウィザードを使用して生成できます。  

-   注文書 (PO.xsd) フラット ファイルのスキーマは、Unqualified の elementFormDefault 値を使用します。 正しい結果が生成されますが、追加の予期しない xmlns 修飾します。 この問題を回避するために、Qualified の elementFormDefault を使用します。  

-   ヘッダーおよびトレーラ フラット ファイル スキーマは、先頭および末尾のメッセージからのデータを個別に使用されます。 フラット ファイル逆アセンブラーのヘッダー、ドキュメント、およびトレーラーのスキーマをヘッダー プロパティを設定した注文書、およびトレーラのスキーマをそれぞれします。  

-   XML エンベロープ スキーマは、1 つの XML メッセージを生成するためにヘッダーと注文書の注文から要素を結合します。 ヘッダー スキーマでは、ソース フィールドを昇格 SourceParty フィールドに、 **BTS.bts_system_properties**名前空間。 エンベロープ スキーマに、送信メッセージに降格する原因となる、同じ値を昇格させます。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 `<Samples Path>`\Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                      ファイル                      |                                                                                               説明                                                                                               |
|---------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    Cleanup.bat                    |    アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。     |
| EnvelopeProcessing.btproj、EnvelopeProcessing.sln |                                                                               このサンプルのプロジェクト ファイルとソリューション ファイルです。                                                                               |
|             EnvelopeProcessing_in.txt             |                                                                                           サンプル入力ファイルです。                                                                                            |
|          Header.xsd、PO.xsd、Trailer.xsd          |                                                                      フラット スキーマは、ヘッダー、本文、およびトレーラーをそれぞれファイルします。                                                                      |
|                  XmlEnvelope.xsd                  |                                                                                    送信 XML エンベロープ用スキーマです。                                                                                    |
|    EnvReceivePipeline.btp, EnvSendPipeline.btp    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信し、それぞれのフラット ファイル逆アセンブラーおよび XML アセンブラー パイプライン コンポーネントでは、パイプライン ファイルを送信します。 |
|           EnvelopeProcessingBinding.xml           |                                                                             ポートのバインドなど、自動化されたセットアップに使用されます。                                                                              |
|                     Setup.bat                     |                                                                                このサンプルをビルドおよび初期化するために使用されます。                                                                                |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを独自のフラット ファイル処理ソリューションの基礎として使用します。 多くの独自の要件に合わせて、このサンプルで使用されるデザイン要素を拡張することができます。 いくつかの例は次のとおりです。  

-   書き込む XML バージョンに加えて、各注文書のフラット ファイルのバージョンのサンプルを強化します。 新しいカスタム送信パイプラインを作成して、フラット ファイル アセンブラーを使用して、これを行うことができます。 フラット ファイル アセンブラー、フラット ファイルのヘッダーを指定、発注書、およびトレーラのスキーマ。 送信ポートで使用する場合は、ヘッダーおよびトレーラの情報を個別の注文を生成します。  

-   詳細については、注文のエンベロープを強化します。 送信メッセージに追加情報を記述するには、「出荷先」名またはクイック昇格を使用して他のフィールドを昇格、封筒にフィールドを追加および同じフィールドをエンベロープ フィールドを昇格させます。 アセンブラーを通じて、メッセージが処理されるときに昇格させたプロパティが降格し、送信メッセージにコピーします。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

#### <a name="to-build-and-initialize-the-envelopeprocessing-sample"></a>ビルドして初期化 EnvelopeProcessing サンプル  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    *\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing  

2. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - フォルダーには、入力 (EnvInput) とこのサンプルの出力 (EnvOutput) フォルダーを作成します。  

      *\<Samples Path\>* \Pipelines\AssemblerDisassembler\EnvelopeProcessing\  

   - コンパイルし、このサンプルの Visual Studio プロジェクトを展開します。  

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

1.  EnvelopeProcessing_in.txt ファイルのコピーを EnvInput フォルダに配置します。  

2.  EnvOutput フォルダーに作成された 3 つの .xml ファイルを確認します。 これらの .xml ファイルの名前は、そのメッセージ ID Guid に基づいています。 入力ファイルから抽出され、エンベロープでラップされたメッセージが含まれます。  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 Setup.bat および Cleanup.bat の構成スクリプトは、次の管理用の Windows Management Instrumentation (WMI) スクリプトに依存します。  

- Start Send Port\StartSendPort.vbs  

- Enable Receive Location\EnableRecLoc  

- Remove Send Port\RemoveSendPort  

  セットアップとクリーンアップ バッチ ファイルは、次のような BTSTask を使用します。  

- **BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには  

- **BTSTask RemoveApp** FlatFileReceiveApplication を削除するには  

## <a name="see-also"></a>参照  
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)