---
title: AS2 over File (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fed2344-8181-4c85-a2ef-a421fc40dce1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b604db858e6ad2826ece6c1a925b1ec80d45c6c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528629"
---
# <a name="as2-over-file-biztalk-server-sample"></a>AS2 over File (BizTalk Server サンプル)
AS2 Over File サンプルでは、ファイル経由で AS2 メッセージを受信場所を受信します。 これにより、通常使用される HTTP アダプタではなく、AS2 メッセージを受信するファイル アダプターを使用することができます。 これを行うには、このソリューションは、AS2 メッセージの HTTP ヘッダーを InboundHTTPHeaders コンテキスト プロパティの AS2 デコーダーで必要に応じてを書き込みます。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、HTTP アダプターをしなくても、AS2 メッセージの HTTP ヘッダーを処理する方法を示します。 具体的には、このサンプルは以下の処理を行います。  

1.  入力フォルダーにテスト メッセージをドロップすると、ファイルの受信場所がそれを取得します。  

2.  カスタムの AS2 でのカスタム パイプライン コンポーネントでは、パイプライン プロセスに、その HTTP ヘッダーを InboundHTTPHeaders コンテキスト プロパティに書き込み、メッセージが表示されます。  

    > [!NOTE]
    >  メッセージ失敗は、カスタム パイプライン コンポーネントのダウン ストリームの処理をしている場合にが既に XML に変換されたため、メッセージの処理を再開するが困難なを必要に応じてエンコードします。  

3.  カスタム受信パイプラインで AS2 デコーダーは、その処理を実行する、InboundHTTPHeaders コンテキスト プロパティのプロパティを読み取り、メッセージを処理します。  

4.  送信ポート、受信パイプラインによって生成された XML メッセージをサブスクライブするには、パススルー送信パイプラインを通過およびし、出力フォルダーにドロップします。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルにある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー。[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Sdk \samples\as2\as2 Over File。  

 次の表は、このサンプルのファイルとその目的を示しています。  

|ファイル|説明|  
|---------------|-----------------|  
|AS2OverFile.csproj|カスタム パイプライン コンポーネントのコードを含むプロジェクト。|  
|AS2OverFile.sln|AS2OverFile.btproj プロジェクトを含むソリューションです。|  
|Program.cs|ヘッダーのデータを表すクラスが含まれています。|  
|SampleMessage.txt|HTTP ヘッダーを含むサンプル メッセージです。|  

## <a name="implementing-and-running-this-sample"></a>実装して、このサンプルを実行します。  
 AS2 Over File サンプルを実装するには、以下を行う必要があります。  

-   このサンプルでは、カスタム パイプライン コンポーネントを作成する BizTalk プロジェクト ビルドおよび配置  

-   カスタム パイプライン コンポーネントを使用してカスタム パイプラインを作成、構築し、そのカスタム パイプラインを持つプロジェクトをデプロイします。  

-   入力を作成して、出力ファイル フォルダ  

-   受信ポートと場所を構成し、受信場所を有効にします。  

-   送信ポートを構成し、送信ポートの開始  

-   サンプル メッセージを送信するためのパーティを作成します。  

#### <a name="to-build-a-custom-pipeline-with-the-as2-over-file-emulator-pipeline-component"></a>AS2 経由で File エミュレータ パイプライン コンポーネントのカスタム パイプラインを構築するには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で AS2OverFile プロジェクトを開き、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\as2\as2 Over File フォルダー。  

2. 厳密な名前キー ファイルを作成、AS2OverFile プロジェクトのプロパティ ダイアログ ボックスを開くし、キー ファイルをプロジェクトに割り当てます。  

3. プロジェクトをビルドする。  

4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、AS2OverFile_Pipeline という名前の新しい BizTalk プロジェクトを作成します。  

5. AS2OverFile_Pipeline プロジェクトを右クリックし、[**追加**、] をクリックし、**新しい項目の**します。  

6. **新しい項目の追加**ダイアログ ボックスで、**パイプライン ファイル**左側のウィンドウで次のように選択します**受信パイプライン**右側のウィンドウで、パイプライン AS2OverFile_ という名前。クリックして、Receive.btp**追加**します。  

7. をクリックして**ビュー**メニュー バー、およびクリックで**ツールボックス**ツールボックスを表示します。  

8. ツールボックスで、右クリック**BizTalk パイプライン コンポーネント**、 をクリックし、**アイテムの選択**します。  

9. **ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブ。クリックして**AS2 Over File Emulator**、順にクリックします**OK**します。  

10. 開き、AS2OverFile.dll ファイルをグローバル アセンブリ キャッシュに追加、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでコマンドを実行して`gacutil /if "<file name and path>"`\AS2 Over File\obj\Debug フォルダーで開きの Microsoft.BizTalk.Sdk.Components.AS2OverFile.dll でします。  

11. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ツールボックスから AS2 Over File Emulator パイプライン コンポーネントをドラッグして、**デコード**カスタム パイプラインのステージ。  

12. AS2 デコーダー コンポーネントをドラッグして、**デコード**AS2 Over File コンポーネントの後に、カスタム パイプラインのステージ。  

    > [!NOTE]
    >  MDN を生成する場合は、カスタムのパイプラインの逆アセンブル ステージに、AS2 逆アセンブラを追加します。 MDN を返すしない場合は、AS2 逆アセンブラーは必要ありません。  

13. 厳密な名前キー ファイルを作成、AS2OverFile_Pipeline プロジェクトのプロパティ ダイアログ ボックスを開くし、キー ファイルをプロジェクトに割り当てます。  

14. ビルドして、カスタム パイプラインをデプロイします。  

15. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[パイプライン] ノードをクリックし、をクリックして、カスタム パイプラインを [パイプライン] ノードに追加**更新**します。  

#### <a name="to-implement-the-solution-for-this-sample"></a>このサンプルのソリューションを実装するには  

1. Windows エクスプ ローラーで、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\as2\as2 Over File フォルダーでは、In 入力フォルダと Out 出力フォルダを作成します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、作成、一方向 AS2OverFile_Receive という名前のポートを受信します。 受信ポートでは、次のプロパティを持つ受信場所を作成します。  


   |     プロパティ     |                                                 設定                                                  |
   |------------------|----------------------------------------------------------------------------------------------------------|
   |       名前       |                                           AS2OverFile_Receive                                            |
   |       型       |                                                   FILE                                                   |
   |  受信フォルダ  | [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Sdk \samples\as2\as2 Over File に/ |
   |    ファイル マスク     |                                                  \*.txt                                                  |
   | 受信パイプライン。 |                                               AS2OverFile                                                |


3. 右クリックし、AS2OverFile_Receive 受信場所 をクリックし、受信場所 ノードで**を有効にする**します。  

4. 送信ポート ノードでは、次のプロパティを持つ静的な一方向の送信ポートを作成します。  


   |    プロパティ    |                                                  設定                                                  |
   |----------------|-----------------------------------------------------------------------------------------------------------|
   |      名前      |                                             AS2OverFile_Send                                              |
   |      型      |                                                   FILE                                                    |
   | 受信フォルダ | [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Sdk \samples\as2\as2 Over File 入力/出力 |
   |   ファイル マスク    |                                              %MessageID%.xml                                              |
   | [送信パイプライン]  |                                                 Passthru                                                  |
   |     Assert     |                                BTS.REceivePortName == AS2OverFile_Receive                                 |


5. 送信ポート ノードで、AS2OverFile_Send 送信ポートを右クリックし、**開始**します。  

6. [パーティ] ノードでは、「パートナー」という名前のパーティを作成します。 エイリアスの一覧にエイリアスを追加、**名前**の**ediint-as2 From 値**、**修飾子**の**AS2-から**、および**値**の**パートナー**します。  

   BizTalk Server は、このサンプルを使用する準備ができました。  

## <a name="running-this-sample"></a>このサンプルの実行  
 AS2 Over File サンプルを実行するのにには、次の手順を使用します。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1. SampleMessage.txt ファイルのコピー、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\AS2 Over File\In フォルダーに sdk \samples\as2\as2 Over File フォルダー。  

2. \AS2 Over File\Out 出力フォルダーに出力 XML メッセージが削除されることを確認します。  

3. 入力メッセージ SampleMessage.txt をテキスト エディターで開くし、出力メッセージを開く\<GUID\>.xml をテキスト エディターでします。 SampleMessage.txt 入力メッセージが HTTP (および AS2) ヘッダーを持つことと、出力メッセージに HTTP ヘッダーがないことを確認します。  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 なし  

## <a name="see-also"></a>参照  
 [EDI および AS2 (BizTalk Server Samples フォルダ)](../core/edi-and-as2-biztalk-server-samples-folder.md)   
 [FILE 送信ポートを使用した AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)