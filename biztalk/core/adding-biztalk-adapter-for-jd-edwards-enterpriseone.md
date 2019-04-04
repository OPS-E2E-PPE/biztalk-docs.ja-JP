---
title: BizTalk Adapter for JD Edwards EnterpriseOne に追加する |Microsoft Docs
description: JD Edwards EnterpriseOne を BizTalk 管理コンソールに追加、送信ポートを作成、トランスポートのプロパティを構成、および BizTalk Server で JD Edwards EnterpriseOne アダプターを使用するときに、xmlreceive と XMLTransmit パイプラインを使用
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: baecebcd-c324-40aa-bacf-876f45b6c37f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676738840cc1156f7809214634a9412f32115ce4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969227"
---
# <a name="configure-jd-edwards-enterpriseone-artifacts-in-biztalk-administration"></a>BizTalk 管理コンソールで JD Edwards EnterpriseOne の成果物を構成します。
Microsoft BizTalk Adapter for J.D.Edwards EnterpriseOne には、Receive Handler フォルダーと Send Handler フォルダーの両方が含まれています。 これらのフォルダーには、BizTalkServerApplication が含まれています。 BizTalk Adapter for J.D.Edwards EnterpriseOne は、BizTalk Server と共にインプロセスで実行され、分離ホスト プロセスでは実行されません。  

## <a name="add-the-adapter-to-biztalk-administration"></a>アダプターを BizTalk 管理コンソールに追加します。 

1.  開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**.  

2.  右クリック**アダプター**を選択します**新規**、選び**アダプター**します。  

3.  アダプターの名前を入力します。 たとえば、入力`JDEEnterpriseOne`します。  

4.  選択**JDEEnterpriseOne**から、**アダプター**一覧**OK**します。  

## <a name="create-the-send-port"></a>送信ポートを作成します。  

1.  **BizTalk Server 管理**、展開**アプリケーション**、成果物をホストするアプリケーションを展開し

2.  右クリックして**送信ポート**を選択します**新規**、し、**静的な送信請求-応答ポート**します。  

3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  

    -   **名前**、送信ポートの名前を入力します。 たとえば、入力`SendToJDE`します。  

    -   **型**ドロップダウン リストで、 **JDEdwards**します。  

    -   **送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。  

5.  **[OK]** を選択して変更を保存します。

## <a name="configure-the-transport-properties"></a>トランスポートのプロパティを構成します。

JD Edwards EnterpriseOne トランスポートのプロパティは、デザイン時および実行時に使用されます。 **トランスポートのプロパティ**、接続および資格情報パラメーターに固有の設定、サーバー システムとアクセスしようとしているオブジェクト。  

 接続パラメーターの設定後、JD Edwards EnterpriseOne システムのテーブル、ビュー、およびプロシージャをアダプター ウィザードで表示できます。  

 JD Edwards EnterpriseOne に接続すると、パラメーターが接続オブジェクトに渡されます (ユーザー、パスワード、環境)。 これにより、JD Edwards EnterpriseOne アプリケーション ビジネス関数のインスタンスが返されます。 資格情報には、さらにエンタープライズ サーバーまたはアプリケーション サーバーの名前と、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がリッスンする定義済みの TCP/IP ポートが含まれます。  

> [!NOTE]
>  エンタープライズ サーバー名およびポートの既定値は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で構成されています。 また、jdeinterop.ini というファイルからも読み込まれます。 ログオン エラーが発生した場合は、資格情報と値を確認してください。  

### <a name="enter-the-properties"></a>プロパティを入力します  

1. BizTalk Server 管理コンソールで、展開**アプリケーション**、アプリケーションを展開します。  

2. 右クリックして**送信ポート**を選択します**新規**、し、**静的な一方向送信ポート**します。  

3. **送信ポートのプロパティ**、**名前**、し、このポートの名前。 たとえば、入力`JDEEnterpriseOneSend`します。  

4. **全般**の**トランスポートの種類**ボックスで、 **JDE EnterpriseOne**ドロップダウン リストでします。  

5. **アドレス (URI)** プロパティ、省略記号を選択します (**.**). **JDE EnterpriseOne トランスポートのプロパティ**を開きます。 

    ![](../core/media/jdeenterprise-trans.gif "JDEEnterprise_Trans")  

