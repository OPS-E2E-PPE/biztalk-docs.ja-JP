---
title: BizTalk Accelerator for SWIFT にアップグレード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede2af21-4c7d-4f9e-b255-1ada86eda68d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4e95d248103d99b4b7f50dc925fb220211530f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215394"
---
# <a name="upgrade-biztalk-accelerator-for-swift"></a>アップグレードの BizTalk Accelerator 用 SWIFT
アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]の BizTalk Server にします。 

### <a name="before-you-upgrade"></a>アップグレードする前に

* アップグレードを実行しているユーザーは、BizTalk Server 管理者グループのメンバーにする必要があります。
* 実行する場合は、SQL Server (MSSQLSERVER) サービスを実行している必要があります、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]をアップグレードします。
* [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] へのアップグレード時にはサイレント インストールを実行しないでください。
* BizTalk Server をアップグレードし、アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]です。
* BizTalk Server ランタイムをインストールする必要があります、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]そのランタイム コンポーネントのインストールにアップグレードします。 前に、BizTalk Server ランタイムがインストールされていないかどうか、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 、アップグレード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]コンポーネントはインストールされませんし、前のアセンブリをグローバル アセンブリ キャッシュ (GAC) からは削除されます。
* インストールするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]、MessagePack がインストールされています。 以前のバージョン、MessagePack は、アップグレード中に置き換えられます。
* アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]を実行して、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]インストールします。 既存の設定を移行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成情報。 
* アップグレードは、非推奨の機能のフォルダーとショートカットを削除することはできません。

## <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス  
 次の表に、サポートされている一覧[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]バージョンをアップグレードすることができます。 "Yes"では、そのバージョンをアップグレードすることを意味します。 "No"を意味するバージョンをアップグレードすることはできません。 場合、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]バージョンが記載されていない、そのバージョンをアップグレードすることはできません。  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2013|はい|可|不可|  
|[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2010|不可|はい|はい|  


## <a name="upgrade-a4swift"></a>A4SWIFT をアップグレードします。

1. バックアップを[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース、および、SWIFT メッセージ スキーマ。 インストール プログラムのアップグレード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース。

2. 内のファイルをバックアップ、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`と`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT MessagePack`を更新するフォルダーです。
  
3. プロジェクト、BizTalk アイテム、またはのいずれかを参照しているアセンブリを展開解除、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] MessagePack アセンブリ。

4. Visual Studio で、次の順序ですべての [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] アセンブリの展開を手動で解除します。

* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.MrsrService
* Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas です。

5. 実行、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アップグレードをセットアップします。

> [!NOTE] 
> アップグレードするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]、アップグレードのアクセス許可を削除する、 **A4SWIFT 管理者**と**A4SWIFT ユーザー**からグループ化、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Service`フォルダーです。         
        
## <a name="post-upgrade-steps"></a>アップグレード後の手順

1. 使用して[BTSTask.exe](../../core/btstask-command-line-reference.md) (%programfiles%\Microsoft BizTalk Server)、次の順序で、A4SWIFT アセンブリを手動で再展開します。
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration

    > [!NOTE]
    > 再展開する必要はありません`Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas`です。 インストールには、このアセンブリが再配置されます。

    > [!IMPORTANT] 
    > 再構築して、前の手順でスキーマ プロジェクトを再展開の古いバージョンを削除する前に`A4SWIFT Base Types.xsd`と`SWIFT Common Data Types.xsd`スキーマ プロジェクトから、これらのスキーマのメッセージ パックのバージョンと置き換えてビルドおよび展開し、スキーマプロジェクトです。 これらのスキーマを交換しない場合、スキーマ プロジェクトをビルドおよび配置できなきます。

2. 再構築し、該当するプロジェクトまたはアセンブリの旧バージョンで使用した展開[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]またはメッセージ パックします。
3. SWIFT メッセージ パック スキーマに変更を加えた場合、新しいメッセージ パック スキーマの変更をビルドおよび展開しそれらのスキーマです。
4. 以前のバージョンと共にインストールされた既存の BRE ポリシーを展開解除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]です。 インストールしてから新しい、対応するポリシーを展開し、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ファイルです。 これを行う手動でまたはを使用して、 **BREDeployment**ツールです。

    > [!NOTE] 
    > 場合でも、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アップグレードには、ビジネス ルール エンジン (BRE) 機能を持つすべての問題は発生しませんの以前のバージョンに置き換えることをお勧め[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]として BRE ポリシーによって、最新のメッセージ パック BRE ポリシーで BRE ポリシー各メッセージ パックの更新を取得します。
    
5. 内のファイルをカスタマイズする場合、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`フォルダーで、新しいバージョンにも同じ変更を加えます。
6. 削除**a4swift_limited**次のように、db_denydatareader ロールのメンバーとして。
    1. SQL Server Management Studio を開きます。 Management Studio で、展開**データベース**、展開**BizTalk Accelerator 用 SWIFT**、し、**ロール**です。
    2. ダブルクリックして**a4swift_limited**です。 選択**権限**、確認のオンと`Bic11`と`Bic10`です。 選択**OK**のプロパティ を閉じます。
    3. ダブルクリックして**db_denydatareader**です。 ユーザー フィールドで、選択**a4swift_limited**、し、**削除**です。 [ **OK**] を選択します。

7. QFERollUpDBUpdate スクリプトを実行します。

    > [!NOTE]
    > メンバーである必要がある必要があります、 **A4Swift 管理者**QFERollUpDBUpdate スクリプトを実行するグループです。
    
    1. SQL Server Management Studio を開きます。 Management Studio で、[新しいクエリ] をクリックします。 
    2. 選択、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]ドロップダウン リストからデータベース。 
    3. Windows エクスプ ローラーに移動`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Scripts`、ドラッグ、 **QFERollUpDBUpdate.sql**ファイルを新しいクエリ ペインにドラッグし、 **Execute**です。
    
    
## <a name="upgrading-in-a-multi-server-environment"></a>マルチ サーバー環境でのアップグレード

マルチ サーバー [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 、すべてのサーバーで、環境の BizTalk Server をアップグレードしてアップグレードして[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]です。 次の順序でサーバーを移行します。

* BizTalk グループをホストするサーバー
* 各処理ノード
* BAM ポータル サーバー


## <a name="next-steps"></a>次の手順
[SWIFT の BizTalk アクセラレータを構成します。](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)