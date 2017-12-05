---
title: "エラー処理 (BizTalk Server Samples フォルダ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, errors
- errors, examples
- examples, messages
- messages, examples
- messages, errors
ms.assetid: b39791ed-277b-4625-b9a9-72480a1b6ff6
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 386e9729ac32cb08863e2ac3e0699ecda7890dbc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error-handling-biztalk-server-samples-folder"></a>エラー処理 (BizTalk Server サンプル フォルダー)
このサンプルの目的は、コンテンツ ベースのルーティング (CBR) アプリケーション用のエラー処理機能を構築することです。  
  
## <a name="prerequisites"></a>前提条件  
 サンプルを実行するにまたは以降をインストールした Microsoft Office InfoPath 2010 をお勧めします。 InfoPath を使用せずにサンプルを実行することもできますが、その場合、経費報告書の内容および HTTP アダプターを経由した経費報告書の送信は確認できません。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、経費報告書処理システムの一部を実装します。 具体的には、このサンプルは以下の処理を行います。  
  
1.  経費報告書に関する情報を含む経費報告書のスキーマおよび部門名を含む個々の送信者を定義します。  
  
2.  ディレクトリを経由した、または InfoPath を使用する Web サービスを経由した経費報告書の送信を可能にします。  
  
3.  昇格、**部門**と**correlationID**ルーティングを制御するポート フィルタで使用できるようにする、メッセージのプロパティを文書化します。  
  
4.  マーケティング部門に属する経費報告書をディレクトリ内のファイルにルーティングし、この部門のバックエンド システムへの配信をシミュレートします。  
  
5.  マーケティング以外の部門に属する経費報告書について失敗したメッセージを生成します。 失敗したメッセージには、エラー コードやエラーの説明など、エラーに関する情報が含まれます。  
  
6.  失敗したメッセージを、手動で修正および再送信されるように、受信者 (ビジネス ユーザーまたはアプリケーション オペレーター) にルーティングします。  
  
7.  再送信された経費報告書を前述の部門に基づいてルーティングします。  
  
 この作業の多くは BizTalk のオーケストレーション スケジュールによって行われます。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このデザインでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の既定の送受信 XML パイプライン、プロパティの昇格、サブスクリプション フィルター、およびオーケストレーション スケジュールを使用して、メッセージをルーティングします。 デザイン要素とその選択理由を次の表に示します。  
  
|デザイン要素|選択理由|  
|--------------------|--------------------------|  
|既定の XML 受信パイプライン|-XMLReceive パイプラインは、プロパティの昇格をサポートしています。PassThruReceive パイプラインされていません。<br />-着信メッセージは既に XML 形式で、基本の逆アセンブリとパーティの解決以外の処理は必要ありません。|  
|失敗したメッセージのルーティング|受信ポートが失敗したメッセージを中断し、既定では否定受信確認を生成します。 ルーティングが有効の場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は処理に失敗したメッセージを、別の受信ポートやオーケストレーション スケジュールなど、メッセージをサブスクライブするアプリケーションにルーティングします。|  
|プロパティの昇格|BizTalk Server は、ルーティング プロパティ フィールドによって異なります。 識別フィールドはオーケストレーションによって使用されるため、ルーティングには使用できません。|  
|サブスクリプション フィルター|-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャしてルーティングを実行します。|  
|BizTalk オーケストレーション スケジュール|-失敗したメッセージに情報を追加する機会を提供します。<br />有効には、人間の介入を専用の場所に障害が発生したメッセージをルーティングします。<br />プロセスは、経費報告書を再送信します。|  
|XMLTransmit|-送信 XML メッセージの基本的なアセンブリを実行します。 PassThruTransmit パイプラインでは追加のサポートは行われません。|  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは <`Samples Path>`\Messaging\ErrorHandling\\です。  
  
 次の表には、このサンプルのファイルの一覧が含まれています。  
  
|ファイル|Description|  
|----------|-----------------|  
|Cleanup.bat|アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。<br /><br /> 送信ポートと受信ポートが削除されます。<br /><br /> 必要に応じて、インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|ErrorHandling.sln|サンプルの Visual Studio ソリューション ファイルです。|  
|ErrorHandlingBinding.xml|サンプルのバインド ファイルです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|Expense Report – John Doe.xml|経費報告書の InfoPath ドキュメント例です。|  
|Invalid Expense Report – John Doe.xml|無効なデータを含む経費報告書の InfoPath ドキュメント例です。|  
|ErrorHandler フォルダー内 : <br /><br /> ErrorHandler.btproj|オーケストレーションの BizTalk プロジェクトです。|  
|ErrorHandler フォルダー内 : <br /><br /> ResubmitLogic.odx|失敗したメッセージをサブスクライブし、手動で修正できるように受信者に送信し、修正されたメッセージをルーティングするためにサーバーに再送信するオーケストレーションです。|  
|ErrorHandler フォルダー内 : <br /><br /> SuspendMessage.odx|エラー処理オーケストレーション内で処理できない中断メッセージに使用するオーケストレーションです。|  
|InfoPathForms フォルダー内:<br /><br /> Expense Report.xsn<br /><br /> Expense Report - Resubmit.xsn|経費報告書の InfoPath フォームと、失敗したメッセージの表示と再送信に使用されるフォームです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> ExpenseReportSchema.xsd|経費報告ドキュメントの XML スキーマです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PipelinesAndSchemas.btproj|サンプルの BizTalk プロジェクトです。|  
|PipelinesAndSchemas フォルダー内: <br /><br /> PropertySchema.xsd|サンプルのプロパティ スキーマです。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルは、独自のエラー処理手順を作成するための開始点として使用できます。  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>Compose サンプルをビルドして初期化するには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     <`Samples Path`>**\Messaging\ErrorHandling**  
  
