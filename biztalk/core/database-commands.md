---
title: データベース コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5bb9d25db876fb7d48900b1ee47f187544a4b87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389772"
---
# <a name="database-commands"></a>データベース コマンド
BAM 管理ユーティリティのデータベース コマンドを使用して、BAM データベースを操作できます。  
  
-   セットアップ-データベース:特定の BAM データベースを作成します。  
  
-   移行-sql:BAM データベースを移行します。  
  
    -   Microsoft SQL Server 2008 への Microsoft SQL Server 2000  
  
    -   Microsoft SQL Server 2008 への Microsoft SQL Server 2005  
  
-   参照の有効化:分散 BAM プライマリ インポート データベースへの参照を有効にします。  
  
-   get 参照:分散 BAM プライマリ インポート データベースへの参照の一覧を取得します。  
  
-   参照の無効化:BAM プライマリ インポート データベースへの参照を無効にします。  
  
> [!NOTE]
>  含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。 トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。 スイッチは、通常の BM コマンドと組み合わせて使用できます。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="setup-databases-command"></a>setup-databases コマンド  
 **使用方法**  
  
 **bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|ConfigFile:\<構成ファイル\>|データベースを作成するための BAM 構成ファイル。|  
|NSUser:\<通知サービスのユーザー名\>|省略可能:データベースを作成するアクセス許可を持つ notification services ユーザーのユーザー ID。|  
|NSUserPassword|省略可能:指定した通知サービスのユーザーのパスワード。|  
  
 まだ存在しない場合、構成ファイル (BAM プライマリ インポート、BAM スター スキーマ、BAM アーカイブ、BAM 分析、およびアラート) で説明されているデータベースを作成します。 データベースが作成されると、コマンドは、関連する BAM メタデータ テーブルおよびストアド プロシージャを作成します。  
  
 BAM 警告を設定している場合、NSUser および NSUserPassword パラメーターが必要です。 コマンドラインで NSUserPassword を指定しない場合は、bm.exe はパスワードを求めます。  
  
> [!NOTE]
>  コマンドの完了後に、トレース ログに alertmodule によって、例外を確認してください可能性があります。  
>   
>  "指定されたアカウントは、データベース所有者です。 データベース所有者常にビューにアクセスして追加をまたはできませんビューから削除します。"  
>   
>  さらに、#19001 により #19001 からのイベントで警告が表示することがあります。  
>   
>  コマンドの実行中にエラーが報告されていない場合は、これらの通知を安全に無視できます。  
  
> [!IMPORTANT]
>  セットアップ データベース コマンドを実行する、[アラート] セクションを含まない BAM 構成ファイルを使用して BAM 警告を構成済みである場合は、アラートが機能しなくなりますように bm.exe は構成を上書きします。  
  
 BAM データベースを設定するには、BAMPrimaryImport、bamstarschema データベース、および BAMArchive データベースをホストする Microsoft SQL server の管理者のアクセス許可があります。 SQL Notification Services データベースを設定するにする必要があります管理者権限し、ローカルの administrators グループのメンバーであるだけでなく、他の管理者グループ、BTS Admins グループなど、構成されているのメンバーであります。  
  
 **使用例**  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a>migrate-sql コマンド  
 **使用方法**  
  
 **bm.exe-から: sql2000-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<server\>] [-データベース:\<データベース\>]**  
  
 \- または -  
  
 **bm.exe-から: sql2005-を: sql2008 [- NSUser:\<通知サービスのユーザー名\>] [- NSUserPassword:\<通知サービスのユーザー パスワード\>] [-サーバー:\<server\>] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|: Sql2000|Microsoft SQL Server 2000 データベースから変換することを指定します。|  
