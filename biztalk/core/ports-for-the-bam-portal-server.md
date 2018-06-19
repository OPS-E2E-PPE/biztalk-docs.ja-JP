---
title: BAM ポータル サーバーのポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df67c31c-a7a3-4bff-9374-0d8a0cf0ad21
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adfa47415c1e367941203d20533c5e3ac3f431da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266466"
---
# <a name="ports-for-the-bam-portal-server"></a>BAM ポータル サーバーのポート
詳細については、BizTalk Server の展開をセキュリティで保護する、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の表は、BAM ポータル Web サイトが必要なサービスにアクセスできるように構成する必要があるポートを示しています。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|ポート|[プロトコル]|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|BizTalk 管理データベース|SQL Server|1433|TCP|データベースを作成および構成する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを作成し、このデータベースに接続する**注:** をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|アプリケーション プール|受信クライアント|HTTP(S)|80 または 443|TCP|Web サイトの受信トラフィック用|  
|ログオン ユーザー|メッセージ ボックス データベース|SQL Server|1433|TCP|データベースを作成および構成する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:** をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|SSO データベースに接続する|  
|ログオン ユーザー|追跡データベース|SQL Server|1433|TCP|データベースを作成および構成する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|SQL Server|1433|TCP|データベースを作成および構成する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:** をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2393|TCP|データベースを作成および構成する|  
|ログオン ユーザー|BAM 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピュータに OLAP データ ファイル (.mdb) を作成する|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|データベースの情報を更新および取得する|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|SSO サービスを使用してデータベースの情報を更新および取得する|  
|SSO サービス アカウント|[マスター シークレット サーバー]|[マスター シークレット サーバー]|135|TCP|SQL Server へのトランザクション接続を確立し、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
|SSO サービス|[マスター シークレット サーバー]|セカンダリ RPC|50000-50200|TCP|セカンダリ PRC ポートを開いて、SSO サービスを使用してマスタ シークレット サーバーに接続する **注:** をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk ホスト インスタンス|メッセージ ボックス データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス|BizTalk 管理データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス|SSO データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス|追跡データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BAM アプリケーション プール ユーザー|BAM Notification Services|SQL Server|1433|TCP|BAM Notification Services データベースにアクセスするには|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [BAM ポータルのセキュリティに関する考慮事項](../core/security-considerations-for-the-bam-portal.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)