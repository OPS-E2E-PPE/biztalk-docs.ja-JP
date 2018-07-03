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
ms.openlocfilehash: adc423fc74cd504f79a1106d196868df20faf974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994467"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a>NLB クラスターで機能する BAM ポータルを構成する方法
BAM ポータルは、ネットワーク負荷分散 (NLB) クラスターで機能するように構成できます。  
  
> [!IMPORTANT]
>  BAM ポータル*のみ*は 32 ビット モードで実行されます。 IIS を 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビット モードで有効になっていることを確認します。 これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
>   
>  BAM ポータルの追加の要件を参照してください。 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)します。  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a>NLB クラスターで BAM ポータルを構成できるよう準備するには  
  
1.  1 台目のコンピューターにポータルをインストールして構成します。  
  
    > [!NOTE]
    >  ポータルの構成は 1 台目のコンピューターでのみ行います。 クラスター内の他のコンピューターで BAM ポータルを有効にすることもできますが、構成は 1 台目のコンピューターでのみ行います。  
  
2.  NLB クラスターに含めるすべてのコンピューターにポータル コンポーネントをインストールし、ポータルを構成したコンピューターの BizTalk グループにクラスター内の他のコンピューターを参加させます。 BizTalk グループを有効にして、適切なグループに参加させる必要があります。  
  
3.  ポータルをインストールしたコンピューター用に構成した BizTalk 管理データベースを選択します。  
  
4.  NLB クラスターを作成します。 作成して、ネットワーク負荷分散クラスターを管理する方法の詳細についてを参照してください「を作成および管理ネットワーク負荷分散クラスターの」 [ http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206)します。  
  
    > [!NOTE]
    >  続行する前に、NLB クラスターが BizTalk Server のコンテキスト外で正しく動作するかどうかを確認してください。  
  
    > [!NOTE]
    >  ハードウェア ベースの NLB をセットアップするには、ハードウェア プロバイダーのドキュメントを参照してください。  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a>BAM 構成を更新してクラスターの場所を反映するには  
  
1. BAM 管理ユーティリティを使用して現在の BAM 構成を取得します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]の config の取得 \bm--filename:myconfig.xml します。  
  
2. ローカル ホスト名を NLB クラスターの名前と置き換えます。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml します。  
  
3. ハードウェア ベースの NLB の場合のみ、構成ファイルに次の記述があることを確認します。  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  ハードウェアベースの NLB で BAM 構成を更新する場合、手順 4. と 5. は必要ありません。  
  
4. 次の行で、コンピューター名 (machinename) をクラスター名と置き換えて、NLB クラスターを指すように変更します。  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. 新しい構成を保存します。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\bm 更新-config--filename:myconfig.xml。  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a>BAM ポータルの web.config ファイルを編集して NLB サーバー名を指すように BAMmanagementService および QueryService の URL を変更するには 注: この手順はハードウェア ベースの NLB の必要はありません。  
  
1. クリックしてメモ帳を使用して web.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とをクリックして **[ok]**。  
  
2. 次の 2 行で、コンピューター名 (machinename) とポート名を、クラスター名を指すように変更します。  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. ファイルを保存します。 これを行うには、次のようにクリックします。**ファイル**、 をクリックし、**保存**メモ帳のメニュー バー。  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a>クラスターに追加した各コンピューターを構成するには  
  
