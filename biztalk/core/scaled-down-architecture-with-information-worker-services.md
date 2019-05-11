---
title: 縮小された、インフォメーション ワーカー サービス アーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: ce1217bf-84a5-4888-89ba-dce85dc38340
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44c31f9fa9683d8a3a7210d324f605cb1689981c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309350"
---
# <a name="scaled-down-architecture-with-information-worker-services"></a>インフォメーション ワーカー サービスを使用した縮小されたアーキテクチャ
BizTalk Server の展開のシステム アーキテクチャの詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 次の図は、サンプルは、一部のドメインと BizTalk Server サーバーおよび必要なファイアウォールの数を減らして組み合わせて、インフォメーション ワーカー サービスを含む BizTalk Server アーキテクチャを提供します。 このアーキテクチャは、ほとんどの分散は、まだその機能に基づいて、BizTalk Server を区切ります。  
  
 ![スケール ダウン トポロジ](../core/media/cd3c85df-40f5-4382-9f8b-b2609f76e8b1.gif "cd3c85df-40f5-4382-9f8b-b2609f76e8b1")  
  
        Scaled Down Architecture with Information Worker Services  
  
 前の図では、サービス インターフェイス ドメインおよびサービス ドメイン内のサーバーは、BizTalk ホスト、および物理サーバーに対応します。 追跡、ホスト インスタンスがスタンドアロン コンピューターにマスター シークレット サーバーおよび管理ツールを保持することをお勧めしますが、送信、処理、および複数のコンピューターで実行しているホストを受信します。 同様に、境界ネットワーク内のサーバーは、論理的な場所に対応します。  
  
 SMTP、Windows メッセージ キュー (MSMQ とも呼ばれます)、ファイル、および SQL の境界ネットワーク内のサーバーは、メール サーバー、キュー、ディレクトリ、または SQL Server それぞれ元の BizTalk 受信および送信ホスト、サービス インターフェイス ドメイン内に対応します。メッセージを送受信します。  
  
 データ ドメイン内の BAM データベースは、BAM プライマリ インポート、BAM 分析、BAM スター スキーマ、および BAM アーカイブ データベースです。 データ ドメイン内の追跡や分析データベースは、BizTalk Server を使用して追跡情報を格納するためのものです。  
  
## <a name="see-also"></a>参照  
 [縮小されたアーキテクチャ](../core/scaled-down-architecture.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [セキュリティで保護されたアーキテクチャの設計](../core/designing-a-secure-architecture.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)