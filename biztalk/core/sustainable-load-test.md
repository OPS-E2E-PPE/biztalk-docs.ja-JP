---
title: 維持可能なロード テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- sustainable load test
- LoadGen tool, sustainable load test
ms.assetid: a9d752ff-aff1-4445-8af5-8f84609880e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d059f7f2aa29be68ea87d72d9357d01601d2c958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321769"
---
# <a name="sustainable-load-test"></a>維持可能なロード テスト
このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。  
  
 最初のテストでは、システムは MST に到達する駆動が正常なシステムの観測にできるようにします。  
  
 次のグラフは、このアプローチを使用して、テスト システムの維持可能な最大スループットの調査した後、主要な指標を示します。  
  
 **維持可能なロード テストのロード プロファイル**  
  
 ![パフォーマンス モニターの測定の維持可能なロード](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")  
  
 このグラフは、テストの時間、スプールの深さが安定し、増大しなかったを示しています。  
  
- グラフの上部にある黒い線は、(たとえばの受信側サーバーの両方)、システムによって 1 秒あたりに受信したメッセージの総数を表示します。  
  
- グラフの下部にある行は、SQL サーバーごとに、メッセージ ボックス スプールの深さを示します。  
  
  システムを駆動するには、最大の安定したスプールの深さのポイントすると、MST は 1 秒あたりに受信したメッセージの数によって測定されます。 このシナリオで説明されている、ハードウェアで 290 メッセージ/秒の MST が行われました。  
  
> [!NOTE]
>  システムを駆動するには、スプールの深さが安定しなく時間の経過と共に、ポイントするとは、MST を超過しています。 変化する負荷をいくつかのテストの実行がどのスプールの深さが安定した最大負荷を評価する必要があるし、システムは、追加のメッセージ バックログを発生させずにメッセージのバックログを処理できます。  
  
 BizTalk 展開のパフォーマンスの分析の一部では、リソースのボトルネックを理解する主要な指標のチェックを含める必要があります。 キーのメジャーと最大持続可能スループットで実行されているこの展開に使用される、値は次のとおりです。  
  
 **CPU 使用率**  
  
|[サーバー]|平均 CPU 使用率|  
|------------|-----------------------------|  
|BizTalk Server|55%|  
|SQL Server (マスター メッセージ ボックス サーバー)|76%|  
|SQL Server (他のメッセージ ボックス サーバー)|83%|  
  
 **物理ディスクのアイドル時間**  
  
|[サーバー]|ディスクの平均アイドル時間|  
|------------|----------------------------|  
|すべての SQL Server の平均値|69%|  
  
 **SQL Server の SQL ロック**  
  
|パラメーター|値|  
|---------------|-----------|  
|ロック タイムアウト合計平均/秒 (SQL Server) 数|1980|  
|平均合計ロック待機時間 (ミリ秒)|495|  
  
 このテスト中にエラーが生成されましたない BizTalk または SQL Server アプリケーション ログにします。  
  
 このデータから、次の結論を描画できます。  
  
- システム内では、明らかなリソース ボトルネックはありません。  
  
- これらのインジケーターのすべては、正常な制限範囲内です。  
  
- CPU とディスク アイドル時間は、余裕があるし、設定されているもの近くにいないことを示しています。  
  
- SQL ロック インジケーターは見栄え**Lock timeouts/sec**までおよそ 5000 (SQL Server) によって問題なく起動しないロック待機時間 1 秒以下でされても正常な状態です。  
  
  最大持続可能スループットを検索する方法について説明し、維持可能な正常なシステムの主要な指標がどのように表示されることが、処理と収集よりも高速化を受信しているシステムに関連付けられているいくつかの動作を見てみましょうガベージ。 続行する[ロード テストをオーバー ドライブ](../core/overdrive-load-test.md)します。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [オーバードライブ ロード テスト](../core/overdrive-load-test.md)