---
title: BizTalk Adapter for JD Edwards OneWorld に追加する |Microsoft Docs
description: BizTalk 管理コンソールに、JD Edwards OneWorld を追加、送信ポートを作成、トランスポートのプロパティを構成および xmlreceive と XMLTransmit パイプラインを使用して、BizTalk Server で JD Edwards OneWorld アダプターを使用する場合
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03126f4e-9156-4c0c-ab5c-0627f0c05263
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decababef3ece92c99687a4019b15625b1b4c6b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981395"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>BizTalk 管理コンソールで JD Edwards EnterpriseOne の成果物を構成します。
Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。 送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。 BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。  

## <a name="add-the-adapter-to-biztalk-administration"></a>アダプターを BizTalk 管理コンソールに追加します。 

1.  開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**.  
  
2.  右クリック**アダプター**を選択します**新規**、選び**アダプター**します。  
  
3.  アダプターの名前を入力します。 たとえば、入力`JDEOneWorld`します。  
  
4.  選択 **[jdeoneworld]** から、**アダプター**一覧**OK**します。  

  
### <a name="check-if-the-adapter-is-working"></a>アダプターが動作しているかどうかは確認します。 
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、調べることで、アダプターが正しく機能していること確認できます、**論理システム**ウィンドウ。 初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。  
  
 
1. **BizTalk Server 管理**、展開**プラットフォームの設定**、展開**アダプター**、し、 **jdeoneworld**します。  
  
2. 詳細ペインで右クリックして**BizTalkServerApplication**を選択し、**プロパティ**します。  
  
3. 選択、**プロパティ**タブ。  
  
4. SQL 接続パラメーターを設定します。  
  
   -   **SQL データベース パラメーターを定義する**SQL Server 名とデータベースはインストール時に設定するものです。 これは、サーバーと、このアダプターのデータベースを再定義できますをテキスト領域です。  
  
5. 選択**閉じる**を終了する、**論理システム**ウィンドウ。  
  
    次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。  

## <a name="create-the-send-port"></a>送信ポートを作成します。  
  
1.  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、アプリケーションを展開します。  
  
2.  右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答送信ポート**します。  
  
    > [!NOTE]
    >  使用することも**静的な一方向ポート**します。  
  
3.  **送信ポートのプロパティ**を選択、**名前**フィールド、および送信ポートの名前を入力します。 たとえば、入力**SendToJDE**します。  
  
4.  **型**ドロップダウン リストで、 **[jdeoneworld]** します。  
  
5.  **URI**ドロップダウン リストで、送信ハンドラーを選択します。  
  
6.  **[OK]** を選択します。 

## <a name="configure-the-transport-properties"></a>トランスポートのプロパティを構成します。
JD Edwards OneWorld の "トランスポート プロパティ" システム定義は、デザイン時および実行時のログオンに使用されます。 この資格情報を設定するのは、デザイン時に JD Edwards OneWorld ビジネス関数を参照するためと、実行時に呼び出しを行うためです。  
  
 JD Edwards OneWorld への接続が作成されるときに、接続オブジェクトにパラメーターが渡されます (ユーザー、パスワード、環境)。 JD Edwards OneWorld Application ビジネス関数のインスタンスが返されます。 資格情報には、さらにエンタープライズ サーバー/アプリケーション サーバーの名前、およびサービスがリッスンする定義済みの TCP/IP ポートが含まれます。  
  
 エンタープライズ サーバーの名前とポートは、jdeinterop.ini というファイルから読み取られます。 これらの値は、システム定義での設定値と同一でなければなりません。  
  
> [!NOTE]
>  入力値はすべて、大文字と小文字が区別されます。  
  
### <a name="set-the-properties"></a>プロパティを設定します  
 **トランスポートのプロパティ**ダイアログ ボックスで、サーバー システムやアクセスしようとしているオブジェクトに固有の接続および資格情報パラメーターを設定します。  
  
1.  資格情報を指定します。 JD Edwards OneWorld システムにアクセスするには、次の方法があります。  
  
    -   ログオン資格情報 (パスワード、ユーザー名): このメソッドを使用する場合は、手順 5. に進みます。  
  
    -   シングル サインオン  
  
2.  シングル サインオン (SSO) を使用する**はい**で、**を使用して SSO**します。  
  
     SSO を設定する方法の詳細については、次を参照してください[アダプターのセキュリティ。](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)  
  
3.  一覧で関連アプリケーションを選択します。  
  
     エンタープライズ シングル サインオンのツールによって作成される関連アプリケーションはそれぞれ、JD Edwards OneWorld などの特定のアプリケーションを表します。 Microsoft BizTalk Adapter for JD Edwards OneWorld では、アプリケーション ユーザーの資格情報が使用されます。 この資格情報は、指定された関連アプリケーションのサーバー システムの SSO 資格情報データベースから取得されます。 取得される資格情報は、BizTalk Server プロジェクトを起動したアプリケーション ユーザーの資格情報です。  
  
     詳細については、[関連アプリケーションを作成する](../core/creating-affiliate-applications3.md)を参照してください。  
  
