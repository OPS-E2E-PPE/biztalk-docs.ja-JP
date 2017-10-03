---
title: "BizTalk 追跡データベースからデータを手動で削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cc2fa6a7e4f6318818534f6b3f99323f1d8ddf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースから手動でデータを削除する方法
SQL Server エージェント ジョブである DTA Archive and Purge では、データベースの連続的な削除および格納された追跡データの圧縮により、BizTalk 追跡 (BizTalkDTADb) データベースから手動でデータを削除する必要性が低減されます。 BizTalk 追跡 (BizTalkDTADb) データベースのサイズが、パフォーマンスが低下するほど大幅に大きくなり、DTA Archive and Purge ジョブがデータベース サイズの増大に対応できなくなった場合には、手動でデータを削除することが必要になる場合があります。  
  
> [!CAUTION]
>  ここで示す手順を実行すると、完了時刻に関係なく、完了したインスタンスのすべての追跡データが BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。 この手順を実行する前に、BizTalk 追跡 (BizTalkDTADb) データベースを、他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとは別にアーカイブする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを手動で削除するには  
  
1.  BizTalk Server データベースをバックアップします。  
  
2.  BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブします。  
  
3.  サービス コンソールを開きます。 をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、をクリックして**続行**です。  
  
4.  サービス コンソールが表示されたら、次の各サービスを検索して停止します。 サービスを停止するには、サービス行を右クリックし、 **Services**  ウィンドウで、クリックして**停止**です。  
  
    -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   エンタープライズ シングル サインオン サービス  
  
         場合 BizTalkServiceBizTalkGroup: BizTalkServerApplication サービスが実行されている、エンタープライズ シングル サインオン サービスをシャット ダウンしようとすると、**その他のサービスの停止**ダイアログが表示されます。 **[はい]**をクリックします。  
  
    -   ルール エンジン更新サービス  
  
5.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。 場合、**ユーザー アカウント制御**ダイアログが表示されます、示されているアクションが、をクリックしてであることを確認**続行**です。  
  
6.  **BizTalk Server 管理コンソール**ウィンドウの左側にある [エクスプ ローラー] ペインで、ダブルクリック**BizTalk グループ**を下の一覧を展開するをダブルクリックし、**プラットフォーム設定**、クリックして**ホスト インスタンス**です。 これは、ホスト インスタンスの一覧が表示されます (、**ホスト インスタンス**ペイン) に関連するプロパティは、画面の右側にあるとします。  
  
7.  **ホスト インスタンス** ウィンドウでは、各実行中のホスト インスタンスを右クリックし、をクリックして**停止**です。  
  
8.  をクリックして**開始**には、**実行**、型**cmd**、順にクリック**[ok]**です。  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **net stop iisadmin/y**  
  
     これで、IIS Admin Service とこのサービスが依存しているすべてのサービスが 1 つずつ停止され、データの削除中に新しいデータが BizTalkDTADb に書き込まれるのを防止できます。 各サービスが停止されるたびに、サービスの一覧を書き留めておいてください。 このサービスの一覧は、後で IIS を再起動するときに必要になります。  
  
     このコマンドを発行した後に表示される出力の例を次に示します (コンピューターに表示される依存サービスは異なる場合があります)。  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリック**SQL Server Management Studio**です。  
  
11. **サーバーへの接続**ダイアログ ボックスでは、BizTalk 追跡 (BizTalkDTADb) データベースが存在する SQL Server および適切な認証の種類の名前を指定し、をクリックして**接続**に適切な SQL Server に接続します。  
  
12. **Microsoft SQL Server Management Studio**をダブルクリックして**データベース**をダブルクリックして、 **BizTalkDTADb**データベースをダブルクリックして**プログラミング**、クリックして**Stored Procedures**です。  
  
13. **オブジェクト エクスプ ローラーの詳細** ウィンドウを右クリックして**dtasp_purgeallcompletedtrackingdata**、クリックして**ストアド プロシージャの実行**です。  
  
14. **プロシージャの実行**ダイアログ ボックスで、をクリックして**OK**です。  
  
     このストアド プロシージャにより、完了時刻に関係なく、完了したインスタンスに関連付けられたすべての追跡データが削除されます。  
  
15. [サービス] を開きます。 をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。 場合、**ユーザー アカウント制御**ダイアログが表示されます、示されているアクションが、をクリックしてであることを確認**続行**です。  
  
16. 次のサービスのそれぞれを右クリックし、をクリックして**開始**:  
  
    -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   エンタープライズ シングル サインオン サービス  
  
    -   ルール エンジン更新サービス  
  
17. をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
18. **BizTalk Server 管理コンソール**をダブルクリックして、 **BizTalk グループ**をダブルクリックして**プラットフォームの設定**、クリックして**ホストインスタンス**です。  
  
19. **オブジェクト エクスプ ローラーの詳細** ウィンドウでは、停止しているホスト インスタンスごとを右クリックし、をクリックして**開始**です。  
  
20. 上記の手順 8. の説明に従って、コマンド プロンプトを起動します。  
  
21. コマンド プロンプトでは、手順 4. で、各 IIS サービスを停止するを再起動します。 型:  
  
     **net start**  *\<IISserviceName >*  
  
     ここで *\<IISserviceName >*を再起動する IIS サービスの名前を指定します。 各 IIS サービスに対してこのコマンドを繰り返し実行する必要があります。  
  
## <a name="see-also"></a>参照  
 [アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [開始、停止、一時停止、再開、または BizTalk Server サービスを再開する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)