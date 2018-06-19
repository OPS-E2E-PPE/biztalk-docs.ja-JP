---
title: Services データベース、BAM 通知への参照を更新する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c27f1ecaf07c3f953372a9e5733d62c8376a288f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973004"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a>BAM Notification Services データベースの参照を更新する方法
送信先システムへのビジネス アクティビティの監視 (BAM) 通知サービス データベースを復元するために必要な手順が完了したら、Notification Services (NSservice.exe) を実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループのすべてのコンピューターに Notification Services を再登録する必要があります。 こうして初めて、Notification Services から新しい場所のデータベースに接続できるようになります。  
  
 Notification Services のインスタンスを再登録すると、NS$instance_name サービスが作成されるほか、ローカル サーバーにパフォーマンス カウンターが作成され、レジストリに情報が追加されます。 インスタンスの登録が必要となるサーバーは次のとおりです。  
  
-   NS$instance_name サービスを実行するすべてのサーバー: このサービスは、イベント プロバイダー ホスト、ジェネレーター、およびディストリビューター コンポーネントを実行します。 スケールアウト構成の場合、このサービスは複数のサーバー上で実行されます。  
  
-   サブスクリプション管理アプリケーションを実行するすべてのサーバー: サブスクリプション管理アプリケーションが専用のサーバーで実行されている場合、インスタンスの登録時に NS$instance_name サービスは作成しないでください。  
  
-   独立したイベント プロバイダーを実行するすべてのサーバー : 独立したイベント プロバイダーが専用のサーバーまたはデータベース サーバーで実行されている場合、インスタンスの登録時に NS$instance_name サービスは作成しないでください。  
  
 Notification Services のインスタンスもクライアント コンポーネントも実行されていないデータベース サーバーには、インスタンスを登録しないでください。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
-   BAM Notification Services データベースを復元するコンピューターに SQL Notification Services のビジネス アクティビティ監視 (BAM) 警告プロバイダーがインストールされている必要があります。  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a>BAM Notification Services データベースの参照を更新するには (SQL Server 2008 R2/SP1)  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。  
  
3.  型: **bm.exe get – filename:config.xml**  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  手順 2. で作成した xml ファイルを開き、Notification Services の再登録が必要なコンピューターを確認します。  
  
     コンピューターの名前にある、 **\<プロパティ名\=\>** 内のパラメーター、  **\<DeploymentUnit 名前 ="Alert"\>** xml ファイルのセクションの内容:  
  
    ```  
    -<DeploymentUnit Name="Alert">  
    <Property Name="GeneratorServerName" />  
    <Property Name="ProviderServerName" />  
    <Property Name="DistributorServerName" />  
      </DeploymentUnit>  
    ```  
  
5.  この xml ファイルで確認した各コンピューターで NS サービスを停止し、Notification Services のインスタンスの登録を解除します。  
  
    1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。  
  
    2.  コマンド プロンプトで次のように入力します: **net NS$ BamAlerts を停止する。**  
  
    3.  次のコマンドを入力して、インスタンスの登録を解除します。  
  
         **nscontrol unregister-name BamAlerts**  
  
         インスタンスの登録を解除すると、レジストリのエントリが削除されるほか、NS$instance_name サービスも (存在する場合は) 削除されます。さらに、このサービスに対応するパフォーマンス カウンターも削除されます。  
  
6.  次の手順で Notification Services を再登録します。  
  
    1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。  
  
    2.  コマンド プロンプトで次のように入力します: **nscontrol register-name BamAlerts-サーバー**  *\<ServerName\>***-サービス - serviceusername"** 。*\<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>***"**  
  
         これにより、Notification Services が適切なデータベースに接続できるようになります。この情報は、nscontrol により、サービス コンピューターのレジストリに格納されます。  
  
        > [!IMPORTANT]
        >  新しい Notification Services データベース サーバーを使用してください、 **-サーバー**サービスの再登録オプションを選択します。 また、新しい Notification Services サービスには、以前と同じユーザー名を使用する必要があります。  
  
7.  BAM ポータルをホストするコンピューターでをクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**の構成ツール**、クリックして**Notification Services コマンド プロンプト**です。  
  
8.  コマンド プロンプトで、次のように入力します。  
  
     **net stop NS$ BamAlerts**  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **nscontrol unregister-name BamAlerts**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **nscontrol register 名前***\<BamAlerts\>***-サーバー**  *\<NotificationServicesDatabaseServer    \>*  
  
11. コマンド プロンプトで次のように入力します。: **「net start NS$ BamAlerts**です。  
  
12. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
13. コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。  
  
14. コマンド プロンプトで、次のように入力します。  
  
     **bm.exe の更新プログラム – filename:config.xml**  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)