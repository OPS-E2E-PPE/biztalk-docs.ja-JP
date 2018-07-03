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
ms.openlocfilehash: 5f1cf1bf2cb2400d4209686e6b1d3d3b11a4461c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987339"
---
# <a name="customizing-the-bam-portal-configuration"></a>BAM ポータルの構成のカスタマイズ
BAM ポータルには、構成可能なオプションが多数あります。 次の手順では、最適なユーザー エクスペリエンスを取得する BAM ポータルを変更する方法を説明します。  

> [!NOTE]
>  権限を借用した管理者以外のユーザーとしてポータルを構成するときに、資格情報の入力を求められることなく BAM ポータルの機能にアクセスするには、ログオフしてログオンし直すことが必要になる場合があります。 たとえば、次のシナリオを考えてみます。  
>   
>  管理者以外の権限を借用したユーザーでは、Web サービスまたは BAM ポータルを構成します。 その後、Everyone グループがポータルにアクセスできないように、ポータルに対するアクセス許可を設定します。 PortalUsersGroup というローカル グループを作成して、そのグループをポータル ユーザー グループとして割り当てます。 つまり、そのグループのユーザーだけがポータルにアクセスできます。 BAM ポータルを構成した後、現在のユーザーをポータル ユーザー グループに追加します。 BAM ポータルを開くと、資格情報を求められます。 ただし、ログオフしてログオンし直すと、資格情報を求められることなく BAM ポータルを開くことができます。  
>   
>  BizTalk Server では、ローカル グループ アカウントとローカル ユーザー アカウントは、単一コンピューター構成でのみサポートされます。 また、ドメイン グループ アカウントとドメイン ユーザー アカウントは、単一および複数の両方のコンピュータ構成でサポートされます。  

## <a name="running-the-bam-portal-in-a-64-bit-environment"></a>64 ビット環境での BAM ポータルの実行  
 64 ビット環境でインターネット インフォメーション サービス (IIS) を使用する場合は、BAM ポータルを実行する 32 ビット モードに IIS を設定する必要があります。 

> [!IMPORTANT]
>  IIS 7 は 32 ビット モードに設定する必要はありません。  

#### <a name="to-set-a-64-bit-mode-iis-installation-to-32-bit-mode"></a>64 ビット モードの IIS を 32 ビット モードに設定するには  

1.  コマンド プロンプトを開き、実行、 **adsutil**コマンド。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、し、入力**cmd**します。  

2.  コマンド プロンプトで、次の入力:`cscript c:\inetpub\adminscripts\adsutil.vbs SET W3SVC/AppPools/Enable32bitAppOnWin64 1`します。  

3.  コマンド プロンプトを閉じます。  

## <a name="configuring-the-bam-portal-banner"></a>BAM ポータルのバナーを構成します。  
 BAM ポータル ページは、ユーザーのビジネスを表すテキストや画像を表示するように変更できます。  

- Windows Server System のロゴ (BAM ポータル ページの右上隅に配置されます)。  

  次の手順では、カスケード スタイル シート ファイル (.css ファイル) を編集して、BAM ポータルの外観をカスタマイズします。 指定されたクラスへの変更のみを行ってください。 クラスに変更を加えている途中でエラーが発生しても BAM ポータルが稼働し続けるように、変更による影響が最小限に留まるようになっています。  

> [!CAUTION]
>  データおよびポータルの機能は非表示に styles.css ファイルの他のクラスを変更して、ポータルを使用できないようにします。  

#### <a name="to-configure-the-banner"></a>バナーを構成するには  

1. BAM ポータルの web.config ファイルを編集します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 次の行を変更することで、メイン ページのクイック スタート コンテンツは置き換え可能な:\<追加キー ="MainPageContentUrl"value="~/MainPageContent.htm"/\>します。 変更**MainPageContent.htm**独自の HTML ファイルを指す値 フィールドにします。 HTML ファイルは、web.config ファイルと同じディレクトリに存在する必要があります。  

3. Web.config ファイルに次の行を追加することでテキストを識別するページの変更:\<キーを追加 ="PortalTitle"value ="New Identifying text"/\>します。 value フィールドを変更して、ポータルを識別するテキストを含めます。  

4. BAM ポータルの styles.css ファイルを編集します。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\Styles.css、をクリック**OK**します。  

