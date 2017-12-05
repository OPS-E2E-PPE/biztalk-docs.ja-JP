---
title: "BAM ポータルの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, prerequisites
- BAM portal, deploying
- developing, BAM portal
- planning, BAM portal
- BAM portal, planning
- BAM portal, developing
- deploying, BAM portal
- security, BAM portal
ms.assetid: 8a8bd331-c5a8-4d8b-9e93-96e6cd581a1d
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85f7291d56d662a8e3a9d46308d6b16ca2a1cafc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-the-bam-portal"></a>BAM ポータルの計画
このトピックでは、ビジネス アクティビティ監視 (BAM) ポータルの展開を計画するときに考慮する必要がある項目について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 **システム要件**です。 BizTalk Server のシステム要件に加え、BAM ポータルをインストールするために次のソフトウェアをインストールする必要があります。  
  
-   インターネット インフォメーション サービス (IIS)  
  
-   Microsoft Office Excel  
  
-   [Microsoft Internet Explorer]  
  
-   [Microsoft .NET Framework]  
  
-   Microsoft XML Core Services (MSXML) 6.0  
  
-   Microsoft Data Access Components (MDAC) 2.7  
  
## <a name="configuration-planning"></a>構成の計画  
 **BizTalk Server の以前のバージョンから移行**です。 以前のバージョンの BizTalk Server からの移行後、BAM ポータルの既存のページのインストールは機能しなくなる場合があります。 BAM ポータルを正常に機能させるには、BizTalk Server のアップグレード ガイドの、BAM に関する考慮事項とガイドラインを参照してください。  
  
 **データベース**です。 データベースについて計画する場合は、次の点を考慮してください。  
  
-   パフォーマンスを向上させるには、データベースのインデックスを計画する必要があります。 通常、日付と時刻の列では、進捗ディメンションのインデックスを必要とします。 インデックスのない進捗ディメンションのクエリは処理速度が遅く、BAM プライマリ インポート テーブルのパフォーマンスに悪影響を及ぼします。  
  
-   BAM を警告なしに設定するかどうかを検討することが必要です。  
  
 **SQL Server Notification Services**です。 SQL Server Notification Services は、サーバーを識別するためのサーバー名として、ローカル ホストまたは IP アドレスをサポートしていません。  このことは、次の 2 つの状況で発生する可能性があります。  
  
1.  構成時 - BAM を選択して警告を有効にした場合、構成処理でサーバー名が求められます。  
  
