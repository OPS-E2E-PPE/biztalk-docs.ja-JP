---
title: BAM アクティビティのイベント ストリームの実装 |Microsoft ドキュメント
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
ms.openlocfilehash: 63594b956affc0f5b94f26ccdcb10d904ef171cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257346"
---
# <a name="implementing-bam-activities-with-event-streams"></a>イベント ストリームを使用した BAM アクティビティの実装
BAM アクティビティは、注文書やローンの申し込みなど、ビジネスの作業単位を表します。 アクティビティは、作業単位に関する履歴 (マイルストーン) とデータをビジネス エンド ユーザーまたはインフォメーション ワーカーに提示します。 たとえば、ローンの申し込みアクティビティには、"ローン承認済み" などのマイルストーンや、"申し込み者名" や "ローン金額" などのデータが含まれることがあります。 BAM アクティビティは、抽象化レベルが高いため実際に実装されている IT インフラストラクチャから独立していますが、ビジネス プロセスに直接マップされることもあります。  
  
 開発者は、特定のアクティビティのコンテキストに含まれる実装から関連のあるマイルストーンとデータのみを公開することによって、この抽象化のレベルを維持する必要があります。 アクティビティの使用方法を示すコード サンプルは、次を参照してください。 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BAM のコードを記述する理由](../core/why-write-code-for-bam.md)  
  
-   [開発者用の BAM 概念](../core/bam-concepts-for-the-developer.md)  
  
-   [BAM 開発プロセスの概要](../core/overview-of-the-bam-development-process.md)  
  
-   [EventStream クラス](../core/eventstream-classes.md)  
  
-   [アクティビティを使用](../core/using-an-activity.md)  
  
-   [アクティビティの関係](../core/activity-relationships.md)  
  
-   [アクティビティ Continuation](../core/activity-continuation.md)  
  
-   [ループ アクティビティ](../core/looping-activities.md)  
  
-   [ソリューションのインストルメント化: API の使用方法の詳細な手順](../core/instrumenting-a-solution-step-by-step-api-usage.md)