5. 右上隅のロゴを変更します。この操作を行うには、.headerLogo div クラスを探して、background-image: url("../images/WSS_Logo.gif") という行を、作成した画像ファイルを指すように変更します。 .gif 形式の画像を使用することをお勧めします。  

6. SharePoint アイコンを変更、.headerPageIcon div クラスを次の行を変更する: 背景イメージ: url("../images/btsSuiteProduction.gif");作成したイメージ ファイルを指すようにします。  

7. ファイルを保存します。  

8. BAM ポータルを開いて、変更内容を表示します。  

## <a name="modifying-the-bam-portal-webconfig-file"></a>BAM ポータルの web.config ファイルを変更します。  
 SSL (Secure Sockets Layer) 用のエンタープライズ シングル サインオン (SSO) 証明書を使用するサーバー上に BAM ポータルが存在する場合、証明書の適切な URL を受け取るようにポータルを構成する必要があります。  

#### <a name="to-modify-the-bam-portal-to-support-ssl-sites"></a>SSL サイトをサポートするように BAM ポータルを変更するには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. SSL 対応のポータルの場所を指すように、ファイル内の次の 2 行を変更します。  

   ```  
   <add key="BamQueryWSUrl" value="http://localhost/BAM/BamQueryService/BamQueryService.asmx"/>  
   <add key="BamManagementWSUrl" value="http://localhost/BAM/BamManagementService/BamManagementService.asmx"/>  
   ```  

3. ファイルを保存します。  

   BAM ポータルでは、ポータルの構成に使用されているカルチャに従って書式設定されたデータが表示され受け取られます。 構成は、web.config ファイルで指定されています。 Web ポータルは、Internet Explorer から送信される「Accept Language」情報を無視します。 たとえば、日本語のカルチャ設定に設定されており、米国を使用する BAM ポータルが構成されている Internet Explorer を実行していること英語はカルチャ設定です。 ここでデータ項目では、日付や整数が表示されますなどが受け入れられ、米国に該当するルールを使用して並べ替える英語のカルチャ設定ではなく、日本語のカルチャの設定に該当するルール。 日本語形式を使用して入力のカルチャに固有の情報が無効と見なされる、BAM ポータルで米国の書式設定されたデータを求めるため、英語版です。  

   カルチャ設定によって変化するデータの表示および書式設定に対して一貫性のある処理を実現するには、すべての BAM ポータル クライアントに適した言語を 1 つ選択します。 このカルチャ用の BAM ポータルを構成します。 Multilingual User Interface Pack をインストールして、すべてのクライアントが、選択したカルチャに設定されるようにする必要があります。  

   米国以外のBAM の英語版のインストール、web.config ファイルのカルチャ パラメーターを設定するために必要な場合があります。 この設定が必要になるのは、次の場合です。  

-   日付と時刻の表示形式をローカライズする場合。  

-   通貨の表示形式をローカライズする場合。  

#### <a name="to-modify-the-culture-setting-of-the-portal"></a>ポータルのカルチャ設定を変更するには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 適切なグローバリゼーション設定を反映するように、ファイルに次の行でカルチャ属性を変更します。  

   ```  
   <globalization requestEncoding="utf-8" responseEncoding="utf-8" culture="de-DE" uiCulture="en" />  
   ```  

3. ファイルを保存します。  

   大量の SQL クエリの待機中にタイムアウトが発生する場合は、クエリ サービスのタイムアウト値を大きくすることが必要になることがあります。  

#### <a name="to-increase-the-query-service-time-out-value"></a>クエリ サービスのタイムアウト値を大きくには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。  

2. QueryServiceTimeout の既定値は 45 秒です。 タイムアウト間隔を増減するには、次の行の値を変更します。  

   ```  
   <add key="QueryServiceTimeout" value="45" />  
   ```  

3. ファイルを保存します。  

   マルチサーバー環境では、サーバーがオフラインの場合もあります。 この場合、BAM ポータルが応答を停止する遅延時間が生じることがあります。 ユーザー エクスペリエンスを向上させるために、サーバーの再試行間隔を変更できます。 再試行間隔を適切な値に変更すると、いったん接続に失敗しても、BAM クエリ Web サービスでサーバーがオフラインであると見なされる時間が最短になります。  

   値は、ローカル データベースがリモート データベースに接続しているときにタイムアウトした場合、データが不完全としてマークし、ローカル コンピューターは、指定した時間が経過するまで、リモート データベースに接続しませんを示します。  

