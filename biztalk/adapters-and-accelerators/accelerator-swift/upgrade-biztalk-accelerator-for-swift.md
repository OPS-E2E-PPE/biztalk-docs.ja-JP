---
title: BizTalk Accelerator for SWIFT にアップグレード |Microsoft Docs
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
ms.openlocfilehash: 873a9d6ab13e152dadf73d20941da8e6e9ce725f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529758"
---
# <a name="upgrade-biztalk-accelerator-for-swift"></a>アップグレードの BizTalk Accelerator for SWIFT
アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef_md](../../includes/a4swift-currentversion-firstref-md.md)]BizTalk Server にします。 

### <a name="before-you-upgrade"></a>アップグレードする前に

* アップグレードを実行しているユーザーは、BizTalk Server 管理者グループのメンバーである必要があります。
* 実行すると、SQL Server (MSSQLSERVER) サービスが実行する必要があります、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]をアップグレードします。
* アップグレードするサイレント インストールを実行しない[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]します。
* BizTalk Server をアップグレードし、アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]します。
* BizTalk Server ランタイムをインストールする必要があります、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]そのランタイム コンポーネントのインストールにアップグレードします。 前に、BizTalk Server ランタイムがインストールされていないかどうか、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 、アップグレード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]コンポーネントはインストールされませんし、前のアセンブリをグローバル アセンブリ キャッシュ (GAC) からは削除されます。
* インストールするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]MessagePack がインストールされています。 以前のバージョン、MessagePack は、アップグレード中に置き換えられます。
* アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]を実行して、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]インストールします。 既存のセットアップが移行されます[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]構成情報。 
* アップグレードは、非推奨の機能のフォルダーとショートカットを削除することはできません。

## <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス  
 次の表は、サポートされている一覧[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]バージョンをアップグレードすることができます。 "Yes"は、そのバージョンをアップグレードすることを意味します。 "No"はそのバージョンをアップグレードすることはできません。 場合、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]バージョンが記載されていない、そのバージョンをアップグレードすることはできません。  


|                                                                                                       | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | BizTalk Server 2013 |
|-------------------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2013 |                         はい                          |                          [はい]                          |         いいえ          |
| [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 2010 |                          いいえ                          |                          はい                          |         はい         |

## <a name="upgrade-a4swift"></a>A4SWIFT をアップグレードします。

1. バックアップ、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース、および、SWIFT のメッセージ スキーマ。 インストール プログラムのアップグレード、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]データベース。

2. 内のファイルをバックアップ、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`と`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT MessagePack`を更新するフォルダー。
  
3. プロジェクト、BizTalk アイテム、またはのいずれかを参照するアセンブリを展開解除、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] MessagePack アセンブリ。

4. Visual Studio で、手動で解除すべて[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]次の順序でアセンブリ。

* Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration
* Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
* Microsoft.Solutions.FinancialServices.SWIFT.MrsrService
* Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas します。

5. 実行、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アップグレードをセットアップします。

> [!NOTE]
> アップグレードするときに[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]、アップグレードへのアクセス許可を削除する、 **A4SWIFT 管理者**と**A4SWIFT ユーザー**グループから、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Service`フォルダー。         
        
## <a name="post-upgrade-steps"></a>アップグレード後の手順

1. 使用して[BTSTask.exe](../../core/btstask-command-line-reference.md) (%programfiles%\Microsoft BizTalk Server)、次の順序で A4SWIFT アセンブリを手動で再展開します。
2. Microsoft.Solutions.FinancialServices.SWIFT.FrrSchemas
3. Microsoft.Solutions.FinancialServices.SWIFT.FrrOrchestration

     > [!NOTE]
     > 再デプロイする必要はありません`Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas`します。 インストールは、このアセンブリを再デプロイします。

     > [!IMPORTANT] 
     > リビルドして、前の手順でスキーマ プロジェクトを再展開の以前のバージョンを削除する前に`A4SWIFT Base Types.xsd`と`SWIFT Common Data Types.xsd`スキーマのプロジェクトからこれらのスキーマのメッセージ パック バージョンに置き換えるとビルドおよび展開し、スキーマプロジェクトです。 これらのスキーマを交換しない場合は、ビルドおよびスキーマ プロジェクトを配置することができなきます。

4. 再構築し、該当するプロジェクトまたはアセンブリの以前のバージョンで使用したデプロイ[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]またはメッセージ パックします。
5. SWIFT メッセージ パックのスキーマに変更を加えた場合、新しいメッセージ パック スキーマの変更をビルドおよび展開しそれらのスキーマ。
6. 以前のバージョンのと共にインストールされた既存の BRE ポリシーを展開解除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]します。 インストールしてから対応する新しいポリシーを展開し[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ファイル。 これを行う手動でまたはを使用して、 **BREDeployment**ツール。

   > [!NOTE]
   > 場合でも、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]アップグレードでは、ビジネス ルール エンジン (BRE) の機能と、問題が発生しない、以前のバージョンを交換することをお勧めします[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]いくつかの BRE ポリシーとして、最新のメッセージ パック BRE ポリシーで BRE ポリシー。メッセージ パックごとに更新されます。
    
7. 内のファイルをカスタマイズする場合、`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT`フォルダーを新しいバージョンに同じ変更を加えます。
8. 削除**a4swift_limited**次のように、db_denydatareader ロールのメンバーとして。
    1. SQL Server Management Studio を開きます。 Management Studio で、展開**データベース**、展開**BizTalk Accelerator for SWIFT**、し、**ロール**します。
    2. ダブルクリック**a4swift_limited**します。 選択**権限**、確認のオンと`Bic11`と`Bic10`します。 選択**OK**プロパティを閉じます。
    3. ダブルクリック**db_denydatareader**します。 ユーザー フィールドで、選択**a4swift_limited**、し、**削除**します。 **[OK]** を選択します。

9. QFERollUpDBUpdate スクリプトを実行します。

    > [!NOTE]
    > メンバーである必要がありますが、 **A4Swift 管理者**QFERollUpDBUpdate スクリプトを実行するグループ。
    
   1. SQL Server Management Studio を開きます。 Management Studio で、[新しいクエリ] をクリックします。 
   2. 選択、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]ドロップダウン リストからデータベース。 
   3. Windows エクスプ ローラーに移動`%programfiles%\Microsoft BizTalk <version> Accelerator for SWIFT\Scripts`、ドラッグ、 **QFERollUpDBUpdate.sql** 、新しいクエリ ウィンドウにファイルを選び**Execute**します。
    
    
## <a name="upgrading-in-a-multi-server-environment"></a>マルチ サーバー環境でのアップグレード

マルチ サーバー [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] 、すべてのサーバーで、環境が、BizTalk Server をアップグレードし、アップグレード[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]します。 次の順序で、サーバーを移行するには。

* BizTalk グループをホストするサーバー
* 各処理ノード
* BAM ポータル サーバー


## <a name="next-steps"></a>次のステップ
[BizTalk Accelerator for SWIFT に構成します。 ](../../adapters-and-accelerators/accelerator-swift/configure-biztalk-accelerator-for-swift.md)