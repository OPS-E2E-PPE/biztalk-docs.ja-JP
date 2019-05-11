---
title: BAM 管理ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7569bb1f257c3b8686902ea5776e5bf8e1b467
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530582"
---
# <a name="bam-management-utility"></a>BAM 管理ユーティリティ
ビジネス アクティビティ監視 (BAM) 定義の管理者では、BAM 管理ユーティリティを使用して、管理し、BAM インフラストラクチャのあらゆる側面を管理します。  
  
 BAM ユーティリティを使用するには、次のタスクを実行します。  
  
-   BAM 定義と BAM 構成 XML を入力として使用します。 BAM 定義 XML または XLS ファイルは、追跡し、集計、追跡データに関するビジネス エンドユーザーのビューにデータを定義します。 BAM 構成 XML には、サーバー名、データベース名、およびその他のデータベースの設定など、インフラストラクチャをデプロイする場所が定められています。  
  
-   BAM プライマリ インポート データベース、BAM スター スキーマ データベース、BAM 分析データベースが含まれているサーバー上のランタイム インフラストラクチャをデプロイし、対応するデータ変換サービス (DTS) パッケージ。 この手順では、次の項目が作成されます。  
  
    -   BAM プライマリ インポート データベース  
  
    -   BAM スター スキーマ データベース  
  
    -   BAM アーカイブ データベース  
  
    -   BAM 分析データベース  
  
> [!NOTE]
>  BAM 管理ユーティリティを実行しているコンピューターのロケール設定は、適切に機能する BAM コマンドの順序でデプロイされている BAM 定義を作成するために使用するロケールと同じである必要があります。 実行する場合など、 **get ビュー**構成されたコンピューターのロケールが英語とフランス語のロケールを使用しているコンピューターで、データベースに対して設定することはできませんをリセットしない限り、返されたビュー名を使用する、コンピューターをフランス語のロケール。  
  
 BAM 管理ユーティリティを使用して、生成して、サーバーに対して追跡構成をデプロイすることができます。 BAM 管理ユーティリティにあるコマンド ライン ツールは、 \<*インストール パス*\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\BM.exe します。  
  
> [!IMPORTANT]
>  BAM 管理ユーティリティを実行するには、メンバーである、 **db_owner**の BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの SQL Server データベース ロール。 BAM 警告に関連する更新を行う場合、BAM 警告データベースの sysadmin アクセス許可が必要です。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
## <a name="bam-management-utility-commands"></a>BAM 管理ユーティリティのコマンド  
 コマンドの説明では、これらの規則を使用します。  
  
- 角かっこ () は、オプションのパラメーターを示します。  
  
- 山かっこ (<) は、必要なパラメーターを示します。  
  
- 中かっこ ({}) 1 つのアイテムが列挙された一覧から選択する必要がありますを指定します。  
  
- セキュリティ アカウントは NT グループまたは個々 の NT ユーザー アカウントのいずれかにできます。  
  
- BAM 定義ファイルを XML ファイルまたは BAM Excel ブック ファイル (.xls) のいずれかを使用できます。  
  
- BAM 構成ファイルが指定されていない場合の既定値は、現在のフォルダーの BamConfiguration.xml です。  
  
  次のトピックでは、個々 のコマンドの説明が含まれています。  
  
- [データベース コマンド](../core/database-commands.md)  
  
- [BAM 定義 (監視モデル) の展開コマンド](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
- [インフラストラクチャ管理コマンド](../core/infrastructure-management-commands.md)  
  
- [アクティビティ管理コマンド](../core/activity-management-commands.md)  
  
- [ビュー管理コマンド](../core/view-management-commands.md)  
  
- [Alert Management コマンド](../core/alert-management-commands.md)  
  
- [ユーザー管理コマンド](../core/user-management-commands.md)  
  
- [警告サブスクリプション管理コマンド](../core/alert-subscription-management-commands.md)  
  
- [インターセプター管理コマンド](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a>BAM 管理ユーティリティのヘルプを表示します。  
 使用する、 **/でしょうか。** または、 **BAM 管理ユーティリティのヘルプ**BAM 管理ユーティリティのヘルプ ファイルを表示するコマンド。  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a>BAM 管理ユーティリティのヘルプ ファイルを表示するには  
  
1.  コマンド プロンプトから次のディレクトリを参照してください。C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking\\します。  
  
2.  型**bm**または**bm ヘルプ**します。  
  
3.  Enter キーを押します。