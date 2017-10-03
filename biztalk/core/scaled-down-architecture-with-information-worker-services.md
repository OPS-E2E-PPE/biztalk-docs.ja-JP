---
title: "縮小されたアーキテクチャでは、インフォメーション ワーカー サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d02558e5904bf740c09ea0db614b2189555ac75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture-with-information-worker-services"></a>インフォメーション ワーカー サービスを使用した縮小されたアーキテクチャ
BizTalk Server の展開のシステム アーキテクチャに関する詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の図は、インフォメーション ワーカー サービスを含むサンプル BizTalk Server アーキテクチャを示しています。このアーキテクチャでは、ドメインの一部と BizTalk Server を組み合わせて、必要なサーバーおよびファイアウォールの数を削減します。 このアーキテクチャは、最も分散されたアーキテクチャではありませんが、BizTalk Server をその機能に基づいて分離しています。  
  
 ![スケール ダウン トポロジ](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")  
  
        Scaled Down Architecture with Information Worker Services  
  
 上記の図では、サービス インターフェイスおよびサービス ドメイン内のサーバーは、物理サーバーではなく BizTalk ホストに対応しています。 マスタ シークレット サーバーおよび管理ツールはスタンドアロン コンピュータに保持しておくことをお勧めしますが、複数のコンピュータ上で実行している追跡ホスト、処理ホスト、送信ホスト、および受信ホスト用にホスト インスタンスを配置できます。 同様に、境界ネットワーク内のサーバーは、論理的な場所に対応しています。  
  
 境界ネットワーク内にある、SMTP、Windows メッセージ キュー (MSMQ)、ファイル、SQL 用のサーバーはそれぞれメール サーバー、キュー、ディレクトリ、SQL Server に対応し、サービス インターフェイス ドメイン内の BizTalk 受信ホストと送信ホストはここからメッセージの送受信を行います。  
  
 データ ドメイン内の BAM データベースは、BAM プライマリ インポート データベース、BAM 分析データベース、BAM スター スキーマ データベース、および BAM アーカイブ データベースです。 データ ドメイン内の追跡データベースおよび分析データベースは、BizTalk Server で追跡情報を格納する際に使用するデータベースです。  
  
## <a name="see-also"></a>参照  
 [縮小されたアーキテクチャ](../core/scaled-down-architecture.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)