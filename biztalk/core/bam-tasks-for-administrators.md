---
title: "管理者用の BAM タスク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b529a0510ee56a92d3957a84a91d635666016f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-tasks-for-administrators"></a>管理者の BAM タスク
このトピックでは、BAM インフラストラクチャを管理する際に BAM 管理者が実行する一般的なタスクについて説明します。  
  
## <a name="configuring-bam"></a>BAM の構成  
 BAM の初期構成は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを使用して行います。 この構成ウィザードを使用すると、管理者は次の操作を実行できます。  
  
-   ビジネス アクティビティの監視ツールを有効にする  
  
-   BAM 集計用に SQL Server Analysis Services を有効にする  
  
-   BAM ツールに使用するサーバー名とデータベースを指定する  
  
-   BAM 警告の SQL Server Notification Services を有効にする  
  
-   BAM Notification Service の実行に使用するアカウントを指定する  
  
-   BAM 警告の送信に使用する SMTP サーバーを指定する  
  
-   BAM 警告の格納に使用するファイルの場所を指定する  
  
-   BAM 警告データベースが存在する SQL Server の名前を指定する  
  
-   警告データベース名のプレフィックスを指定する  
  
-   コンピューターで BAM ポータルを有効にする  
  
-   BAM ポータルの実行に使用する Web サービス アカウントを指定する  
  
-   BAM ポータルにアクセスできる Windows グループを指定する  
  
-   BAM ポータル Web サイトの場所を指定する  
  
 この構成ウィザードの使用に関する詳細については、次のトピックを参照してください。  
  
