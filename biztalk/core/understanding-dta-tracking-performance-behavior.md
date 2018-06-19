---
title: DTA 追跡のパフォーマンスに関する動作を理解する |Microsoft ドキュメント
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
ms.openlocfilehash: 278d1e3c4b52c14c68d692ce3d3a3179d15bb10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287026"
---
# <a name="understanding-dta-tracking-performance-behavior"></a>DTA 追跡のパフォーマンス特性について
DTA 追跡の維持可能な最大スループット (MST) を決定する主要な要因として、次のものがあります。  
  
-   システムに必要なメッセージのスループット (単位時間に受信されたメッセージ)。  
  
-   メッセージごとの追跡データ量。  
  
-   データが BizTalkDTADb データベースから削除されるまでの存続期間 (データ保有期間)。  
  
-   BizTalkDTADb のデータをアーカイブして削除するかどうか。 アーカイブは任意ですが、削除は定期的に行う必要があります。  
  
 これらの要因のすべてに共通するのは、DTA がデータを受け入れて処理 (アーカイブおよび削除) する速度です。  
  
## <a name="how-the-biztalkdtadb-insert-and-processing-speed-affects-your-system"></a>BizTalkDTADb の挿入と処理速度がシステムに与える影響  
 ここで、追跡を見ていきましょうに記載されているデータの経路[維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)、およびシステムのさまざまなコンポーネントで BizTalkDTADb の挿入と処理速度の影響を評価します。  
  
 まず trackingdata テーブルとスプール テーブルについて考えてみると、これらのテーブルから BizTalkDTADb データベースにデータを移動するプロセスが、ランタイムによって trackingdata テーブルおよびスプール テーブルにデータが挿入されるのと同等以上の速度で BizTalkDTADb データベースにデータを挿入できなければ、trackingdata テーブルおよびスプール テーブルにバックログが蓄積され始めることは想像がつきます。 これは、メッセージ スループットの低下により最終的にはバックログを解消できることがわかっている限り、短期的には必ずしも問題にはなりません。 しかし、データがスプール テーブルまたは trackingdata テーブルに残っている間は、BizTalkDTADb データベースのデータを [グループ ハブ] ページでクエリを追跡したりその他のツールで照会することはできません。  このため、問題解決には役立ちません。 したがって、想定されるバックログ期間は、BizTalkDTADb データに基づいて調査する必要のある問題が発生した時点でタイムリーに追跡情報を利用できる程度に抑える必要があります。  
  
 テストの結果、バックログが蓄積されるかどうかを決定する要因は、追跡データを BizTalkDTADb データベースに移動するプロセス (TDDS および TrackedMessages_Copy_BizTalkMsgBoxDb) ではなく、BizTalkDTADb データベースが入力を受け入れる速度であることがわかっています。 通常、I/O バインドになるのは BizTalkDTADb データベースのデータ ファイルです。 つまり、DTA 全体の速度を決定するのは、BizTalkDTADb データベースのデータ ファイルが存在するドライブの速度ということになります。  
  
## <a name="how-the-amount-of-data-in-biztalkdtadb-affects-io-speed"></a>BizTalkDTADb のデータ量が I/O 速度に与える影響  
 I/O 速度に関連するもう 1 つの主要な要因は、BizTalkDTADb データベースのデータ量です。BizTalkDTADb データベース内の追跡データの量が多くなると、新しいデータの挿入時に並べ替えるデータの量が多くなり、これが挿入ごとに必要な I/O の量に影響するため、BizTalkDTADb データベースの入力および処理の速度は低下します。  
  
 ここでかかわってくるのが、BizTalkDTADb データベースのサイズが大きくなりすぎないように維持するアーカイブと削除のプロセスです。 基本的な考え方は、BizTalkDTADb データベースのサイズを抑え、スプール テーブルと trackingdata テーブルにデータが滞り始めるレベルに達しないようにするというものです。 ただし、DTA Purge and Archive (BizTalkDTADb) SQL ジョブに実装されている削除とアーカイブのプロセスも BizTalkDTADb データベース サーバーのリソース (CPU、メモリ、そして特に I/O) を必要とするため、追跡を有効にして MST を測定する際にはこの点も考慮する必要があります。  
  
## <a name="see-also"></a>参照  
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [DTA 追跡の MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [DTA 追跡の MST の検索のヒントし、テクニック](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)   
 [追跡データベースのサイズに関するガイドライン](../core/tracking-database-sizing-guidelines.md)