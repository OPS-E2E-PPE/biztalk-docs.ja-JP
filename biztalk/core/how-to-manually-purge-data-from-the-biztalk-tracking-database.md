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
ms.openlocfilehash: e4e4366edf0187ee74391ea144b67878fb51999a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336685"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを手動で削除する方法
DTA Archive and Purge SQL Server エージェント ジョブには、格納された追跡データの圧縮、データベースの連続的な削除のための BizTalk 追跡 (BizTalkDTADb) データベースからデータを手動で削除する必要があます。 BizTalk 追跡 (BizTalkDTADb) データベースには、その程度のパフォーマンスが低下が大きくなった場合にデータが発生している削除と、DTA Archive は手動でする必要があり、Purge ジョブで、データベースの成長続けることができます。  
  
> [!CAUTION]
>  この手順を実行すると、完成したインスタンスのすべての追跡データが完了時間に関係なく、BizTalk 追跡 (BizTalkDTADb) データベースから削除します。 この手順を実行する前に、他の個別に BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、SQL Server sysadmin 固定サーバーの役割のメンバーであるアカウントを使用してログオンする必要があります。  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>BizTalk 追跡データベースからデータを手動で削除するには  
  
1. BizTalk Server データベースをバックアップします。  
  
2. BizTalk 追跡 (BizTalkDTADb) データベースをアーカイブします。  
  
3. サービス コンソールを開きます。 をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、クリックして**続行**します。  
  
4. サービス コンソールが表示されたらを検索して、次のサービスそれぞれを停止します。 サービスを停止するには、サービス行を右クリックして、**サービス**ペイン、およびクリック**停止**します。  
  
   -   ときに BizTalkServiceBizTalkGroup:BizTalkServerApplication  
  
   -   エンタープライズ シングル サインオン サービス  
  
        場合、ときに BizTalkServiceBizTalkGroup:[Biztalkserverapplication] サービスが実行されている、エンタープライズ シングル サインオン サービスをシャット ダウンしようとすると、**その他のサービスの停止**ダイアログが表示されます。 **[はい]** をクリックします。  
  
   -   ルール エンジン更新サービス  
  
5. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。  
  
6. **BizTalk Server 管理コンソール**ウィンドウの左側にある エクスプ ローラー ペインで、ダブルクリック**BizTalk グループ**を下の一覧を展開するをダブルクリックし、**プラットフォーム設定**、 をクリックし、**ホスト インスタンス**します。 これは、ホスト インスタンスの一覧が表示されます (、**ホスト インスタンス**ウィンドウ) に関連するプロパティは、画面の右側にあるとします。  
  
7. **ホスト インスタンス**ウィンドウが各実行中のホスト インスタンスを右クリックし、をクリックし、**停止**します。  
  
8. をクリックして**開始**に移動して、**実行**、型**cmd**、順にクリックします**OK**。  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **net stop iisadmin/y**  
  
     これにより、IIS 管理サービスと、すべての依存サービスを 1 つずつ停止し、新しいデータがデータが削除されるときに、BizTalkDTADb に書き込まれることを防ぎます。 各 1 つが停止しているように、サービスの一覧を書き留めます。 IIS を再起動するときに、この後でサービスの一覧を使用する必要があります。  
  
     (コンピューターに表示される依存サービスが異なる場合があります)、このコマンドを発行後に表示される出力の例を次に示します。  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008 SP2**、順にクリックします**SQL Server Management Studio**します。  
  
11. **サーバーへの接続**ダイアログ ボックスで、SQL Server が BizTalk 追跡 (BizTalkDTADb) データベースが存在し、適切な認証の種類の名前を指定し、順にクリックします**Connect**に適切な SQL Server に接続します。  
  
12. **Microsoft SQL Server Management Studio**、ダブルクリック**データベース**、ダブルクリック、 **BizTalkDTADb**データベースをダブルクリックします**プログラミング**、 をクリックし、 **Stored Procedures**します。  
  
13. **オブジェクト エクスプ ローラーの詳細**ウィンドウで、右クリックして **[dtasp_purgeallcompletedtrackingdata]** 、順にクリックします**ストアド プロシージャの実行**します。  
  
14. **プロシージャの実行**ダイアログ ボックスで、をクリックして**OK**します。  
  
     このストアド プロシージャは、完了時刻に関係なく完了したインスタンスに関連付けられているすべての追跡データを削除します。  
  
15. [サービス] を開きます。 をクリックして**開始**、 をクリックして**実行**、し、入力**services.msc**です。 場合、**ユーザー アカウント制御**ダイアログが表示されたら、示されているアクションが、クリックしてであることを確認**続行**します。  
  
16. 次のサービスのそれぞれを右クリックし をクリックし、**開始**:  
  
    -   ときに BizTalkServiceBizTalkGroup:BizTalkServerApplication  
  
    -   エンタープライズ シングル サインオン サービス  
  
    -   ルール エンジン更新サービス  
  
17. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
18. **BizTalk Server 管理コンソール**をダブルクリック、 **BizTalk グループ**、ダブルクリックして**プラットフォームの設定**、順にクリックします**ホストインスタンス**します。  
  
19. **オブジェクト エクスプ ローラーの詳細**ウィンドウが各停止しているホスト インスタンスを右クリックし、クリックして**開始**します。  
  
20. 上記の手順 8. の説明に従って、コマンド プロンプトを起動します。  
  
21. コマンド プロンプトでは、手順 4. で、各 IIS サービスを停止するを再起動します。 型:  
  
     **net start**  *\<IISserviceName\>*  
  
     場所 *\<IISserviceName\>* 再起動する IIS サービスの名前を指定します。 各 IIS サービスは、このコマンドを繰り返す必要があります。  
  
## <a name="see-also"></a>参照  
 [アーカイブおよび BizTalk 追跡データベースの削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [開始、停止、一時停止、再開、または BizTalk Server サービスを再起動する方法](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)