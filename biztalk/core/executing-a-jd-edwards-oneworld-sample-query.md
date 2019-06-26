---
title: JD Edwards OneWorld サンプル クエリの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b060d383-a2df-472f-90cc-e79078b0bcfd
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e017be5c36766c6be0997c5dbcf1f1aef7d2384
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346038"
---
# <a name="execute-a-jd-edwards-oneworld-sample-query"></a>JD Edwards OneWorld サンプル クエリを実行します。
JD Edwards OneWorld (JDEOW) システムがからアクセスできる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] JD Edwards OneWorld アダプターを使用してシステム。 このアダプターに含まれている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。
  
 これは、JD Edwards OneWorld ラボ作業の 2 番目の部分です。 支援を受けることがなく、JD Edwards OneWorld システム上のデータのアクセス手動で (ラボ 1) 最初の部分で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または他の Microsoft テクノロジです。 このパート (ラボ 2) では、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトの一部として、BizTalk オーケストレーションを作成します。 JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得するには、このオーケストレーションのポートを構成します。  
  
## <a name="prerequisites"></a>前提条件  
  
- Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]
  
- Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 
  
- JD Edwards OneWorld クライアント ソフトウェア  
  
- 別のサーバー上の JD Edwards OneWorld システムへのネットワーク接続  
  
- Microsoft BizTalk Adapters for Enterprise Applications  
  
> [!NOTE]
>  参照してください[をインストールし、エンタープライズ アプリケーション用のアダプターを構成](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)キーの構成については、JD Edwards、PeopleSoft、および TIBCO アダプター。  
  
## <a name="lab-2---executing-a-jd-edwards-oneworld-sample-query"></a>ラボ 2 - JD Edwards OneWorld サンプル クエリを実行します。  
 この演習では、実行、**取得**JD Edwards OneWorld システムに対して操作します。 具体的には、次のタスクを実行します。  
  
- JD Edwards OneWorld の前提条件を確認します。  
  
- JD Edwards OneWorld 送信ポートを設定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- BizTalk オーケストレーション プロジェクトの作成  
  
- プロジェクトのビルドと展開  
  
- アプリケーションのテストと XML 出力の表示  
  
  JD Edwards OneWorld システムからのデータにアクセスする、JD Edwards OneWorld アダプターを使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
  このアダプターでは、要求と応答のオーケストレーションによって実行を使用して JD Edwards OneWorld オブジェクトの処理ができます。 多くのメソッドは、スキーマ オブジェクトを使用できます。 このラボは、使用する方法を示します、 **Address Book MBF**メソッド。  
  
  サービス要求を実行する前に、JD Edwards OneWorld の特定のオブジェクトのサービスの要求および応答スキーマを作成する必要があります。 アダプターの追加生成項目/追加ウィザードは、JD Edwards oneworld のサポート メタデータ オブジェクトを直接調べることで、これらのスキーマを作成します。 このラボ用のスキーマを作成するために必要な手順を示しています、 **Address Book MBF**メソッドとクエリを処理します。  
  
## <a name="step-1-verify-the-jd-edwards-oneworld-prerequisites"></a>手順 1:JD Edwards OneWorld の前提条件を確認します。  
 JD Edwards OneWorld アダプターを使用するための BizTalk プロジェクトの作成を開始する前に、ファイルが必要にして、アダプターは、JD Edwards OneWorld システムへのアクセスに正しく設定されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター、JD Edwards OneWorld アダプター JD Edwards OneWorld システムと Java インターフェイスを使用して通信します。    

1. 4 つのファイルは、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに適切なインターフェイスへのアクセスの必要があります。Connector.jar、Kernel.jar、BTSLIBinterop.jar、および JDEJAccess.jar します。  
  
    -   Connector.jar および Kernel.jar ファイルは、JD Edwards OneWorld システムに付属し、JD Edwards OneWorld 管理者から取得されます。 これらのファイルは、C:\JDEOWJars フォルダーにあります。  
  
    -   BTSLIBinterop.jar ファイルは、アダプターのインストール ガイドに含まれる手順に従って JD Edwards OneWorld システムによって生成されます。 このファイルは、C:\JDEOWJars フォルダーにあります。  
  
    -   JDEJAccess.jar ファイルは JDEOW アダプターの一部であるし、アダプターのインストールに含まれています。 既定にある、C:\Program files \microsoft BizTalk Adapters for Enterprise applications \j.d. します。 Edwards OneWorld® \Classes フォルダーです。  
  
