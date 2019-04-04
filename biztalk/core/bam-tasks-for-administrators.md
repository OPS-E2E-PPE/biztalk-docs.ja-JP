---
title: 管理者の BAM タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742eeffd496eaf43fbdd809f2610f2af64d04251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996363"
---
# <a name="bam-tasks-for-administrators"></a>管理者の BAM タスク
このトピックでは、BAM インフラストラクチャを管理する際に BAM 管理者が実行する一般的なタスクについて説明します。  
  
## <a name="configuring-bam"></a>BAM の構成  
 BAM の初期構成が完了したら、BizTalk Server 構成ウィザードを使用します。 この構成ウィザードを使用すると、管理者は次の操作を実行できます。  
  
- ビジネス アクティビティの監視ツールを有効にする  
  
- BAM 集計用に SQL Server Analysis Services を有効にする  
  
- BAM ツールに使用するサーバー名とデータベースを指定する  
  
- BAM 警告の SQL Server Notification Services を有効にする  
  
- BAM Notification Service の実行に使用するアカウントを指定する  
  
- BAM 警告の送信に使用する SMTP サーバーを指定する  
  
- BAM 警告の格納に使用するファイルの場所を指定する  
  
- BAM 警告データベースが存在する SQL Server の名前を指定する  
  
- 警告データベース名のプレフィックスを指定する  
  
- コンピューターで BAM ポータルを有効にする  
  
- BAM ポータルの実行に使用する Web サービス アカウントを指定する  
  
- BAM ポータルにアクセスできる Windows グループを指定する  
  
- BAM ポータル Web サイトの場所を指定する  
  
  この構成ウィザードの使用に関する詳細については、次のトピックを参照してください。  
  
- [BAM 警告を構成します。](../install-and-config-guides/configure-biztalk-server.md)  
  
- [BAM ツールを構成します。](../install-and-config-guides/configure-biztalk-server.md)  
  
