---
title: 大規模な分散、インフォメーション ワーカー サービス アーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 54bb036868202c153fef2405a6f26d977e823b40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328930"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a>インフォメーション ワーカー サービスを使用した大規模な分散アーキテクチャ
BizTalk Server の展開のシステム アーキテクチャを設計する方法の詳細については、次を参照してください。 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)します。  
  
 ビジネス アクティビティ監視 (BAM) は、ビジネス プロセスやパートナーと直接通信の可視性をインフォメーション ワーカーに提供します。 これは、これらのサービスをセキュリティで保護するための要件の異なるセットを表示します。 インフォメーション ワーカーが企業のドメイン内およびデータ ドメインではなく、アカウントを持っている可能性がありますし、BizTalk Server が生成するデータの一部にアクセスするアクセス サービス インターフェイス ドメインを必要な。  
  
 次の図は、BAM を含む分散型 BizTalk Server アーキテクチャを示しています。  
  
 ![分散アーキテクチャ](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")  
インフォメーション ワーカー サービスを分散型 BizTalk Server アーキテクチャ  
  
 」に示すアーキテクチャと比較して[大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)、インフォメーション ワーカー サービスの分散アーキテクチャには、BAM ポータルなどの追加のインフォメーション ワーカー サービスが含まれています。 インフォメーション ワーカー サービスのコンテナーには、次のサーバーとサービスが含まれています。  
  
-   BAM ポータル サーバー。 ビジネス エンドユーザーは、BAM ポータルを使用して、主要業績評価指標 (Kpi)、ビジネス プロセスに関するその他の情報と、ビジネス目標に向けた進行状況を測定するを監視する BAM データベースにアクセスします。 このサーバーは、BAM クエリ Web サービスと BAM 管理 Web サービスにもあります。  
  
-   BAM 用の SQL Server: BAM プライマリ インポート データベース、BAM アーカイブ データベース、BAM スター スキーマ データベース、および BAM 分析データベース。  
  
## <a name="see-also"></a>参照  
 [大規模な分散アーキテクチャ](../core/large-distributed-architecture.md)   
 [縮小されたアーキテクチャ情報ワーカー サービスを使用](../core/scaled-down-architecture-with-information-worker-services.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)