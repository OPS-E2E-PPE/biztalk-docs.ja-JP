---
title: CBRSample (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: f850f3f64fbc13596c5548fadf57c5055052a244
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357583"
---
# <a name="cbrsample-biztalk-server-sample"></a>CBRSample (BizTalk Server サンプル)
CBRSample サンプルはフィルターと送信を変換するマップを適用する方法とコンテンツに基づいてインスタンス メッセージをルーティングします。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、名前、アドレス、および国コードに基づいて 2 つのフォルダーのいずれかの連絡先情報を格納しているメッセージのルーティングを示します。 具体的には、このサンプルは以下の処理を行います。  

1.  サンプル メッセージ形式基本的な情報を含むユーザー ID と完全名、国コード、および電話番号情報とアドレスを持つ id を含む個人に関するを定義します。  

2.  昇格、 **CountryCode**その it をコントロールの変換およびルーティングにポート フィルタで使用できるように、入力ドキュメントのプロパティ。  

3.  メッセージをカナダ バージョンに変換と**CountryCode**は 200 または米国バージョンと**CountryCode**が 100 にします。 どちらの変換が中間を除くすべてのデータの初期を通過 (**初期**)。 カナダ バージョンにもマップ**状態**に**Province**と**ZipCode**に**PinCode**します。  

4.  ディレクトリの米国およびカナダ バージョンのメッセージを CAN ディレクトリには、米国のメッセージをルーティングします。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 デザインは、既定の送信送受信 XML パイプライン、プロパティの昇格、サブスクリプション フィルター、および送信マップ内で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージをルーティングします。 次の表は、デザイン要素とその選択理由を示します。  


|        デザイン要素        |                                                                                                          選択理由                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 既定の XML 受信パイプライン | -XMLReceive パイプラインには、プロパティの昇格がサポートしていますPassThruReceive パイプラインは提供されません。<br />-受信メッセージは既に XML 形式で、基本の逆アセンブリとパーティの解決以外の処理は必要ありません。 |
|      プロパティの昇格      |          -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルーティングを実行するフィールドをプロパティに依存します。 識別フィールドはオーケストレーションによって使用されるため、ルーティングには使用できません。           |
|     サブスクリプション フィルター      |                                                -サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。                                                |
|         送信マップ         |                                                     マップでは、1 つの形式から別のデータを変換します。 サンプルは、受信メッセージを米国またはカナダのいずれかの形式にマップします。                                                      |
|         XMLTransmit          |                                                         -送信 XML メッセージの基本的なアセンブリを実行します。追加サポートを提供している PassThruTransmit パイプラインはありません。                                                          |

 この基本パターンを拡張しより複雑なシナリオのために使用します。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは <`Samples Path>`\Messaging\CBRSample\\します。  

 次の表は、このサンプルのファイルとその目的を示しています。  

|ファイル|説明|  
|---------------|-----------------|  
|CBRDataCAN.Xml, CBRDataUS.Xml|ファイル CBRInputSchema.xsd で定義されたスキーマに準拠しているサンプル入力ファイル。|  
|CBRInput2CANMap.btm, CBRInput2USMap.btm|それぞれカナダ ファイルと米国形式の変換をマップします。|  
|CBRInputSchema.xsd, CBROutputSchemaCAN.xsd, CBROutputSchemaUS.xsd|スキーマ ファイル入力形式、カナダ出力形式、および米国では、それぞれの形式を出力します。|  
|CBRPromotedPropertySchema.xsd|対応する昇格させたプロパティのスキーマ ファイル、 **CountryCode** XML 内の要素は、ファイルを入力します。|  
|CBRSample.btproj, CBRSample.sln|このサンプルの BizTalk プロジェクトおよびソリューション ファイル。|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 コンテンツに基づいてメッセージのルーティングに必要なアクションの動作例としては、このサンプルを使用します。  

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
 初期化 CBRSample サンプルをビルドし、する必要がありますを構築し、このサンプルでは、BizTalk プロジェクトを配置する受信ポートと場所、構成を 2 つの異なる送信ポートを構成します。  

#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a>このサンプルの BizTalk プロジェクト ビルドおよび配置するには  

1. コマンド ウィンドウで、次のフォルダーに移動します。  

    `<Samples Path>` **\Messaging\CBRSample**  

2. 実行**Setup.bat**、次の操作を実行します。  

   - 入力を作成します (**で**) と出力フォルダ (**米国**と**できます**) このサンプルの。  

   - コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

   > [!NOTE]
   >  このサンプルでは、作成してポートをバインドするときに、次の警告が表示されます。  
   > 
   >  **警告:受信ハンドラーが指定されていない受信場所"CBRReceiveLocation";最初の更新の受信トランスポートの種類に一致するハンドラー。**  
   > 
   >  この警告は無視してかまいません。 (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
   > 
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
   > 
   > [!NOTE]
   >  開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。  
   > 
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

#### <a name="to-prepare-to-configure-the-receive-port-and-location-and-the-send-ports"></a>受信ポートと場所、および送信ポートを構成する準備を行う  

1.  **Microsoft SQL Management Studio**、適切な BizTalk 管理データベースを選択します。  

    > [!NOTE]
    >  BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。  

#### <a name="to-configure-enlist-and-start-the-us-send-port"></a>米国の送信ポートを構成し、参加、開始するには  

1.  BizTalk Server 管理コンソールで [**送信ポート**を右クリックして **[cbrussendport]**、] をクリックし、**編集**。  

2.  **静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **100**します。  

3.  ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2USMap**, 、順にクリック **OK**します。 マップを表示するスクロール ボタンをクリックする必要があります。  

#### <a name="to-configure-enlist-and-start-the-canadian-send-port"></a>構成、参加、およびカナダの送信ポートを開始するには  

1. BizTalk Server 管理コンソールで [**送信ポート**を右クリックして **[cbrcansendport]**、] をクリックし、**編集**。  

2. **静的な一方向送信ポート プロパティ** ダイアログ ボックスのダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。フィルター**, を設定して、新しい行を追加 **プロパティ** に **CBRSample.CountryCode**, したまま、 **演算子** 列に設定 **==**, と設定、 **値** 列を **200**します。  

3. ダイアログ ボックスの左側のフォルダ ツリーで選択 **フィルターとのマッピングと &#124; 文字です。送信マップ**, 、設定されて、 **に適用するマップ** プロパティを **CBRSample.CBRInput2CANMap**, 、順にクリック **OK**します。  

   次の手順では、受信ポートに送信ポートを接続します。 サンプルの使用は、ドキュメントをルーティングするプロパティを昇格します。  

   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] このサンプルを使用する準備ができました。  

## <a name="running-this-sample"></a>このサンプルの実行  
 CBRSample サンプルを実行するのにには、次の手順を使用します。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1. 入力ファイルをコピー **CBRDataCAN.xml**と**CBRDataUS.xml**、次の入力フォルダに。  

    `<Samples Path>` **\Messaging\CBRSample\In**  

2. これらの各ファイルを変換する方法を確認し、2 つの出力フォルダーの値に基づいて、次のいずれかにルーティング、 **CountryCode**要素 (100 または 200)。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 変換およびルーティング、入力ファイル**CBRDataCAN.xml**フォルダー。  

      `<Samples Path>` **\Messaging\CBRSample\CAN**  

   - BizTalk Server が変換および入力ファイルをルーティング**CBRDataUS.xml**フォルダー。  

      `<Samples Path>` **\Messaging\CBRSample\US**  

## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 [なし] :  

## <a name="see-also"></a>参照  
 [既定のパイプライン](../core/default-pipelines.md)   
 [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [Messaging (BizTalk Server Samples フォルダー)](../core/messaging-biztalk-server-samples-folder.md)