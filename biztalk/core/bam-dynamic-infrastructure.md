---
title: BAM 動的インフラストラクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed2c99ad52068d26a1144bb47cf3d247c6456d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358558"
---
# <a name="bam-dynamic-infrastructure"></a>BAM 動的インフラストラクチャ
SQL Server のテーブル、BAM ビュー、ストアド プロシージャ、およびデータ変換サービス (DTS) パッケージとして構成され、増分使用して管理される BAM データベース (プライマリ インポート、アーカイブ、スター スキーマ、および分析) での BAM インフラストラクチャの構成します。BAM 定義の展開。 インフラストラクチャは、ここで、実行時に、イベント、相関、集計、およびユーザーがクエリで使用可能になります。  
  
 このセクションでは、このインフラストラクチャ プロセスの一部について説明します。 たとえば、(BAM 定義)、アプリケーションから目的のデータを抽出するとできます保存するクエリで使用できるようにします。 さらに、集計クエリの高速のデータの特定の事前に作成した集計を維持することができます。  
  
 通常、データ ウェアハウスを実装するために膨大な開発作業でこのような機能を実現します。 Microsoft で BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]大幅に簡略化このプロセスは、ただし、アクティビティとビューの定義に基づいて SQL および OLAP のインフラストラクチャを自動的に生成しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM 定義について](../core/what-is-a-bam-definition.md)  
  
-   [BAM 定義スキーマについて](../core/what-is-a-bam-definition-schema.md)  
  
-   [アクティビティ データのストレージ](../core/activity-data-storage.md)  
  
-   [集計について](../core/what-is-an-aggregation.md)  
  
-   [BAM データのクエリ](../core/querying-bam-data.md)  
  
-   [BAM インフラストラクチャの制限](../core/bam-infrastructure-limitations.md)  
  
-   [英語以外のインストールで範囲外の数値ディメンション警告を定義する方法](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)