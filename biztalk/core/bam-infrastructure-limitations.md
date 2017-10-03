---
title: "BAM インフラストラクチャの制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, limitations
- infrastructure, BAM
- BAM, objects
- BAM, infrastructure
- BAM, naming conventions
ms.assetid: e33d2f6c-8d26-4a76-810e-85d810cfdbee
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfb8751e42918a64f13d35685d7d73b4f2406ff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-infrastructure-limitations"></a>BAM インフラストラクチャの制限
このリリースの [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の BAM インフラストラクチャには、次のような設計上の制限があります。  
  
-   リアルタイム集計 (RTA) では、MIN 関数または MAX 関数はサポートされていません。  
  
-   1 つの RTA ビュー内で、複数のデータ ディメンションから 1 つのレベルのエイリアスを参照することはできません。  
  
-   標準キューブも RTA も個別のカウント メジャーをサポートしていません。 標準キューブと RTA のどちらも、BAM 管理ユーティリティによって既定のカウント メジャーが生成されます。 この場合の既定のカウントは、ファクト (アクティビティ インスタンス) の個々のカウントではなく合計カウントです。  
  
-   同じ BAM アクティビティを使用する RTA を複数定義しないでください。 そのような RTA を複数定義した場合、BAM データをアーカイブしたときに RTA データが不正確になります。  
  
## <a name="bam-maximum-number-of-objects"></a>BAM におけるオブジェクトの最大数  
 次の表は、BAM インフラストラクチャにおけるオブジェクトの最大数を示しています。  
  
|オブジェクト|実装の制限|Reason|  
|------------|--------------------------|------------|  
|アクティビティにおけるチェックポイント|1,000|SQL Server では 1,024 個のストアド プロシージャ引数がサポートされており、BizTalk Server では 3 つのシステム プロシージャを使用します。|  
|アクティビティにおけるインデックス|245|SQL Server では、テーブルあたり 245 個の非クラスター化インデックスがサポートされています。 BizTalk Server では、常に ActivityID に基づいてインデックスが作成されます。|  
|DataLength|4000 Unicode 文字|NVARCHAR 型の SQL 変数が使用されます。|  
|ActivityRef|128|プライマリ インポート データベースとリレーションシップ テーブル (アクティビティごとに 2 つ) を結合することによってビューを取得できます。 SQL Server の SELECT ステートメントでは、256 個のテーブルがサポートされています。|  
|ビュー内の列<br /><br /> (エイリアス、期間、ディメンション レベル)|150|段階テーブルに関する SQL Server の制限は 1,024 列で、そのうちの 24 列が BAM によりシステム列のために予約されています。|  
|OLAP キューブ内のディメンション|128|OLAP 制限キューブあたり 128 ディメンションです。|  
|OLAP におけるメジャー|1,024|OLAP 制限はキューブあたり 1,024 メジャーです。 カウント メジャーは常時作成されます。|  
|OLAP におけるディメンション レベル|64|OLAP 制限には、キューブあたり 256 レベルの追加制限があります。|  
|RTA ビューにおけるディメンション レベル|14 ディメンション レベル|BAM により、すべてのディメンション レベルでインデックスが作成され、SQL Server インデックスは 16 列まで生成できます。BAM は、システム列のために 2 つのレベルを予約しています。|  
|RTA ビューにおけるメジャー、非表示メジャー (既定カウント、AVG の非表示 SUM メジャー)、およびディメンション レベル|1,024|SQL テーブル/ビューの場合、最大で 1,024 列です。|  
|アクティビティ ビュー|63|63 個に制限されますが、アラートを構成するときに[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]です。|  
  
## <a name="bam-object-names"></a>BAM オブジェクト名  
 次の表は、BAM 定義スキーマおよび Microsoft Excel スプレッドシートのオブジェクト名の制限文字数を示しています。  
  
|オブジェクト名|XSD の制限文字数|Excel の制限文字数|  
|------------------|--------------------|----------------------|  
|チェックポイント名|50 文字|50 文字|  
|[インデックス名]|100 文字|100 文字|  
|期間の名前|100 文字|100 文字|  
|エイリアス名|50 文字|50 文字|  
|アクティビティ名|48 文字|20 文字|  
|ビュー名|18 文字|18 文字|  
|アクティビティ ビュー名|52 文字 (名前は "View" というプレフィックスと 48 文字のビュー名で構成されます)|N/A (アクティビティ名から派生)|  
|キューブ名|20 文字|N/A (ビュー名から派生)|  
|RealTimeAggregation 名|48 文字|N/A (キューブ名から派生)|  
|ディメンション名|20 文字|20 文字|  
|レベル名|20 文字|20 文字|  
|メジャー名|20 文字|20 文字|  
|アラート名|128 文字|なし|  
|アラート メッセージ|1024 文字|なし|  
|イベント ルール名|255 文字|なし|  
|イベント プロバイダー名|255 文字|なし|  
  
## <a name="see-also"></a>参照  
 [BAM 構成スキーマ](../core/bam-configuration-schema.md)   
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)