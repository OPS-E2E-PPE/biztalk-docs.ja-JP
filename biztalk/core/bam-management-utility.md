---
title: "BAM 管理ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be7c36900c39f46f636077c5c9d0cb630265cc80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-management-utility"></a>BAM 管理ユーティリティ
BAM 管理ユーティリティは、BAM インフラストラクチャのあらゆる要素を管理、保守するために、ビジネス アクティビティ監視 (BAM) 定義の管理者によって使用されます。  
  
 BAM ユーティリティを使用すると、次のようなタスクを実行できます。  
  
-   BAM 定義/BAM 構成の XML を入力として使用する。 BAM 定義ファイル (XML または XLS) は、追跡データや集計データ、さらには、追跡データに対するビジネス エンド ユーザー向けのビューを定義するファイルです。 BAM 構成 XML は、サーバー名、データベース名、データベース設定など、インフラストラクチャの展開先となる環境を定義したものです。  
  
-   サーバー上にランタイム インフラストラクチャを展開する。このインフラストラクチャには、BAM プライマリ インポート データベース、BAM スター スキーマ データベース、BAM 分析データベース、および対応するデータ変換サービス (DTS) パッケージが含まれます。 この作業では、次のアイテムが作成されます。  
  
    -   BAM プライマリ インポート データベース  
  
    -   BAM スター スキーマ データベース  
  
    -   BAM アーカイブ データベース  
  
    -   BAM 分析データベース  
  
> [!NOTE]
>  BAM コマンドを適切に動作させるためには、BAM 管理ユーティリティを実行するコンピューターのロケール設定が、展開されている BAM 定義の作成に使用したロケールと一致している必要があります。 たとえばを実行する場合、 **get ビュー**構成されているコンピューターのロケールが英語とフランス語ロケールのコンピューターで、データベースに対して設定することはできませんをリセットしない限り、返されたビュー名を使用する、コンピューターをフランス語ロケール。  
  
 BAM 管理ユーティリティを使用すると、サーバーに対して追跡構成を生成したり展開したりできます。 BAM 管理ユーティリティにあるコマンド ライン ツールは、 \<*インストール パス*> \Program Files\Microsoft BizTalk Server\<バージョン > \Tracking\BM.exe です。  
  
> [!IMPORTANT]
>  BAM 管理ユーティリティを実行するには、メンバーである、 **db_owner**の BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの SQL Server データベース ロール。 また、BAM 警告に関連する更新を行う場合には、BAM 警告データベースに対する sysadmin アクセス許可も必要です。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
## <a name="bam-management-utility-commands"></a>BAM 管理ユーティリティのコマンド  
 コマンドの使用法を次の表記規則に従って説明します。  
  
-   角かっこ ([]) は省略可能なパラメーターであることを示します。  
  
-   山かっこ (<>) は必須のパラメーターであることを示します。  
  
-   中かっこ ({}) は、かっこ内に列挙されている項目から、いずれか 1 つを選択する必要があることを示します。  
  
-   セキュリティ アカウントには、NT グループ アカウントを使用することも、個々の NT ユーザー アカウントを使用することもできます。  
  
-   BAM 定義ファイルの形式には、XML ファイルまたは BAM Excel ブック ファイル (.xls) を使用できます。  
  
-   BAM 構成ファイルが指定されなかった場合、現在のフォルダーの BamConfiguration.xml が既定で使用されます。  
  
 各コマンドについては、次のトピックで説明します。  
  
-   [データベース コマンド](../core/database-commands.md)  
  
-   [BAM 定義 (監視モデル) コマンドの展開](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
-   [インフラストラクチャ管理コマンド](../core/infrastructure-management-commands.md)  
  
-   [アクティビティ管理コマンド](../core/activity-management-commands.md)  
  
-   [ビュー管理コマンド](../core/view-management-commands.md)  
  
-   [警告管理コマンド](../core/alert-management-commands.md)  
  
-   [ユーザー管理コマンド](../core/user-management-commands.md)  
  
-   [警告サブスクリプション管理コマンド](../core/alert-subscription-management-commands.md)  
  
-   [インターセプター管理コマンド](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a>BAM 管理ユーティリティのヘルプの表示  
 使用する、 **/しますか?** または、 **BAM 管理ユーティリティのヘルプ**を BAM 管理ユーティリティのヘルプ ファイルを表示するコマンド。  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a>BAM 管理ユーティリティのヘルプ ファイルを表示するには  
  
1.  コマンド プロンプトから次のディレクトリを参照: C:\Program files \microsoft BizTalk Server\<バージョン > \Tracking\\です。  
  
2.  型**bm**または**bm ヘルプ**です。  
  
3.  Enter キーを押します。