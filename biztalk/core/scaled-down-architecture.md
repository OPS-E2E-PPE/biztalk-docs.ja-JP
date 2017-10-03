---
title: "縮小されたアーキテクチャ |Microsoft ドキュメント"
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
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a112f3f737a1a5aec0cfac16b7689d3dada1e8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture"></a>縮小されたアーキテクチャ
詳細については、システムのアーキテクチャの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を参照してください[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 次の図は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のサンプル アーキテクチャを示しています。このアーキテクチャでは、一部のドメインと BizTalk Server を組み合わせて、必要なサーバーおよびファイアウォールの数を削減します。 このアーキテクチャは、最も分散されたアーキテクチャではありませんが、BizTalk Server をその機能に基づいて分離しています。  
  
 ![縮小されたアーキテクチャ](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")  
  
        Scaled Down Architecture  
  
 上記の図では、サービス インターフェイスおよびサービス ドメイン内のサーバーは、物理サーバーではなく BizTalk ホストに対応しています。 マスタ シークレット サーバーおよび管理ツールはスタンドアロン コンピュータに保持しておくことをお勧めしますが、複数のコンピュータ上で実行している追跡ホスト、処理ホスト、送信ホスト、および受信ホスト用にホスト インスタンスを配置できます。 同様に、境界ネットワーク内のサーバーは、論理的な場所に対応しています。  
  
 境界ネットワーク内にある、SMTP、メッセージ キュー、ファイル、SQL 用のサーバーはそれぞれ、メール サーバー、キュー、ディレクトリ、SQL Server に対応し、処理ドメインおよびサービス ドメイン内の BizTalk 受信ホストおよび送信ホストはここからメッセージの送受信を行います。  
  
## <a name="see-also"></a>参照  
 [縮小されたインフォメーション ワーカー サービスのアーキテクチャ](../core/scaled-down-architecture-with-information-worker-services.md)   
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)