6. **JDE EnterpriseOne トランスポートのプロパティ**プロパティ、展開、**アダプターの必須プロパティ**、し、JD Edwards EnterpriseOne サーバーへの接続に必要なすべての情報を入力します。  次のガイドラインに従ってトランスポートのプロパティを設定してください。  


   |                      これを使用して、                       |                                                                                                                                                                                                            これを行う                                                                                                                                                                                                             |
   |-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **アダプタに必要なプロパティ**           |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                        ホスト                         |                                                                                                                   ホスト サーバー コンピューターの名前<br /><br /> `actsvr1`)<br /><br /> -- または--<br /><br /> コンピューターの IP アドレス<br /><br /> `123.456.0.789`)                                                                                                                    |
   |                      JAVA_HOME                      |                                                                                                                                                                  JDK インストールへの完全なパスを入力します (たとえば、<br /><br /> `C:\jdk1sdk1.4.2_07`)                                                                                                                                                                  |
   |                JDEdwards 環境                |                                                                                  JD Edwards EnterpriseOne の環境の名前を入力 (たとえば、 `DV7333`)。<br /><br /> DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。                                                                                   |
   |                 JDEdwards JAR ファイル                 | 各 JAR ファイルの完全パスとファイル名を入力します。<br /><br /> -C:\JDEOWJars\Connector.jar<br />-C:\JDEOWJars\Kernel.jar<br />-\Microsoft BizTalk Adapters for Enterprise applications \j.d. プログラムの。 Edwards EnterpriseOne(r)\Classes\JDEDynAccess.jar<br /><br /> 各 jar ファイルは、次に示すようにセミコロン (;) で区切り、スペースは挿入しません。<br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`) |
   |                      パスワード                       |                                                              ユーザーのパスワードを入力します。 シングル サインオン (SSO) を使用しない場合、サーバー システムにアクセスするには BizTalk Adapter for JD Edwards EnterpriseOne の資格情報関連のパラメーターを設定する必要があります。 このパスワードは、ユーザー名に対応しています。このパスワードに基づいて、データベースにアクセスしたときに付与される特権が決定されます。                                                              |
   |                        Port                         |                                                                                                                                                                         入力した数値識別子、送信ポートまたは受信ポート (たとえば、 `6009`)。                                                                                                                                                                          |
   |                      [ユーザー名]                      |                                                                                                                                                                                         ユーザーの名前を入力し、クリックして**OK**します。                                                                                                                                                                                         |
   | **Bootstrap Data Source に必要なプロパティ\*\\**\* |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                  Data Source Name                   |                                                                                                                                                                           データ ソースの名前を入力します。 この名前はすべてのデータの種類に必須です。                                                                                                                                                                            |
   |                   データベースの所有者                    |                                                                                                                                                                                               データベース所有者の名前を入力します。                                                                                                                                                                                                |
   |                データベース サーバー名                 |                                                                                                                                                                                               データベース サーバーの名前を入力します。                                                                                                                                                                                               |
   |                データベース サーバー ポート                 |                                                                                                                                                                                     データベース サーバー ポートの識別用の番号を入力します。                                                                                                                                                                                      |
   |                    データベースの種類                    |                                                                                                          データベースの種類を示す単一の文字を入力します。 以下に例を示します。<br /><br /> **I** -iSeries<br /><br /> **O** -Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** -UDB                                                                                                           |
   |               物理データベース名                |                                                                                                                                                                      物理データベースの名前を入力します。 この名前はすべてのデータベースの種類に必須です。                                                                                                                                                                       |
   |               **同時実行制御**               |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                最大同時呼び出し数                 |                                                                                                                    数値を入力、**最大同時呼び出し数**します。 この数など、同時呼び出しの最大数を表す`10`します。<br /><br /> このフィールドの既定値は 5 です。                                                                                                                    |
   |                  **エージェントを更新します。**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                    エージェントの更新                    |                           選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。<br /><br /> たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。                           |
   |                 **セキュリティ サーバー**                 |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                セキュリティ サーバー名                 |                                                                                                                                                             セキュリティ サーバーの名前を入力します。 このフィールドは省略可能で、既定値は JD Edwards サーバー ホストです。                                                                                                                                                              |
   |                サービス名接続                 |                                                                                                                                                  セキュリティ サーバーとオブジェクト構成マッピング (OCM) で使用されるポート番号を入力します。 既定値は JD Edwards サーバー ポートです。                                                                                                                                                  |
   |                 **シングル サインオン**                  |                                                                                                                                                                                                                                                                                                                                                                                                                                   |
   |                [関連アプリケーション]                |                                                                                                                                                                        一覧から関連アプリケーションを選択します (SSO を使用している場合のみ)。                                                                                                                                                                        |
   |                       SSO の使用                       |                                                                                                                                                                           選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。                                                                                                                                                                           |


7. 選択**OK**をすべてのプロパティを受け入れるようにします。  

### <a name="bootstrap-data-source-required-properties"></a>Bootstrap Data Source に必要なプロパティ  
 Bootstrap セクションは、サインオンでシステム テーブルにアクセスするために使用されます。 Bootstrap Data Source の情報によって、OCM が存在するデータ ソースが定義されます。  

 Bootstrap Data Source のパラメーターには、プラットフォームによっては設定する必要がない項目もあります。 一般的でない、データベースを使用している場合は、[JDBJ-JDBC DRIVERS] セクションを更新する必要があります**jdeinterop.ini** JDBC ドライバーを宣言します。 プラットフォームごとに、必要な設定を次に示します。  

-   **iSeries**します。 [データ ソース名]、[データベースの種類]、[データベース サーバー名]、[物理データベース名]  

-   **Oracle**します。 データ ソース名、データベースの種類、物理データベース名、データベースの所有者  

-   **SQL Server**します。 [データ ソース名]、[データベースの種類]、[データベース サーバー名]、[データベース サーバー ポート]、[物理データベース名]、[データベース所有者]  

-   **SQL Server OLEDB**します。 [データ ソース名]、[データベースの種類]、[データベース サーバー名]、[データベース サーバー ポート]、[物理データベース名]、[データベース所有者]  

-   **UDB**します。 データ ソース名、データベースの種類、物理データベース名、データベースの所有者  

### <a name="optimize-configuration"></a>構成を最適化します。  
 BizTalk Adapter for JD Edwards EnterpriseOne の構成を最適化するのに役立つ情報を次に示します。  

#### <a name="max-concurrent-calls-parameter"></a>[最大同時呼び出し数] パラメーター  
 `Max Concurrent Calls` パラメーターは、スループットがバックエンドの処理機能を上回るインスタンスで使用できます。 内のアダプターにパラメーターを追加する、**送信ポートのトランスポート プロパティ**メッセージ オーバー ロードの保護をアクティブ化するページ。 既定値は -1 です。これは呼び出しが制限されないことを意味します。  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、送信アダプターに対してメッセージを送信するとき、まずアダプターからバッチを受け取り、そのバッチについて `TransmitMessage()` を呼び出して各メッセージを転送します。 この処理が完了すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はバッチで `Done()` を呼び出し、アダプターがバックエンドに対するメッセージ送信を開始します。  

 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が `Done` を呼び出す前に複数のバッチを取得した場合、`Done` コマンドは実行されないことがあります。 バッチ内に含めるメッセージの最大数を設定することで、バックエンドに送信するメッセージを制御できます。  

 このパラメーターに加えた変更は、1 分以内に有効になります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、SQL データベースに保存されているアダプター構成に対する変更を取得する必要があります。  

#### <a name="refresh-agent"></a>エージェントの更新  
 選択すると**はい**の**エージェントの更新**、runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。  

 たとえば場合は、サーバーとの接続が失われたまたは、サーバーに追加したものと選択範囲の Microsoft アダプター ウィザードに表示されませんが自動的に再起動を処理することができます。  

 エージェントの更新パラメーターは、[トランスポートのプロパティ] ウィンドウで設定します。参照エージェントとランタイム エージェントの両方を更新します。 runtimeagent.exe は 1 分の遅延後または次の送信呼び出し時に更新されます。  

> [!NOTE]
>  browsingagent.exe は、現在の参照セッションを終了するまで更新されません。 "Add generated item..."を終了する必要があります例。 セッションと、browsingagent.exe を更新するを再入力を参照します。  

#### <a name="single-sign-on"></a>シングル サインオン  
 JD Edwards EnterpriseOne システムへのアクセスには、2 つの方法を使用できます。 1 つはログイン資格情報 (トランスポートのプロパティのログイン パラメーター) を使用する方法で、もう 1 つはシングル サインオン (SSO) を使用する方法です。 選択**はい**で、**を使用して、SSO**でシングル サインオンを使用するフィールド。  

 詳細および基本的な手順をシングル サインオンの設定については、[BizTalk Adapter for JD Edwards EnterpriseOne セキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)を参照してください。

 さらに、一覧から関連アプリケーションを選択する必要があります。 エンタープライズ シングル サインオン ツールで作成される関連アプリケーションは、JD Edwards EnterpriseOne などのアプリケーションを表します。 BizTalk Adapter for JD Edwards EnterpriseOne は、アプリケーション ユーザーの資格情報を使用します。  

 これらの資格情報は、指定された関連アプリケーションのサーバー システムの SSO データベースから取得されます。 取得される資格情報は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを起動したユーザー (アプリケーション ユーザー) の資格情報です。  

 関連アプリケーションを作成する方法の詳細についてを参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications4.md)します。 また、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オンライン ヘルプでも参照できます。  

## <a name="use-the-xmltransmit-and-xmlreceive-pipelines"></a>XMLTransmit および XMLReceive パイプラインを使用します。

このアダプターは、選択することが必要です**XMLTransmit**と**XMLReceive**送信および受信パイプラインはそれぞれします。  


1.  BizTalk Server 管理コンソールで、展開**アプリケーション**、アプリケーションを展開します。  

2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  

3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  

    1.  たとえば、送信ポートの名前を入力`SendToJDEEnterpriseOne`します。  

    2.  **型**ドロップダウン リストで、 **JDE EnterpriseOne**します。  

    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  

    4.  送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。  

    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。  

4.  **[OK]** をクリックします。  


## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications2.md)  
 [シングル サインオンと BizTalk Adapter for JD Edwards EnterpriseOne](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)   