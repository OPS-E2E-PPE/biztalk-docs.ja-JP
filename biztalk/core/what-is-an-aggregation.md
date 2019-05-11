---
title: 集計とは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OLAP cubes, BAM
- BAM, aggregations
- BAM, OLAP cubes
- aggregations [BAM], OLAP cubes
- aggregations [BAM], about aggregations
- aggregations [BAM]
ms.assetid: 77d40602-ef56-4a5b-a18f-56ccbff573a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e0cc2b49c154f930c925ae88ee66889107a63f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379699"
---
# <a name="what-is-an-aggregation"></a>集計とは何ですか。
Excel では、集計を事前計算された要約データとして定義し、質問の答えをあらかじめ用意しておくことで、クエリの応答時間を短縮します。 たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。 ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。  
  
 次に、事前に計算された集計データの例を示します。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
BAM OLAP キューブ  
  
 上の図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。 通常、Excel では、このデータをメジャーとして定義し、 フィルター選択または分類に使用するデータをディメンションとして定義します。  
  
 多次元データのユーザー エクスペリエンスについては、Excel のヘルプでピボットテーブルに関するトピックを参照してください。  
  
 特定のビューで利用できるデータに基づいた多次元アクティビティの集計を作成することができます。 多次元アクティビティの集計には、メジャー (金額など、集計するデータ) とディメンション (州や都市など、フィルター選択またはグループ化に使用するデータ) が含まれています。  
  
 集計は、オンライン分析処理 (OLAP) キューブの形式またはリアルタイム集計として作成できます。OLAP キューブは特定の時点のスナップショットを表し、リアルタイム集計は、ビジネス シナリオに基づいており、多次元構造を使用してリアルタイムでデータを参照できます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [スケジュール済みの集計](../core/scheduled-aggregations.md)  
  
-   [リアルタイム集計](../core/real-time-aggregations.md)