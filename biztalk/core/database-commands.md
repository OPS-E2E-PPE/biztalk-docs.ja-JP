---
title: "データベース コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2232602ec5a91768f4b9dbde5f6c63a79de0c332
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="database-commands"></a>データベース コマンド
BAM 管理ユーティリティのデータベース コマンドを使用すると、BAM データベースを操作することができます。  
  
-   データベースのセットアップ: BAM 固有のデータベースを作成します。  
  
-   移行 sql: から BAM データベースを移行します。  
  
    -   Microsoft SQL Server 2000 から Microsoft SQL Server 2008 へ  
  
    -   Microsoft SQL Server 2008 への Microsoft SQL Server 2005  
  
-   参照を有効にする: 分散 BAM プライマリ インポート データベースへの参照を有効にします。  
  
-   get 参照: 分散 BAM プライマリ インポート データベースへの参照の一覧を取得します。  
  
-   参照を無効にする: BAM プライマリ インポート データベースへの参照を無効にします。  
  
> [!NOTE]
>  含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。 Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。 このスイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="setup-databases-command"></a>setup-databases コマンド  
 **使用方法**  
  
 **bm.exe のセットアップ-データベース-ConfigFile:\<構成ファイル\>[- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\> ]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|ConfigFile:\<構成ファイル\>|データベースの作成に使用する BAM 構成ファイルです。|  
|NSUser:\<通知サービスのユーザー名\>|省略可能: データベースを作成する権限を持つ notification services ユーザーのユーザー ID。|  
|NSUserPassword|省略可能: 指定された通知サービスのユーザーのパスワードです。|  
  
 構成ファイルに指定されたデータベース (BAM プライマリ インポート、BAM スター スキーマ、BAM アーカイブ、BAM 分析、警告の各データベース) が存在しない場合は作成します。 データベースの作成後、関連する BAM メタデータ テーブルとストアド プロシージャが作成されます。  
  
 BAM 警告を設定する場合、NSUser パラメーターおよび NSUserPassword パラメーターは省略できません。 コマンド ラインで NSUserPassword を指定しなかった場合、bm.exe により、パスワードの入力を求められます。  
  
> [!NOTE]
>  コマンドの実行後、トレース ログを見ると、AlertModule によって、次のような例外が出力されていることがあります。  
>   
>  "指定したアカウントはデータベース所有者です。 データベース所有者は常にビューへのアクセス権限を持っており、ビューに追加したり、ビューから削除することはできません。"  
>   
>  さらに、NotificationServices #19001 により、イベントの警告が出力されていることがあります。  
>   
>  コマンドの実行中にエラーが報告されなければ、これらのメッセージは無視してかまいません。  
  
