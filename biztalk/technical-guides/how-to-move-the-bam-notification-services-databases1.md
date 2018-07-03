---
title: Services Databases1 の BAM Notification を移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 432499729e0f28092e13e222e29d2c92607ec6ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996235"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>BAM Notification Services データベースを移動する方法
この手順を使用すると、BAM Notification Services データベースを別のサーバーに移動します。  エンド ツー エンドのシナリオの観点から BAM Notification Services データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM Notification Services データベースを移動します。](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [サービス データベースを新しい BAM 通知への参照を更新しています](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  BAM Notification Services Application (BAMAlertsApplication) データベースおよび BAM Notification Services Instance (BAMAlertsNSMain) データベースをまとめて移動する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_NotiMoveDB"></a> BAM Notification Services データベースを移動します。  
 BAM Notification Services データベースを移動する次の手順で、手順に従います。  
  
#### <a name="to-move-the-bam-notification-services-database"></a>BAM Notification Services データベースを移動するには  
  
1. 停止のすべての BAM キューブ更新およびデータ保守 SSIS パッケージ、または BAM Notification Services データベースを復元するまで実行されないようにします。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[方法を開始、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(<http://go.microsoft.com/fwlink/?LinkId=154394>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3. IIS サービスを停止します。  
  
4. BAM 警告 Notification service を停止します。  
  
   1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2.  コマンド プロンプトで、次のように入力します。  
  
        **net stop NS$ BamAlerts**  
  
5. 古いサーバー上に BAM Notification Services データベースをバックアップします。 データベースのバックアップの手順についてに記載された手順に従います[方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースをバックアップする方法のオンライン ブックの「します。  
  
   > [!NOTE]  
   >  BAMAlertsApplication、BAMAlertsNSMain の両方のデータベースには、この手順を実行します。  
  
6. BAM Notification Services データベースのコピーを新しい[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7. 新しいサーバーに BAM Notification Services データベースを復元します。 以下の手順については、データベースを復元する方法」の手順に従って[方法: データベース バックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(<http://go.microsoft.com/fwlink/?LinkId=156511>) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブックの「します。  
  
   > [!NOTE]  
   >  BAMAlertsApplication、BAMAlertsNSMain の両方のデータベースには、この手順を実行します。  
  
##  <a name="BKMK_NotiUpdate"></a> サービス データベースを新しい BAM 通知への参照を更新しています  
 データベースを移動した後は、新しい BAM Notification Services データベースに対するすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
- 新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)します。  
  
- すべてのコンピューター上の通知サービスを再登録、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 参照してください[Notification Services を登録](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)します。  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a> BAM 構成を更新するには  
  
1. BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
   1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
   2. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
      - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. コマンド プロンプトで、次のように入力します。  
  
       **Bm.exe config の取得 –filename:BAMConfiguration.xml-サーバー:\<servername\> -データベース:\<データベース\>**  
  
      > [!NOTE]
      >  このコマンドを実行するときに、実際の構成情報の取得元のサーバーの名前に置き換えてください。<servername>の構成情報の取得元のデータベースの実際の名前に置き換えます<database>します。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2. BAMConfiguration.xml ファイルを編集し、変更、 **DBServer**プロパティで、`<DeploymentUnit Name="Alert">`セクションを新しいサーバー名。  
  
3. BAMConfiguration.xml ファイルを保存して閉じます。  
  
4. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
5. BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
   - 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 ビット バージョンの Windows Server にインストールされます。  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. コマンド プロンプトで、次のように入力します。  
  
    **bm.exe の更新-構成-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_NotiRegister"></a> Notification Services を登録します。  
 BAM Notification Services データベースを移動した後は、Notification Services (NSservice.exe) を実行している BizTalk Server グループ内のすべてのコンピューターで通知サービスを再登録する必要があります。 こうして初めて、Notification Services から新しい場所のデータベースに接続できるようになります。 Notification Services を登録する方法の詳細については、次の手順 5 ~ 11 [BAM Notification Services データベースへの参照を更新する方法](http://go.microsoft.com/fwlink/?LinkId=156684)(<http://go.microsoft.com/fwlink/?LinkId=156684>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 上記のリンクで説明されている手順を実行する際に、次に注意してください。  
  
-   手順 5. と 6. を前のリンクは、BAM 構成 XML に、次のプロパティで示されているサーバーで実行する必要があります。  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   手順 7 ~ 11 は、BAM ポータルをホストするコンピューターで実行する必要があります。  
  
## <a name="see-also"></a>参照  
 [データベースの移動](../technical-guides/moving-databases.md)