1. web.config ファイルを、クラスターに追加した各コンピューターの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal フォルダーにコピーします。  
  
   > [!NOTE]
   >  次の手順をすべての参照を**Program Files**フォルダーになります**Program Files (x86)** 64 ビット コンピューター用です。  
   > 
   > [!IMPORTANT]
   >  仮想ディレクトリを作成するときには、その設定が 1 台目のコンピューターの BizTalk Server 構成で作成した 3 つの BAM 仮想ディレクトリの設定と正確に同じかどうかを確認してください。これにはまず、 ファイル パス、ASP.NET のバージョン、ディレクトリのアクセス許可、およびアプリケーション プールを確認します。  次に、1 台目のコンピューターの設定で使用したドメイン サービス アカウントと同じアカウントを使用して、設定するコンピューターで BAMAppPool を実行します。 BAMAppPool がすべてのコンピューターで稼働することを確認します。 コピーする必要がある web.config ファイルは 2 つです。  
   > 
   >  web.config ファイルの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal に加え、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService と [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService の web.config ファイルをこのコンピューターの同じフォルダーにコピーする必要があります。  
  
2. ハードウェア ベースの NLB の場合のみ、次の 2 行で、コンピューター名 (machinename) とポート名を、クラスター名を指すように変更します。  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. BAMAppPool というアプリケーション プールを作成します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。  
  
4. BAM という既定の Web サイトの下に、仮想ディレクトリを作成します。  
  
5. BAM 仮想ディレクトリのアプリケーション プールを BAMAppPool に変更します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスは、%InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService、および %InstallationFolder%/BamPortal/BAMQueryService とする必要があります。  
  
6. BAM の下に BAMManagementService という仮想ディレクトリを作成します。  
  
7. BAMManagementService のアプリケーション プールを BAMAppPool に変更します。  
  
   > [!NOTE]
   >  仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。  
  
8. BAM の下に BAMQueryService という仮想ディレクトリを作成します。  
  
9. BAMQueryService のアプリケーション プールを BAMAppPool に変更します。  
  
10. .NET Framework 4 アプリケーションのバージョンを設定するのにには、BAM、BAMMANAGEMENTSERVICE、および BAMQUERYSERVICE のバージョンを変更するのに仮想ディレクトリ プロパティの ASP NET タブ上にある INETMGR を使用します。  
  
11. 「aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password」を実行します。  ここで指定するアカウントは、BAM 管理 Web サービス ユーザー アカウントです。  
  
    > [!CAUTION]
    >  BAM ポータル*のみ*は 32 ビット モードで実行されます。 IIS を 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビット モードで有効になっている必要があります。 これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。  
    >   
    >  [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)追加の要件を一覧表示されます。  
  
12. SubInACL を実行して、WebServices の AppPool ユーザーに対して読み取り ACL を設定します。コマンド ライン ツールである SubInACL を使用すると、管理者は、ファイル、レジストリ キー、およびサービスに関するセキュリティ情報を入手し、この情報をユーザー間、ローカル グループまたはグローバル グループ間、およびドメイン間で転送できます。  
  
13. ダウンロードから SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990)します。  
  
14. コマンド プロンプトを開きます。 これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。  
  
15. コマンド プロンプトで、次の入力: subinacl.exe/subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""付与/ネットワーク サービスの = = R"  
  
    > [!NOTE]
    >  このコマンドでは、SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity のレジストリ キーに BAM アプリケーション プール ユーザーの読み取りアクセスを許可します。 例では Network Service を使用しています。アプリケーション プール用 IIS では Network Service が既定として使用されます。 既定の IIS 設定を使用しない場合は、展開で使用するアプリケーション プール ユーザーを代わりに指定してください。  
  
16. コマンド プロンプトで、次の入力: subinacl.exe/keyreg「hkey_local_machine \software\microsoft\biztalk server \3.0」"付与/=\<BAM web サービス アカウント\>"  
  
    > [!NOTE]
    >  このコマンドの目的は、BAM 管理 Web サービス ユーザー アカウントに SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity レジストリ キーへの読み取りアクセスを与えることです。  
  
17. BAMManagement Web サービスが実行されるアプリケーション プールで ASPNET_SETREG キーにアクセスできることを確認します。  
  
18. コンピューターの管理ツールを使用して、IIS ワーカー プロセス グループ (IIS_WPG) および SharePoint Services グループ (STS_WPG) に、BAM 管理 Web サービス ユーザー アカウントと BAM アプリケーション プール ユーザー アカウントを追加します。  
  
19. アプリケーション プールと Web サービスのユーザーの一時 ASP.NET フォルダーに対するアクセス許可を設定します。 c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ バージョン 2.0。\<最小のバージョン番号\>\Temporary ASP.NET Files"/T/E/G \<BAM web サービス アカウント\>: F  
  
    > [!NOTE]
    >  BAM 管理 Web サービス ユーザー アカウントと BAM アプリケーション プール ユーザー アカウントの両方にアクセス権限を与えてください。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの管理](../core/managing-the-bam-portal.md)