-   [BizTalk Server 構成を使用して BAM 警告の構成](http://msdn.microsoft.com/library/04d79f8c-9e7f-4ba8-83ce-f79c33fb8e60)  
  
-   [BizTalk Server 構成を使用して BAM ツールを構成します。](http://msdn.microsoft.com/library/075a1627-5bc2-488c-a88c-42c86cc8c3bb)  
  
-   [BizTalk Server 構成を使用して BAM ポータルを構成します。](http://msdn.microsoft.com/library/8af7cccb-823e-48bd-9743-dfbba4bafa11)  
  
### <a name="distributed-notification-services"></a>分散された Notification Services  
 BAM が分散環境で実行されるように構成すると、警告や通知を処理するときにパフォーマンスが向上します。 このような BAM 構成では、Notification Services のプロバイダー、ジェネレーター、ディストリビューターの各ロールを異なるコンピューターに配置するため、Notification Services を複数のコンピューター環境にインストールする必要があります。  
  
##### <a name="to-configure-distributed-notification-services"></a>分散された Notification Services を構成するには  
  
1.  [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services をインストールします。 分散された Notification Services の詳細については、次を参照してください。、 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services のマニュアル[http://go.microsoft.com/fwlink/?LinkId=68095](http://go.microsoft.com/fwlink/?LinkId=68095)です。  
  
    > [!NOTE]
    >  Notification Services は含まれていない[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]です。 使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]、インストール[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services をインストールするときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を選択して、 **SQL Notification Services 用 BAM 警告プロバイダー**オプションで **追加ソフトウェア**上、**コンポーネントのインストール**インストール ウィザードのページです。  
  
2.  BAM 通知を作成する、C:\Program files \microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol の実行の分散環境では、各コンピューター上のサービス名の登録 - bamalerts-サーバー\<サーバー名 > - サービス -serviceusername\<警告ユーザー アカウント >-servicepassword \<passwd > コマンド プロンプトからです。  
  
3.  各コンピューターで、分散された Notifications Services 用に構成されている BAM インフラストラクチャ構成ファイルを編集します。 構成ファイルを取得するを使用して、 **bm.exe get config ファイル名:\<出力ファイル >**コマンド。  
  
4.  構成ファイルを編集し、分散された Notification Services 環境でサーバーを参照します。  
  
    ```  
    <Property Name="GeneratorServerName">PFIDWYUK</Property>  
    <Property Name="ProviderServerName">PFIDWYUK</Property>  
    <Property Name="DistributorServerName">PFIDWYUK</Property>  
    ```  
  
5.  Bm.exe の更新プログラムの構成を使用するファイル名:\<構成ファイル > BAM 構成を更新します。  
  
6.  分散環境のすべてのコンピューターで、Notification Services を再起動します。  
  
 複数コンピューター環境で BAM をインストールする方法の詳細については、次を参照してください[関連するインストール ガイドを BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582)と[のインストールと構成での BAM (ビジネス アクティビティ監視) 複数のコンピューター。環境](http://go.microsoft.com/fwlink/p/?LinkID=208597)です。  
  
### <a name="moving-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースの移動  
 ハードウェアのアップグレードやスケールアップを行うときなど、ある時点で BAM プライマリ インポート データベースの移動が必要になる場合があります。 データベースを移動するには、バックアップ操作と復元操作を実行します。 このプロセスの詳細については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。  
  
### <a name="working-with-bam-definitions"></a>BAM 定義の操作  
 管理者は BAM 定義と密接にかかわっています。 BAM 定義の操作に使用する主なツールは BAM 管理ユーティリティです。 このユーティリティを使用すると、次のタスクを実行できます。  
  
-   アクティビティを変更する。 使用することができます、**展開すべて**、**更新すべて**、**削除アクティビティ**、 **set-actvitywindow** BAM 管理ユーティリティのコマンド展開済みのアクティビティを変更します。  
  
-   アクティビティ テーブルにインデックスを適用してパフォーマンスを向上する。 使用する、**インデックスの作成**と**delete インデックス**アクティビティのインデックスを変更するコマンド。  
  
-   ビューにセキュリティを設定する。 使用することができます、**アカウントの追加**と**削除アカウント**ユーザーに付与するためのコマンドにアクセス権をビュー。  
  
-   アクティビティの分散ナビゲーションを構成する。 使用する、**参照を有効にする**と**無効参照**アクティビティの分散ナビゲーションを設定するコマンド。 アクティビティの分散ナビゲーションの詳細については、次を参照してください。[管理分散ナビゲーションのリモート アクティビティ](../core/managing-distributed-navigation-of-remote-activities.md)です。  
  
-   変更を監査する。 BAM 動的インフラストラクチャを使用して、変更の一覧を表示することができます、 **get 変更**コマンド。  
  
 BAM 管理ユーティリティで使用可能なすべてのコマンドの説明は、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。 BAM 管理ユーティリティを使用した BAM 定義の操作の例については、次を参照してください。 [BAM 動的インフラストラクチャを管理する](../core/managing-the-bam-dynamic-infrastructure.md)です。  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>1 つの BAM データベースを参照する複数の BizTalk グループの構成  
 新しいまたは既存のいずれかを使用する BAM を構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、既に別の使用されている同じ BAM データベースを使用するグループを構成することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  この方法で BAM を構成するには、次のタスクを行う必要があります。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを使用して、既存の BAM プライマリ インポート データベースから構成情報を取得します。 構成情報には、サーバー名とデータベース名が含まれます。 チェック ボックスの状態に注意してください。 [BAM ツール] ページと [BAM 警告] ページの両方の構成情報を取得するようにしてください。  
  
-   新しいグループに BAM を構成し、対象のプライマリ インポート テーブル (PIT) 用に構成されている情報を正確に入力します。 新しいグループの構成情報を入力するときに、既存のグループから収集されたすべての情報を使用して、新しいグループを構成します。ただし、BAM 警告ユーザーについては空白のままにする必要があります。  
  
## <a name="backing-up-and-restoring-bam"></a>BAM のバックアップと復元  
 管理者は、ディザスター リカバリーの状況に備えて計画を行う必要があります。 BAM 分析、追跡分析、BAM スター スキーマ、BAM アーカイブ、および BAM プライマリ インポート データベースをバックアップして、これらを復元する状況に備える必要があります。  バックアップして、BAM データベースの復元については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。  
  
## <a name="working-with-renamed-servers"></a>名前を変更したサーバーの操作  
 サーバーの名前を変更するか、BAM インフラストラクチャをサーバー間で移動するとき、Excel ブックで BAM 定義を更新して、Excel ブックを更新する必要があります。  
  
 次のようなシナリオで、ブックの更新が必要になります。  
  
-   BAM インフラストラクチャを新しいデータベースに移動するステージング シナリオ。 Excel ブックが機能していることを確認するには、ブックを再展開または移行してから再び更新する必要があります。  
  
-   BizTalk Server を実行しているコンピューターの名前を変更するシナリオ。 これは、DTS パッケージおよびブックの更新だけでなく OLAP データ ソースの更新が必要です。  
  
 Excel ブックの更新には、次の 2 つの手法があります。  
  
-   新しいサーバーから、次の BAM マネージャー コマンドを実行します。  
  
     **bm.exe 更新 livedataworkbook-名前:\<update.xls をライブ データ ブック >**  
  
    > [!NOTE]
    >  新しいサーバー名および BAM プライマリ インポート データベース名を指定することもできます: **bm.exe 更新 livedataworkbook-名前:\<update.xls をライブ データ ブック > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**  
  
-   または、この Excel ブックを Excel 内で更新します。  
  
    1.  更新するブックを開きます。  
  
    2.  BAM メニューから  **BAM データベースの接続**です。  
  
    3.  新しいサーバーおよび BAM プライマリ インポート データベースの名前を入力します。  
  
## <a name="managing-alerts"></a>警告の管理  
 管理者は、いくつかの方法で警告を管理することができます。  
  
 BAM 管理ユーティリティを使用して、警告の展開と削除を実行できます。 このユーティリティは、警告の有効化と無効化だけでなく、サブスクリプションの追加と削除にも使用できます。 詳細については、BAM 管理ユーティリティを使用して、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)、 [BAM セキュリティを管理する](../core/managing-bam-security.md)、および[BAM 定義を管理する](../core/managing-bam-definitions.md)です。  
  
 BAM ポータルを使用して、警告の作成や削除を行うこともできます。  BAM ポータルを使用して警告を作成する方法の詳細については、次を参照してください。 [BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)です。  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>警告記録テーブルのクリーンアップ  
 BAM 警告が構成されている場合、作成される各アクティビティ ビューに対して SQL ジョブが作成されます。 次のテンプレートを使用して、ジョブに名前が付けられます。  
  
 bam _\<ビュー名 > _\<アクティビティ ビュー > _DelAlertHistJob  
  
 このジョブに指定されたインスタンス警告に対する監査データをクリーンアップ\<アクティビティ ビュー > は Bam_Metadata_AlertChronicle テーブルにします。 特定のアクティビティ ビューにインスタンス警告を定義した場合、警告が発生するたびに、このテーブルに新しい行が追加されます。  
  
 テーブルをクリーンアップするために、ジョブは手動で実行することも、アプリケーションや環境に応じて実行されるようにスケジュールすることもできます。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)