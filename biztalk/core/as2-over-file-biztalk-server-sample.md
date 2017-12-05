---
title: "AS2 over File (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d4c077cce861e94f6c2cdc0bfc6f4a14669340
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 Over File (BizTalk Server サンプル)
AS2 Over File サンプルでは、FILE 受信場所経由で AS2 メッセージを受信する方法を示します。 これにより、通常使用される HTTP アダプタではなく、FILE アダプタを使用して AS2 メッセージを受信できます。 そのために、このソリューションは、AS2 デコーダーの要求に応じて、AS2 メッセージの HTTP ヘッダーを InboundHTTPHeaders コンテキスト プロパティに書き込みます。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、HTTP アダプタを使用せずに AS2 メッセージの HTTP ヘッダーを処理する方法を示します。 具体的には、このサンプルは以下の処理を行います。  
  
1.  テスト メッセージを入力フォルダにドロップすると、FILE 受信場所がそのメッセージを取得します。  
  
2.  カスタム AS2 受信パイプラインのカスタム パイプライン コンポーネントはメッセージを処理し、HTTP ヘッダーを InboundHTTPHeaders コンテキスト プロパティに書き込みます。  
  
    > [!NOTE]
    >  メッセージの処理がカスタム パイプライン コンポーネントのダウンストリームに失敗した場合、メッセージが既に XML エンコードに変換されているため、メッセージの処理の再開が困難になる可能性があります。  
  
3.  カスタム受信パイプラインの AS2 デコーダはメッセージを処理し、InboundHTTPHeaders コンテキスト プロパティのプロパティを読み取り、その処理を行います。  
  
4.  送信ポートは受信パイプラインによって生成された XML メッセージをサブスクライブし、パススルー送信パイプラインを通じて渡した後、出力フォルダにドロップします。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール フォルダー ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File) にあります。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|AS2OverFile.csproj|カスタム パイプライン コンポーネント コードを含むプロジェクトです。|  
|AS2OverFile.sln|AS2OverFile.btproj プロジェクトを含むソリューションです。|  
|Program.cs|ヘッダー データを表すクラスが含まれています。|  
|SampleMessage.txt|HTTP ヘッダーを含むサンプル メッセージです。|  
  
## <a name="implementing-and-running-this-sample"></a>このサンプルの実装と実行  
 AS2 Over File サンプルを実装するには、次の操作を行う必要があります。  
  
-   このサンプルの BizTalk プロジェクトをビルドして展開し、カスタム パイプライン コンポーネントを作成します。  
  
-   カスタム パイプライン コンポーネントを使用してカスタム パイプラインを作成し、そのカスタム パイプラインを使用してプロジェクトをビルドおよび展開します。  
  
-   入力ファイル フォルダと出力ファイル フォルダを作成します。  
  
-   受信ポートと受信場所を構成し、受信場所を有効にします。  
  
-   送信ポートを構成して開始します。  
  
-   サンプル メッセージを送信するパーティを作成します。  
  
#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>AS2 Over File エミュレータ パイプライン コンポーネントを使用してカスタム パイプラインを構築するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File フォルダーで AS2OverFile プロジェクトを開きます。  
  
2.  厳密な名前キー ファイルを作成し、AS2OverFile プロジェクトの [プロパティ] ダイアログ ボックスを開き、キー ファイルをプロジェクトに割り当てます。  
  
3.  プロジェクトをビルドする。  
  
4.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、AS2OverFile_Pipeline という名前の新しい BizTalk プロジェクトを作成します。  
  
5.  AS2OverFile_Pipeline プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。  
  
6.  **新しい項目の追加**ダイアログ ボックスで、**パイプライン ファイル**、左側のペインで選択**受信パイプライン**AS2OverFile_ パイプラインの名前を右側のペインでクリックして、Receive.btp**追加**です。  
  
7.  をクリックして**ビュー**をクリックしてメニュー バーで**ツールボックス**ツールボックスを表示します。  
  
