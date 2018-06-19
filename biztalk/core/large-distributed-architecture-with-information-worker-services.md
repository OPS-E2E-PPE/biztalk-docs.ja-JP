---
title: Large Distributed Architecture インフォメーション ワーカー サービスと共に |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b9b1729411e089566988714b83778abac80eb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262194"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a>インフォメーション ワーカー サービスを使用した大規模な分散アーキテクチャ
BizTalk Server の展開のシステム アーキテクチャの設計の詳細については、次を参照してください。[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 ビジネス アクティビティの監視 (BAM) は、インフォメーション ワーカーがビジネス プロセスを表示し、パートナーと直接通信できるようにします。 ここでは、これらのサービスをセキュリティで保護するための各種の要件を示します。 インフォメーション ワーカーは通常、データ ドメインではなく企業ドメイン内のアカウントを持っています。また、BizTalk Server によって生成されるデータの一部にアクセスするためのアクセス サービス インターフェイス ドメインを必要とします。  
  
 次の図は、BAM を含む分散型 BizTalk Server アーキテクチャを示しています。  
  
 ![分散アーキテクチャ](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")  
インフォメーション ワーカー サービスを使用した分散型 BizTalk Server アーキテクチャ  
  
 」に示すアーキテクチャと比較して[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)、インフォメーション ワーカー サービスの分散アーキテクチャには、BAM ポータルなどの追加のインフォメーション ワーカー サービスが含まれています。 インフォメーション ワーカー サービスには次のサーバーとサービスが含まれます。  
  
-   BAM ポータル サーバー : ビジネス エンド ユーザーは、BAM ポータルを使用して BAM データベースにアクセスし、ビジネス目標に対する進捗状況を測定する主要業績評価指標 (KPI) や、ビジネス プロセスに関するその他の情報を監視します。 また、このサーバーには BAM クエリ Web サービスと BAM 管理 Web サービスも含まれています。  
  
-   BAM 用の SQL Server: BAM プライマリ インポート データベース、BAM アーカイブ データベース、BAM スター スキーマ データベース、および BAM 分析データベース。  
  
## <a name="see-also"></a>参照  
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [縮小されたインフォメーション ワーカー サービスのアーキテクチャ](../core/scaled-down-architecture-with-information-worker-services.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)