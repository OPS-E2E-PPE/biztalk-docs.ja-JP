---
title: NLB クラスターで機能する BAM ポータルを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0273433cf06fd0c455d6ed5a0be05198a149b4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386173"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a>NLB クラスターで機能する BAM ポータルを構成する方法
ネットワーク負荷分散 (NLB) クラスターで機能する BAM ポータルを構成できます。  
  
> [!IMPORTANT]
>  BAM ポータル*のみ*は 32 ビット モードで実行されます。 64 ビット コンピューターで IIS がインストールされている場合、ASP.NET 2.0 が 32 ビット モードで有効になっているを確認します。 これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
>   
>  BAM ポータルの追加の要件を参照してください。 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)します。  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a>NLB クラスターで BAM ポータルを構成する準備を行う  
  
1.  インストールし、最初のコンピューターで、ポータルを構成します。  
  
    > [!NOTE]
    >  最初のコンピューターでポータルを構成するだけです。 クラスター内の他のコンピューターで BAM ポータルを有効にするオプションがありますが、構成は、最初のコンピューターでのみ行われます。  
  
2.  NLB クラスターに含まれるすべてのコンピューターにポータル コンポーネントをインストールし、ポータルが構成されているコンピューターの BizTalk グループにクラスター内の他のコンピューターを参加します。 BizTalk グループを有効にし、適切なグループに参加する必要があります。  
  
3.  ポータルがインストールされているコンピューター用に構成された BizTalk 管理データベースを選択します。  
  
4.  NLB クラスターを作成します。 作成して、ネットワーク負荷分散クラスターを管理する方法の詳細についてを参照してください「を作成および管理ネットワーク負荷分散クラスターの」 [ http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206)します。  
  
    > [!NOTE]
    >  NLB クラスターが正しく動作する BizTalk Server のコンテキスト外で続行する前に確認してください。  
  
    > [!NOTE]
    >  ハードウェア ベースの NLB を設定するには、ハードウェア プロバイダーのドキュメントを参照してください。  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a>クラスターの場所を反映するように BAM 構成を更新するには  
  
1. 現在の BAM 構成を取得するのにには、BAM 管理ユーティリティを使用します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]の config の取得 \bm--filename:myconfig.xml します。  
  
2. ローカル ホスト名を NLB クラスターの名前に置き換えます。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml します。  
  
3. ハードウェア ベースの NLB のみの場合は、構成ファイルは、次を確認します。  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  ハードウェア ベースの NLB で BAM 構成を更新するときに、手順 4. と 5. は必要ありません。  
  
4. コンピューター名 (machinename) をクラスター名に置き換えることにより、NLB クラスターを指す次の行を変更します。  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. 新しい構成を保存します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\bm 更新-config--filename:myconfig.xml。  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a>NLB サーバー名を指すように BAMmanagementService および QueryService の Url を変更する BAM ポータルの web.config ファイルを編集します。 注:この手順は、ハードウェア ベースの NLB の必要はありません。  
  
1. クリックしてメモ帳を使用して web.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とをクリックして **[ok]**。  
  
2. 次のコンピューター名 (machinename) と、クラスターの名前の名前を指す次の 2 行でポートの名前を変更します。  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. ファイルを保存します。 これを行うには、次のようにクリックします。**ファイル**、 をクリックし、**保存**メモ帳のメニュー バー。  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a>クラスターで追加した各コンピューターを構成するには  
  
