---
title: "JD Edwards OneWorld サンプル クエリを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35d05dfe719a9b199d7422f99ef80e888126f01f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="executing-a-jd-edwards-oneworld-sample-query"></a>JD Edwards OneWorld サンプル クエリの実行
JD Edwards OneWorld (JDEOW) システムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムからアクセスするには、JD Edwards OneWorld アダプターを使用します。 このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。  
  
 これは、JD Edwards OneWorld ラボ作業の 2 つめのパートです。 最初のパート (ラボ 1) では、JD Edwards OneWorld システムのデータに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの Microsoft テクノロジーを使用せずに手動でアクセスしました。 このパート (ラボ 2) では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。 JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、このオーケストレーションのポートを構成します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   Microsoft [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   JD Edwards OneWorld クライアント ソフトウェア  
  
-   別のサーバー上にある JD Edwards OneWorld システムへのネットワーク接続  
  
-   Microsoft BizTalk Adapters for Enterprise Applications  
  
> [!NOTE]
>  インストールと構成については Microsoft BizTalk Adapters for Enterprise Applications を参照してください。[ハイパーリンク"http://go.microsoft.com/fwlink/?LinkId=196039"\t"_blank"http://go.microsoft.com/fwlink/?LinkId=196039](http://go.microsoft.com/fwlink/?LinkId=196039)です。 このドキュメントには、JD Edwards、PeopleSoft、JD Edwards OneWorld、TIBCO、および Siebel の各 LOB アダプターのキー構成情報が記載されています。  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a>ラボ 2 - JD Edwards OneWorld サンプル クエリの実行  
 このラボでは、実行、**取得**JD Edwards OneWorld システムに対して操作を実行します。 具体的には、次のタスクを実行します。  
  
-   JD Edwards OneWorld の前提条件を確認します。  
  
-   JD Edwards OneWorld 送信ポートを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でセットアップ  
  
-   BizTalk オーケストレーション プロジェクトの作成  
  
-   プロジェクトのビルドと展開  
  
-   アプリケーションのテストと XML 出力の表示  
  
 JD Edwards OneWorld アダプターを使用して、JD Edwards OneWorld システム上のデータに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアクセスします。  
  
 このアダプターを使用すると、オーケストレーションによって実行される要求と応答を使用して JD Edwards OneWorld のオブジェクトの処理を行うことができます。 1 つのスキーマ オブジェクトに対して使用可能なメソッドは多数あります。 このラボを使用する方法を示しています、 **Address Book MBF**メソッドです。  
  
 サービス要求を実行する前に、対象の JD Edwards OneWorld オブジェクトに対するサービス要求と応答のスキーマを作成する必要があります。 これらのスキーマは、生成した項目の追加/アダプターの追加ウィザードによって、JD Edwards OneWorld 内のサポート メタデータ オブジェクトに直接問い合わせることによって作成されます。 このラボ用スキーマの作成に必要な手順を示しています、 **Address Book MBF**メソッドとクエリを処理します。  
  
## <a name="procedures-for-lab-2--executing-a-jd-edwards-oneworld-sample-query"></a>ラボ 2 の手順 - JD Edwards OneWorld サンプル クエリの実行  
  
### <a name="verifying-the-jd-edwards-oneworld-prerequisites"></a>JD Edwards OneWorld の前提条件の確認  
 JD Edwards OneWorld アダプターと共に使用する BizTalk プロジェクトの作成を開始する前に、JD Edwards OneWorld システムにアクセスできるように適切にファイルとアダプターがセットアップされていることを確認する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上の JD Edwards OneWorld アダプターと JD Edwards OneWorld システムとの通信には、Java インターフェイスが使用されます。  
  
 JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに適切にアクセスするには、Connector.jar、Kernel.jar、BTSLIBinterop.jar、JDEJAccess.jar の 4 つのファイルが必要です。  
  
-   Connector.jar と Kernel.jar は、JD Edwards OneWorld システムに付属しています。JD Edwards OneWorld 管理者から入手してください。 これらのファイルの場所は、C:\JDEOWJars フォルダーです。  
  
-   BTSLIBinterop.jar ファイルは、アダプターのインストール ガイドに記載されている手順に従って JD Edwards OneWorld システムによって生成されます。 このファイルの場所は、C:\JDEOWJars フォルダーです。  
  
-   JDEJAccess.jar ファイルは JDEOW アダプターの一部であり、アダプターのインストール時に作成されます。 既定にある、C:\Program files \microsoft BizTalk Adapters Enterprise applications \j.d. 用です。 Edwards OneWorld® \Classes フォルダーです。  
  
##### <a name="to-verify-the-jd-edwards-oneworld-prerequisites"></a>JD Edwards OneWorld の前提条件を確認するには  
  
1.  Connector.jar、Kernel.jar、BTSLIBinterop.jar の各ファイルが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上の C:\JDEOWJars フォルダーにあることを確認します。  
  
2.  JDEJAccess.jar ファイルが上に存在することを確認、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\Program files \microsoft BizTalk Adapters for Enterprise applications \j.d. 内のコンピューター。 Edwards OneWorld® \Classes フォルダーです。  
  
3.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
### <a name="configuring-biztalk-send-ports"></a>BizTalk 送信ポートの構成  
 ここでは、JD Edwards OneWorld アダプターがインストールされていることを確認して、JD Edwards OneWorld 送信ポートを作成します。  
  
##### <a name="to-verify-that-the-jd-edwards-oneworld-adapter-is-installed-in-includepragueincludesprague-mdmd"></a>JD Edwards OneWorld アダプターが [!INCLUDE[prague](../includes/prague-md.md)] にインストールされていることを確認するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**の順に展開および**アダプター**です。  
  
     いることを確認、 **JDE_OneWorld**アダプターがインストールされ、一覧にします。 JD Edwards OneWorld アダプターがインストールされていない場合は、BizTalk Adapters for Enterprise Applications をインストールしてください (前の「前提条件」の項を参照してください)。 アダプターをインストールしたらを右クリックし**アダプター**  をクリックし、 **New - Adapter** JD Edwards OneWorld アダプターをインストールします。 このインストールを完了するには、ホスト インスタンスを再起動する必要があります。  
  
##### <a name="to-create-the-jd-edwards-oneworld-send-port"></a>JD Edwards OneWorld 送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。  
  
2.  右クリック**送信ポート**をクリックして**新規**、順にクリック**静的な送信請求-応答送信ポート**です。これらのフィールドに、次の値を入力します。  
  
    1.  **[名前]:**  `JDE_OneWorldPort`  
  
    2.  **型:**  `JDE_OneWorld`  
  
    3.  **送信ハンドラー。**  `BizTalkServerApplication`  
  
    4.  **送信パイプライン。**  `XMLTransmit`  
  
    5.  **受信パイプライン。**  `XMLReceive`  
  
3.  **[構成]**をクリックし、次のプロパティ値を入力します。  
  
    1.  **ホスト:** \<JDEOW ホスト名を入力 >  
  
    2.  **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
    3.  **JDEdwards 環境:** \<JDEOW 環境を入力 >  
  
    4.  **JDEdwards JAR ファイル:** \<JAR ファイルの完全なパスを入力 >  
  
         `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
    5.  **パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。  
  
    6.  **ポート:**  `6009`  
  
    7.  **ユーザー名:** \<JD Edwards のユーザー名を入力 >  
  
     ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
4.  をクリックして**OK**を閉じるには、2 回、**送信ポートのプロパティ** ダイアログ ボックス。  
  
### <a name="creating-a-biztalk-orchestration-project"></a>BizTalk オーケストレーション プロジェクトの作成  
 ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で BizTalk プロジェクトを作成します。また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と JD Edwards OneWorld システムとの通信を処理するためのオーケストレーションをこのプロジェクト内に構成します。 送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。  
  
##### <a name="to-create-the-biztalk-orchestration-project-in-visual-studio"></a>Visual Studio で BizTalk オーケストレーション プロジェクトを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を開き、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。 **[ファイル]** メニューの **[新規作成]**をクリックします。 **[新しいプロジェクト]** ダイアログ ボックスが表示されます。 **[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]** 入力`JDE_OW_Test`クリックして一意のプロジェクト名として**OK**です。  
  
2.  ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]**をクリックし、 **[生成した項目の追加]**をクリックします。 [カテゴリ] ウィンドウで、次のように選択します。**アダプター メタデータの追加**、[テンプレート] ペインで選択**アダプター メタデータの追加**、順にクリック**追加**です。  
  
3.  アダプターの追加ウィザードで選択、 **JD Edwards OneWorld**アダプター、select、 **[jde_oneworldport]** 、前の手順で作成したポートを送信し、をクリックして**次**.  
  
     ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4.  **[インポートするサービス**] ページで、開いている**JD Edwards OneWorld**です。 JDEOW システムへのアダプター経由でのアクセスには、BrowsingAgent プログラムが使用されます。 この BrowsingAgent からは、次に示すサービスが返されます。  
  
     ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5.  展開**CALLBSFN**まで下にスクロール**N0100041 - Address Book MBF**です。 N0100041 を選択し、クリックして**完了**です。  
  
6.  ソリューション エクスプローラーに、新しい BizTalk オーケストレーションと、2 つの新しい関連スキーマ ファイルが表示されます。 これらのファイルはアダプターの追加ウィザードによって作成されます。 **BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。  
  
     ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
 このオーケストレーションは、JD Edwards OneWorld システムに合わせてフォーマットされた XML ファイルをファイル アダプターから受け取ります。 この XML ファイルは、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに送信されます。 JD Edwards OneWorld は、クエリを処理して、結果が格納された出力 XML ファイルを生成します。 この XML ファイルは、JD Edwards OneWorld アダプターを介してオーケストレーションに返され、ファイル アダプターによってディスク上の出力場所に書き込まれます。  
  
 オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。 初めに、受信ポートを構成します。これは、ファイル アダプターがディスクから読み取った XML ファイルをオーケストレーションに渡すのに使用されます。  
  
##### <a name="to-configure-a-receive-port-to-accept-the-input-xml-file"></a>入力 XML ファイルを受け取るための受信ポートを構成するには  
  
1.  **BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。  
  
2.  BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。  
  
3.  **ポートのプロパティ** ページで、入力`JDE_File_In`の**名前**、クリックして**次へ**です。  
  
4.  **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。  
  
     **ポートの種類名**:`JDE_FileIn_Port`  
  
     **[通信方式]**: **一方向**  
  
     **[アクセスの制限]**: **[内部 - このプロジェクト限定]**  
  
5.  **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
     **[ポートの通信方向]**: **常にこのポートでメッセージを受信する**  
  
     **[ポートのバインド]**: **[後で指定する]**  
  
6.  **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
 次に、送信/受信ポートを作成します。これは、クエリが格納された最初の XML 入力ファイルを JD Edwards OneWorld システムに送信するためのものです。 このポートは、クエリの結果が格納された出力 XML ファイルを JD Edwards OneWorld システムから受信するのにも使用されます。  
  
##### <a name="to-configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a>JD Edwards OneWorld とのインターフェイスとなる送信/受信ポートを構成するには  
  
1.  BizTalk Orchestration.odx ファイルで右ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。  
  
2.  **[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]**をクリックします。 **使用可能なポートの種類** **JD_OW_Test.N0100041**、順にクリック**次へ**です。  
  
     ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3.  プロパティ値を次のとおりに選択します。  
  
     **ポートの通信方向**:**要求の送信と応答の受信を行います**  
  
     **[ポートのバインド]**: **[後で指定する]**  
  
4.  **[次へ]**をクリックし、 **[完了]**をクリックします。 ポート画面に、ポートと使用可能なメソッドが表示されます。  
  
 最後に、送信ポートを構成します。これは、クエリの結果を格納した XML ファイルをファイル アダプターがディスクに出力するときに使用されます。  
  
##### <a name="to-configure-a-send-port-to-output-the-xml-file-to-disk"></a>XML ファイルをディスクに出力するための送信ポートを構成するには  
  
1.  BizTalk Orchestration.odx ファイルで、左ポート画面を右クリックし、をクリックして**新しい構成済みポート**です。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。  
  
2.  **ポートのプロパティ** ページで、入力`JDE_FileOut`の**名前**、クリックして**次へ**です。  
  
3.  **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]**を選択し、次のプロパティ値を入力または選択します。  
  
     **ポートの種類名**:`JDE_FileOut_Port`  
  
     **[通信方式]**: **一方向**  
  
     **[アクセスの制限]**: **[内部 - このプロジェクト限定]**  
  
4.  **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
     **[ポートの通信方向]**: **[常にこのポートでメッセージを送信する]**  
  
     **[ポートのバインド]**: **[後で指定する]**  
  
5.  **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
 ポート画面に、JD Edwards OneWorld のサービスのための新しいポートと使用できるメソッドが表示されます。 JD Edwards OneWorld システムとの間でファイルを送受信するように JD Edwards OneWorld アダプターを設定する作業は、後で行います。  
  
 **JDE_File_In**と**JDE_File_Out**必要性を作成したポートには、メッセージの種類が関連付けられています。  
  
##### <a name="to-assign-message-types-to-the-ports"></a>メッセージの種類をポートに割り当てるには  
  
1.  左のポート画面上で、 **JDE_File_In**ポートでは、をクリックして**要求**です。 プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbf**です。  
  
2.  左のポート画面上で、 **JDE_File_Out**ポートでは、をクリックして**要求**です。 プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリック**jde_ow_testaddressbookmastermbfresponse**です。  
  
 2 つの挿入**送信**図形と 2 つ**受信**図形をオーケストレーションにポートにリンクします。  
  
##### <a name="to-add-send-and-receive-shapes"></a>送信図形と受信図形を追加するには  
  
1.  ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。 をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`Get_File`の、**名前**、設定と**Activate**に`true`です。 このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。  
  
2.  ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **GetFileReceive**図形です。 クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`SendToJDEOW`の、**名**です。  
  
3.  ドラッグ、**受信**コンポーネントをツールボックスからすぐ下にドロップし、 **SendToJDEOWSend**図形です。 クリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`JDEOW_Resp`の、**名前**です。  
  
4.  ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **JDEOW_RespReceive**図形です。 クリックして、新しい**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`FileToDisk`の、**名**です。  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  接続、 **JDE_FileIn**ポートを**GetFileReceive**コンポーネントです。  
  
6.  接続、 **JDE_FileOut**ポートを**FileToDiskReceive**コンポーネントです。  
  
7.  移動して**オーケストレーション ビュー**展開**メッセージ**です。 識別子を変更**Message_1**に`MsgToJDEOW`、および**Message_2**に`JDEOW_Resp.`  
  
8.  強調表示、 **SendToJDEOWSend**コンポーネントで、設定、**メッセージ**プロパティを**MsgToJDEOW**です。  
  
9. 強調表示、 **JDEOW_RespReceive**コンポーネントで、設定、**メッセージ**プロパティを**JDEOW_Resp**です。  
  
10. 接続**SendToJDEOW**を**要求**の部分、 **JDE_OW_Port**ポートです。  
  
11. 接続**JDEOW_Resp**を**応答**の部分、 **JDE_OW_Port**ポートです。  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
### <a name="building-and-deploying-the-project"></a>プロジェクトのビルドと展開  
 BizTalk プロジェクトが完成したので、ビルドし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。  
  
##### <a name="to-build-and-deploy-the-project"></a>プロジェクトをビルドして展開するには  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  プロジェクトをビルドするには、厳密な名前のキー ファイルが必要です。 コマンド プロンプトで、次のとおりに入力して厳密な名前のキー ファイルを作成します。  
  
     **sn-k labs.snk**  
  
3.  ソリューション エクスプ ローラーで右クリックし、 **[jd_ow_test]**プロジェクトをクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。  
  
4.  **[署名]** タブをクリックします。  
  
5.  **[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]**をクリックします。  
  
6.  キー ファイル **labs.snk**を一覧から選択して **[開く]**をクリックします。  
  
7.  プロジェクト デザイナーの **[展開]** タブをクリックします。  
  
8.  設定、**アプリケーション名**に`JDE_OW_Test`です。  
  
9. ソリューション エクスプ ローラーで右クリックし、 **JDE_OW_Test**プロジェクトをクリックして**を構築します。**  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. ビルドが完了したらを右クリックし、 **[XX_JD Edwards oneworldquery]**プロジェクトをクリックして**展開**です。 出力ウィンドウに、次のように出力が表示されます。  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
### <a name="testing-the-application-and-viewing-the-xml-output"></a>アプリケーションのテストと XML 出力の表示  
 次に、作成して展開したアプリケーションをテストします。 初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。 アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。  
  
##### <a name="to-generate-the-xml-file-for-the-query"></a>クエリの XML ファイルを生成するには  
  
1.  ソリューション エクスプ ローラーで、 **N0100041Service_N0100041.xsd**ファイルを開きます。  
  
2.  右クリック**N0100041Service_N0100041.xsd**  をクリックし、**プロパティ**です。 **[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  クリックして **OK.** [プロパティ] ウィンドウで選択**\<スキーマ >**設定と**ルート参照:**に`AddressBookMasterMBF`です。 これにより、生成された XML のみを含む、**クエリ**xml です。  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  右クリック**N0100041Service_N0100041.xsd**  をクリックし、**インスタンスの生成**です。 これにより生成、 **Sample.xml**ファイル。 このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。  
  
##### <a name="to-configure-and-start-the-biztalk-application"></a>BizTalk アプリケーションを構成して開始するには  
  
1.  入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。 移動して**C:\LABS\JDE_OW_Test**という 2 つの新しいサブフォルダーを作成および`FileIn`と`FileOut`です。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**を展開および**アプリケーション**です。  
  
3.  右クリック**JDE_OW_Test**、クリックして**構成**です。  
  
     ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4.  **[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。 [ **BizTalkServerApplication**] を選択します。  
  
5.  **受信ポート**をクリックして**\<なし >**です。 ドロップダウン リストの **[新しい受信ポート]**を選択します。  
  
6.  **名前**、型`JDE_FileIn_Port`、順にクリック**OK**です。 受信場所を指定する必要があるというメッセージ ボックスが表示されます。 **[OK]**をクリックし、 **[新規作成]**をクリックします。  
  
     ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7.  プロパティに次の値を入力または選択します。  
  
     **名前**: JDE_`FileInLoc`  
  
     **種類**: **ファイル**  
  
     **受信ハンドラー**: **BizTalkServerApplication**  
  
     **受信パイプライン**: **XMLReceive**  
  
     ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8.  をクリックして**構成**、型`C:\LABS\JDE_OW_Test\FileIn`の**受信フォルダー**、クリックして**[ok]** 3 回です。  
  
     ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. をクリックして**\<なし >**の**JDE_OW_Port**ドロップダウン リストでします。  
  
10. 選択**新しい送信ポートを**を選択するか、プロパティに次の値を入力します。  
  
     **名前**:`JDE_OW_Port`  
  
     **型**: **JDE_OneWorld**  
  
     **[送信ハンドラー]**: **BizTalkServerApplication**  
  
     **[パイプライン]**: **XMLTransmit** および **XMLReceive**  
  
11. **[構成]**をクリックし、次のプロパティ値を入力します。  
  
     **ホスト:** \<JDEOW ホスト名を入力 >  
  
     **JAVA_HOME:**`C:\j2sdk1.4.2_08`  
  
     **JDEdwards 環境:** \<JDEOW 環境を入力 >  
  
     **JDEdwards JAR ファイル:**<enter full path of JAR files>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     **パスワード:**ドロップダウン リストを使用して、JD Edwards OneWorld パスワードを入力します。  
  
     **ポート:**  `6009`  
  
     **ユーザー名:**<enter your JD Edwards User Name>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. **[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。  
  
13. 構成 Applicationwindow、クリックして**\<なし >**の**JDE_FileOut**ドロップダウン リストでします。  
  
14. **[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。  
  
     **名前**:`FileOutPort`  
  
     **種類**: **ファイル**  
  
     **[送信ハンドラー]**: **BizTalkServerApplication**  
  
     **送信パイプライン**: **XMLTransmit**  
  
15. をクリックして**構成**および種類`C:\Labs\JDE_OW_Test\FileOut`の**先のフォルダーです。** 」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. **[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。  
  
17. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **JDE_OW_Test**アプリケーション、およびクリック**開始**です。  
  
##### <a name="to-test-the-orchestration"></a>オーケストレーションをテストするには  
  
1.  **C:\Labs\JDE_OW_Test**ディレクトリ、 **Sample.xml**ファイルとして表示されます。  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  編集、 **Sample.xml**を除くすべての項目を削除するファイル、 **cActionCode**と**mnAddressBookNumber**要素。  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  **CActionCode**要素は、文字を挿入`i`です。  
  
4.  **MnAddressBookNumber**数を挿入する`500`です。  
  
5.  変更を保存し、ファイルのコピー、 **C:\Labs\JDE_OW_Test\FileIn**フォルダーです。 これが受信場所であり、ここからオーケストレーション プロセスが開始します。  
  
6.  表示する必要があります XML ファイル、数秒で、 **C:\Labs\JDE_OW_Test\FileOut**フォルダーです。 このファイルには、アドレスが 500 であるすべてのレコードが格納されています。  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     この返されたレコード データは、ラボ 1 で JD Edwards OneWorld システムに対してクエリによって返されるデータと一致する必要があります。 ラボ 1 で取得したレコードを比較すると、できることを確認する、**取得**メソッドが正常に動作します。  
  
## <a name="summary"></a>概要  
 このラボでは、初めに、JD Edwards OneWorld システムにアクセスするための前提条件が適切にセットアップされていることを確認しました。 次に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。 JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するように、この BizTalk オーケストレーションを構成しました。 オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。 これらのポートを JD Edwards OneWorld アダプターにバインドし、メッセージを該当するポートに割り当てました。  
  
 BizTalk プロジェクトの作成後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。 次に、新しいアプリケーションを構成して実行し、JD Edwards OneWorld システムからデータを取得しました。 アプリケーションが正しく動作したことを確認するために、出力 XML ファイルを、ラボ 1 で JD Edwards OneWorld システムから受信したファイルと比較しました。