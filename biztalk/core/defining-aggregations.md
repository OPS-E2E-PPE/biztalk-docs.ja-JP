---
title: 集計の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], creating
- Excel add-in [BAM], creating aggregations
- aggregations [BAM], Excel add-in
- aggregations [BAM], about aggregations
ms.assetid: d5bf22d5-f491-4b08-a604-c7158e6e282f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a379e27e7805aa7e4b67ad3c94afba65b546c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352476"
---
# <a name="defining-aggregations"></a>集計の定義
Excel では定義**集計**として事前に計算された要約データをクエリの応答時間を向上させることで答えをあらかじめ、質問の前にします。 たとえば、数十万行が格納されているデータ ウェアハウスのファクト テーブルに対して、特定の 2 つの製品の出荷スケジュールを要求するクエリがあるとします。この計算でファクト テーブルをスキャンする必要があると、応答に時間がかかります。 ただし、このクエリの回答となる集計データがあらかじめ計算されていれば、即座に応答できます。  
  
 次に、事前に計算された集計データの例を示します。  
  
 ![](../core/media/bam-olap-cube.gif "bam_olap_cube")  
事前に計算された集計データ  
  
 上の図では、2 か月間に特定の場所への出荷された各製品数の概要を示しています。 Excel は、通常、としては、このデータを定義**メジャー**します。 にフィルター処理と分類のために使用するデータとして定義します**ディメンション**します。  
  
> [!NOTE]
>  BAM では、名前付きインスタンスの使用はサポートしません[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services。  
  
 多次元データの表示、ユーザー エクスペリエンスは、Excel のヘルプでピボット テーブルに関するトピックを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メジャーを定義する方法](../core/how-to-define-measures.md)  
  
-   [ディメンションの定義](../core/defining-dimensions.md)  
  
-   [ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)  
  
-   [リアルタイム集計の定義](../core/defining-real-time-aggregations.md)  
  
## <a name="see-also"></a>参照  
 [BAM ビューの定義](../core/defining-a-bam-view.md)