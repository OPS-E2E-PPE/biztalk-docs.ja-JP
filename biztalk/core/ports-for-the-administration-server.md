---
title: "管理サーバーのポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, administration server
- administration server
ms.assetid: dc0094b2-5ba2-4b8f-84aa-b6232be358ee
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd44158d721f8b6d247b51073e9f9e77ea7f6deb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-administration-server"></a>管理サーバーのポート
詳細については、BizTalk Server の展開をセキュリティで保護する、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の表は、管理サーバーが必要なサービスにアクセスできるように構成する必要があるポートを示しています。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 
  
|[同期先サーバー]|対象のサービス|ポート|[プロトコル]|Reason|  
|---|---|---|---|---|  
|BizTalk 管理データベース|SQL Server|1433|TCP|BizTalk 管理データベースの情報を作成して構成し、その情報にアクセスする|  
|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、データベースを更新する|  
|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|BAM プライマリ インポート データベース|SQL Server|1433|TCP|BizTalk 管理コンソール (または WMI) を使用して、BAM プライマリ インポート データベースが存在することを確認する|  
|BizTalk 管理データベース|SQL Server|1433|TCP|BizTalk 管理コンソール (または WMI) を使用して、構成データの表示とホスト インスタンスのインストールを行う|  
|BizTalk 管理データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、BizTalk 管理コンソール (または WMI) を使用してホストを作成し更新する|  
|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用してホストを作成する**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|メッセージ ボックス データベース|SQL Server|1433|TCP|BizTalk 管理コンソール (または WMI) を使用してホストを作成する|  
|メッセージ ボックス データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、BizTalk 管理コンソール (または WMI) を使用してホストを作成し更新する|  
|メッセージ ボックス データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用してホストを作成する**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|処理サーバー|WMI/RPC|135|TCP|SQL Server へのトランザクション接続を確立し、BizTalk 管理コンソール (または WMI) を使用してグループに新しいサーバーを追加する|  
|処理サーバー|WMI/RPC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用して、グループに新しいサーバーを追加する**注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|処理サーバー|サーバー メッセージ ブロック (SMB)|445|TCP|ファイル共有にアクセスするために使用します。 BizTalk 管理コンソール (または WMI) を使用してホスト インスタンスのインストールにも必要可能性があります。|  
|ビジネス ルール エンジン データベース|SQL Server|1433|TCP|ビジネス ルール エンジン展開ウィザードを使用して、ビジネス ルールを展開する|  
|ビジネス ルール エンジン データベース|DTC|135|TCP|SQL Server へのトランザクション接続を確立し、ビジネス ルール エンジン展開ウィザードを使用してビジネス ルールを展開する|  
|ビジネス ルール エンジン データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを開いて、ビジネス ルール エンジン展開ウィザードを使用してビジネス ルールを展開する **注:**をサーバーの負荷に応じて複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk 管理データベース|SQL Server|1433|TCP|アセンブリを展開する|  
|追跡データベース|SQL Server|1433|TCP|アセンブリを展開する|  
|IIS サーバー|IIS|1164|TCP|HTTP または Web サービス ポートをパックする BizTalk アプリケーションの展開を有効にするには、MSI に IIS サーバーでホストされます。|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [アプリケーションの展開のセキュリティに関する推奨事項](../core/application-deployment-security-recommendations.md)   
 [メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)