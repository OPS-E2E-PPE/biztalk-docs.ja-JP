---
title: BAM ポータル構成のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 507bd5f0-b2a0-4d52-85f8-9d984138ca79
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4749ada0c4e85252403a10dbe88d0f7ea2191a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353173"
---
# <a name="customizing-the-bam-portal-configuration"></a>BAM ポータル構成のカスタマイズ
BAM ポータルで構成可能なオプションを数多くあります。 次の手順では、最適なユーザー エクスペリエンスを取得する BAM ポータルを変更する方法を説明します。  

> [!NOTE]
>  非管理者として、ポータルを構成するには、ユーザーが権限借用、ときに、いったんログオフして再度ログオン資格情報の入力を求められることがなく BAM ポータルの機能にアクセスする前にする必要があります。 たとえば、次のシナリオを考えてみます。  
>   
>  管理者以外の権限を借用したユーザーでは、Web サービスまたは BAM ポータルを構成します。 Everyone グループがあるポータルにアクセスするように、アクセス許可は、ポータルにするし設定にします。 PortalUsersGroup というローカル グループを作成し、ポータル ユーザー グループとそのグループを割り当てます。 これは、そのグループ内のユーザーのみがある、ポータルにアクセスすることを意味します。 BAM ポータルを構成した後は、ポータル ユーザー グループに、現在のユーザーを追加します。 BAM ポータルを開くと、資格情報のなります。 いったんログオフしてログオンすると、ただしが、資格情報を求められることがなく BAM ポータルを開くことができません。  
>   
>  BizTalk Server では、ローカル グループ アカウントとローカル ユーザー アカウントは、単一コンピューター構成でのみサポートされます。 また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a>64 ビット環境で BAM ポータルの実行  
 64 ビット環境でインターネット インフォメーション サービス (IIS) を使用する場合は、BAM ポータルを実行する 32 ビット モードに IIS を設定する必要があります。 

> [!IMPORTANT]
>  IIS7 を 32 ビット モードに設定する必要はありません。  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a>64 ビット モードの IIS のインストールを 32 ビット モードに設定するには  

1.  コマンド プロンプトを開き、実行、 **adsutil**コマンド。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、し、入力**cmd**します。  

2.  コマンド プロンプトで、次の入力:`cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`します。  

3.  コマンド プロンプトを閉じます。  

## <a name="configuring-the-bam-portal-banner"></a>BAM ポータルのバナーを構成します。  
 同様のテキストや画像、ビジネスを表示するには、BAM ポータル ページを変更することができます。  

- BAM ポータル ページの右上隅にある Windows Server System ロゴです。  

  次の手順では、BAM ポータルの外観をカスタマイズするカスケード スタイル シート ファイル (.css ファイル) を編集します。 指定されたクラスへの変更は、変更のみがサポートされています。 可能な限り、クラスに対する変更の影響を特定した変更処理中にエラーを動作中で、BAM ポータルのままにできるようにします。  

> [!CAUTION]
>  データおよびポータルの機能は非表示に styles.css ファイルの他のクラスを変更して、ポータルを使用できないようにします。  

#### <a name="to-configure-the-banner"></a>バナーを構成するには  

1. BAM ポータルの web.config ファイルを編集します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 次の行を変更することで、メイン ページのクイック スタート コンテンツは置き換え可能な:\<追加キー ="MainPageContentUrl"value="~/MainPageContent.htm"/\>します。 変更**MainPageContent.htm**独自の HTML ファイルを指す値 フィールドにします。 HTML ファイルは、web.config ファイルと同じディレクトリにある必要があります。  

3. Web.config ファイルに次の行を追加することでテキストを識別するページの変更:\<キーを追加 ="PortalTitle"value ="New Identifying text"/\>します。 ポータルを識別するためにテキストを格納する値のフィールドを変更します。  

4. BAM ポータルの styles.css ファイルを編集します。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css、をクリック**OK**します。  

5. 右上隅のロゴを変更するには、.headerLogo div クラスを検索して、次の行を変更する: 背景イメージ: url("../images/WSS_Logo.gif");作成したイメージ ファイルを指すようにします。 .Gif 形式のイメージを使用することをお勧めします。  

6. SharePoint アイコンを変更、.headerPageIcon div クラスを次の行を変更する: 背景イメージ: url("../images/btsSuiteProduction.gif");作成したイメージ ファイルを指すようにします。  

7. ファイルを保存します。  

8. 変更を確認する BAM ポータルを開きます。  

