---
title: Services データベース、BAM 通知への参照を更新する方法 |Microsoft Docs
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
ms.openlocfilehash: 93a285b770ce7f2ab20cc8865e7804e31141336f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383637"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a>BAM Notification Services データベースの参照を更新する方法
送信先システムにビジネス アクティビティ監視 (BAM) Notification Services データベースを復元するための手順を実行した後は、すべてのコンピューター上の通知サービスを再登録する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行しているグループNotification Services (NSservice.exe)。 これにより、Notification Services の新しい場所にデータベースに接続できます。  
  
 Notification Services のインスタンスを登録すると、NS $instance_name サービスを作成します、ローカルのサーバーでパフォーマンス カウンターを作成し、レジストリに情報を追加します。 次のサーバー インスタンスを登録する必要があります。  
  
- NS $instance_name サービスを実行する各サーバー。 サービスでは、ホスト、ジェネレーター、およびディストリビューター コンポーネント イベント プロバイダーを実行します。 スケール アウト構成では、サービスは、複数のサーバーで実行されます。  
  
- サブスクリプションの管理アプリケーションを実行する各サーバー。 サブスクリプション管理アプリケーションは、独自のサーバーで実行する場合は作成できません、NS $instance_name サービス インスタンスを登録するときに。  
  
- 独立したイベント プロバイダーを実行する各サーバー。 独立したイベント プロバイダーは、独自のサーバーまたはデータベース サーバーで実行する場合は作成できません NS $instance_name サービス インスタンスを登録するときにします。  
  
  データベース サーバーが実行されない場合も、Notification Services インスタンスまたはクライアント コンポーネントでは、このサーバーのインスタンスを登録できません。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。  
  
-   SQL Notification Services 用ビジネス アクティビティ監視 (BAM) 警告プロバイダーは、BAM Notification Services データベースを復元するコンピューターにインストールする必要があります。  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a>BAM Notification Services データベース (SQL Server 2008 R2 SP1) への参照を更新するには  
  
1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトで、次のディレクトリに移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. Type: **bm.exe get-config –filename:config.xml**  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. これには、Notification Services 再登録する必要があります、コンピューターの一覧を取得する 2 の手順で作成した xml ファイルを開きます。  
  
    コンピューター名が記載されて、 **\<プロパティ名\=\>** 内のパラメーター、 **\<DeploymentUnit 名前 ="Alert"\>** xml ファイルのセクション:  
  
   ```  
   -<DeploymentUnit Name="Alert">  
   <Property Name="GeneratorServerName" />  
   <Property Name="ProviderServerName" />  
   <Property Name="DistributorServerName" />  
     </DeploymentUnit>  
   ```  
  
5. Xml ファイルに記載の各コンピューターで NS サービスを停止し、Notification Services のインスタンスの登録を解除します。  
  
   1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。  
  
   2.  コマンド プロンプトで「: **net NS$ BamAlerts を停止します。**  
  
   3.  インスタンスの登録を解除するには、次のコマンドを入力します。  
  
        **nscontrol unregister-name BamAlerts**  
  
        インスタンスの登録を解除すると、レジストリのエントリが削除されるほか、NS$instance_name サービスも (存在する場合は) 削除されます。さらに、このサービスに対応するパフォーマンス カウンターも削除されます。  
  
6. 通知サービスを再登録します。  
  
   1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。  
  
   2.  コマンド プロンプトで「: **nscontrol register-name BamAlerts-サーバー**  *\<ServerName\>***-service - serviceusername"*** \<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>* * *"**  
  
        これにより、Notification Services が適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンできます。  
  
       > [!IMPORTANT]
       >  新しい Notification Services データベース サーバーを使用して、忘れず、 **-サーバー**サービスを再登録するときのオプションします。 さらに、古いものと、新しい Notification Services サービスの同じユーザー名を使用する必要があります。  
  
7. BAM ポータルをホストするコンピューターで次のようにクリックします**開始**、 をクリック**プログラム**、 をクリック**Microsoft SQL Server 2008 R2**、 をクリック**構成ツール。**、 をクリックし、 **Notification Services コマンド プロンプト**します。  
  
8. コマンド プロンプトで、次のように入力します。  
  
    **net stop NS$BamAlerts**  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **nscontrol unregister-name BamAlerts**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **nscontrol register 名前***\<BamAlerts\>***-サーバー**  *\<NotificationServicesDatabaseServer\>*  
  
11. コマンド プロンプトで「:**開始 NS$ BamAlerts を net**します。  
  
12. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
13. コマンド プロンプトで、次のディレクトリに移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
14. コマンド プロンプトで、次のように入力します。  
  
     **bm.exe update-config –FileName:config.xml**  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM のバックアップと復元](../core/backing-up-and-restoring-bam.md)