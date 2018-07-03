---
title: 'チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用して PeopleSoft Enterprise からデータを取得する |Microsoft Docs'
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
ms.openlocfilehash: 9728e642a1ad9e03e550a652757d33038cbab79d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993427"
---
# <a name="tutorial-using-the-biztalk-adapter-for-peoplesoft-enterprise-to-retrieve-data-from-peoplesoft-enterprise"></a>チュートリアル: BizTalk Adapter for PeopleSoft Enterprise を使用した PeopleSoft Enterprise からのデータの取得
BizTalk Adapter for PeopleSoft Enterprise を使用すると、PeopleSoft システムに対してクエリを実行し、そのクエリの結果を返すことができます。 ここでは、この機能を示す SDK サンプルについて説明します。  

## <a name="prerequisites"></a>前提条件  

- Java 2 Platform をインストールする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を BizTalk Adapter for PeopleSoft Enterprise の Geis で実行されています。  

- PeopleSoft Java Object Adapter JAR ファイル、 **psjoa.jar**にアクセスできるフォルダーにコピーするか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で BizTalk Adapter for PeopleSoft Enterprise が実行されています。  

- サンプルをビルドして展開するには、BizTalk Adapter for PeopleSoft Enterprise を実行する [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされている必要があります。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、フォルダーから XML ファイルを取得し、そのファイルをオーケストレーションに送信し、BizTalk Adapter for PeopleSoft Enterprise を使用して PeopleSoft システムに対してクエリを実行します。 クエリの結果は、XML ファイルに書き込まれます。  

## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でデザインされ、BizTalk Adapter for PeopleSoft Enterprise を BizTalk オーケストレーションと組み合わせて使用する基本的な機能を紹介する目的で作成されました。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次のフォルダーにあります。  

 \Program Files\Microsoft BizTalk Adapters for Enterprise Applications\PeopleSoft Enterprise(r)\Sdk\PeopleSoftTwoWaySend  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                               **ランタイム プロジェクト ファイル名**                                |                                                                                                                                                                           **ランタイム プロジェクト ファイルの説明**                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                       TwoWaySend.btproj、<br /><br /> TwoWaySend.sln                       |                                                                                                                                                                      アプリケーションのプロジェクトおよびソリューション ファイル。                                                                                                                                                                      |
| LOCATIONService.xsd、<br /><br /> LOCATIONService_1.xsd、<br /><br /> LOCATIONService_2.xsd | アプリケーションのスキーマ ファイル。 **注:** プロジェクトのアダプター スキーマ ファイルは、使用してもともと作成された、**アダプター メタデータの追加ウィザード**します。 アダプター メタデータの追加ウィザードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] マニュアルの「アダプター メタデータを BizTalk プロジェクトに追加する方法」を参照してください。 |
|                                 PeopleSoftTwoWaySend.odx                                  |                                                                                                                                                                        アプリケーションが使用するオーケストレーション。                                                                                                                                                                         |
|                                 PeopleSoftTwoWaySend.snk                                  |                                                                                                                                                                                厳密な名前のキー ファイル。                                                                                                                                                                                |

## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  

#### <a name="create-a-new-instance-of-the-peoplesoft-enterprise-adapter"></a>PeopleSoft Enterprise アダプターの新しいインスタンスを作成する  

1. 起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 クリックして**開始**、**プログラム**、 **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、 **BizTalk Server 管理**します。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順にクリックします**アダプター**します。  

3. 右クリック**アダプター**  をポイント**新規**、**アダプター**を表示する、**アダプター プロパティ**ダイアログ。  

4. 値を入力、**名前**フィールドに、たとえば**PeopleSoft**します。  

5. 選択**PeopleSoft enterprise (r)** で利用可能なアダプターの一覧から、**アダプター**ドロップダウンをクリック **[ok]**。  

#### <a name="create-a-solicit-response-biztalk-send-port"></a>送信請求 - 応答の BizTalk 送信ポートを作成する  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。  

2. 右クリックして**送信ポート** をポイント**新規**、**静的な送信請求-応答送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  

3. 値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWaySP**します。  

4. 使用可能なアダプターの一覧から PeopleSoft アダプターを選択、**型**ドロップダウン ボックスし、をクリックして、**構成**アダプターを表示するボタン**トランスポートのプロパティ** ダイアログ ボックス。  

   > [!NOTE]
   >  この値は、管理コンソールで PeopleSoft Enterprise アダプターを作成したときに指定した名前です。  

