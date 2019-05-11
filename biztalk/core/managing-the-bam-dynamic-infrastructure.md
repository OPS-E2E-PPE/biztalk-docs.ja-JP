---
title: BAM 動的インフラストラクチャの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, managing [BAM]
- managing [BAM], infrastructure
ms.assetid: af8a76b5-407a-484d-aff4-0d911f88313e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40b0ef23d013149f7f01efe6f0157ce98b856f2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380179"
---
# <a name="managing-the-bam-dynamic-infrastructure"></a>BAM 動的インフラストラクチャの管理
ビジネス アクティビティの監視 (BAM) 機能では、SQL とオンライン分析処理 (OLAP) のインフラストラクチャに動的に生成されるインフラストラクチャを使用します。 管理者は、BAM 管理ユーティリティを使用して、ビジネス アナリストが作成する BAM 定義ブックまたは XML ファイルを展開します。  
  
 BAM 動的インフラストラクチャは、BAM ブック ビュー、BAM の展開、BAM データ変換サービス (DTS) パッケージ、および BAM データベースで構成されています。 BAM 動的インフラストラクチャの詳細については、次を参照してください。 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)します。  
  
 BizTalk Server では、BizTalk Server を構成するときに、次の BAM データベースが作成されます。  
  
- BAM プライマリ インポート (BAMPrimaryImport) データベース  
  
- BAM スター スキーマ (BAMStarSchema) データベース (オプション)  
  
- BAM 分析 (BAMAnalysis) データベース (オプション)  
  
- BAM アーカイブ (BAMArchive) データベース  
  
  BAM データベースについては、次を参照してください。 [BAM データベースを管理する](../core/managing-bam-databases.md)します。  
  
  管理者は、このセクションで説明している BAM インフラストラクチャの次の管理作業を行います。  
  
- BAM 定義と BAM ビューの展開および展開解除  
  
- BAS ビューへのユーザー アクセスの管理  
  
- BAM DTS パッケージの実行  
  
- BAM データベースのバックアップ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM 定義の管理](../core/managing-bam-definitions.md)
  
-   [BAM セキュリティの管理](../core/managing-bam-security.md)  
  
-   [集計の管理](../core/managing-aggregations.md) 
  
-   [BAM データベースの管理](../core/managing-bam-databases.md)
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)