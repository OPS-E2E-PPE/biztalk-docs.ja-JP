---
title: DTA 追跡のパフォーマンス特性を理解する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1a70951-bfed-435c-97f4-0b28a8e4e4dc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 409138a38b75aebdd4e2df63d23e301dae483738
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292675"
---
# <a name="understanding-dta-tracking-performance-behavior"></a>DTA 追跡のパフォーマンス特性を理解します。
DTA 追跡の維持可能な最大のスループット (MST) を決定する主な要因は次のとおりです。  
  
- 目的のメッセージのスループット、つまり、システムの単位時間あたりの受信メッセージ。  
  
- メッセージごとに、データの量が追跡されています。  
  
- BizTalkDTADb データベースから削除されるまで、つまり、データのリテンション期間の有効期限は、データをどのくらいの時間です。  
  
- かどうか、BizTalkDTADb データがアーカイブだけでなく削除します。 アーカイブは省略可能ですが、削除し、定期的に実行する必要があります。  
  
  1 つあります共通これらすべての要素があること。 位置、DTA はそのまま使用し、処理の速度 (アーカイブおよび削除) のデータ。  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a>BizTalkDTADb の挿入と処理速度がシステムに影響  
 次に、追跡してみましょうで説明されているデータの経路[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)、およびシステムのさまざまなコンポーネントで BizTalkDTADb の挿入と処理速度の影響を評価します。  
  
 以降、trackingdata テーブルおよびスプール テーブルでは、想像が、これらのテーブルから BizTalkDTADb データベースにデータを移動するプロセスは、少なくとも同じ速度に、ランタイムを挿入、BizTalkDTADb データベースにデータを挿入することがない場合、trackingdata テーブルとスプール テーブル、スプールと trackingdata テーブルは、バックログが蓄積が開始されます。 最終的にドレインするまでにバックログを許可するメッセージのスループットに減少することがわかっている限りいない必ずしも短期的に悪いことになります。 ただし、として、スプール テーブルまたは trackingdata テーブルには、データが残っている間、そのされません、BizTalkDTADb データベースのグループ ハブ ページまたはその他のツールでクエリを追跡することによってクエリで使用できます。  したがって、されません問題解決のために便利です。 そのため、想定されるバックログ期間が短いことから追跡情報の問題が発生する必要がありますも BizTalkDTADb のデータを使用して、調査に必要な適切なタイミングで引き続き使用できますがあります。  
  
 テストからわかる決定要因は、バックログが蓄積する場合 BizTalkDTADb データベース (TDDS および TrackedMessages_Copy_BizTalkMsgBoxDb) が、速度で BizTalkDTADb データベースの追跡データを移動するプロセスではありません。入力を受け入れます。 通常、I/O バウンドになっている BizTalkDTADb データベースのデータ ファイルになります。 つまりに BizTalkDTADb データベースのデータ ファイルが置かれているドライブの速度は、DTA 全体の速度を決定するをお勧めします。  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a>BizTalkDTADb のデータの量が I/O 速度に与える影響  
 I/O 速度に関連するもう 1 つの主要要素が BizTalkDTADb データベース内のデータの量単により多くのデータであるために、BizTalkDTADb データベースの入力および処理の速度が低下として BizTalkDTADb データベースが増えるの追跡データの量、。新しいデータの挿入し、挿入ごとに必要な I/O の量に影響を並べ替えます。  
  
 これは、アーカイブおよび削除でかかわってくる大きくなりすぎるため、BizTalkDTADb データベースを保持するプロセスです。 基本的な考え方では、位置が滞り始めるスプールと trackingdata テーブル レベルの下、BizTalkDTADb データベースのサイズを保持することを確認します。 ただし、DTA Purge and Archive (BizTalkDTADb) SQL ジョブで実装されている削除とアーカイブのプロセスも必要なリソース (CPU、メモリ、および特に I/O) での MST を測定するときに考慮する必要があります、BizTalkDTADb データベース サーバーから追跡します。  
  
## <a name="see-also"></a>参照  
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [DTA 追跡の MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [DTA 追跡の MST を特定のヒントし、テクニック](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [追跡データベースのサイズに関するガイドライン](../core/tracking-database-sizing-guidelines.md)