2. Connector.jar、Kernel.jar、ことを確認し、BTSLIBinterop.jar ファイル上に存在、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\JDEOWJars フォルダー内のコンピューター。  
  
3. JDEJAccess.jar ファイルに存在することを確認、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] C:\Program files \microsoft BizTalk Adapters for Enterprise applications \j.d. 内のコンピューター。 Edwards OneWorld\Classes フォルダーです。  
  
## <a name="step-2-configure-biztalk-send-ports"></a>手順 2:BizTalk 送信ポートを構成します。  
次に、JD Edwards OneWorld アダプターがインストールされているし、送信ポートの作成を確認します。  

1. 開いている**BizTalk Server 管理**、展開**コンソール ルート**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。  
  
   確認、 **JDE_OneWorld**アダプターが一覧表示します。 JD Edwards OneWorld アダプターがインストールされていない場合は、(前の「前提条件」セクションを参照してください)、エンタープライズ アプリケーション用 BizTalk アダプターをインストールします。 右クリックし、アダプターがインストールされると**アダプター**順にクリックします**新規作成-アダプター** JD Edwards OneWorld アダプターをインストールします。 これを有効にするためにホスト インスタンスを再起動します。  
  
2. 展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  
  
3. 右クリック**送信ポート**、 をクリックして**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。これらのフィールドには、次の値を入力します。  
  
   1.  **名:**  `JDE_OneWorldPort`  
  
   2.  **種類:**  `JDE_OneWorld`  
  
   3.  **送信ハンドラー。**  `BizTalkServerApplication`  
  
   4.  **送信パイプライン。**  `XMLTransmit`  
  
   5.  **受信パイプライン。**  `XMLReceive`  
  
4. **[構成]** をクリックし、次のプロパティ値を入力します。  
  
   1. **ホスト:** \<JDEOW ホスト名を入力します。\>  
  
   2. **JAVA_HOME:** `C:\j2sdk1.4.2_08`  
  
   3. **JDEdwards 環境:** \<JDEOW 環境を入力します。\>  
  
   4. **JDEdwards JAR ファイル:** \<JAR ファイルの完全なパスを入力します。\>  
  
       `C:\JDEOWJars\BTSLIBInterop.jar; C:\JDEOWJars\Connector.jar; C:\JDEOWJars\Kernel.jar;C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\J.D. Edwards OneWorld®\Classes\JDEJAccess.jar`  
  
   5. **パスワード:** ドロップダウン リストを使用し、JD Edwards OneWorld パスワードを入力します。  
  
   6. **ポート:**  `6009`  
  
   7. **ユーザー名:** \<JD Edwards のユーザー名を入力します。\>  
  
      ![](../core/media/jdeow-transportproperties-configurebutton.gif "JDEOW_TransportProperties_ConfigureButton")  
  
5. 選択**OK**を閉じる、**送信ポートのプロパティ**します。  
  
