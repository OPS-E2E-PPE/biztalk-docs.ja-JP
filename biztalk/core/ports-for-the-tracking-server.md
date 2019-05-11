---
title: 追跡サーバーのポート |Microsoft Docs
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
ms.openlocfilehash: 27fe3413478fc0e0b507eb61bdb559cd78874489
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394849"
---
# <a name="ports-for-the-tracking-server"></a>追跡サーバーのポート
BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。  
  
 次の表は、ポートの追跡に必要なサービスにアクセスするサーバーの構成する必要があります。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|BizTalk 管理データベース|SQL Server|1433|TCP|作成して、BizTalk 管理データベースを構成するには|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|135|TCP|SQL Server を更新して、データベースから情報を取得するトランザクションの接続を確立します。|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|SSO データベース|SQL Server|1433|TCP|SSO データベースに接続する SSO サービス|  
|ログオン ユーザー|BAM プライマリ インポート データベース|SQL Server|1433|TCP|BAM プライマリ インポート データベースを検証します。 追跡ホストは、実行時に、このデータベースに接続します。|  
|ログオン ユーザー|BAM スター スキーマ データベース|SQL Server|1433||更新し、データベースから情報を取得します。 **注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|445|TCP|リモート コンピューター上の OLAP データ ファイル (.mdb) を作成します。 **注:** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)||作成して、BAM 分析データベースを構成する**に注意してください。** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続します。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|分析 (PivotTable レポート) 用のデータ取得に対して**に注意してください。** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続します。|  
|ログオン ユーザー|追跡データベース|SQL Server|1433|TCP|データベースの情報を更新および取得する|  
|ログオン ユーザー|メッセージ ボックス データベース|SQL|1433|TCP|データベースの情報を更新および取得する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|135|TCO|SQL Server への接続をトランザクション|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|50000-50200||セカンダリ RPC ポート|  
|ログオン ユーザー|BAM アーカイブ データベース|SQL Server|1433|TCP|更新して、データベースから情報を取得**に注意してください。** 追跡ホストは、このサーバーから新しい BizTalk グループを作成する BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続します。|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|データベースの情報を更新および取得する|  
|SSO サービス アカウント|[マスター シークレット サーバー]|マスタ シークレット サービス|135|TCP|SQL Server へのトランザクション接続を確立し、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
|SSO サービス アカウント|[マスター シークレット サーバー]|セカンダリ RPC|50000-50200|TCP|セカンダリ RPC ポートをマスター シークレット サーバーに接続する SSO サービス|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)   
 [BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)