> [!IMPORTANT]
>  既に BAM 警告が構成されているとき、警告セクションを含まない BAM 構成ファイルを使って setup-database コマンドを実行すると、今後、警告が生成されないよう、bm.exe により構成が上書きされます。  
  
 BAM データベースをセットアップするには、BAMPrimaryImport データベース、BAMStarSchema データベース、および BAMArchive データベースをホストする Microsoft SQL Server に対する管理者権限を持っている必要があります。 SQL Notification Services データベースを設定するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された他の管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。  
  
 **使用例**  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a>migrate-sql コマンド  
 **使用方法**  
  
 **bm.exe-から: sql2000-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<サーバー\> ][-データベース:\<データベース\>]**  
  
 \- または -  
  
 **bm.exe-から: sql2005-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<サーバー\> ][-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|: Sql2000|Microsoft SQL Server 2000 データベースからの変換であることを指定します。|  
|To:sql2008|Microsoft SQL Server 2008 データベースに変換することを指定します。|  
|: Sql2005|Microsoft SQL Server 2005 データベースから変換であることを指定します。|  
|To:sql2008|Microsoft SQL Server 2008 データベースに変換することを指定します。|  
|NSUser:\<通知サービスのユーザー名\>|省略可能: データベースを作成する権限を持つ Notification Services ユーザーのユーザー ID。|  
|NSUserPassword|省略可能: 指定した Notification Services ユーザーのパスワードです。|  
|サーバー:\<サーバー\>|省略可能: 変換後のデータベースが存在するサーバーの名前。 サーバーは、Microsoft SQL Server 2008 データベースをホストするコンピューターと同じドメインにする必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 名前の変換後のデータベースです。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から BAM インフラストラクチャを Microsoft SQL Server 2008 に移行します。 Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から Microsoft SQL Server 2008 に、データベース サーバーおよび分析サーバーをアップグレードした後は、このコマンドを使用します。  
  
 BAM 警告を構成した場合、NSUser パラメーターおよび NSUserPassword パラメーターは省略できません。 コマンド ラインで NSUserPassword を指定しなかった場合、bm.exe により、パスワードの入力を求められます。  
  
 SQL Server Notification Services データベースを移行するには、管理者権限を持っており、ローカルの Administrators グループのメンバーであることが必要です。また、追加で構成された他の管理者グループ (BTS Admins グループなど) のメンバーであることも必要です。  
  
> [!NOTE]
>  エラー メッセージを受け取る場合は、"エラー: コンピューターで NS$ BAMAlerts サービスを開始できません '\<コンピューター名\>' です。 サービスは適切な時間内に開始要求または制御要求に応答しませんでした。」が表示される場合は、サービスを手動で開始してみます。 移行時など、SQL Server が極端なビジー状態の場合は、サービスを再開できない場合があります。  
  
> [!NOTE]
>  Notification Services がインストールされているコンピューターで migrate-sql コマンドを実行するには、そのコンピューターのローカル管理者グループのメンバーである必要があります。  
  
 **使用例**  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a>enable-reference コマンド  
 **使用方法**  
  
 **bm.exe 参照を有効にする TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\> ]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|TargetServer:\<ターゲット サーバー\>|参照を有効にするサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。|  
|TargetDatabase:\<ターゲット データベース\>|参照を有効にするデータベースの名前です。|  
|サーバー:\<サーバー\>|省略可能: への参照を有効になっている対象サーバーとデータベースを持つサーバーの名前。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: への参照を有効になっている対象サーバーとデータベースを持つデータベースの名前。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 分散されている別の BAM プライマリ インポート データベースへの参照を有効にします。 対象となる BAM プライマリ インポート データベース上のビューやアクティビティのメタデータを、現在のデータベースからサブスクライブできます。 分散アクティビティを表示できるようにしたい場合に使用します。  
  
 対象サーバーを SQL Server のインスタンスとして指定できます (例 : 'mymachine2\myinstance')。  
  
 **使用例**  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a>get-references コマンド  
 **使用方法**  
  
 **bm.exe get 参照 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|サーバー:\<サーバー\>|省略可能: 参照の一覧を取得するサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: 参照の一覧を取得する対象のデータベースの名前です。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 コマンドを実行するコンピューターで有効にされている参照を一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a>disable-reference コマンド  
 **使用方法**  
  
 **bm.exe 無効参照 TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\> ]**  
  
 **パラメーター**  
  
|パラメーター|Description|  
|---------------|-----------------|  
|TargetServer:\<ターゲット サーバー\>|参照を無効にするサーバーの名前です。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。|  
|TargetDatabase:\<ターゲット データベース\>|参照を無効にするデータベースの名前です。|  
|サーバー:\<サーバー\>|省略可能: ターゲット参照をサーバーとデータベースが無効にするサーバーの名前。 このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。 サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。|  
|データベース:\<データベース\>|省略可能: を無効にするのには、参照を対象サーバー上のデータベースとデータベースの名前です。 指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。|  
  
 対象サーバー上の別の分散 BAM プライマリ インポート データベースへの参照を無効にします。  
  
 対象サーバーを SQL Server のインスタンスとして指定できます (例 : 'mymachine2\myinstance')。  
  
 **使用例**  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)