5. 次の値を入力、**アダプターに必要なプロパティ**:  


   |       **プロパティ**       |                                                                                                                                        **[値]**                                                                                                                                         |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | アプリケーション サーバーのパス  | PeopleSoft Server のコンピューターおよびポートの場所 (例: //PSServer:8888)。 **注:** する上記の例ででした入力ように//psserver 値、PeopleSoft サーバーは、既定のポート値 9000 を使用している場合、既定のポート 9000 が使用されるポート番号を指定しない場合。 |
   |        JAVA_HOME         |                                                                                          Java 2 Platform SDK ファイルに関連付けられているホーム ディレクトリへのパス (例: C:\j2sdk1.4.2_08)。                                                                                          |
   |         パスワード         |                                                                                                                 PeopleSoft システムへの接続時に使用するパスワード。                                                                                                                  |
   | PeopleSoft 8.x JAR ファイル |                                                                                          PeopleSoft Java Object Adapter JAR ファイルの場所**psjoa.jar**、C:\JARS\psjoa.jar など。                                                                                          |
   |        [ユーザー名]         |                                                                                                                    PeopleSoft システムへの接続時に使用するユーザー名。                                                                                                                     |


6. **[OK]** をクリックします。  

7. 選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウンします。  

8. 選択、 **XMLReceive**で利用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン をクリック**ok**します。  

9. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  

#### <a name="create-a-one-way-biztalk-send-port"></a>一方向 BizTalk 送信ポートを作成する  

1. 送信ポートで使用されるターゲット フォルダーを作成します (例: C:\Files\Out)。  

2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**送信ポート**します。  

3. 右クリックして**送信ポート** をポイント**新規**、**静的な一方向送信ポート**を表示する、**送信ポートのプロパティ**ダイアログ。  

4. 値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWayFileSP**します。  

5. 選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。  

6. 先ほど作成したフォルダーの場所を入力、**先フォルダー**プロパティをクリックします**OK**。  

7. 選択、 **XMLTransmit**で利用可能なパイプラインの一覧から、**送信パイプライン**ドロップダウン をクリック**ok**します。  

8. 送信ポートを右クリックし、をクリックして**開始**を参加させて、送信ポートを開始します。  

#### <a name="create-a-file-receive-port"></a>ファイル受信ポートを作成する  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**受信ポート**します。  

2. 受信ポート フォルダーを右クリックし、をクリックし、**新規**、**一方向の受信ポート**受信ポートのプロパティ ダイアログを表示します。  

3. 値を入力、**名前**フィールドに**PeopleSoftTwoWayFileRP**、 をクリック**OK**します。  

#### <a name="create-a-file-receive-location"></a>ファイル受信場所を作成する  

1.  ファイル受信場所で監視されるフォルダー (C:\Files\In など) を作成します。  

2.  右クリックし、新しい受信ポート をクリックし、**新規**、**受信場所**を表示する、**受信場所のプロパティ**ダイアログ。  

3.  値を入力、**名前**フィールドに、たとえば**PeopleSoftTwoWayFileRL**します。  

4.  選択**ファイル**で使用可能なアダプターの一覧から、**型**ドロップダウン ボックス、をクリックし、**構成**アダプターを表示するボタン**トランスポートプロパティ** ダイアログ ボックス。  

5.  先ほど作成したフォルダーの場所を入力、**受信フォルダー**プロパティをクリックします**OK**します。  

6.  選択**XMLReceive**で使用可能なパイプラインの一覧から、**受信パイプライン**ドロップダウン ボックスし、をクリックして**OK**。  

7.  受信場所を右クリックし、をクリックして**を有効にする**します。  

#### <a name="modify-the-adapter-schema-target-namespace-property"></a>アダプター スキーマのターゲットの名前空間プロパティを変更する  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を起動し、TwoWaySend.sln を開きます。 クリックして**ファイル**、**オープン**、**プロジェクト/ソリューション**を表示する、**プロジェクトを開く**ダイアログ。  

2. TwoWaySend.sln ファイルを [参照] をクリックし、このファイルを選択し、をクリックして**開く**サンプル プロジェクトを含むソリューションを開きます。  

3. をクリックして、**ビュー**メニュー選択し、**ソリューション エクスプ ローラー**ソリューション エクスプ ローラーを表示します。  

4. ソリューション エクスプローラーで、LOCATIONService_1.xsd ファイルをダブルクリックして開きます。  

5. 右クリックし、**スキーマ**LOCATIONService_1.xsd のノード、**プロパティ**スキーマのプロパティを表示するメニュー オプション。  

6. 編集、 **Target Namespace**など、アダプター名の適切な値を使用するプロパティ、 **Target Namespace**プロパティを次のように読み取る必要があります。  

   ```  
   http://schemas.microsoft.com/[PeopleSoft://CI/LOCATION]  
   ```  

    場所*PeopleSoft*はで表示される PeopleSoft アダプターの名前、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  

   > [!IMPORTANT]
   >  場合設定値を**Target Namespace**によって入力ドキュメント インスタンスが処理されると、ルーティングの障害が発生し、入力ドキュメント インスタンスで指定された名前空間と一致しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  

#### <a name="generate-a-document-instance-from-the-adapter-schema"></a>アダプター スキーマからドキュメント インスタンスを生成する  

1.  ダブルクリック**LOCATIONService_1.xsd**をスキーマ エディターでファイルを開き、ソリューション エクスプ ローラーでします。  

2.  右クリックし、 **\<スキーマ\>** スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。  

3.  選択**取得**で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。 生成されるサンプルのドキュメント インスタンスを生成するときにようにこれ行う必要があります、**取得**スキーマのノード。  

4.  右クリックして**LOCATIONService_1.xsd**ソリューション エクスプ ローラーをクリックします**プロパティ**プロパティ ウィンドウでプロパティを表示します。  

5.  [プロパティ] ウィンドウでクリックして選択、**出力インスタンス ファイル名**オプション。  

6.  表示するには、省略記号ボタン (...) をクリックして、**出力ファイルの選択**ダイアログ。  

7.  たとえば、フォルダーと出力ファイル インスタンスの名前を指定**C:\instance.xml**  をクリック**保存**します。  

    > [!NOTE]
    >  ファイル受信場所に指定したフォルダーの場所は、ここに指定しないでください。  

8.  ソリューション エクスプ ローラーで LOCATIONService_1.xsd を右クリックし、をクリックして**インスタンスの生成**指定された場所にドキュメント インスタンスを生成します。  

9. 右クリックし、 **\<スキーマ\>** スキーマ エディターでノード**プロパティ**ノードのプロパティを表示します。  

10. 選択 (**既定)** で使用可能なノードの一覧から、**ルート参照**ドロップダウン ボックス。  

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
    >  上記の例で*PeopleSoft*アダプターの実際の名前のプレース ホルダーは、BizTalk 管理コンソールに表示します。 *共有*と*WFKLOC* PeopleSoft システムの特定のレコードを識別するために使用される値のプレース ホルダーです。  

2.  変更したドキュメント インスタンスを保存します。  

#### <a name="build-and-deploy-the-project"></a>プロジェクトのビルドと展開  

1. ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを表示します。  

2. をクリックして、**展開**プロジェクト デザイナー タブ。  

3. 適切な値を入力、 **Server**プロパティと**構成データベース**のプロパティの  **BizTalk グループ**します。  

4. ソリューション エクスプ ローラーで TwoWaySend プロジェクトを右クリックし、をクリックして**デプロイ**プロジェクトをビルドしてアセンブリを展開する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成データベース。  

#### <a name="bind-and-enlist-the-orchestration"></a>オーケストレーションをバインドして参加させる  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリック**オーケストレーション**します。  

2. をクリックして、**更新**ボタン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのツールバーまたはキーを押して、 **F5**を更新するキーボードのキー、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの表示。  

3. 表示するオーケストレーションをダブルクリックして、**オーケストレーションのプロパティ**ダイアログ。  

4. クリックして**バインド**オーケストレーションのバインド オプションを表示するダイアログ ボックスの左側のウィンドウでします。  

5. バインド オプションに適切な値を指定します。次に例を示します。  


   |      **パラメーター**      |        **[値]**         |
   |-------------------------|--------------------------|
   |          ホスト           | BizTalkServerApplication |
   |     FileReceivePort     |  PeopleSoftTwoWayFileRP  |
   | PeopleSoftTwoWaySend678 |    PeopleSoftTwoWaySP    |
   |      ResponsePort       |  PeopleSoftTwoWayFileSP  |


6. [OK] をクリックします。  

#### <a name="start-the-orchestration"></a>オーケストレーションを開始します  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールでは、オーケストレーションを右クリックし、クリックして**開始**を参加させて、オーケストレーションを開始します。  

#### <a name="drop-a-document-instance-into-the-folder-monitored-by-the-file-receive-location"></a>ファイル受信場所の監視対象フォルダーにドキュメント インスタンスをドロップする  

-   先ほど作成したドキュメント インスタンスを、ファイル受信場所の監視対象として構成されているフォルダーにコピーします。  

#### <a name="verify-that-the-document-instance-was-processed-by-the-biztalk-adapter-for-peoplesoft-enterprise"></a>ドキュメント インスタンスが BizTalk Adapter for PeopleSoft Enterprise によって処理されたことを確認する  

- ファイル送信ポートの送信先として構成されているフォルダーを開いて、出力ドキュメントが生成されていることを確認します。 このファイルには、BizTalk Adapter for PeopleSoft Enterprise によって処理されたクエリの結果が含まれている必要があります。  

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