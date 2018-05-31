---
title: 'チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用して PeopleSoft Enterprise からデータを取得する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c173fa4c-911e-4fa3-813f-e8f36b0049a5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 510ee984688d218e2c83b4e70dcdf737cd5566e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975528"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a>チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用した PeopleSoft Enterprise からのデータの取得
BizTalk Adapter for PeopleSoft Enterprise を使用すると、PeopleSoft システムに対してクエリを実行し、そのクエリの結果を返すことができます。 ここでは、この機能を示す SDK サンプルについて説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   Java 2 Platform がインストールされている必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Adapter for PeopleSoft Enterprise の Geis で実行されています。  
  
-   PeopleSoft Java Object Adapter JAR ファイル**psjoa.jar**にアクセスできるフォルダーにコピーするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で BizTalk Adapter for PeopleSoft Enterprise が実行されています。  
  
-   サンプルをビルドして展開するには、BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている必要があります。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for PeopleSoft Enterprise を使用して PeopleSoft システムに対してクエリを実行します。 クエリの結果は、XML ファイルに書き込まれます。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for PeopleSoft Enterprise を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次のフォルダーにあります。  
  
 \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|**ランタイム プロジェクト ファイル名**|**ランタイム プロジェクト ファイルの説明**|  
|----------------------------------|------------------------------------------|  
|TwoWaySend.btproj、<br /><br /> TwoWaySend.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|LOCATIONService.xsd、<br /><br /> LOCATIONService_1.xsd、<br /><br /> LOCATIONService_2.xsd|アプリケーションのスキーマ ファイル。 **注:** アダプター スキーマ ファイルは、プロジェクトでは、使用してもともと作成された、**アダプター メタデータの追加ウィザード**です。 アダプター メタデータの追加ウィザードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「アダプター メタデータを BizTalk プロジェクトに追加する方法」を参照してください。|  
|PeopleSoftTwoWaySend.odx|アプリケーションが使用するオーケストレーション。|  
|PeopleSoftTwoWaySend.snk|厳密な名前のキー ファイル。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
  
#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>PeopleSoft Enterprise アダプターの新しいインスタンスを作成する  
  
1.  起動して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 をクリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**をクリックして**アダプター**です。  
  
3.  右クリック**アダプター**を指す**新規**、**アダプター**を表示する、**アダプターのプロパティ**ダイアログ。  
  
4.  値を入力して、**名前**フィールド、たとえば**PeopleSoft**です。  
  