1. Web.config ファイルのコピー [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal フォルダー、クラスターに追加した各コンピューターにします。  
  
   > [!NOTE]
   >  次の手順をすべての参照を**Program Files**フォルダーになります**Program Files (x86)** 64 ビット コンピューター用です。  
   > 
   > [!IMPORTANT]
   >  次の手順では、仮想ディレクトリを作成するときは、最初のコンピューターで BizTalk Server 構成で作成された 3 つの BAM 仮想ディレクトリとして正確な設定があるかどうかを確認することを確認します。 ファイルのパス、ASP.NET のバージョン、ディレクトリのアクセス許可、およびアプリケーション プールを確認します。  最初のコンピューターを設定するときに使用したのを設定しているコンピューターで BAMAppPool を実行するのにには、同じドメインのサービス アカウントを使用します。 BAMAppPool がすべてのコンピューターで実行されていることを確認します。 これは、2 つの web.config ファイルをコピーする必要があります。  
   > 
   >  Web.config ファイルに加えて[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal、web.config ファイルをコピーする必要があります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \bammanagementservice と[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \bamqueryservice の同じフォルダーにこのコンピューターにします。  
  
2. ハードウェア ベースの nlb のみの場合は、次のコンピューター名 (machinename) と、クラスターの名前の名前を指す次の 2 行でポートの名前を変更します。  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. BAMAppPool というアプリケーション プールを作成します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。  
  
4. BAM という既定の web サイトの下の仮想ディレクトリを作成します。  
  
5. BAM 仮想ディレクトリのアプリケーション プールを BAMAppPool に変更します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスには、InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService と %InstallationFolder%/BamPortal/BAMQueryService を指定します。  
  
6. BAM の下に BAMManagementService という仮想ディレクトリを作成します。  
  
7. BAMManagementService のアプリケーション プールを BAMAppPool に変更します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。  
  
8. BAM の下に BAMQueryService という仮想ディレクトリを作成します。  
  
9. BAMQueryService のアプリケーション プールを BAMAppPool に変更します。  
  
10. .NET Framework 4 アプリケーションのバージョンを設定するのにには、BAM、BAMMANAGEMENTSERVICE、および BAMQUERYSERVICE のバージョンを変更するのに仮想ディレクトリ プロパティの ASP NET タブ上にある INETMGR を使用します。  
  
11. Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.  アカウントを指定、BAM 管理 Web サービスのユーザー アカウントを次に示します。  
  
    > [!CAUTION]
    >  BAM ポータル*のみ*は 32 ビット モードで実行されます。 64 ビット コンピューターで IIS がインストールされている場合は、32 ビット モードで ASP.NET 2.0 を有効にする必要があります。 これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
    >   
    >  [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)追加の要件を一覧表示されます。  
  
12. 読み取りを設定 SubInACL、管理者はファイル、レジストリ キー、およびサービスに関するセキュリティ情報を取得し、ローカル コンピューターからユーザーに、この情報を転送できるようにするコマンド ライン ツールを実行して、WebServices の AppPool ユーザー用の Acl またはグローバル グループとグループ、ドメインにドメインからです。  
  
13. ダウンロードから SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990)します。  
  
14. コマンド プロンプトを開きます。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。  
  
15. コマンド プロンプトで、次の入力: subinacl.exe/subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""付与/ネットワーク サービスの = = R"  
  
    > [!NOTE]
    >  このコマンドでは、SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity のレジストリ キーに BAM アプリケーション プール ユーザーの読み取りアクセスを許可します。 アプリケーション プールの IIS によって使用される既定値であるために、ネットワーク サービスを使用します。 既定の IIS 設定を使用しない場合は、配置で使用するアプリケーション プール ユーザーを置き換える必要があります。  
  
16. コマンド プロンプトで、次の入力: subinacl.exe/keyreg「hkey_local_machine \software\microsoft\biztalk server \3.0」"付与/=\<BAM web サービス アカウント\>"  
  
    > [!NOTE]
    >  このコマンドでは、SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity のレジストリ キーに、BAM 管理 Web サービスのユーザー アカウントの読み取りアクセスを許可します。  
  
17. BAMManagement Web サービス アプリケーション プールを実行する id に ASPNET_SETREG キーに読み取りアクセスがあることを確認します。  
  
18. コンピューターの管理の管理者ツールを使用すると、IIS ワーカー プロセス グループ (IIS_WPG) および SharePoint services グループ (STS_WPG) に BAM 管理 Web サービスのユーザーと BAM アプリケーション プールのユーザー アカウントを追加できます。  
  
19. アプリケーション プールと Web サービスのユーザーの一時 ASP.NET フォルダーに対するアクセス許可を設定します。 c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ バージョン 2.0。\<最小のバージョン番号\>\Temporary ASP.NET Files"/T/E/G \<BAM web サービス アカウント\>: F  
  
    > [!NOTE]
    >  BAM 管理 Web サービスのユーザー アカウントと BAM アプリケーション プール ユーザー アカウントの両方へのアクセスを付与します。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの管理](../core/managing-the-bam-portal.md)