## <a name="modifying-the-bam-portal-webconfig-file"></a>BAM ポータルの web.config ファイルを変更します。  
 BAM ポータルが Secure Sockets Layer (SSL) のエンタープライズ シングル サインオン (SSO) 証明書を使用するサーバー上にある場合は、証明書の適切な URL を受け入れるように、ポータルを構成する必要があります。  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a>サイトの SSL をサポートするために、BAM ポータルを変更するには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. SSL が有効なポータルの場所を指すファイルで次の 2 行を変更します。  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. ファイルを保存します。  

   BAM ポータルが表示され、データを受け入れるに構成されているカルチャに従って書式設定します。 構成は、web.config ファイルで指定されます。 Web ポータルでは、Internet Explorer によって送信される「Accept Language」情報を無視します。 たとえば、日本語のカルチャ設定に設定されており、米国を使用する BAM ポータルが構成されている Internet Explorer を実行していること英語はカルチャ設定です。 ここでデータ項目では、日付や整数が表示されますなどが受け入れられ、米国に該当するルールを使用して並べ替える英語のカルチャ設定ではなく、日本語のカルチャの設定に該当するルール。 日本語形式を使用して入力のカルチャに固有の情報が無効と見なされる、BAM ポータルで米国の書式設定されたデータを求めるため、英語。  

   表示の一貫性のある処理とカルチャ設定に基づいて変化するデータの書式設定を取得するには、すべての BAM ポータル クライアントに適した言語を選択します。 このカルチャ用の BAM ポータルを構成します。 Multilingual User Interface Pack をインストールして、すべてのクライアントが選択したカルチャに設定することを確認する必要があります。  

   米国以外のBAM の英語版のインストール、web.config ファイルのカルチャ パラメーターを設定するために必要な場合があります。 これが必要がある場合は次のとおりです。  

-   日付と時刻の表示形式をローカライズします。  

-   通貨の表示形式をローカライズします。  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a>ポータルのカルチャ設定を変更するには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 適切なグローバリゼーション設定を反映するように、ファイルに次の行でカルチャ属性を変更します。  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. ファイルを保存します。  

   大規模な SQL クエリの待機中にタイムアウトを発生している場合は、クエリ サービスのタイムアウト値を大きく必要があります。  

#### <a name="to-increase-the-query-service-time-out-value"></a>クエリ サービスのタイムアウト値を大きくには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。  

2. Queryservicetimeout の既定値には 45 秒です。 タイムアウト間隔を増減させるのには、次の行の値を変更します。  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. ファイルを保存します。  

   マルチ サーバー環境で時間のサーバーがオフラインの場合があります。 この場合、ポータルのユーザーには、BAM ポータルが応答を停止する時間遅延が発生可能性があります。 ユーザー エクスペリエンスを向上させるには、サーバーの再試行間隔を変更できます。 これは、BAM クエリ Web サービスを 1 回の接続が失敗した後、サーバーがオフラインである前提としています、最小時間を作成します。  

   値は、ローカル データベースがリモート データベースに接続しているときにタイムアウトした場合、データが不完全としてマークし、ローカル コンピューターは、指定した時間が経過するまで、リモート データベースに接続しませんを示します。  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a>マルチ サーバー環境で分散アクティビティの再試行間隔を長くには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。  

2. Serverretryinterval の既定値は、5 分です。 サーバーの再試行間隔を増減させるのには、次の行の値を変更します。  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. ファイルを保存します。  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a>BAM ポータルでアラート通知を構成するには、オプションが表示されます。  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 値フィールドを変更する、\<キーを追加"AlertNotificationOptions"の値を = =""/\>次の値のいずれかの通知オプションを指定するコンマ区切りのリストを含む web.config ファイルの行。 空の値は、サーバーによって返される順序でサーバー上の利用可能なすべての通知オプションを表示します。 認識されない値は、空の値と同じです。  


   |    値    |                                              説明                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | ファイル, 電子メール | ファイルと電子メールのオプションが表示されます。 ボックスの一覧で、ファイルは最初に表示され、電子メールで送信します。 |
   | 電子メール, ファイル | ファイルと電子メールのオプションが表示されます。 ボックスの一覧では、電子メールは、最初に表示され、ファイルします。 |
   |    ファイル     |                             ファイルのみの通知は、ポータルに表示されます。                             |
   |    Email    |                            電子メール通知のみがポータルに表示されます。                            |


3. ファイルを保存します。  

## <a name="distributed-server-environments"></a>分散型サーバー環境  
 BAM ポータルのインストールでは、異なるサーバーで、アラートと、BAM ポータルを配置、イベント ログに次のエラーが表示されます。"System.Reflection.TargetInvocationException:呼び出しのターゲットによって例外がスローされました。 ---> レジストリの Notification Services の指定したインスタンスのエントリが見つかりませんでした。"  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a>別のサーバーで、ポータルとアラートを構成するには  

1. コマンド プロンプトを開きます。  

2. 実行**C:\Program files \microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register bamalerts という名前のサーバー**<em>\<サーバー名\></em> を置き換えます *\<サーバー名\>* サーバーの名前に置き換えます。  

3. F5 キーを押して、ブラウザーを更新します。  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a>Kerberos ネットワーク プロトコルを使用する BAM ポータルを許可する IIS の構成  
 BAM ポータルを使用した Kerberos ネットワーク プロトコルを使用する場合は、Web ポータルの ACL セキュリティを変更する必要があります。 IIS が正しく構成されていない場合、次のエラーがユーザーに表示されます。  

 HTTP エラー 401.1 - 権限がありません。無効な資格情報により、アクセスが拒否されました。  

 IIS のセキュリティ設定を変更する方法の詳細についてにあるサポート技術情報の記事を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)します。  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a>BAM ポータルの SQL Server 2008 の展開での集計 BAM データの表示  
 デプロイ環境は、SQL Server 2008 を使用する BAM ポータルに接続するクライアント コンピューターから BAM ポータルの集計データを表示するには、クライアント コンピューターの Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider をインストールする必要があります。 Analysis services がインストールされていない場合のユーザーは、次のエラー メッセージを受信します。  

 サーバー *\<servername\>* 接続できないか、ビジー状態です。  



## <a name="see-also"></a>参照  
 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)