5.  選択**PeopleSoft enterprise (r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウン リスト をクリック**OK**です。  
  
#### <a name="create-a-solicit-response-biztalk-send-port"></a>送信請求 - 応答の BizTalk 送信ポートを作成する  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**送信ポート**です。  
  
2.  右クリック**送信ポート**を指す**新規**、**静的な送信請求-応答送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  
  
3.  値を入力して、**名前**フィールド、たとえば**PeopleSoftTwoWaySP**です。  
  
4.  使用可能なアダプターの一覧から PeopleSoft アダプターを選択、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートのプロパティ** ダイアログ ボックス。  
  
    > [!NOTE]
    >  この値は、管理コンソールで PeopleSoft Enterprise アダプターを作成したときに指定した名前です。  
  
5.  次の値を入力、**アダプターに必要なプロパティ**:  
  
    |**プロパティ**|**値**|  
    |------------------|---------------|  
    |アプリケーション サーバーのパス|PeopleSoft Server のコンピューターおよびポートの場所 (例: //PSServer:8888)。 **注:** する上記の例ででした入力ように//PSServer の値、PeopleSoft サーバーは、既定のポート値 9000 を使用している場合、9000 の既定のポートが使用されるポート番号を指定しない場合。|  
    |JAVA_HOME|Java 2 Platform SDK ファイルに関連付けられているホーム ディレクトリへのパス (例: C:\j2sdk1.4.2_08)。|  
    |Password|PeopleSoft システムへの接続時に使用するパスワード。|  
    |PeopleSoft 8.x JAR ファイル|PeopleSoft Java Object Adapter JAR ファイルの場所**psjoa.jar**C:\JARS\psjoa.jar 例を示します。|  
    |ユーザー名|PeopleSoft システムへの接続時に使用するユーザー名。|  
  
6.  **[OK]** をクリックします。  
  
7.  選択、 **XMLTransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウンします。  
  
8.  選択、 **xmlreceive**パイプラインで使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト をクリック**OK**です。  
  
9. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  
  
#### <a name="create-a-one-way-biztalk-send-port"></a>一方向 BizTalk 送信ポートを作成する  
  
1.  送信ポートで使用されるターゲット フォルダーを作成します (例: C:\Files\Out)。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**送信ポート**です。  
  
3.  右クリック**送信ポート**を指す**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  
  
4.  値を入力して、**名前**フィールド、たとえば**PeopleSoftTwoWayFileSP**です。  
  
5.  選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。  
  
6.  用に作成したフォルダーの場所を入力、**コピー先フォルダー**プロパティをクリック**OK**です。  
  
7.  選択、 **xmltransmit**パイプラインで使用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン リスト をクリック**OK**です。  
  
8.  送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  
  
#### <a name="create-a-file-receive-port"></a>ファイル受信ポートを作成する  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**受信ポート**です。  
  
2.  受信ポート フォルダーを右クリックし、をクリックして**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。  
  
3.  値を入力、**名前**フィールド、たとえば**PeopleSoftTwoWayFileRP**、 をクリック**OK**です。  
  
#### <a name="create-a-file-receive-location"></a>ファイル受信場所を作成する  
  
1.  ファイル受信場所で監視されるフォルダー (C:\Files\In など) を作成します。  
  
2.  右クリックし、新しい受信ポートをクリックし、**新規**、**受信場所の**を表示する、**受信場所のプロパティ**ダイアログ。  
  
3.  値を入力して、**名前**フィールド、たとえば**PeopleSoftTwoWayFileRL**です。  
  
4.  選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン リスト ボックスし、をクリックして、**構成**アダプターを表示するにはボタン**トランスポートプロパティ** ダイアログ ボックス。  
  
5.  用に作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリック**OK**です。  
  
6.  選択 **[xmlreceive]** で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン リスト ボックスし、をクリックして**OK**です。  
  
7.  受信場所を右クリックし、をクリックして**を有効にする**です。  
  
#### <a name="modify-the-adapter-schema-target-namespace-property"></a>アダプター スキーマのターゲットの名前空間プロパティを変更する  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を起動し、TwoWaySend.sln を開きます。 をクリックして**ファイル**、**開く**、**プロジェクト/ソリューション**を表示する、**プロジェクトを開く**ダイアログ。  
  
2.  TwoWaySend.sln ファイルを [参照] をクリックし、このファイルを選択し、をクリックして**開く**サンプル プロジェクトを含むソリューションを開きます。  
  
3.  をクリックして、**ビュー**メニュー**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーを表示します。  
  
4.  ソリューション エクスプローラーで、LOCATIONService_1.xsd ファイルをダブルクリックして開きます。  
  
5.  右クリックし、**スキーマ**LOCATIONService_1.xsd と選択のノード、**プロパティ**スキーマのプロパティを表示するメニュー オプション。  
  
6.  編集、 **Target Namespace**アダプター名はたとえば、適切な値を使用するプロパティ、 **Target Namespace**プロパティを次のように読み取る必要があります。  
  
    ```  
    http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
    ```  
  
     ここで*PeopleSoft*はで表示される PeopleSoft アダプターの名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
    > [!IMPORTANT]
    >  場合設定値を**Target Namespace**によって入力ドキュメント インスタンスが処理されるときに、ルーティングの障害が発生し、入力ドキュメント インスタンスで指定された名前空間と一致しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>アダプター スキーマからドキュメント インスタンスを生成する  
  
1.  ダブルクリックして**LOCATIONService_1.xsd**ソリューション エクスプ ローラーでスキーマ エディターでファイルを開く。  
  
2.  右クリックし、 **\<スキーマ\>** スキーマ エディターでをクリックしてノード**プロパティ**ノードのプロパティを表示します。  
  
3.  選択**取得**で利用可能なノードの一覧から、**ルート参照**ボックスの一覧です。 これから生成されるサンプルのドキュメント インスタンスを生成するときにそのように実行する、**取得**スキーマのノードです。  
  
4.  右クリック**LOCATIONService_1.xsd**ソリューション エクスプ ローラーでクリック**プロパティ**プロパティ ウィンドウでプロパティを表示します。  
  
5.  [プロパティ] ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプション。  
  
6.  表示するには、省略記号ボタン (...) をクリックして、 **出力ファイルの**ダイアログ。  
  
7.  たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**です。  
  
    > [!NOTE]
    >  ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。  
  
8.  ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**インスタンスの生成**を指定した場所にドキュメント インスタンスを生成します。  
  
9. 右クリックし、 **\<スキーマ\>** スキーマ エディターでをクリックしてノード**プロパティ**ノードのプロパティを表示します。  
  
10. 選択 (**既定)** で利用可能なノードの一覧から、**ルート参照**ボックスの一覧です。  
  
#### <a name="modify-the-generated-document-instance"></a>生成されたドキュメント インスタンスを変更する  
  
1.  生成されたドキュメント インスタンスをメモ帳などのテキスト エディターで開き、ドキュメント インスタンスの内容を編集して、これらのフィールドのデータによって既存のレコードが返されるようにします。  
  
    ```  
    <ns0:Get xmlns:ns0="http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]">  
    <ns0:SETID>SHARE</ns0:SETID>  
    <ns0:LOCATION>WFKLOC</ns0:LOCATION>  
    <ns0:getHistory>true</ns0:getHistory>  
    </ns0:Get>  
    ```  
  
    > [!NOTE]
    >  上記の例で*PeopleSoft*アダプターの実際の名前を表すプレース ホルダーは、BizTalk 管理コンソールで表示します。 *共有*と*WFKLOC* PeopleSoft システムの特定のレコードの識別に使用される値のプレース ホルダーです。  
  
2.  変更したドキュメント インスタンスを保存します。  
  
#### <a name="build-and-deploy-the-project"></a>プロジェクトのビルドと展開  
  
1.  ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを表示します。  
  
2.  クリックして、**展開**プロジェクト デザイナーのタブです。  
  
3.  適切な値を入力、**サーバー**プロパティおよび**構成データベース**プロパティの  **BizTalk グループ**です。  
  
4.  ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**展開**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  
  
#### <a name="bind-and-enlist-the-orchestration"></a>オーケストレーションをバインドして参加させる  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**を展開して**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**です。  
  
2.  クリックして、**更新**ボタンをクリックして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール ツールバーまたはキーを押して、 **f5 キーを押して**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。  
  
3.  表示するオーケストレーションをダブルクリック、**オーケストレーションのプロパティ**ダイアログ。  
  
4.  をクリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左ペインでします。  
  
5.  バインド オプションに適切な値を指定します。次に例を示します。  
  
    |**パラメーター**|**値**|  
    |-------------------|---------------|  
    |Host|BizTalkServerApplication|  
    |FileReceivePort|PeopleSoftTwoWayFileRP|  
    |PeopleSoftTwoWaySend678|PeopleSoftTwoWaySP|  
    |ResponsePort|PeopleSoftTwoWayFileSP|  
  
6.  [OK] をクリックします。  
  
#### <a name="start-the-orchestration"></a>オーケストレーションを開始します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、をクリックして**開始**を参加させて、オーケストレーションを開始します。  
  
#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする  
  
-   先ほど作成したドキュメント インスタンスを、ファイル受信場所の監視対象として構成されているフォルダーにコピーします。  
  
#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a>ドキュメント インスタンスが BizTalk Adapter for PeopleSoft Enterprise によって処理されたことを確認する  
  
-   ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。 このファイルには、BizTalk Adapter for PeopleSoft Enterprise によって処理されたクエリの結果が含まれている必要があります。  
  
 ドキュメント インスタンスが正常に処理された場合、次の一連のイベントが発生します。  
  
1.  ファイル アダプターがフォルダーからファイルを取得し、メッセージボックスに BizTalk メッセージとして公開します。  
  
2.  オーケストレーションがこの公開されたメッセージをサブスクライブします。これにより、BizTalk メッセージング エンジンがオーケストレーションのインスタンスをアクティブ化し、オーケストレーション インスタンスにメッセージを送信できるようにします。  
  
3.  オーケストレーション インスタンスがメッセージ ボックスにメッセージを返します。  
  
4.  送信請求 - 応答の送信ポートがこの公開されたメッセージをサブスクライブし、BizTalk メッセージング エンジンがメッセージを PeopleSoft 送信ポートに送信します。  
  
5.  送信ポートがメッセージを BizTalk Adapter for PeopleSoft Enterprise に渡します。  
  
6.  入力ファイルで定義されたパラメーターを使用して、BizTalk Adapter for PeopleSoft Enterprise が PeopleSoft システムに対して Get ステートメントを実行します。  
  
7.  BizTalk Adapter for PeopleSoft Enterprise が、オーケストレーションの送信請求 - 応答ポートへの応答メッセージとして Get ステートメントの結果を返します。  
  
8.  オーケストレーションがメッセージ ボックスに結果セットを公開します。  
  
9. ファイル送信ポートがこのメッセージをサブスクライブし、BizTalk がメッセージをファイル アダプターに送信します。  
  
10. ファイル アダプターが、結果セットを含むメッセージを指定の出力フォルダーに書き込みます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk Adapter for PeopleSoft Enterprise の使用](../core/tutorials-using-biztalk-adapter-for-peoplesoft-enterprise.md)