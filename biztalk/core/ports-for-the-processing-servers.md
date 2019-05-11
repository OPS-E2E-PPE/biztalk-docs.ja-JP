---
title: 処理サーバーのポート |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- servers, processing
- ports, processing servers
ms.assetid: 0207b68f-8769-4674-aadc-b3a67b6f210b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b352828afa630f90baec332fe20a9db8b92a6cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394839"
---
# <a name="ports-for-the-processing-servers"></a>処理サーバーのポート
BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。  
  
 次の表は、ポートが必要なサービスにアクセスする処理サーバー用に構成する必要があります。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|BizTalk 管理データベース|SQL Server|1433|TCP|作成して、BizTalk 管理データベースを構成するには|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|メッセージ ボックス データベース|SQL Server|1433|TCP|作成して、メッセージ ボックス データベースを構成するには|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|135|TCP|ホストを作成する SQL Server への接続をトランザクション|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|SSO データベースに接続するエンタープライズ シングル サインオン サービス|  
|ログオン ユーザー|SSO データベース|DTC|135|TCP|SSO データベースに接続する SQL Server への接続をトランザクション|  
|ログオン ユーザー|SSO データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|追跡データベース|SQL Server|1433|TCP|作成して、追跡データベースを構成するには|  
|ログオン ユーザー|追跡データベース|DTC|135|TCP|SQL Server への接続をトランザクション|  
|ログオン ユーザー|追跡データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|SQL Server|1433|TCP|作成して、ビジネス ルール エンジン データベースを構成するには|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2393|TCP|更新および BAM 分析データベースから情報を取得するには|  
|ログオン ユーザー|BAM 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピューター上の OLAP データ ファイル (.mdb) を作成するには|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|分析 (PivotTable レポート) 用のデータの取得|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP (OLAP)|2393|TCP|作成して BizTalk 分析データベースを構成する**に注意してください。** 処理サーバーは、BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続する必要があります。|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピューターで OLAP データ ファイル (.mdb) を作成する**に注意してください。** 処理サーバーは、BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続する必要があります。|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP (OLAP)|2725|TCP|作成して、データベースを構成してには、、データ分析 (PivotTable レポート) を取得するには|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|RPC|135|TCP|SQL Server へのトランザクション接続を確立し、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|セカンダリ RPC|50000-50200|TCP|セカンダリ PRC ポートを開いて、SSO サービスを使用してマスタ シークレット サーバーに接続する **注:** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk ホスト インスタンスのサービス アカウント|メッセージ ボックス データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンスのサービス アカウント|BizTalk 管理データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンスのサービス アカウント|SSO データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンスのサービス アカウント|追跡データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [BizTalk Server ランタイムのセキュリティに関する推奨事項](../core/biztalk-server-runtime-security-recommendations.md)   
 [ビジネス ルール エンジンのセキュリティに関する推奨事項](../core/business-rule-engine-security-recommendations.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)