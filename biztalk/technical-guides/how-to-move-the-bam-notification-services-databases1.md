---
title: "BAM Notification を移動する方法はサービス Databases1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0ae3e4b5af7304eb07973fd5e19efce2e68c99
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>BAM Notification Services データベースを移動する方法
この手順を使用すると、BAM Notification Services データベースを別のサーバーに移動します。  エンド ツー エンドのシナリオの観点から BAM Notification Services データベースの移動にも 2 つの主要な手順が含まれます。  
  
-   [BAM Notification Services データベースを移動します。](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [サービスのデータベースを新しい BAM 通知への参照を更新](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  BAM Notification Services Application (BAMAlertsApplication) データベースおよび BAM Notification Services Instance (BAMAlertsNSMain) データベースを一緒に移動する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールのメンバーであるアカウントを使用してログオンする必要があります。  
  
##  <a name="BKMK_NotiMoveDB"></a>BAM Notification Services データベースを移動します。  
 BAM Notification Services データベースを移動する次の手順で、手順を実行します。  
  
#### <a name="to-move-the-bam-notification-services-database"></a>BAM Notification Services データベースを移動するには  
  
1.  すべての BAM キューブ更新およびデータ保守 SSIS パッケージを停止するか、BAM Notification Services データベースを復元が完了するまで実行されないように措置を講じます。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。 詳細については、トピックを参照してください。[開始方法、停止、一時停止、再開、または BizTalk Server サービスを再起動](http://go.microsoft.com/fwlink/?LinkId=154394)(http://go.microsoft.com/fwlink/?LinkId=154394) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
3.  IIS サービスを停止します。  
  
4.  BAM 警告 Notification service を停止します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  コマンド プロンプトで、次のように入力します。  
  
         **Net stop NS$ BamAlerts**  
  
5.  古いサーバーで、BAM Notification Services データベースをバックアップします。 データベースをバックアップする方法の手順についてに記載された手順に従います[する方法:、データベースのバックアップ (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブック、データベースをバックアップする方法です。  
  
    > [!NOTE]  
    >  BAMAlertsApplication データベースと BAMAlertsNSMain データベースのこの手順を実行します。  
  
6.  BAM Notification Services データベースに新しいコピー[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
7.  新しいサーバーで、BAM Notification Services データベースを復元します。 データベースを復元する方法について以下に記載された手順[する方法: データベースのバックアップ (SQL Server Management Studio) を復元](http://go.microsoft.com/fwlink/?LinkId=156511)(http://go.microsoft.com/fwlink/?LinkId=156511) で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースを復元する方法のオンライン ブック。  
  
    > [!NOTE]  
    >  BAMAlertsApplication データベースと BAMAlertsNSMain データベースのこの手順を実行します。  
  
##  <a name="BKMK_NotiUpdate"></a>サービスのデータベースを新しい BAM 通知への参照を更新  
 データベースを移動した後は、新しい BAM Notification Services データベースに対するすべての参照を更新する必要があります。 次の参照を更新する必要があります。  
  
-   新しいデータベースとサーバーの名前で、BAM 構成を更新します。 参照してください[BAM 構成を更新する](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)です。  
  
-   すべてのコンピューターに、通知サービスを再登録、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。 参照してください[Notification Services を登録](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)です。  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a>BAM 構成を更新するには  
  
1.  BAM を復元するときに使用する .xml ファイルのコピーを用意します。  
  
    1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
    2.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
             **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
        -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
    3.  コマンド プロンプトで、次のように入力します。  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-サーバー:\<servername\> -データベース:\<データベース\>**  
  
        > [!NOTE]  
        >  このコマンドを実行するときに、サーバーの構成情報の取得元の実際の名前に置き換える<servername>の構成情報の取得元のデータベースの実際の名前を使用して<database>です。 詳細については、BAM 管理 (BM) ユーティリティを使用して、次を参照してください。[インフラストラクチャ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
2.  BAMConfiguration.xml ファイルを編集し、変更、 **DBServer**内のプロパティ、`<DeploymentUnit Name="Alert">`セクションに新しいサーバーの名前。  
  
3.  BAMConfiguration.xml ファイルを保存して閉じます。  
  
4.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
5.  BizTalk Server を実行するコンピューター上には、次のフォルダーを参照してください。  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 64 ビット バージョンの Windows Server にインストールされています。  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010 \tracking**  
  
    -   場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が 32 ビット バージョンの Windows Server にインストールされています。  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010 \tracking**  
  
6.  コマンド プロンプトで、次のように入力します。  
  
     **bm.exe 更新-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_NotiRegister"></a>Notification Services を登録します。  
 BAM Notification Services データベースを移動した後は、Notification Services (NSservice.exe) を実行している BizTalk Server グループ内のすべてのコンピューターで、通知サービスを再登録する必要があります。 こうして初めて、Notification Services から新しい場所のデータベースに接続できるようになります。 Notification Services を登録する方法の手順については、手順 5. ~ 11. を[BAM Notification Services データベースへの参照を更新する方法](http://go.microsoft.com/fwlink/?LinkId=156684)(http://go.microsoft.com/fwlink/?LinkId=156684) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
 上記のリンクに記載の手順を実行中に、次に注意してください。  
  
-   手順 5. と 6. 先行リンクには、BAM 構成 XML に、次のプロパティで示されているサーバーで実行する必要があります。  
  
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