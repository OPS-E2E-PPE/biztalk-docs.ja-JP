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
ms.openlocfilehash: e6d7cb6adf314bd5575d354c52c2682138bad784
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382204"
---
# <a name="improving-the-performance-of-the-archiving-and-purging-process"></a>アーカイブおよび削除のプロセスのパフォーマンスの向上
格納されているデータの量、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを設計した方法に応じて非常に簡単に拡張できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオでは、によって処理されるメッセージのサイズと数に応じて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]シナリオ、およびがあるかによって異なります追跡を構成します。 正常なレベルで、データベースのサイズを維持することによって処理効率が上がると、システム内のデータの量が特定の時点に正規化されます。 これは、効率的で一貫性のあるパフォーマンスを提供します。 このプロセスを自動化することによって解放する自分で手動でデータベースの保守の負担の。  
  
## <a name="configuring-a-healthy-environment"></a>正常な環境を構成します。  
 正常性を維持するために、戦略[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境は、特定のシナリオとで実行されているハードウェアに大きく依存します。 監視することには、増加率および BizTalk 追跡 (BizTalkDTADb) データベースのサイズです。 追跡データベースのテーブルの数が、データベースのサイズの大部分のアカウントし、ランタイムで、パフォーマンスに影響を与えるためです。  
  
 追跡ポイントの数がどのように存在に基づいて追跡データの量を大幅に異なるを生成するために、同じシナリオを構成することができます多くのさまざまなメッセージが使用される、メッセージのサイズとメッセージ本文の追跡のレベルを使用します。 次に、いくつかの重要な要因を監視します。  
  
- -パイプライン、オーケストレーション、ポートなどの追跡ポイントの数  
  
- 追跡メッセージのプロパティの数  
  
- 受信メッセージあたりのメッセージ数  
  
- メッセージ サイズ  
  
- トラフィック レート (平均およびピーク)  
  
- メッセージ本文の追跡の構成  
  
  自動を検討する場合、アーカイブとデータの削除が、追跡データベースに保持する必要があるライブ データの量を検討します。 対象となるライブ データの量を削除パフォーマンスを低下させることがなくサポートできるように、環境に応じて DTA Purge and Archive ジョブ パラメーターを調整する必要があります。  
  
  DTA Purge and Archive ジョブでは、指定された時間間隔内でデータ量を削除できます。 ジョブの容量を実行しているシナリオ、現在のデータベースのサイズ、およびハードウェアによって異なります。 安定した環境を確保するためには、受信追跡データの生成と削除のバランスが必要です。 テスト環境では、データの有効期間と削除のジョブの頻度を変えることでバランスを見つけることができます。 バランスの取れた状態で、システムは維持可能なスループットを提供します。 目標は、BizTalk 追跡データベースのテーブル サイズして持続的なパフォーマンスの問題が発生する前に十分なバッファーことです。  
  
## <a name="performance-limitations"></a>パフォーマンスの制限  
 すべてのシナリオでは、削除パフォーマンスはスケーラビリティがありません。 、すべてのシナリオには、追跡データの量が増加を生成することです。 追跡の蓄積が常に遅いレートで追跡データが削除されたとき、データベース サイズ、削除パフォーマンス低下につながります。  
  
 負荷が大きすぎる条件下でメッセージ本文のコピーがも実行が遅くなりが、メッセージ ボックス データベース内のバックログになる可能性があります。 極端な場合は、毎日のメッセージの本文をコピーおよび追跡メッセージ本文がない使用可能な関連インスタンス情報が含まれる場合でもアーカイブに可能性があります。 通常、高負荷の期間は低負荷の期間が交互し、低負荷の期間中に遅延を解消するジョブを有効にします。  
  
 アーカイブおよび BizTalk 追跡データベースの削除では、データベースの継続的な排除と格納された追跡データの圧縮のため負荷が大きすぎる状態の可能性を低減する必要があります大幅。 これらのプロセスは、手動介入の必要性を大幅に削減します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 追跡データベースのアーカイブおよび削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)