- [BAM ポータルを構成します。](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a>分散された Notification Services の SQL Server 2008 R2 のみ
BAM が分散環境で実行されるように構成すると、警告や通知を処理するときにパフォーマンスが向上します。 このような BAM 構成では、Notification Services のプロバイダー、ジェネレーター、ディストリビューターの各ロールを異なるコンピューターに配置するため、Notification Services を複数のコンピューター環境にインストールする必要があります。  

> [!NOTE]
> SQL Server 2012 以降では、BizTalk Server は、SQL Database Mail を使用します。 SQL Server 2012 を使用している場合、またはそれ以降にこれは適用されません。 参照してください[BAM 警告](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)のガイダンスについてはします。
  
##### <a name="to-configure-distributed-notification-services"></a>分散された Notification Services を構成するには  
  
1. SQL Server Notification Services をインストールします。 
  
   > [!NOTE]
   >  SQL Server では、notification Services が含まれていません。 選択して BizTalk Server をインストールするときに、SQL Server Notification Services をインストール、 **SQL Notification Services 用 BAM 警告プロバイダー**オプションで **追加ソフトウェア**上、 **コンポーネントのインストール**インストール ウィザードのページ。  
  
2. BAM 通知を作成する C:\Program files \microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol を実行する分散環境では、各コンピューター上のサービス名を登録 - bamalerts-サーバー\<サーバー名\>-サービス - serviceusername\<警告ユーザー アカウント\>-servicepassword \<passwd\>コマンド プロンプトからです。  
  
3. 各コンピューターで、分散された Notifications Services 用に構成されている BAM インフラストラクチャ構成ファイルを編集します。 構成ファイルを取得する、 **bm.exe config の取得のファイル名:\<出力ファイル\>** コマンド。  
  
4. 構成ファイルを編集し、分散された Notification Services 環境でサーバーを参照します。  
  
   ```  
   <Property Name="GeneratorServerName">PFIDWYUK</Property>  
   <Property Name="ProviderServerName">PFIDWYUK</Property>  
   <Property Name="DistributorServerName">PFIDWYUK</Property>  
   ```  
  
5. 更新プログラムの config の bm.exe を使用してファイル名:\<config ファイル\>BAM 構成を更新します。  
  
6. 分散環境のすべてのコンピューターで、Notification Services を再起動します。  
  
   複数コンピューター環境で BAM をインストールする方法の詳細については、[BAM インストールおよび構成 (ビジネス アクティビティ監視)、複数コンピューター環境で](http://go.microsoft.com/fwlink/p/?LinkID=208597)を参照してください。  
  
### <a name="moving-the-bam-primary-import-database"></a>BAM プライマリ インポート データベースの移動  
 ハードウェアのアップグレードやスケールアップを行うときなど、ある時点で BAM プライマリ インポート データベースの移動が必要になる場合があります。 データベースを移動するには、バックアップ操作と復元操作を実行します。 このプロセスの詳細については、[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)を参照してください。  
  
### <a name="working-with-bam-definitions"></a>BAM 定義の操作  
 管理者は BAM 定義と密接にかかわっています。 BAM 定義の操作に使用する主なツールは BAM 管理ユーティリティです。 このユーティリティを使用すると、次のタスクを実行できます。  
  
- アクティビティを変更する。 使用することができます、**展開すべて**、**更新すべて**、**削除アクティビティ**、 **set-actvitywindow** BAM 管理ユーティリティのコマンド展開済みのアクティビティを変更します。  
  
- アクティビティ テーブルにインデックスを適用してパフォーマンスを向上する。 使用する、**インデックスの作成**と**インデックスを削除**アクティビティのインデックスを変更するコマンド。  
  
- ビューにセキュリティを設定する。 使用することができます、**アカウントの追加**と**削除アカウント**コマンドをユーザーに付与するアクセス権をビュー。  
  
- アクティビティの分散ナビゲーションを構成する。 使用する、**参照を有効にする**と**無効にする参照**アクティビティの分散ナビゲーションを構成するコマンド。 アクティビティの分散ナビゲーションの詳細については、[を管理する分散ナビゲーションのリモート アクティビティ](../core/managing-distributed-navigation-of-remote-activities.md)を参照してください。  
  
- 変更を監査する。 BAM 動的インフラストラクチャを使用して変更を一覧表示、 **get 変更**コマンド。  
  
  BAM 管理ユーティリティで使用できるすべてのコマンドについては、[BAM 管理ユーティリティ](../core/bam-management-utility.md)を参照してください。 BAM 管理ユーティリティを使用した BAM 定義の操作の例については、[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)を参照してください。  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>1 つの BAM データベースを参照する複数の BizTalk グループの構成  
 新しいまたは既存の BizTalk Server グループのいずれかを使用する BAM を構成する場合は、既に別の BizTalk Server グループで使用されている同じ BAM データベースを使用するグループを構成できます。  この方法で BAM を構成するには、次のタスクを実行する必要があります。  
  
-   BizTalk Server の構成ウィザードを使用して既存の BAM プライマリ インポート データベースから構成情報を取得します。 構成情報には、サーバー名とデータベース名が含まれます。 チェック ボックスの状態に注意してください。 [BAM ツール] ページと [BAM 警告] ページの両方の構成情報を取得するようにしてください。  
  
-   新しいグループに BAM を構成し、対象のプライマリ インポート テーブル (PIT) 用に構成されている情報を正確に入力します。 新しいグループの構成情報を入力するときに、既存のグループから収集されたすべての情報を使用して、新しいグループを構成します。ただし、BAM 警告ユーザーについては空白のままにする必要があります。  
  
## <a name="backing-up-and-restoring-bam"></a>BAM のバックアップと復元  
 管理者は、ディザスター リカバリーの状況に備えて計画を行う必要があります。 BAM 分析、追跡分析、BAM スター スキーマ、BAM アーカイブ、および BAM プライマリ インポート データベースをバックアップして、これらを復元する状況に備える必要があります。  バックアップおよび BAM データベースを復元する方法については、[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)を参照してください。  
  
## <a name="working-with-renamed-servers"></a>名前を変更したサーバーの操作  
 サーバーの名前を変更するか、BAM インフラストラクチャをサーバー間で移動するとき、Excel ブックで BAM 定義を更新して、Excel ブックを更新する必要があります。  
  
 次のようなシナリオで、ブックの更新が必要になります。  
  
- BAM インフラストラクチャを新しいデータベースに移動するステージング シナリオ。 Excel ブックが機能していることを確認するには、ブックを再展開または移行してから再び更新する必要があります。  
  
- BizTalk Server を実行しているコンピューターの名前を変更するシナリオ。 これは、DTS パッケージと、ブックの更新に加えて、OLAP データ ソースの更新が必要です。  
  
  Excel ブックの更新には、次の 2 つの手法があります。  
  
- 新しいサーバーから、次の BAM マネージャー コマンドを実行します。  
  
   **bm.exe の update livedataworkbook-名前:\<update.xls livedata ブック\>**  
  
  > [!NOTE]
  >  新しいサーバー名および BAM プライマリ インポート データベース名を指定することもできます: **bm.exe 更新-livedataworkbook-名前:\<update.xls livedata ブック\>[-サーバー:\<server\>] [-データベース:\<データベース\>]**  
  
- または、この Excel ブックを Excel 内で更新します。  
  
  1.  更新するブックを開きます。  
  
  2.  BAM のメニューから**BAM データベースの接続**します。  
  
  3.  新しいサーバーおよび BAM プライマリ インポート データベースの名前を入力します。  
  
## <a name="managing-alerts"></a>警告の管理  
 管理者は、いくつかの方法で警告を管理することができます。  
  
 BAM 管理ユーティリティを使用して、警告の展開と削除を実行できます。 このユーティリティは、警告の有効化と無効化だけでなく、サブスクリプションの追加と削除にも使用できます。 詳細については、BAM 管理ユーティリティを使用して、[BAM 管理ユーティリティ](../core/bam-management-utility.md)、 [BAM セキュリティの管理](../core/managing-bam-security.md)、および[BAM 定義を管理する](../core/managing-bam-definitions.md)を参照してください。  
  
 BAM ポータルを使用して、警告の作成や削除を行うこともできます。  BAM ポータルを使用してアラートを作成する方法の詳細については、[BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)を参照してください。  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>警告記録テーブルのクリーンアップ  
 BAM 警告が構成されている場合、作成される各アクティビティ ビューに対して SQL ジョブが作成されます。 次のテンプレートを使用して、ジョブに名前が付けられます。  
  
 bam _\<ビュー名\>_\<アクティビティ ビュー\>_DelAlertHistJob  
  
 このジョブを指定したインスタンス警告に対する監査データをクリーンアップ\<アクティビティ ビュー\>は Bam_Metadata_AlertChronicle テーブル内。 特定のアクティビティ ビューにインスタンス警告を定義した場合、警告が発生するたびに、このテーブルに新しい行が追加されます。  
  
 テーブルをクリーンアップするために、ジョブは手動で実行することも、アプリケーションや環境に応じて実行されるようにスケジュールすることもできます。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)