2.  実行**Setup.bat**、次の操作を実行します。  
  
    -   3 つのフォルダーを作成します。 **ExpenseReportIn**、 **ExpenseReportOut**、および**ResubmittedReportIn**次のパスの下。  
  
         <`Samples Path`>**\Messaging\ErrorHandling**  
  
    -   コピーし、InfoPath フォーム**Expense Report.xsn**と**Expense Report – Resubmit.xsn**フォルダーに**C:\Temp\InfoPathForms**です。  
  
    -   このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。  
  
    -   という仮想ディレクトリを作成**ExpenseReports**です。  
  
    -   いう新しい BizTalk アプリケーションを作成**Error Handling Sample**され、そこにサンプル アセンブリを展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成してバインドします。  
  
    -   オーケストレーションを参加させて開始し、受信場所を有効にしてから、送信ポートを開始します。  
  
         Setup.bat を実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアは、サンプル アセンブリの署名に使用します。  
  
3.  このサンプルを実行する前に、いることを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でビルドまたは初期化プロセス中にエラーが報告されません。  
  
    > [!NOTE]
    >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
4.  インターネット インフォメーション サービス (IIS) 7.0 を使用している場合は、サンプルが使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP 受信場所に対応している仮想ディレクトリの設定を調整するために、追加の構成手順を実行する必要があります。 IIS を構成するには、次の手順を実行します。  
  
    1.  IIS 7.0 マネージャーを使用して、BizTalk 分離ホスト ユーザー グループ用の新しいアプリケーション プールを作成します。  
  
    2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分離ホスト ユーザーの ID で実行するようにアプリケーション プールを構成します (他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信場所用に構成されているアプリケーション プールがある場合は、この手順を省略できます)。  
  
    3.  仮想ディレクトリを構成する**ExpenseReport** HTTP 受信前の手順で作成したアプリケーション プールを使用します。  
  
     BTSHTTPReceive.dll ISAPI 拡張機能用の Web サーバー拡張をまだ作成していない場合は、ここで作成し、そのステータスを [許可] に設定して有効にします。 これを行う IIS 7.0 の IIS 管理コンソールを使用して (か直接**管理ツール**またはコンピュータの管理コンソールを使用) 次のようにします。  
  
    1.  展開して、**インターネット インフォメーション サービス マネージャー**ツリー。  
  
    2.  クリックして、 **Web サービス拡張**フォルダーです。  
  
    3.  管理コンソールの右側のウィンドウでをクリックして**新しい Web サービス拡張を追加**です。  
  
    4.  **新しい Web サービス拡張**ダイアログ ボックスで、をクリックして**追加**です。  
  
    5.  **ファイルの追加**ダイアログ ボックスで、をクリックして**参照**ファイルを選択して <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**、順にクリック**[ok]**.  
  
    6.  仮想ディレクトリを構成する**ExpenseReport**ローカル パスを使用する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive  
  
     詳細については、次を参照してください。 [HTTP の受信場所の IIS を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)です。  
  
## <a name="running-the-sample"></a>サンプルを実行します。  
 正しい経費報告書でサンプルを実行する前に、次の手順に従って、"エラーなし" のケース サンプルが正しく機能することを確認します。  
  
#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a>"エラーなし" のケース サンプルが正しく機能することを確認するには  
  
1.  InfoPath フォームを開きます**Expense Report - John Doe.xml**です。 見て、**部門**フォーム内でフィールドです。 このフィールドは "Marketing" に設定されている必要があります。  
  
2.  InfoPath ウィンドウの左上隅にある [クリックして**送信**] をクリックしてまたは**経費報告書**です。 経費報告書が正常に送信されたことを示す確認ウィンドウが表示されるまで待ちます。  
  
     - または -  
  
     コピーし、このファイルに貼り付け、 **ExpenseReportIn**フォルダーです。  
  
3.  ドロップされた新しいファイルを表示する必要があります、 **ExpenseReportOut**フォルダーです。 このファイルは、前の手順で送信された経費報告書レポート フォームと同じです。  
  
 "エラーなし" ケースを確認した後、次の手順に従って、正しい経費報告書のサンプルを実行し、エラー処理機能をトリガーします。  
  
#### <a name="to-trigger-error-handling"></a>エラー処理をトリガーするには  
  
1.  InfoPath フォームを開きます**Invalid Expense Report - John Doe.xml**です。 見て、**部門**フォーム内でフィールドです。 このフィールドは、無効な値に設定されています。  
  
2.  InfoPath ウィンドウの左上隅にある クリックして**送信**です。 経費報告書が正常に送信されたことを示す確認ウィンドウが表示されるまで待ちます。  
  
     - または -  
  
     コピーし、このファイルに貼り付け、 **ExpenseReportIn**フォルダーです。  
  
3.  という名前の新しいファイルを表示する必要があります**ErrorReport_\<***日付*_*時間***\>.xml** をドロップ**ExpenseReportOut**フォルダーです。  
  
     このファイルを開き、前の手順で送信された経費報告書の先頭にエラー情報が追加されていることを確認します。  
  
4.  クリックして、誤った部門値を"Marketing"に置き換えます**送信**InfoPath ウィンドウの左上隅にあります。  
  
     - または -  
  
     コピーし、このファイルに貼り付け、 **ResubmittedReportIn**フォルダーです。  
  
5.  作成した新しいファイルを表示する必要があります、 **ExpenseReportOut**フォルダーです。 このファイルが、サーバーに再送信された修正済みの費用報告書です。  
  
## <a name="see-also"></a>参照  
 [失敗したメッセージのルーティングを使用します。](../core/using-failed-message-routing.md)   
 [Messaging (BizTalk Server Samples フォルダー)](../core/messaging-biztalk-server-samples-folder.md)