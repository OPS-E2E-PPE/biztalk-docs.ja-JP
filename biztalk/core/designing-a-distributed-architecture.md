---
title: 分散アーキテクチャの設計 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 156c7107abfd0fd140a5e7b07f06d00eabf7c961
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239426"
---
# <a name="designing-a-distributed-architecture"></a>分散アーキテクチャの設計
BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 トピックで示すアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱なセキュリティ上の潜在的な脅威の多くに対処します。 アーキテクチャを設計する際に優先度の一覧でセキュリティを高に設定する必要がある一方で、分散環境には高可用性、スケーラビリティ、パフォーマンスなどの追加の考慮事項があります。 このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーキテクチャの設計時に検討する追加のオプションについて説明します。  
  
## <a name="domains"></a>ドメイン  
 インターネットによる通信を主に利用する会社では、企業ドメインからイントラネット サービスを削除できます。 逆に、BizTalk Server を使用してイントラネット経由で他のアプリケーションやビジネス パートナーに接続する場合、境界ネットワークを削除できます。 場合は、会社は、インターネットとイントラネットに接続された通信の両方を少数のパートナーでは、境界ネットワークとイントラネット サービスを組み合わせることを検討する可能性があります。  
  
 データ ドメイン内の処理サーバーと SQL Server 間の通信の遅延を最小限にする必要がある場合で、ネットワーク スニッフィング、パケットの改ざん、ホストの偽装など、内部ネットワーク内のセキュリティに関する問題の心配がない場合、処理ドメインとデータ ドメイン間のファイアウォールを削除し、それらのドメインをマージできます。 インターネット プロトコル セキュリティ (IPsec) または Secure Sockets Layer (SSL) を使用して、あるサーバーから別のサーバーにデータが移動するときにそのデータを保護することをお勧めします。  
  
## <a name="sql-server-clustering"></a>SQL Server クラスタリング  
 このセクションでは詳しくは説明しませんが、フェールオーバー保護のためにデータベースをクラスタ化することを強くお勧めします。 SQL Server 2008 フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)です。  
  
## <a name="messagebox-database"></a>メッセージ ボックス データベース  
 会社のメッセージ スループットの要件によっては、メッセージ ボックス データベースを追加 (または削除) することが必要になる場合があります。 複数のメッセージ ボックスの詳細については、次を参照してください。 [Scaled-Out データベース](../core/scaled-out-databases.md)です。  
  
## <a name="see-also"></a>参照  
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [高可用性の計画](../core/planning-for-high-availability3.md)   
 [パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)