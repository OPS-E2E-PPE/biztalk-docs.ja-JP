---
title: 追跡サーバーのポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking server
- ports, tracking server
ms.assetid: 4b4913a4-7d8d-4fd0-a116-ba868c4ad7da
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975f5e42c800a6d4ae4015108afa2650b2c7f626
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266354"
---
# <a name="ports-for-the-tracking-server"></a>追跡サーバーのポート
詳細については、BizTalk Server の展開をセキュリティで保護する、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の表は、追跡サーバーが必要なサービスにアクセスできるように構成する必要があるポートを示しています。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|ポート|[プロトコル]|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|BizTalk 管理データベース|SQL Server|1433|TCP|BizTalk 管理データベースを作成および構成する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースの情報を更新および取得する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:** をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|SSO データベース|SQL Server|1433|TCP|SSO サービスを使用して SSO データベースに接続する|  
|ログオン ユーザー|BAM プライマリ インポート データベース|SQL Server|1433|TCP|BAM プライマリ インポート データベースを検証する。 追跡ホストは実行時にこのデータベースに接続します。|  
|ログオン ユーザー|BAM スター スキーマ データベース|SQL Server|1433||更新して、データベースから情報を取得します。 **注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみこのデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|445|TCP|リモート コンピューター上の OLAP データ ファイル (.mdb) を作成します。 **注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみこのデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)||作成して、BAM 分析データベースを構成する**注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみこのデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|分析 (PivotTable レポート) 用のデータを取得できる**注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみこのデータベースに接続します。|  
|ログオン ユーザー|追跡データベース|SQL Server|1433|TCP|データベースの情報を更新および取得する|  
|ログオン ユーザー|メッセージ ボックス データベース|SQL|1433|TCP|データベースの情報を更新および取得する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|135|TCO|SQL Server へのトランザクション接続を確立する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|50000-50200||セカンダリ RPC ポート|  
|ログオン ユーザー|BAM アーカイブ データベース|SQL Server|1433|TCP|更新して、データベースから情報を取得**注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみこのデータベースに接続します。|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|データベースの情報を更新および取得する|  
|SSO サービス アカウント|[マスター シークレット サーバー]|マスタ シークレット サービス|135|TCP|SQL Server へのトランザクション接続を確立し、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
|SSO サービス アカウント|[マスター シークレット サーバー]|セカンダリ RPC|50000-50200|TCP|セカンダリ RPC ポートを開いて、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)   
 [BizTalk Server 2013 および 2013 R2 のインストール概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)