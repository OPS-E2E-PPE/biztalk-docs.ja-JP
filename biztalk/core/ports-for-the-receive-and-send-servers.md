---
title: "受信と送信サーバーのポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection strings
- servers, sending
- ports, servers
- servers, receiving
- BizTalk Server, service accounts
- SSO, service accounts
ms.assetid: 19cafe74-6676-4779-8ced-de0841dba19f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ddda71d04cf784f07cf8e0783775d7ae91e6d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-receive-and-send-servers"></a>受信サーバーと送信サーバーのポート
詳細については、BizTalk Server の展開をセキュリティで保護する、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の表は、受信サーバーと送信サーバーが必要なサービスにアクセスできるように構成する必要があるポートを示しています。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|ポート|[プロトコル]|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|BizTalk サービス アカウント|ファイル共有<br /><br /> EDI ドキュメント ホーム共有|受信/送信サーバー|445|TCP|ファイル アダプタのファイルの場所に対してファイルの取得や削除を行う|  
|BizTalk サービス アカウント|FTP サーバー|FTP サービス|20|TCP|FTP アダプタを使用して FTP サーバーに対してファイルの取得や削除を行う|  
|BizTalk サービス アカウント|FTP サーバー|FTP サービス|21|TCP|FTP アダプタを使用して FTP サーバーに対してファイルの取得や削除を行う|  
|BizTalk サービス アカウント|POP3 サーバー|POP3 サービス|110|TCP|POP3 アダプタを使用して POP3 サーバーから電子メールを取得する|  
|BizTalk サービス アカウント|処理サーバー|Windows メッセージ キュー|1801|TCP|BizTalk メッセージ キュー アダプタを使用して BizTalk ランタイムに対してメッセージを送受信する|  
|[接続文字列]|SQL アダプタの接続先|SQL Server|1433|TCP|SQL アダプタによって使用されるデータベースからメッセージを送受信する|  
|[接続文字列]|SQL アダプタの接続先|DTC|135|TCP|SQL アダプタの SQL Server へのトランザクション接続を確立する|  
|[接続文字列]|SQL アダプタの接続先|DTC|50000-50200|TCP|SQL アダプタのセカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk サービス アカウント|SMTP/Exchange|SMTP (SMTP)|25|TCP|SMPT アダプタを使用して SMTP サーバーに接続する|  
|ログオン ユーザー|BizTalk 管理データベース|SQL Server|1433|TCP|BizTalk 管理データベースを作成および構成する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|メッセージ ボックス データベース|SQL Server|1433|TCP|メッセージ ボックス データベースを作成および構成する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、ホストを作成する|  
|ログオン ユーザー|メッセージ ボックス データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|SSO サービス アカウント|SSO データベース|SQL Server|1433|TCP|エンタープライズ シングル サインオン サービスを使用して SSO データベースに接続する|  
|ログオン ユーザー|SSO データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、SSO データベースに接続する|  
|ログオン ユーザー|SSO データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|追跡データベース|SQL Server|1433|TCP|追跡データベースを作成および構成する|  
|ログオン ユーザー|追跡データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立する|  
|ログオン ユーザー|追跡データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|SQL Server|1433|TCP|ビジネス ルール エンジン データベースを作成および構成する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを作成、構成、および更新する|  
|ログオン ユーザー|ビジネス ルール エンジン データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)|TCP|BAM 分析データベースの情報を更新および取得する|  
|ログオン ユーザー|BAM 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピューター上の OLAP データ ファイル (.mdb) を作成するには|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|分析用のデータ (PivotTable® レポート) を取得する|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)|TCP|BizTalk 分析データベースの構成を作成し**注:**処理サーバーは、BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続する必要があります。|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピューターで OLAP データ ファイル (.mdb) を作成する**注:**処理サーバーは、BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続する必要があります。|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP (OLAP)|2725|TCP|データベースを作成および構成し、分析用のデータ (PivotTable レポート) を取得する|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|RPC|135|TCP|SQL Server へのトランザクション接続を確立し、SSO サービスを使用してマスタ シークレット サーバーに接続する|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|セカンダリ RPC|50000-50200|TCP|セカンダリ PRC ポートを開いて、SSO サービスを使用してマスタ シークレット サーバーに接続する **注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk ホスト インスタンス用のサービス アカウント|メッセージ ボックス データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス用のサービス アカウント|BizTalk 管理データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス用のサービス アカウント|SSO データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
|BizTalk ホスト インスタンス用のサービス アカウント|追跡データベース|SQL Server|1433|TCP|ランタイム操作中にデータベースの情報を更新および取得する|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [HTTP アダプタのセキュリティに関する推奨事項](../core/http-adapter-security-recommendations.md)   
 [SOAP アダプタのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)   
 [FTP アダプタのセキュリティに関する推奨事項](http://msdn.microsoft.com/library/ea7c0577-9d72-4d63-94e7-8f649c6e713f)   
 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)   
 [ファイル アダプタのセキュリティに関する推奨事項](http://msdn.microsoft.com/library/fe4d51c0-b697-457b-bf27-f1cf6965d954)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)