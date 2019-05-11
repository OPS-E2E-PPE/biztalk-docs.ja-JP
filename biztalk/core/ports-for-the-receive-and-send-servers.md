---
title: 受信と送信サーバーのポート |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection strings
- servers, sending
- ports, servers
- servers, receiving
- BizTalk Server, service accounts
- SSO, service accounts
ms.assetid: 19cafe74-6676-4779-8ced-de0841dba19f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e54f655cf736bf01a25dfcdb2fe3d5b1cf959a1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394823"
---
# <a name="ports-for-the-receive-and-send-servers"></a>受信と送信サーバーのポート
BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。  
  
 次の表は、ポート、受信用に構成し、必要なサービスにアクセスするサーバーを送信する必要があります。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|BizTalk サービス アカウント|ファイル共有<br /><br /> EDI ドキュメント ホーム共有|受信/送信サーバー|445|TCP|取得し、ファイル アダプターのファイルの場所にファイルを削除|  
|BizTalk サービス アカウント|FTP サーバー|FTP サービス|20|TCP|取得し、FTP サーバーにファイルをドロップする FTP アダプターの|  
|BizTalk サービス アカウント|FTP サーバー|FTP サービス|21|TCP|取得し、FTP サーバーにファイルをドロップする FTP アダプターの|  
|BizTalk サービス アカウント|POP3 サーバー|POP3 サービス|110|TCP|POP3 アダプターが POP3 サーバーから電子メールを取得するには|  
|BizTalk サービス アカウント|処理サーバー|Windows メッセージ キュー|1801|TCP|BizTalk ランタイムにメッセージを送受信する BizTalk メッセージ キュー アダプタの|  
|[接続文字列]|SQL アダプタの接続先|SQL Server|1433|TCP|取得し、SQL アダプターによって使用されるデータベースからメッセージを送信|  
|[接続文字列]|SQL アダプタの接続先|DTC|135|TCP|SQL Server を SQL アダプターのトランザクション接続を確立|  
|[接続文字列]|SQL アダプタの接続先|DTC|50000-50200|TCP|SQL アダプタのセカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk サービス アカウント|SMTP/Exchange|SMTP (SMTP)|25|TCP|SMPT アダプタを SMTP サーバーに接続するには|  
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
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)|TCP|更新および BAM 分析データベースから情報を取得するには|  
|ログオン ユーザー|BAM 分析データベース|OLAP サーバー ファイル システム|445|TCP|リモート コンピューター上の OLAP データ ファイル (.mdb) を作成するには|  
|ログオン ユーザー|BAM 分析データベース|OLAP (OLAP)|2725|TCP|分析 (PivotTable® レポート) 用のデータの取得|  
|ログオン ユーザー|BizTalk 分析データベース|OLAP (OLAP)|2383 (SQL Server 2005 Analysis Services)|TCP|作成して BizTalk 分析データベースを構成する**に注意してください。** 処理サーバーは、BizTalk 構成マネージャーを実行する場合にのみ、このデータベースに接続する必要があります。|  
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
 [HTTP アダプタのセキュリティに関する推奨事項](../core/http-adapter-security-recommendations.md)   
 [SOAP アダプタのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)   
 [FTP アダプターのセキュリティに関する推奨事項](http://msdn.microsoft.com/library/ea7c0577-9d72-4d63-94e7-8f649c6e713f)   
 [SMTP アダプタのセキュリティに関する推奨事項](../core/smtp-adapter-security-recommendations.md)   
 [ファイル アダプタのセキュリティに関する推奨事項](http://msdn.microsoft.com/library/fe4d51c0-b697-457b-bf27-f1cf6965d954)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)