|: Sql2008|Microsoft SQL Server 2008 データベースに変換することを指定します。|  
|: Sql2005|Microsoft SQL Server 2005 データベースから変換することを指定します。|  
|: Sql2008|Microsoft SQL Server 2008 データベースに変換することを指定します。|  
|NSUser:\<通知サービスのユーザー名\>|省略可能:データベースを作成する権限を持つ Notification Services ユーザーのユーザー ID。|  
|NSUserPassword|省略可能:指定した Notification Services ユーザーのパスワードです。|  
|サーバー:\<サーバー\>|省略可能:変換されたデータベースが存在するサーバーの名前。 Microsoft SQL Server 2008 データベースをホストするコンピューターと同じドメイン内、サーバーがある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:クリックし、変換されたデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から BAM インフラストラクチャを Microsoft SQL Server 2008 に移行します。 Microsoft SQL Server 2000 または Microsoft SQL Server 2005 から Microsoft SQL Server 2008 に、データベース サーバーおよび分析サーバーをアップグレードした後は、このコマンドを使用します。  
  
 BAM 警告が構成されている場合、NSUser および NSUserPassword パラメーターが必要です。 コマンドラインで NSUserPassword を指定しない場合は、bm.exe はパスワードを求めます。  
  
 SQL Server Notification Services データベースを移行する必要があります管理者権限し、ローカルの administrators グループのメンバーであるだけでなく、他の管理者グループ、BTS など、構成されているのメンバーであります。管理者グループ。  
  
> [!NOTE]
>  エラー メッセージを受信する場合は、"エラー。コンピューターで NS$ BAMAlerts サービスを開始できません '\<コンピューター名\>'。 サービスが適切な方法で開始または制御要求に応答しませんでした"、サービスを手動で再起動してみてください。 SQL サーバーが移行中に極端なビジー状態である場合、サービスが再起動しない場合があります。  
  
> [!NOTE]
>  Notification Services がインストールされているコンピューターで migrate-sql コマンドを実行する方法には、そのコンピューターのローカルの Administrators グループに属している必要があります。  
  
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
  
 **bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|TargetServer:\<ターゲット サーバー\>|参照を有効にするサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。|  
|TargetDatabase:\<ターゲット データベース\>|参照を有効にするデータベースの名前。|  
|サーバー:\<サーバー\>|省略可能:ターゲット サーバーとデータベースへの参照を有効にする必要がありますサーバーの名前。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:ターゲット サーバーとデータベースへの参照を有効にする必要がありますデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 別の分散 BAM プライマリ インポート データベースへの参照を有効にします。 これにより、ビューやアクティビティのメタデータを現在のデータベースからのサブスクリプションが、ターゲットの BAM プライマリ インポート データベースにできます。 これを使用するには分散アクティビティのナビゲーションを有効にします。  
  
 ターゲット サーバーは、SQL Server、たとえば、'mymachine2\myinstance' のインスタンスとして指定できます。  
  
 **使用例**  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a>get-references コマンド  
 **使用方法**  
  
 **bm.exe の get 参照 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|サーバー:\<サーバー\>|省略可能:参照の一覧を取得するサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:参照の一覧を取得する対象のデータベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 コマンドを実行するコンピューターで有効になっている参照を一覧表示します。  
  
 **使用例**  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a>disable-reference コマンド  
 **使用方法**  
  
 **bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**  
  
 **パラメーター**  
  
|パラメーター|説明|  
|---------------|-----------------|  
|TargetServer:\<ターゲット サーバー\>|参照を無効にするサーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。|  
|TargetDatabase:\<ターゲット データベース\>|参照を無効にするデータベースの名前。|  
|サーバー:\<サーバー\>|省略可能:サーバーとデータベースで無効にするが、ターゲットへの参照、サーバーの名前。 サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。 サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。|  
|データベース:\<データベース\>|省略可能:サーバーとデータベースで無効にするが、ターゲットへの参照データベースの名前。 名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。|  
  
 ターゲット サーバー上の別の分散 BAM プライマリ インポート データベースへの参照を無効にします。  
  
 ターゲット サーバーは、SQL Server、たとえば、'mymachine2\myinstance' のインスタンスとして指定できます。  
  
 **使用例**  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)