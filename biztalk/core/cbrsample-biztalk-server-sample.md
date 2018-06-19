---
title: CBRSample (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, routing
- messages, filters
- outbound maps
- examples, messages
- messages, routing
- examples, outbound maps
- examples, filters
- messages, examples
ms.assetid: 8fba494c-9257-4eed-8b6a-867056147c2c
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b772bc44d4a745d5bfa330e7df7fcadcf2c020db
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22234730"
---
# <a name="cbrsample-biztalk-server-sample"></a>CBRSample (BizTalk Server サンプル)
CBRSample サンプルは、フィルタと送信マップを適用して、コンテンツに基づいてインスタンス メッセージを変換およびルーティングする方法を示しています。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、名前、住所、連絡先情報が含まれたメッセージを、国コードに基づいて 2 つのフォルダのいずれかにルーティングします。 具体的には、このサンプルは以下の処理を行います。  
  
1.  ユーザー ID や氏名による識別情報、国コード付きの住所、電話番号情報など、人物の基本情報を含んでいるサンプル メッセージ形式を定義します。  
  
2.  昇格、 **CountryCode** ことは、コントロールの変換およびルーティングにポート フィルタで使用できるように、入力ドキュメントのプロパティです。  
  
3.  メッセージをカナダ バージョンに変換と **CountryCode** は 200 または (米国) 版と同じとき **CountryCode**が 100 にします。 どちらの変換が中間を除くすべてのデータの初期を通過 (**初期**)。 カナダ バージョンにもマップ **状態** に **Province** と **ZipCode** に **PinCode**します。  
  
4.  米国バージョンのメッセージを US ディレクトリに、カナダ バージョンのメッセージを CAN ディレクトリにルーティングします。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このデザインでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の既定の送受信 XML パイプライン、プロパティの昇格、サブスクリプション フィルター、送信マップを使用して、メッセージをルーティングします。 次の表は、デザイン要素とその選択理由を示しています。  
  
|デザイン要素|選択理由|  
|--------------------|--------------------------|  
|既定の XML 受信パイプライン|XMLReceive パイプラインは、プロパティの昇格をサポートしています。PassThruReceive パイプラインされていません。<br />-受信メッセージは既に XML 形式で、基本の逆アセンブリとパーティの解決以外の処理は必要ありません。|  
|プロパティの昇格|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルーティング プロパティ フィールドによって異なります。 識別フィールドはオーケストレーションによって使用されるため、ルーティングには使用できません。|  
|サブスクリプション フィルター|-サブスクリプションのフィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャして実際のルーティングを実行します。|  
|送信マップ|マップでは、1 つの形式から別のデータを変換します。 このサンプルでは、受信メッセージが米国形式またはカナダ形式にマップされます。|  
|XMLTransmit|-送信 XML メッセージの基本的なアセンブリを実行します。PassThruTransmit パイプラインには、追加のサポートをされていません。|  
  
 この基本パターンを拡張して、より複雑なシナリオに使用することができます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは <`Samples Path>`\Messaging\CBRSample\\します。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|CBRDataCAN.Xml、CBRDataUS.Xml|ファイル CBRInputSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。|  
|CBRInput2CANMap.btm、CBRInput2USMap.btm|それぞれカナダ形式と米国形式の変換のマップ ファイルです。|  
|CBRInputSchema.xsd、CBROutputSchemaCAN.xsd、CBROutputSchemaUS.xsd|それぞれ入力形式、カナダ出力形式、米国出力形式のスキーマ ファイルです。|  
|CBRPromotedPropertySchema.xsd|対応する昇格させたプロパティのスキーマ ファイル、 **CountryCode** 、XML の要素は、ファイルを入力します。|  
|CBRSample.btproj、CBRSample.sln|このサンプルの BizTalk プロジェクト ファイルとソリューション ファイルです。|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、コンテンツに基づいたメッセージのルーティングに必要なアクションの動作例として使用してください。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 CBRSample サンプルをビルドして初期化するには、このサンプルの BizTalk プロジェクトをビルドして展開し、受信ポートと受信場所を構成して、2 つの異なる送信ポートを構成する必要があります。  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>このサンプルの BizTalk プロジェクトをビルドして展開するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     `<Samples Path>` **\Messaging\CBRSample**  
  
2.  実行 **Setup.bat**, 、次の操作を実行します。  
  
    -   入力を作成 (**で**) と出力フォルダ (**u. s.** と **できます**) このサンプルのです。  
  
    -   このサンプル用に Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
    > [!NOTE]
    >  このサンプルでは、作成してポートのバインドとは、次の警告が表示されます。  
    >   
    >  **警告: 受信ハンドラーが指定されていない受信場所"CBRReceiveLocation"です。トランスポートの種類が一致するハンドラーを受信して更新します。**  
    >   
    >  この警告は無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
  
    > [!NOTE]
    >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
    > [!NOTE]
    >  開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
  
    > [!NOTE]
    >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a>受信ポート、受信場所、および送信ポートを構成する準備を行うには  
  
1.  **Microsoft SQL Management Studio**, 、適切な BizTalk 管理データベースを選択します。  
  
    > [!NOTE]
    >  BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。  
  
#### <a name="to-configure-enlist-and-start-the-us-send-port"></a>米国用の送信ポートの構成、参加、開始を行うには  
  
1.  BizTalk Server 管理コンソールで [ **送信ポート**, を右クリックして **CBRUSSendPort**, 、] をクリックし、 **編集**します。  
  
2.  **静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **100**します。  
  
3.  ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2USMap**, 、順にクリック **OK**します。 マップを表示するには、スクロール ボタンのクリックが必要な場合があります。  
  
#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a>カナダ用の送信ポートの構成、参加、開始を行うには  
  
1.  BizTalk Server 管理コンソールで [ **送信ポート**, を右クリックして **CBRCANSendPort**, 、] をクリックし、 **編集**します。  
  
2.  **静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **200**します。  
  
3.  ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2CANMap**, 、順にクリック **OK**します。  
  
 この手順により、送信ポートが受信ポートに接続されます。 このサンプルでは、昇格されたプロパティを使用してドキュメントをルーティングします。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でこのサンプルを使用する準備ができました。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順に従って、CBRSample サンプルを実行します。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  入力ファイルをコピー **CBRDataCAN.xml** と **CBRDataUS.xml**, 、次の入力フォルダにします。  
  
     `<Samples Path>` **\Messaging\CBRSample\In**  
  
2.  これらの各ファイルを変換する方法を確認し、次のいずれかにルーティングされる 2 つの出力フォルダーの値に基づいて、 **CountryCode** 要素 (100 または 200)。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 変換およびルーティング入力ファイル**CBRDataCAN.xml**フォルダーに。  
  
         `<Samples Path>` **\Messaging\CBRSample\CAN**  
  
    -   BizTalk Server は、変換し、入力ファイルをルーティング **CBRDataUS.xml** フォルダーにします。  
  
         `<Samples Path>` **\Messaging\CBRSample\US**  
  
## <a name="classes-or-methods-used-in-this-sample"></a>このサンプルで使用されるクラスまたはメソッド  
 [なし] :  
  
## <a name="see-also"></a>参照  
 [既定のパイプライン](../core/default-pipelines.md)   
 [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [Messaging (BizTalk Server Samples フォルダー)](../core/messaging-biztalk-server-samples-folder.md)