8.  ツールボックスを右クリックして**BizTalk パイプライン コンポーネント**、クリックして**アイテムの選択**です。  
  
9. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブです。をクリックして**AS2 Over File Emulator**、順にクリック**OK**です。  
  
10. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトを開き、\AS2 Over File\obj\Debug フォルダーの Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll で `gacutil /if "<file name and path>"` コマンドを実行して、AS2OverFile.dll ファイルをグローバル アセンブリ キャッシュに追加します。  
  
11. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ツールボックスから AS2 Over File Emulator パイプライン コンポーネントをドラッグして、**デコード**カスタム パイプラインのステージ。  
  
12. AS2 デコーダー コンポーネントをドラッグして、**デコード**AS2 Over File コンポーネントの後に、カスタム パイプラインのステージ。  
  
    > [!NOTE]
    >  MDN を生成する場合は、AS2 逆アセンブラをカスタム パイプラインの逆アセンブル ステージに追加します。 MDN を返さない場合、AS2 逆アセンブラは不要です。  
  
13. 厳密な名前キー ファイルを作成し、AS2OverFile_Pipeline プロジェクトの [プロパティ] ダイアログ ボックスを開き、キー ファイルをプロジェクトに割り当てます。  
  
14. カスタム パイプラインをビルドして配置します。  
  
15. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[パイプライン] ノードをクリックし、をクリックして、カスタム パイプラインを [パイプライン] ノードに追加**更新**です。  
  
#### <a name="to-implement-the-solution-for-this-sample"></a>このサンプルのソリューションを実装するには  
  
1.  Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File フォルダーに In 入力フォルダーおよび Out 出力フォルダーを作成します。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、AS2OverFile_Receive という名前の一方向の受信ポートを作成します。 作成した受信ポートで、次のプロパティを使用して受信場所を作成します。  
  
    |プロパティ|設定|  
    |--------------|-------------|  
    |名前|AS2OverFile_Receive|  
    |型|FILE|  
    |受信フォルダ|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/In|  
    |ファイル マスク|*.txt|  
    |受信パイプライン。|AS2OverFile|  
  
3.  受信場所 ノードを右クリックし、AS2OverFile_Receive 受信場所、をクリックしてで**を有効にする**です。  
  
4.  [送信ポート] ノードで、次のプロパティを使用して静的な一方向の送信ポートを作成します。  
  
    |プロパティ|設定|  
    |--------------|-------------|  
    |名前|AS2OverFile_Send|  
    |型|FILE|  
    |受信フォルダ|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File/Out|  
    |ファイル マスク|%MessageID%.xml|  
    |[送信パイプライン]|Passthru|  
    |[フィルター]|BTS.REceivePortName == AS2OverFile_Receive|  
  
5.  送信ポート ノードで、AS2OverFile_Send 送信ポートを右クリックし、をクリックして**開始**です。  
  
6.  [パーティ] ノードで、"Partner" という名前のパーティを作成します。 エイリアスの一覧にエイリアスを追加、**名前**の**ediint-as2 From Value**、**修飾子**の**AS2-から**、および**値**の**パートナー**です。  
  
 BizTalk Server は、このサンプルを使用する準備ができました。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、AS2 Over File サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  SampleMessage.txt ファイルを、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\AS2\AS2 Over File フォルダーから \AS2 Over File\In フォルダーにコピーします。  
  
2.  出力 XML メッセージが \AS2 Over File\Out 出力フォルダーにドロップされることを確認します。  
  
3.  入力メッセージ SampleMessage.txt をテキスト エディターで開き出力メッセージ\<GUID\>をテキスト エディターで .xml です。 SampleMessage.txt 入力メッセージに HTTP (および AS2) ヘッダーがあり、出力メッセージに HTTP ヘッダーがないことを確認します。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 なし  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 (BizTalk Server Samples フォルダ)](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [FILE 送信ポートを使用した AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)