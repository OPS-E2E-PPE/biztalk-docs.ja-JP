---
title: アーカイブのパフォーマンスの向上と、プロセスの削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], system performance
- DTA Purge and Archive job, performance
- purging, limitations
- performance, archiving
- performance, purging
- purging, system performance
ms.assetid: d65da58d-65e0-4f6c-8b15-5d4448049b42
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f65455e5ad2a87f2d95afcdebe9a81c0d2f87e4d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000091"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a>アーカイブおよび削除のプロセスのパフォーマンスの向上
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに格納されているデータの量は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] シナリオの設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] シナリオで処理されるメッセージの数とサイズ、および追跡に関する構成内容によって、非常に短期間で増加することがあります。 データベース サイズを正常なレベルに保つことにより、処理の効率を向上させ、システム内のデータの量をどの時点でも正常な値に維持することができます。 また、効率的で一貫性のあるパフォーマンスを達成できます。 このプロセスを自動化すると、データベースを手動で保守するための労力を軽減することができます。  
  
## <a name="configuring-a-healthy-environment"></a>正常な環境の構成  
 正常な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を保つための戦略は、使用するシナリオおよび実行用のハードウェアに大きく依存します。 監視すべき主要な対象は、BizTalk 追跡 (BizTalkDTADb) データベースの増加率およびサイズです。 追跡データベース内にある少数のテーブルが、データベース サイズの大部分を占めているため、これらのテーブルが実行時のパフォーマンスを左右します。  
  
 シナリオが同じでも、生成される追跡データの量は構成によって大きく異なり、存在する追跡ポイントの数、使用されるメッセージ数、メッセージのサイズ、および追跡に使用されるメッセージ本文のレベルに応じて変化します。 監視すべき重要な事項を次に示します。  
  
- 追跡ポイントの数 (パイプライン、オーケストレーション、ポートなど)  
  
- 追跡対象のメッセージ プロパティ数  
  
- 1 つの受信メッセージあたりのメッセージ数  
  
- メッセージ サイズ  
  
- トラフィック レート (平均およびピーク)  
  
- メッセージ本文の追跡の構成  
  
  データの自動的なアーカイブおよび削除の実行を検討する場合は、追跡データベースに保持する必要のあるライブ データの量を考慮します。 削除の実行時にパフォーマンスの低下がないように、対象となるライブ データの量を処理するには、使用する環境に応じて DTA Purge and Archive ジョブ パラメーターを適切に調整する必要があります。  
  
  DTA Purge and Archive ジョブでは、指定した間隔で所定の量のデータを削除できます。 ジョブの容量は、実行しているシナリオ、現在のデータベース サイズ、およびハードウェアによって異なります。 安定した環境を維持するために、受信追跡データの生成と削除のバランスを整える必要があります。 テスト環境では、データの有効期間と削除ジョブの頻度を変化させながら適正なバランスを見つけることができます。 良好なバランスを保つことにより、維持可能なスループットが達成されます。 これらの操作の目的は、BizTalk 追跡データベース テーブルのサイズが増大して持続的なパフォーマンス低下の問題が発生する前に、十分なバッファーを確保することです。  
  
## <a name="performance-limitations"></a>パフォーマンスの制限  
 すべてのシナリオで削除パフォーマンスが向上するわけではありません。 一部のシナリオでは、生成される追跡データの量が増えてしまうことがあります。 常に遅いレートで追跡データの削除が実行されると、データベース サイズが蓄積され、削除パフォーマンスの低下につながります。  
  
 負荷が大きすぎる状態では、メッセージ本文のコピーの実行が遅くなり、メッセージ ボックス データベースのバックログになる場合があります。 極端な場合は、毎日のメッセージ本文のコピーおよび追跡のアーカイブで、メッセージ本文に関連インスタンス情報が含まれているにもかかわらず、メッセージ本文を利用できないことがあります。 通常、高負荷の期間と低負荷の期間が交互に発生するので、ジョブは低負荷の期間中に遅れを取り戻すことができます。  
  
 BizTalk Tracking データベースのアーカイブおよび削除を行うと、データベースが継続的に簡略化され、格納された追跡データが圧縮されるので、負荷が大きすぎる状態が発生する可能性は非常に少なくなります。 これらのプロセスにより、手動による介入の必要性は大きく低減します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)