---
title: BizTalk 追跡データベースからデータを手動で削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffb7b0eb838295e4abdc059a1437b6cf338d0a99
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993083"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースから手動でデータを削除する方法
SQL Server エージェント ジョブである DTA Archive and Purge では、データベースの連続的な削除および格納された追跡データの圧縮により、BizTalk 追跡 (BizTalkDTADb) データベースから手動でデータを削除する必要性が低減されます。 BizTalk 追跡 (BizTalkDTADb) データベースのサイズが、パフォーマンスが低下するほど大幅に大きくなり、DTA Archive and Purge ジョブがデータベース サイズの増大に対応できなくなった場合には、手動でデータを削除することが必要になる場合があります。  
  
> [!CAUTION]
>  ここで示す手順を実行すると、完了時刻に関係なく、完了したインスタンスのすべての追跡データが BizTalk 追跡 (BizTalkDTADb) データベースから削除されます。 この手順を実行する前に、BizTalk 追跡 (BizTalkDTADb) データベースを、他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースとは別にアーカイブする必要があります。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを手動で削除するには  
  
1. BizTalk Server データベースをバックアップします。  
  
2. BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブします。  
  
3. サービス コンソールを開きます。 クリックして**開始**、 をクリックして**実行**、し、入力**services.msc**します。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、クリックして**続行**します。  
  
4. サービス コンソールが表示されたら、次の各サービスを検索して停止します。 サービスを停止するには、サービス行を右クリックして、**サービス**ペイン、およびクリック**停止**します。  
  
   -   ときに BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
   -   エンタープライズ シングル サインオン サービス  
  
        場合、ときに BizTalkServiceBizTalkGroup: BizTalkServerApplication サービスが実行されている、エンタープライズ シングル サインオン サービスをシャット ダウンしようとすると、**その他のサービスの停止**ダイアログが表示されます。 **[はい]** をクリックします。  
  
   -   ルール エンジン更新サービス  
  
5. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。  
  
6. **BizTalk Server 管理コンソール**ウィンドウの左側にある エクスプ ローラー ペインで、ダブルクリック**BizTalk グループ**を下の一覧を展開するをダブルクリックし、**プラットフォーム設定**、 をクリックし、**ホスト インスタンス**します。 これは、ホスト インスタンスの一覧が表示されます (、**ホスト インスタンス**ウィンドウ) に関連するプロパティは、画面の右側にあるとします。  
  
7. **ホスト インスタンス**ウィンドウが各実行中のホスト インスタンスを右クリックし、をクリックし、**停止**します。  
  
8. をクリックして**開始**に移動して、**実行**、型**cmd**、順にクリックします**OK**。  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **net stop iisadmin/y**  
  
     これで、IIS Admin Service とこのサービスが依存しているすべてのサービスが 1 つずつ停止され、データの削除中に新しいデータが BizTalkDTADb に書き込まれるのを防止できます。 各サービスが停止されるたびに、サービスの一覧を書き留めておいてください。 このサービスの一覧は、後で IIS を再起動するときに必要になります。  
  
     このコマンドを発行した後に表示される出力の例を次に示します (コンピューターに表示される依存サービスは異なる場合があります)。  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリックします**SQL Server Management Studio**します。  
  
11. **サーバーへの接続**ダイアログ ボックスで、SQL Server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL Server に接続します。  
  
12. **Microsoft SQL Server Management Studio**、ダブルクリック**データベース**、ダブルクリック、 **BizTalkDTADb**データベースをダブルクリックします**プログラミング**、 をクリックし、 **Stored Procedures**します。  
  
13. **オブジェクト エクスプ ローラーの詳細**ウィンドウで、右クリックして **[dtasp_purgeallcompletedtrackingdata]**、順にクリックします**ストアド プロシージャの実行**します。  
  
14. **プロシージャの実行**ダイアログ ボックスで、をクリックして**OK**します。  
  
     このストアド プロシージャにより、完了時刻に関係なく、完了したインスタンスに関連付けられたすべての追跡データが削除されます。  
  
15. [サービス] を開きます。 クリックして**開始**、 をクリックして**実行**、し、入力**services.msc**します。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。  
  
16. 次のサービスのそれぞれを右クリックし をクリックし、**開始**:  
  
    -   ときに BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   エンタープライズ シングル サインオン サービス  
  
    -   ルール エンジン更新サービス  
  
17. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
18. **BizTalk Server 管理コンソール**をダブルクリック、 **BizTalk グループ**、ダブルクリックして**プラットフォームの設定**、順にクリックします**ホストインスタンス**します。  
  
19. **オブジェクト エクスプ ローラーの詳細**ウィンドウが各停止しているホスト インスタンスを右クリックし、クリックして**開始**します。  
  
20. 上記の手順 8. の説明に従って、コマンド プロンプトを起動します。  
  
21. コマンド プロンプトでは、手順 4. で、各 IIS サービスを停止するを再起動します。 型:  
  
     **net start**  *\<IISserviceName\>*  
  
     場所*\<IISserviceName\>* 再起動する IIS サービスの名前を指定します。 各 IIS サービスに対してこのコマンドを繰り返し実行する必要があります。  
  
## <a name="see-also"></a>参照  
 [アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)