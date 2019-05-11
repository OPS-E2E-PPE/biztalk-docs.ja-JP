---
title: イベント ストリームを使用した BAM アクティビティを実装する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], about activities
- activities [BAM]
- BAM, activities
ms.assetid: 94e6d9dd-93c3-4ab0-9de7-a860dd1e3406
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f64b52fe6985da2f5f83cabe77fc3841c1a4db8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382615"
---
# <a name="implementing-bam-activities-with-event-streams"></a>イベント ストリームを使用した BAM アクティビティの実装
BAM アクティビティは、購入順序やローンの申し込みなど、ビジネスの作業単位を表します。 アクティビティは、ビジネス エンドユーザーまたはインフォメーション ワーカーに履歴 (マイルス トーン) と作業単位に関するデータを示します。 たとえば、ローンの申し込みアクティビティ可能性があります「ローン承認済み」などのマイルス トーンと「応募者名」や「ローン金額です」などのデータが含まれる BAM アクティビティは、抽象化レベルが高いため実際に実装されている IT インフラストラクチャから独立していますが、ビジネス プロセスに直接マップされることもあります。  
  
 開発者は、特定のアクティビティのコンテキストに含まれる実装から関連のあるマイルストーンとデータのみを公開することによって、この抽象化のレベルを維持する必要があります。 アクティビティの使用方法を示すコード サンプルは、次を参照してください。 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM のコードを記述する理由](../core/why-write-code-for-bam.md)  
  
-   [開発者のための BAM 概念](../core/bam-concepts-for-the-developer.md)  
  
-   [BAM 開発プロセスの概要](../core/overview-of-the-bam-development-process.md)  
  
-   [EventStream クラス](../core/eventstream-classes.md)  
  
-   [アクティビティを使用](../core/using-an-activity.md)  
  
-   [アクティビティ リレーションシップ](../core/activity-relationships.md)  
  
-   [アクティビティ Continuation](../core/activity-continuation.md)  
  
-   [ループ アクティビティ](../core/looping-activities.md)  
  
-   [ソリューションのインストルメント化します。ステップ バイ ステップの API 使用量](../core/instrumenting-a-solution-step-by-step-api-usage.md)