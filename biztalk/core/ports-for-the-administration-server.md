---
title: 管理サーバーのポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, administration server
- administration server
ms.assetid: dc0094b2-5ba2-4b8f-84aa-b6232be358ee
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6e6a548604f74f6da6a7d17cb8a5a4be13e7457
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394877"
---
# <a name="ports-for-the-administration-server"></a>管理サーバーのポート
BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。  
  
 次の表は、必要なサービスにアクセスする管理サーバーを構成する必要がありますポートを一覧表示します。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 
  
|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|---|---|---|---|---|  
|BizTalk 管理データベース|SQL Server|1433|TCP|作成、構成、および BizTalk 管理データベースの情報にアクセスするには|  
|BizTalk 管理データベース|DTC|135|TCP|SQL Server データベースを更新するトランザクションの接続を確立します。|  
|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポート**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|BAM プライマリ インポート データベース|SQL Server|1433|TCP|BizTalk 管理コンソール (または WMI) を使用してが存在する BAM プライマリ インポート データベースを確認するには|  
|BizTalk 管理データベース|SQL Server|1433|TCP|構成データを表示し、BizTalk 管理コンソール (または WMI) を使用してホスト インスタンスのインストール|  
|BizTalk 管理データベース|DTC|135|TCP|SQL Server を作成し、BizTalk 管理コンソール (または WMI) を使用してホストを更新するトランザクションの接続を確立します。|  
|BizTalk 管理データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用してホストを作成する**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|メッセージ ボックス データベース|SQL Server|1433|TCP|BizTalk 管理コンソール (または WMI) を使用してホストを作成するには|  
|メッセージ ボックス データベース|DTC|135|TCP|SQL Server を作成し、BizTalk 管理コンソール (または WMI) を使用してホストを更新するトランザクションの接続を確立します。|  
|メッセージ ボックス データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用してホストを作成する**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|処理サーバー|WMI/RPC|135|TCP|BizTalk 管理コンソール (または WMI) を使用して、グループに新しいサーバーを追加する SQL Server への接続をトランザクション|  
|処理サーバー|WMI/RPC|50000-50200|TCP|セカンダリ RPC ポートを BizTalk 管理コンソール (または WMI) を使用して、グループに新しいサーバーを追加する**に注意してください。** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|処理サーバー|サーバー メッセージ ブロック (SMB)|445|TCP|ファイル共有にアクセスするために使用します。 BizTalk 管理コンソール (または WMI) を使用してホスト インスタンスをインストールする必要も可能性があります。|  
|ビジネス ルール エンジン データベース|SQL Server|1433|TCP|ビジネス ルール エンジン展開ウィザードを使用してビジネス ルールを展開するには|  
|ビジネス ルール エンジン データベース|DTC|135|TCP|ビジネス ルール エンジン展開ウィザードを使用してビジネス ルールを展開する SQL Server への接続をトランザクション|  
|ビジネス ルール エンジン データベース|DTC|50000-50200|TCP|セカンダリ RPC ポートがビジネス ルール エンジン展開ウィザードを使用してビジネス ルールを展開するには。 **注:** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
|BizTalk 管理データベース|SQL Server|1433|TCP|アセンブリを配置するには|  
|追跡データベース|SQL Server|1433|TCP|アセンブリを配置するには|  
|IIS サーバー|IIS|1164|TCP|HTTP または Web サービス ポートをパックする BizTalk アプリケーションの展開を有効にするには、MSI に IIS サーバーでホストされます。|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [アプリケーションの展開のセキュリティに関する推奨事項](../core/application-deployment-security-recommendations.md)   
 [メッセージとインスタンス データ追跡のセキュリティに関する考慮事項](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)