#### <a name="to-increase-the-retry-interval-for-distributed-activities-in-a-multiserver-environment"></a>マルチサーバー環境で分散アクティビティの再試行間隔を大きくするには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService\web.config、をクリック**OK**します。  

2. ServerRetryInterval の既定値は 5 分です。 サーバーの再試行間隔を増加または減少するには、次の行の値を変更します。  

   ```  
   <add key="ServerRetryInterval" value="5"/>  
   ```  

3. ファイルを保存します。  

#### <a name="to-configure-how-alert-notification-options-are-presented-in-the-bam-portal"></a>BAM ポータルに警告通知オプションを表示する方法を構成するには  

1. メモ帳を使用して web.config ファイルを開きます。 をクリックして**開始**、 をクリックして**実行**、「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」と順にクリックします**OK**します。  

2. 値フィールドを変更する、\<キーを追加"AlertNotificationOptions"の値を = =""/\>次の値のいずれかの通知オプションを指定するコンマ区切りのリストを含む web.config ファイルの行。 値が空の場合は、サーバーで使用可能なすべての通知オプションがサーバーから返される順に表示されます。 値が認識されない場合は、値が空の場合と同様に処理されます。  


   |    値    |                                              説明                                               |
   |-------------|--------------------------------------------------------------------------------------------------------|
   | ファイル, 電子メール | [ファイル] オプションと [電子メール] オプションが表示されます。 ドロップダウン リストでは、最初に [ファイル]、次に [電子メール] が表示されます。 |
   | 電子メール, ファイル | [ファイル] オプションと [電子メール] オプションが表示されます。 ドロップダウン リストでは、最初に [電子メール]、次に [ファイル] が表示されます。 |
   |    ファイル     |                             ポータルに、[ファイル] 通知のみが表示されます。                             |
   |    Email    |                            ポータルに、[電子メール] 通知のみが表示されます。                            |


3. ファイルを保存します。  

## <a name="distributed-server-environments"></a>分散型サーバー環境  
 BAM ポータルのインストールでは、異なるサーバーで、アラートと、BAM ポータルを配置、する場合は、イベント ログに次のエラーが表示されます:"System.Reflection.TargetInvocationException: 呼び出しのターゲットが例外をスローしました。 ---> レジストリの Notification Services の指定したインスタンスのエントリが見つかりませんでした。"  

#### <a name="to-configure-the-portal-and-alerts-on-different-servers"></a>さまざまなサーバー上でポータルおよび警告を構成するには  

1. コマンド プロンプトを開きます。  

2. 実行**C:\Program files \microsoft SQL Server\90\Notification Services\9.0.242\Bin\nscontrol register bamalerts という名前のサーバー**<em>\<サーバー名\></em> を置き換えます*\<サーバー名\>* サーバーの名前に置き換えます。  

3. <localizedText>F5</localizedText> キーを押して、ブラウザーを更新します。  

## <a name="configuring-iis-to-allow-the-bam-portal-to-use-the-kerberos-network-protocol"></a>BAM ポータルによる Kerberos ネットワーク プロトコルの使用を許可する IIS の構成  
 BAM ポータルを使用した Kerberos ネットワーク プロトコルを使用する場合は、Web ポータルの ACL セキュリティを変更する必要があります。 IIS が正しく構成されていない場合、次のエラーが発生します。  

 HTTP エラー 401.1 - 権限がありません: 無効な資格情報により、アクセスが拒否されました。  

 IIS のセキュリティ設定を変更する方法の詳細についてにあるサポート技術情報の記事を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=57922](http://go.microsoft.com/fwlink/?LinkId=57922)します。  

## <a name="viewing-aggregate-bam-data-in-the-bam-portal-in-sql-server-2008--deployments"></a>BAM ポータルの SQL Server 2008 の展開での集計 BAM データの表示  
 デプロイ環境は、SQL Server 2008 を使用する BAM ポータルに接続するクライアント コンピューターから BAM ポータルの集計データを表示するには、クライアント コンピューターの Microsoft SQL Server 2008 Analysis Services 10.0 OLE DB Provider をインストールする必要があります。 Analysis Services がインストールされていない場合は、次のエラー メッセージが表示されます。  

 サーバー *\<servername\>* 接続できないか、ビジー状態です。  



## <a name="see-also"></a>参照  
 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)