2.  構成 .xml ファイルの変更時 - 構成処理の結果生成された構成 .xml ファイルを再利用するために変更する場合。  
  
 **IIS のインストール**です。 BAM ポータルは、32 ビット モードでのみ実行されます。 IIS を 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 を 32 ビット モードで有効にする必要があります。 これを行うには、IIS マネージャーを開いて、開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**です。 **[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。 詳細については、BizTalk Server のアップグレード ガイドを参照してください。  
  
## <a name="deployment-planning"></a>展開の計画  
 **複数コンピュータ展開**です。 複数コンピューター環境に BizTalk Server を展開するかどうか。 BAM ポータルを警告データベースとは別のサーバー上に構成する場合、マルチサーバー環境におけるクエリ サービスのタイムアウト値を増やす必要があります。 追加の構成については、次を参照してください。 [BAM ポータルの構成をカスタマイズする](../core/customizing-the-bam-portal-configuration.md)です。  
  
-   **複数カルチャの展開**です。 複数カルチャ環境に BizTalk Server を展開するかどうか。 BizTalk Server をインストールして、ユーザー インターフェイス (UI) がインストールされているバージョンの言語では、BAM ポータルのように構成したユーザーのカルチャ設定は取得されます。 適切なカルチャ設定を反映するように BAM ポータルの web.config ファイルを変更するを参照してください。 [BAM ポータルの構成をカスタマイズする](../core/customizing-the-bam-portal-configuration.md)です。  
  
 **クラスター展開**です。 ネットワーク負荷分散 (NLB) クラスターに展開するかどうか。 参照してください[BAM ポータルの構成をカスタマイズする](../core/customizing-the-bam-portal-configuration.md)追加の構成についてはします。  
  
 **SSL**です。 SSL を使用して BAM ポータルを IIS に展開するかどうか。 参照してください、 [BAM ポータルの構成をカスタマイズする](../core/customizing-the-bam-portal-configuration.md)追加の構成については、トピックです。  
  
 ビューを作成するユーザーは、Excel 用の BAM アドインをインストールしておく必要があります。  
  
## <a name="permissions"></a>Permissions  
 **BAM マネージャー**です。 BAM マネージャー (bm.exe) の add-account コマンドでは、追加したユーザーにデータベースのアクセス許可が自動的に与えられません。 これは、BAM マネージャーの実行で必要となるものが、dbo アクセス許可だけであるためです。 その結果、BAM ポータルからリアルタイム集計 (RTA) にアクセスすると、SQL Server でエラーが発生します。ただし、次に説明するように、SQL Server 内の特定のグループに所属していれば、エラーは発生しません。  
  
 **SQL Server ロール**です。 ユーザーにデータベースへのアクセスを許可するには、securityadmin グループまたは sysadmin グループのメンバーである必要があります。  
  
 securityadmin グループまたは sysadmin グループのメンバーは、sp_grantdbaccess および sp_grantlogin を実行して、アクセス許可を与えることができます。  
  
 SQL Server の役割の詳細についてを参照してください「の役割で SQL Server のアーキテクチャ」 [http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205)です。  
  
## <a name="development-planning"></a>開発の計画  
 **ピボット テーブルの接続文字列を**です。 BAM マネージャー ユーティリティは、展開時に、リアルタイム集計 (RTA) のピボットテーブル定義の接続文字列を必ず変更するというわけではありません。 RTA ピボットテーブルが手動で編集された既存の OLAP 接続文字列を保持しており、値キーの大文字小文字が正しくない場合に、接続文字列の変更が行われます。 たとえば、BAM 定義 XML ファイルの次の行では、キーが想定した RtaRef ではなく RTARef になっています。  
  
 **\<PivotTableView CubeRef"POCube"次の行を = ="POAmountByLocation"\>**  
  
 そのため、ピボットテーブルは、RTA ピボットテーブルではなく OLAP キューブを使用して生成されます。  
  
 **フィールド名**です。 監視ソリューションを開発する際には、各フィールドをはっきりと識別できる名前付け規則を使用することをお勧めします。 BAM は、BAM 定義のビュー セクションと集計の OLAP キューブとの間に一意名を必要としません。  そのため、[アクティビティの検索] クエリ ビルダーにある [列の選択] およびフィールド選択用ドロップダウン リストには、同じ名前の 2 つのフィールドが含められることもありえます。 これにより、結果に含めるフィールドを選択する際、フィールドが適切であってもエラーが発生することがあります。  
  
 パススルー パイプラインを使用する BizTalk Server ポートの場合、メッセージ ペイロードからデータを追跡できません。 パススルー パイプラインは、メッセージの種類をスキーマ名に評価しません。この結果、すべてのメッセージには Null のスキーマが設定されます。  
  
-   追跡プロファイルがポートとスキーマの組み合わせにマップされるので、パススルー パイプラインのメッセージ ペイロード データを追跡しても、何も追跡されません。  
  
 **ピボット テーブルの名前**: Excel で作成するピボット テーブルの表示名のユーザーを作成する必要があります、BAM ポータルの集計タスクにおけるエクスペリエンスを計画および開発ユーザー、ときにします。  この名前は、ピボットテーブルを右クリックしてショートカット メニューから [オプション] を選択すると、カスタマイズできます。  
  
 **日付範囲**です。 使用して通知クエリとインスタンスを作成するときにアクティビティの検索ページに留意する場合、@@DateFirst SQL クエリ内の値が CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek 値と一致しませんし、日付の範囲に表示される、[検索] ページでは、集計の生成に使用される 1 週間境界は一致しません。  
  
 たとえば、SQL Server の週の開始日が日曜日に設定されている場合、2005 年の第 2 週の日付の範囲は 2005 年 1 月 2 日から 2005 年 1 月 8 日までになり、第 2 週に表示される SQL Server および OLAP の集計はこの日付の範囲に基づきます。 ただし、BAM ポータルで週の開始日を土曜日に指定すると、2005 年の第 2 週でドリルダウンが実行され、検索ページには、日付の範囲が 2005 年 1 月 8 日から 2005 年 1 月 14 日までとして表示されます。 この結果、検索クエリによって返される値は、ピボットテーブルに表示される集計値と一致しない場合があります。  
  
 目的の結果を得るには、必要な日付の範囲を取得するようにクエリ内の時間範囲を調整します。  
  
 **分散ナビゲーション**です。 BAM ポータル分散ナビゲーション機能を使用すると、リモートの全境界でのアクティビティ リレーションシップを表示できます。 アクティビティを開発する際は、次の点を考慮してください。  
  
-   関連するアクティビティを別の BAM プライマリ インポート データベースから同じビューに配置する場合があります。 アクティビティは同じ名前が付いていても、異なるサーバー上に存在する可能性があります。たとえば、2 つの異なる部署の両方に発注アクティビティがある場合があります。 BAM ポータルのユーザーがポータルの [マイ ビュー] で [ビュー] を選択すると、各タスクの下に表示される両方のアクティビティを参照できます。  
  
-   異なるサーバー上で BAM ポータルを使用して展開済みのビューを表示する場合は、2 つのポータル (それぞれが、ローカルの BAM プライマリ インポート データベースに対して実行されている) の動作が同じになるように、参照を対称的に有効にする必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルの構成のカスタマイズ](../core/customizing-the-bam-portal-configuration.md)