4.  展開、 **JD Edwards OneWorld システム**ノードし、JD Edwards OneWorld サーバーへの接続に必要なすべての情報を入力します。  
  
     ![](../core/media/jdedadapter-02-jdesystem.gif "JDEdAdapter_02_JDESystem")  
  
     接続パラメーターの設定が完了すると、JD Edwards OneWorld システムの内容を参照できるようになります。 詳細については、[を BizTalk Server プロジェクトに JD Edwards OneWorld スキーマをインポートする](../core/importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)を参照してください。  
  
5.  呼び出しでは、たとえば 200 の数を示す値を入力**最大同時呼び出し数**必要な場合。  
  
     `Max Concurrent Calls`パラメーターでは、構成を最適化することができます。 スループットがバックエンドの処理能力を上回る場合に、このパラメーターを使用してメッセージ オーバーロード保護をアクティブにします。 既定値は -1 で、これは呼び出しの数が無制限であることを示します。  
  
     BizTalk Server が送信アダプターにメッセージを送信するときに、BizTalk Server は最初にアダプターからバッチを 1 つ受け取ります。 `TransmitMessage` をそのバッチに対して起動して、各メッセージを送信します。 この処理が完了すると、BizTalk Server はバッチで `Done` を呼び出し、アダプタがバックエンドに対するメッセージ送信を開始します。 BizTalk Server が複数のバッチを受け取ってから `Done` を呼び出しても、メッセージは送信されません。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。  
  
     このパラメーターの変更が反映されるまで最大 1 分程度かかります。BizTalk Server は、SQL データベースに保存されたアダプター構成に対する変更を取得する必要があるからです。  
  
6.  選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。  
  
     たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。  
  
    > [!NOTE]
    >  browsingagent.exe が最新の状態に更新されるのは、ユーザーが現在の参照セッションを終了したときです。 たとえば、終了する必要があります、**項目の追加生成**閲覧セッションを browsingagent.exe を更新します。  
  
7.  必要なすべての情報を提供するには、後に次のようにクリックします。**適用**、順にクリックします **[ok]** の接続情報を受け入れます。  
  
     JD Edwards OneWorld にアクセスするには、BizTalk Adapter for JD Edwards OneWorld の接続パラメーターを設定する必要があります。  
  
### <a name="adapter-required-properties"></a>必要なアダプターのプロパティ  
 コントロール パネルでグローバル環境変数を設定しなかった場合は、このセクションで設定できます。  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Host`|ホスト サーバーのコンピューター名の名前を入力 (たとえば、 `actsvr1`); またはコンピューターの IP アドレス (たとえば、 `123.456.0.789`)。|  
|JAVA_HOME|JDK インストール ディレクトリの完全パスを入力します。|  
|JD Edwards 環境|たとえば、JD Edwards oneworld では、環境の名前を入力`DV7333`します。<br /><br /> DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。|  
|JDEdwards JAR ファイル|各 JAR ファイルの完全なパスとファイル名を入力します。<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-JDEActionalInterop.jar<br /><br /> jar ファイルの区切りにはセミコロン (;) を使用し、スペースは入れません。 以下に例を示します。<br /><br /> `<drive>\Connector.jar;<drive>\Kernel.jar;`|  
|パスワード|指定したユーザーのパスワードを入力します。|  
|Port|データを交換するポート番号を入力 (たとえば、 `6009`)。|  
|[ユーザー名]|JD Edwards OneWorld システムへのログオンに使用する JD Edwards OneWorld ユーザー名を入力します。|  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>XMLTransmit および XMLReceive パイプラインを使用します。
Microsoft の BizTalk Adapter for JD Edwards OneWorld では、送信 XMLTransmit および XMLReceive を選択すること、および受信パイプラインが必要です。  
  
1.  **BizTalk Server 管理**、展開**アプリケーション**、アプリケーションを展開します。  
  
2.  選択**送信ポート**を送信ポートを右クリックし、**プロパティ**します。  
  
3.  **送信ポートのプロパティ**次の操作を行います。  
  
    1.  送信パイプラインを選択、**送信パイプライン**ドロップダウン リスト。  
  
    2.  受信パイプラインを選択、**受信パイプライン**ドロップダウン リスト。  
  
4.  **[OK]** を選択します。  

## <a name="next-steps"></a>次のステップ
[Visual Studio へのアダプター スキーマのインポート](importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects.md)  
[メッセージ コンテキストのプロパティの使用](using-message-context-properties2.md)