---
title: "BizTalk Adapter for JD Edwards OneWorld に追加 |Microsoft ドキュメント"
description: "JD Edwards OneWorld を BizTalk 管理コンソールに追加、送信ポートを作成、トランスポートのプロパティを構成および BizTalk Server で JD Edwards OneWorld アダプターを使用するときに、XMLReceive パイプラインと XMLTransmit パイプラインを使用"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 784323634d3084efd0b56aac1d5dbc97f2b4329f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>BizTalk 管理コンソールで JD Edwards EnterpriseOne の成果物を構成します。
Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。 送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。 BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。  

## <a name="add-the-adapter-to-biztalk-administration"></a>BizTalk 管理コンソールに、アダプターを追加します。 

1.  開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、順に展開**のプラットフォームの設定**.  
  
2.  右クリック**アダプター****新規**を選択して**アダプター**です。  
  
3.  アダプターの名前を入力します。 たとえば、入力`JDEOneWorld`です。  
  
4.  選択**[jdeoneworld]**から、**アダプター**一覧**OK**です。  

  
### <a name="check-if-the-adapter-is-working"></a>アダプターが動作しているかどうかは確認します。 
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、できることを確認するを確認して、アダプターが正しく機能している、**論理システム**ウィンドウです。 初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。  
  
 
1.  **BizTalk Server 管理コンソール**、展開**プラットフォームの設定**、展開**アダプター**、し、 **jdeoneworld**です。  
  
2.  詳細ウィンドウで右クリック**BizTalkServerApplication**を選択して**プロパティ**です。  
  
3.  選択、**プロパティ**タブです。  
  
4.  SQL 接続パラメーターを設定します。  
  
    -   **SQL データベース パラメーターを定義する**SQL Server 名とデータベースがインストール時に設定します。 これは、テキスト領域がサーバーと、このアダプターのデータベースを再定義できることです。  
  
5.  選択**閉じる**を終了する、**論理システム**ウィンドウです。  
  
     次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。  

## <a name="create-the-send-port"></a>送信ポートを作成します。  
  
1.  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、アプリケーションを展開します。  
  
2.  右クリック**送信ポート****新規**、し、**静的な送信請求-応答送信ポート**です。  
  
    > [!NOTE]
    >  使用することも**静的な一方向ポート**です。  
  
3.  **送信ポートのプロパティ**、select、**名前**フィールド、および送信ポートの名前を入力します。 たとえば、入力**SendToJDE**です。  
  
4.  **型**ドロップダウン リストで、 **[jdeoneworld]**です。  
  
5.  **URI**ドロップダウン リストで、送信ハンドラーを選択します。  
  
6.  **[ OK]** を選択します。 

## <a name="configure-the-transport-properties"></a>トランスポートのプロパティを構成します。
JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。 この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。  
  
 JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。 JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。 資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。  
  
 エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。 これらの値は、システム定義での設定値と同一でなければなりません。  
  
> [!NOTE]
>  入力値はすべて、大文字と小文字が区別されます。  
  
### <a name="set-the-properties"></a>プロパティを設定します  
 **トランスポートのプロパティ**ダイアログ ボックスで、サーバーのシステムおよびアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。  
  
1.  資格情報を指定します。 JD Edwards OneWorld システムにアクセスするには、次の方法があります。  
  
    -   ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。  
  
    -   シングル サインオン  
  
2.  シングル サインオン (SSO) を使用するのには、選択**はい**で、 **SSO を使用する**です。  
  
     SSO を設定する方法の詳細については、次を参照してください[アダプターのセキュリティ。](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。 Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。 この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。 取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。  
  
     詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。  
  
4.  展開して、 **JD Edwards OneWorld システム**ノードと JD Edwards OneWorld サーバーに接続に必要なすべての情報を入力します。  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。 詳細については、次を参照してください。[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)です。  
  
5.  呼び出し、たとえば 200 の数を示す値を入力**Max Concurrent Calls**必要がある場合。  
  
     `Max Concurrent Calls`パラメーターを使用して、構成を最適化することができます。 スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。 既定値は -1 で、これは呼び出しの数が無制限であることを示します。  
  
     BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。 `TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。 この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。  
  
     このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。  
  
6.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
    > [!NOTE]
    >  browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。 たとえば、終了する必要があります、**項目の生成された追加**参照セッションとを browsingagent.exe を更新します。  
  
7.  必要なすべての情報を提供すると、をクリックして**適用**、クリックして**[ok]**の接続情報を受け入れます。  
  
     JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。  
  
### <a name="adapter-required-properties"></a>必要なアダプターのプロパティ  
 コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。  
  
|パラメーター|Description|  
|---------------|-----------------|  
|`Host`|ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。|  
|JAVA_HOME|JDK インストール ディレクトリの完全パスを入力します。|  
|JD Edwards 環境|たとえば、JD Edwards OneWorld の環境の名前を入力`DV7333`です。<br /><br /> DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。|  
|JDEdwards JAR ファイル|各 JAR ファイルの完全なパスとファイル名を入力します。<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。 例:<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|Password|指定されたユーザーのパスワードを入力します。|  
|ポート|データを交換するポート番号を入力 (たとえば、 `6009`)。|  
|[ユーザー名]|JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>XMLTransmit および XMLReceive パイプラインを使用します
Microsoft BizTalk Adapter for JD Edwards OneWorld では、送信、XMLTransmit および XMLReceive を選択し、受信パイプラインが必要です。  
  
1.  **BizTalk Server 管理コンソール**、展開**アプリケーション**、し、アプリケーションを展開します。  
  
2.  選択**送信ポート**を送信ポートを右クリックし、**プロパティ**です。  
  
3.  **送信ポート プロパティ**を次の操作します。  
  
    1.  送信パイプラインを選択して、**送信パイプライン**ドロップダウン リスト。  
  
    2.  受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。  
  
4.  **[ OK]** を選択します。  

## <a name="next-steps"></a>次の手順
[Visual Studio にアダプター スキーマをインポートします。](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[メッセージ コンテキストのプロパティの使用](using-message-context-properties2.md)