## <a name="step-3-create-a-biztalk-orchestration-project"></a>手順 3:BizTalk オーケストレーション プロジェクトを作成します。  
次に、BizTalk プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オーケストレーション間の通信を処理するためにプロジェクトを構成および[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と JD Edwards OneWorld システム。 送信と受信のポートを追加し、プロジェクトをビルドしてから、プロジェクトを展開します。  

  
1. 開いている[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、C:\LABS フォルダーに新しい BizTalk プロジェクトを作成します。 **[ファイル]** メニューの **[新規作成]** をクリックします。 **[新しいプロジェクト]** ダイアログ ボックスが表示されます。 **[テンプレート]** セクションで **[空の BizTalk Server プロジェクト]** 入力`JDE_OW_Test`クリックと一意のプロジェクトの名前として**OK**。  
  
2. ソリューション エクスプローラーでプロジェクト名を右クリックし、 **[追加]** をクリックし、 **[生成した項目の追加]** をクリックします。 カテゴリ ウィンドウで、次のように選択します。**アダプター メタデータの追加**、テンプレート ペインで選択**アダプター メタデータの追加**、 をクリックし、**追加**します。  
  
3. アダプターの追加ウィザードで選択、 **JD Edwards OneWorld**アダプターで、 **[jde_oneworldport]** 送信前の手順で作成したポートをクリックして**次**.  
  
    ![](../core/media/jdeow-addadapterwizardselectadapter.gif "JDEOW_AddAdapterWizardSelectAdapter")  
  
4. **[インポートするサービス**] ページで、開いている**JD Edwards OneWorld**します。 JDEOW システムには、BrowsingAgent プログラムを使用してアダプターを介して接続します。 BrowsingAgent は、次のサービスを返します。  
  
    ![](../core/media/jdeow-callbsfn.gif "JDEOW_CALLBSFN")  
  
5. 展開**CALLBSFN**まで下にスクロール**n0100041 - Address Book MBF**します。 [N0100041] を選択し、クリックして**完了**します。  
  
6. ソリューション エクスプ ローラーで、新しい BizTalk オーケストレーションに 2 つの新しい関連スキーマ ファイルがあります。 これらのファイルはアダプターの追加ウィザードによって作成されます。 **BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。  
  
    ![](../core/media/jdeow-solution-explorer-jde-ow-test-schemas.gif "JDEOW_Solution_Explorer_JDE_OW_TEST_Schemas")  
  
   このオーケストレーションは、JD Edwards OneWorld システムの書式設定された XML ファイル、ファイル アダプターからの入力として受け取ります。 オーケストレーションでは、JD Edwards OneWorld アダプターを使用して、XML ファイルを JD Edwards OneWorld システムに送信します。 JD Edwards OneWorld では、クエリを処理し、結果を含む出力 XML ファイルを生成します。 この XML ファイルは、JD Edwards OneWorld アダプターを介してオーケストレーションに返し、ファイル アダプターがディスク上の出力の場所に XML ファイルを書き込みます。  
  
   オーケストレーションを完成させるには、XML の送信と受信のためのポートを作成および構成する必要があります。 最初に、ファイル アダプターによってディスクからオーケストレーションにクエリを含む XML 入力に使用する受信ポートを構成します。  
  
#### <a name="configure-a-receive-port-to-accept-the-input-xml-file"></a>入力 XML ファイルをそのまま使用する受信ポートを構成します。  
  
1. **BizTalk Orchestration.odx** ファイルをダブルクリックし、オーケストレーションを開きます。  
  
2. BizTalk Orchestration.odx ファイルで、左側のポート画面を右クリックし、順にクリックします**新しい構成済みポート**します。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
3. **ポートのプロパティ**ページで、入力`JDE_File_In`の**名前**、順にクリックします**次**。  
  
4. **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。  
  
    **ポートの種類名**: `JDE_FileIn_Port`  
  
    **通信方式**:**One Way**  
  
    **アクセス制限**:**内部 - このプロジェクト限定**  
  
5. **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
    **ポートの通信方向**:**常にこのポートでメッセージを受信します。**  
  
    **ポートのバインド**:**後で指定します。**  
  
6. **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
   次に、JD Edwards OneWorld システムにクエリを含む最初の XML 入力ファイルを送信する送信/受信ポートを作成します。 このポートは、JD Edwards OneWorld システムへの呼び出しからのクエリ結果を含む出力 XML ファイルも受け取ります。  
  
#### <a name="configure-a-sendreceive-port-to-interface-with-jd-edwards-oneworld"></a>JD Edwards oneworld インターフェイスへの送信/受信ポートを構成します。  
  
1. BizTalk Orchestration.odx ファイルで右ポート画面を右クリックし をクリックし、**新しい構成済みポート**します。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
2. **[ポートの種類の選択]** ページで、 **[既存のポートの種類を使用する]** をクリックします。 **使用可能なポートの種類**を選択します**jd_ow_test.n0100041**、順にクリックします**次**します。  
  
    ![](../core/media/a421358c-6e90-4fe0-b243-6beb1b51955a.gif "a421358c-6e90-4fe0-b243-6beb1b51955a")  
  
3. 次のプロパティ値を選択します。  
  
    **ポートの通信方向**:**要求の送信と応答の受信を行います**  
  
    **ポートのバインド**:**後で指定します。**  
  
4. **[次へ]** をクリックし、 **[完了]** をクリックします。 ポート画面で、ポートと使用可能なメソッドが表示されます。  
  
   最後に、ファイル アダプターによってディスクにクエリ結果を含む XML 出力に使用する送信ポートを構成します。  
  
#### <a name="configure-a-send-port-to-output-the-xml-file-to-disk"></a>XML ファイルをディスクに出力する送信ポートを構成します。  
  
1. BizTalk Orchestration.odx ファイルで、左側のポート画面を右クリックし、順にクリックします**新しい構成済みポート**します。 ポート構成ウィザードが起動します。 **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
2. **ポートのプロパティ**ページで、入力`JDE_FileOut`の**名前**、順にクリックします**次**。  
  
3. **[ポートの種類の選択]** ページで、 **[新しいポートの種類の作成]** を選択し、次のプロパティ値を入力または選択します。  
  
    **ポートの種類名**: `JDE_FileOut_Port`  
  
    **通信方式**:**One Way**  
  
    **アクセス制限**:**内部 - このプロジェクト限定**  
  
4. **[次へ]** をクリックして **[ポートのバインド]** ページに移動し、次のプロパティ値を選択します。  
  
    **ポートの通信方向**:**常にメッセージを送信しますこのポートで**  
  
    **ポートのバインド**:**後で指定します。**  
  
5. **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
   新しいポートと JD Edwards OneWorld のサービスの使用可能なメソッドには、ポート画面に表示されます。 後で、JD Edwards OneWorld システムからファイルを送受信するには、JD Edwards OneWorld アダプターを指定します。  
  
   **JDE_File_In**と**JDE_File_Out**必要性を作成したポートに関連付けられたメッセージの種類。  
  
#### <a name="assign-message-types-to-the-ports"></a>メッセージの種類、ポートを割り当てる  
  
1. 左側のポート画面での**JDE_File_In**ポートは、をクリックして**要求**します。 プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリックします**JDE_OW_TestAddressBookMasterMBF**します。  
  
2. 左側のポート画面での**JDE_File_Out**ポートは、をクリックして**要求**します。 プロパティ ウィンドウで **メッセージの種類**、展開**マルチパート メッセージ**、順にクリックします**JDE_OW_TestAddressBookMasterMBFResponse**します。  
  
   2 つの挿入**送信**図形と 2 つ**受信**図形をオーケストレーションにポートにリンクします。  
  
#### <a name="add-send-and-receive-shapes"></a>追加の送信と受信図形  
  
1.  ツールボックスから **受信** コンポーネントをドラッグし、オーケストレーション (緑色の円) の先頭の真下にドロップします。 をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`Get_File`の、**名前**、設定と**アクティブ化**に`true`します。 このように設定すると、この受信ポートでドキュメントを受信したときにオーケストレーションがアクティブになります。  
  
2.  ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **GetFileReceive**図形。 [新規] をクリックして**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`SendToJDEOW`の、**名前**します。  
  
3.  ドラッグ、**受信**コンポーネントをツールボックスからすぐ下にドロップし、 **SendToJDEOWSend**図形。 をクリックして、**受信**図形、および [プロパティ] ウィンドウで次のように入力します。`JDEOW_Resp`の、**名前**します。  
  
4.  ドラッグ、**送信**コンポーネントをツールボックスからすぐ下にドロップし、 **JDEOW_RespReceive**図形。 [新規] をクリックして**送信**図形、および [プロパティ] ウィンドウで次のように入力します。`FileToDisk`の、**名前**します。  
  
     ![](../core/media/jdeow-orchestration-multipartmessages.gif "JDEOW_Orchestration_MultiPartMessages")  
  
5.  接続、 **JDE_FileIn**ポートを**GetFileReceive**コンポーネント。  
  
6.  接続、 **JDE_FileOut**ポートを**FileToDiskReceive**コンポーネント。  
  
7.  移動して**オーケストレーション**展開**メッセージ**します。 識別子を変更**Message_1**に`MsgToJDEOW`、および**Message_2**に `JDEOW_Resp.`  
  
8.  強調表示、 **SendToJDEOWSend**コンポーネントと設定、**メッセージ**プロパティを**MsgToJDEOW**します。  
  
9. 強調表示、 **JDEOW_RespReceive**コンポーネントと設定、**メッセージ**プロパティを**JDEOW_Resp**します。  
  
10. 接続**SendToJDEOW**を**要求**の部分、 **JDE_OW_Port**ポート。  
  
11. 接続**JDEOW_Resp**を**応答**の部分、 **JDE_OW_Port**ポート。  
  
     ![](../core/media/jdeow-portsurface-connectcomponentstoports.gif "JDEOW_PortSurface_ConnectComponentsToPorts")  
  
## <a name="step-4-build-and-deploy-the-project"></a>手順 4:プロジェクトのビルドと展開  
 BizTalk プロジェクトが完成したので、ビルドし、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に展開できます。  
  
1.  開始**Visual Studio コマンド プロンプト**します。  
  
2.  プロジェクトをビルドするには、厳密な名前キー ファイルが必要です。 コマンド プロンプトで、厳密な名前キー ファイルを作成するには、次を入力します。  
  
     **sn -k labs.snk**  
  
3.  ソリューション エクスプ ローラーで右クリックし、 **[jd_ow_test]** プロジェクトをクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  
  
4.  **[署名]** タブをクリックします。  
  
5.  **[アセンブリの署名]** オプションを選択し、 **[厳密な名前のキー ファイルを選択してください]** オプションのドロップダウン リストをクリックして、 **[参照]** をクリックします。  
  
6.  キー ファイル **labs.snk**を一覧から選択して **[開く]** をクリックします。  
  
7.  プロジェクト デザイナーの **[展開]** タブをクリックします。  
  
8.  設定、**アプリケーション名**に`JDE_OW_Test`します。  
  
9. ソリューション エクスプ ローラーで右クリックし、 **JDE_OW_Test**プロジェクトをクリックして**ビルドします。**  
  
     ![](../core/media/jdeow-buildcompleteoutput.gif "JDEOW_BuildCompleteOutput")  
  
10. 右クリックし、ビルドが正常に完了した後、 **[XX_JD Edwards oneworldquery]** プロジェクトをクリックして**デプロイ**します。 出力ウィンドウで、次の出力が表示されます。  
  
     ![](../core/media/jdeow-deployoutput.gif "JDEOW_DeployOutput")  
  
## <a name="step-5-test-the-application-and-viewing-the-xml-output"></a>手順 5:テスト アプリケーションと XML 出力を表示します。  
 次に、作成して展開したアプリケーションをテストします。 初めに、オーケストレーション プロセスを開始する XML ファイルを作成します。次に、アプリケーション内で XML ファイルを送受信するためのフォルダーを構成します。 アプリケーションの構成後は、アプリケーションを実行し、オーケストレーションが返す XML ファイルを表示します。  
  
#### <a name="generate-the-xml-file-for-the-query"></a>クエリの XML ファイルを生成します。  
  
1.  ソリューション エクスプ ローラーでダブルクリック**N0100041Service_N0100041.xsd**ファイルを開きます。  
  
2.  右クリックして**N0100041Service_N0100041.xsd**  をクリックし、**プロパティ**します。 **[出力インスタンス ファイル名]** に、サンプル XML のパスとファイル名を次のとおりに入力します。  
  
     `C:\LABS\JDE_OW_TEST\SAMPLE.XML`  
  
3.  **[OK]** をクリックします。 [プロパティ] ウィンドウで次のように選択します。 **\<スキーマ\>** 設定と**ルート参照:** に`AddressBookMasterMBF`します。 これにより、生成された XML のみを含む、**クエリ**xml。  
  
     ![](../core/media/jdeow-jde-ow-test-msvisualstudio-schemas.gif "JDEOW_JDE_OW_Test_MSVISUALSTUDIO_SCHEMAS")  
  
4.  右クリックして**N0100041Service_N0100041.xsd**  をクリックし、**インスタンスの生成**します。 これを生成、 **Sample.xml**ファイル。 このファイルは、オーケストレーション プロセスを開始するアダプターに対する入力として、受信場所にドロップされます。  
  
#### <a name="configure-and-start-the-biztalk-application"></a>構成し、BizTalk アプリケーションを起動  
  
1. 入力ファイルの受信と送出ファイルの送信のフォルダーを構成します。 移動して**C:\LABS\JDE_OW_Test**という 2 つの新しいサブフォルダーを作成および`FileIn`と`FileOut`します。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**コンソール ルート**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. 右クリック**JDE_OW_Test**、 をクリックし、**構成**します。  
  
    ![](../core/media/jdeow-configureapplicationjde-ow-test.gif "JDEOW_ConfigureApplicationJDE_OW_Test")  
  
4. **[Orchestration_1]** を選択し、 **[ホスト]** ドロップダウン ボックスをクリックします。 **[BizTalkServerApplication]** を選択します。  
  
5. [**受信ポート**、] をクリックして **\<None\>** します。 ドロップダウン リストの **[新しい受信ポート]** を選択します。  
  
6. **名前**、型`JDE_FileIn_Port`、順にクリックします**OK**します。 受信場所を指定する必要があるというメッセージ ボックスが表示されます。 **[OK]** をクリックし、 **[新規作成]** をクリックします。  
  
    ![](../core/media/jdeow-filein-port-receiveportproperties.gif "JDEOW_FileIn_Port_ReceivePortProperties")  
  
7. プロパティに次の値を入力または選択します。  
  
    **[名前]** :JDE_`FileInLoc`  
  
    **[種類]** : **[最近使ったファイル]**  
  
    **受信ハンドラー**: **[Biztalkserverapplication]**  
  
    **受信パイプライン**: **[Xmlreceive]**  
  
    ![](../core/media/jdeow-filein-loc-receivelocationproperties.gif "JDEOW_FileIn_Loc_ReceiveLocationProperties")  
  
8. をクリックして**構成**、型`C:\LABS\JDE_OW_Test\FileIn`の**受信フォルダー**、順にクリックします**OK** 3 回です。  
  
    ![](../core/media/jdeow-file-transport-properties-filein.gif "JDEOW_File_Transport_Properties_FileIn")  
  
9. クリックして **\<None\>** の**JDE_OW_Port**ドロップダウン リストでします。  
  
10. 選択**新しい送信ポートを**選択するか、次のプロパティの値を入力します。  
  
     **名前**: `JDE_OW_Port`  
  
     **[種類]** :**JDE_OneWorld**  
  
     **送信ハンドラー**: **[Biztalkserverapplication]**  
  
     **パイプライン**:**XMLTransmit**と**XMLReceive**  
  
11. **[構成]** をクリックし、次のプロパティ値を入力します。  
  
     **ホスト:** \<JDEOW ホスト名を入力します。\>  
  
     **JAVA_HOME:** `C:\j2sdk1.4.2_08`  
  
     **JDEdwards 環境:** \<JDEOW 環境を入力します。\>  
  
     **JDEdwards JAR ファイル:** <enter full path of JAR files>  
  
     `C:JDEOWJarsBTSLIBInterop.jar; C:JDEOWJarsConnector.jar; C:JDEOWJarsKernel.jar;C:Program FilesMicrosoft BizTalk Adapters for Enterprise ApplicationsJ.D. Edwards OneWorld®ClassesJDEJAccess.jar`  
  
     **パスワード:** ドロップダウン リストを使用し、JD Edwards OneWorld パスワードを入力します。  
  
     **ポート:**  `6009`  
  
     **ユーザー名:** <enter your JD Edwards User Name>  
  
     ![](../core/media/jdeow-transportproperties-configurebutton2.gif "JDEOW_TransportProperties_ConfigureButton2")  
  
12. **[OK]** を 2 回クリックしてダイアログ ボックスを閉じます。  
  
13. 構成 Applicationwindow で、クリックして **\<None\>** の**JDE_FileOut**ドロップダウン リストでします。  
  
14. **[新しい送信ポート]** を選択し、プロパティの値を次のとおりに入力または選択します。  
  
     **名前**: `FileOutPort`  
  
     **[種類]** : **[最近使ったファイル]**  
  
     **送信ハンドラー**: **[Biztalkserverapplication]**  
  
     **送信パイプライン**: **[Xmltransmit]**  
  
15. **[構成]** をクリックし、`C:\Labs\JDE_OW_Test\FileOut` に「 **C:\Labs\PS_Test\FileOut** 」と入力します。 **[ファイル名]** に「 **%MessageID%.xml** because this results in a unique file に「 each message.  
  
     ![](../core/media/jdeow-file-transport-properties-fileout.gif "JDEOW_File_Transport_Properties_FileOut")  
  
16. **[OK]** を 3 回クリックして、ダイアログ ボックスを閉じます。  
  
17. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして、 **JDE_OW_Test**アプリケーション、およびクリック**開始**します。  
  
#### <a name="test-the-orchestration"></a>オーケストレーションをテストします。  
  
1.  **C:\Labs\JDE_OW_Test**ディレクトリ、 **Sample.xml**ファイルとして表示されます。  
  
     ![](../core/media/jdeow-samplexml-notepad-addressbookmastermbf.gif "JDEOW_SampleXML_Notepad_AddressBookMasterMBF")  
  
2.  編集、 **Sample.xml**以外をすべて削除するファイル、 **cActionCode**と**mnAddressBookNumber**要素。  
  
     ![](../core/media/jdeow-samplexml-notepad-cactioncode.gif "JDEOW_SampleXML_Notepad_cActionCode")  
  
3.  **CActionCode**要素の文字を挿入する`i`します。  
  
4.  **MnAddressBookNumber**挿入数`500`します。  
  
5.  変更を保存し、ファイルのコピー、 **C:\Labs\JDE_OW_Test\FileIn**フォルダー。 これは、オーケストレーション プロセスを開始する受信場所です。  
  
6.  表示する必要があります XML ファイル、数秒で、 **C:\Labs\JDE_OW_Test\FileOut**フォルダー。 これは、すべてのレコード、アドレスが 500 を含める必要があります。  
  
     ![](../core/media/jdeow-xml-output-jde-callbsfn.gif "JDEOW_XML_Output_JDE_CALLBSFN")  
  
     この返されたレコード データは、ラボ 1 で JD Edwards OneWorld システムに対してクエリによって返されるデータと一致する必要があります。 ラボ 1 で取得したレコードを比較して、ことを確認できます、**取得**メソッドが正常に動作します。  
  
## <a name="summary"></a>まとめ  
 この演習では、JD Edwards OneWorld システムにアクセスする前提条件が正しく設定されてことを確認最初。 次に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、オーケストレーションが含まれる新しい BizTalk プロジェクトを作成しました。 JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムからデータを取得する BizTalk オーケストレーションを構成したとします。 オーケストレーションを構成するために、送信ポート、受信ポート、および送信/受信ポートを作成しました。 JD Edwards OneWorld アダプターにこれらのポートをバインドし、メッセージを適切なポートに割り当てました。  
  
 BizTalk プロジェクトの作成後、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してプロジェクトをビルドして展開しました。 新しいアプリケーションを構成し、JD Edwards OneWorld システムからデータを取得しました。 アプリケーションが正しく機能したことを確認するには、出力 XML ファイルをラボ 1 で JD Edwards OneWorld システムから受信したファイルを比較します。