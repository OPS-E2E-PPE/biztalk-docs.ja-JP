---
title: "BAM 動的インフラストラクチャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3660eeb6f85fb21ff78b7b833b21adbb3af87385
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-dynamic-infrastructure"></a>BAM 動的インフラストラクチャ
SQL Server のテーブル、BAM ビュー、ストアド プロシージャ、および構成され、増分使用して管理される BAM データベース (プライマリ インポート、アーカイブ、スター スキーマ、および分析) でデータ変換サービス (DTS) パッケージの BAM インフラストラクチャの構成します。BAM 定義を展開します。 インフラストラクチャは、ここで、実行時に、イベントは、相関、集計、および、ユーザーによるクエリの利用できるようです。  
  
 このセクションでは、このインフラストラクチャ プロセスの一部について説明します。 たとえば、アプリケーションから目的のデータ (BAM 定義) を抽出すると、そのデータを保存して、クエリに使用できるようになります。 また、集計クエリの処理速度を上げるために、事前作成済みの特定のデータ集計を保持できます。  
  
 通常、データ ウェアハウスを実装する場合、膨大な開発作業を行ってこのような機能を実現します。 しかし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM では、アクティビティやビューの定義に基づいて SQL および OLAP のインフラストラクチャを自動的に生成することで、このプロセスを大幅に簡略化しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM 定義とは何ですか。](../core/what-is-a-bam-definition.md)  
  
-   [BAM 定義スキーマとは何ですか。](../core/what-is-a-bam-definition-schema.md)  
  
-   [アクティビティ データのストレージ](../core/activity-data-storage.md)  
  
-   [集計とは何ですか。](../core/what-is-an-aggregation.md)  
  
-   [BAM データを照会します。](../core/querying-bam-data.md)  
  
-   [BAM インフラストラクチャの制限](../core/bam-infrastructure-limitations.md)  
  
-   [英語以外のインストールで範囲外の数値ディメンション警告を定義する方法](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)