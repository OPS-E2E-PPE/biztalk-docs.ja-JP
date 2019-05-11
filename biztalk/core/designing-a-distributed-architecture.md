---
title: 分散アーキテクチャの設計 |Microsoft Docs
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
ms.openlocfilehash: b3e495fd45074398fbdedec2e4b8e3fb544f9e55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389720"
---
# <a name="designing-a-distributed-architecture"></a>分散アーキテクチャの設計
BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 トピックに示されているアーキテクチャ[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)BizTalk 環境を脆弱性のある潜在的なセキュリティ脅威の多くを解決します。 アーキテクチャを設計するときに、セキュリティが高優先順位の一覧にする必要がありますが、高可用性、スケーラビリティ、パフォーマンスなどの分散環境で追加の考慮事項があります。 このセクションを設計するときに検討する追加のオプションを提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アーキテクチャ。  
  
## <a name="domains"></a>ドメイン  
 会社では、ほとんどのインターネットによる通信を実行する場合は、会社のドメインからイントラネット サービスを削除できます。 逆に、他のアプリケーションや、イントラネット経由で接続するビジネス パートナーへの接続に BizTalk Server を使用する場合は、境界ネットワークを削除できます。 存在する場合、会社はパートナーの数が少ないインターネットおよびイントラネットによる通信の両方に、イントラネット サービスと境界ネットワークを組み合わせることを検討できます。  
  
 場合は、データ ドメイン内の SQL サーバーの処理サーバーとの間の通信での待機時間を最小限に抑えたいし、セキュリティ問題など、ネットワーク スニッフィング、パケットの改ざん、ホストの内部ネットワークで偽装が問題ではありません、処理とデータのドメイン間のファイアウォールを削除し、これらのドメインをマージします。 インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を別に 1 つのサーバーから移動するデータを保護するために使用をお勧めします。  
  
## <a name="sql-server-clustering"></a>SQL Server クラスタ リング  
 このセクションで詳しく説明しませんがフェールオーバー保護のため、データベースをクラスタ リングを強くお勧めします。 SQL Server 2008 フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)します。  
  
## <a name="messagebox-database"></a>メッセージ ボックス データベース  
 会社のメッセージ スループット要件によっては、メッセージ ボックス データベースの追加 (または削除) する必要があります。 複数のメッセージ ボックスの詳細については、次を参照してください。 [Scaled-Out データベース](../core/scaled-out-databases.md)します。  
  
## <a name="see-also"></a>参照  
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [高可用性の計画](../core/planning-for-high-availability3.md)   
 [パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)   
 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)