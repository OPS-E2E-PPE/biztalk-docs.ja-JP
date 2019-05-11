---
title: フラッド ゲート ロード テスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b78509cc1bc2c38ab1fcf536ce71e3d14b70d500
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387959"
---
# <a name="floodgate-load-test"></a>フラッド ゲート ロード テスト
このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。  
  
## <a name="what-causes-floodgate-events"></a>どのような原因のフラッド ゲート イベントでしょうか。  
 だけが、さまざまなシナリオがあるいくつかの大きなピーク (とも呼ばれます**フラッド ゲート イベント**) メッセージのシステムに到着毎日です。 これらのピークの間でスループットが非常に低いできます。 これらのシナリオの例は次のとおりです。  
  
- 株式取引先、たとえば、市場の開始と市場を閉じる  
  
- 銀行トランザクション調整の日の終了時にシステムで、たとえば、  
  
  その他の種類のイベントには、フラッド ゲート イベントに似たバックログ動作を可能性があります。 たとえば、パートナーに送信する場合アドレスがオフラインに宛てたメッセージ バックログが蓄積この結果をアドレスの再試行または保留する必要があります。 パートナーは行が返される、別のタイプのフラッド ゲート イベント、再開する必要がある保留メッセージの数が多いである可能性があります。 システムの次のテストでは、この動作を示します。  
  
## <a name="simulating-a-floodgate-event"></a>フラッド ゲート イベントをシミュレートします。  
 このテストでは、これはもちろん、非常に安定した、最大約 30 の維持可能なスループットで、システムを初期駆動します。 次に、フラッド ゲート イベントをシミュレートするには、短期間のうちの約 410 メッセージ/秒で送信するツールが構成されている負荷の生成時間 (と同じオーバー ドライブ テスト)。 スプールの深さ、1 秒あたりに受信したメッセージを測定する結果のロード プロファイルは、下に表示されます。  
  
 **フラッド ゲート ロード テストのロード プロファイル**  
  
 ![フラッド ゲート ロードのパフォーマンス監視画面](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")  
  
 グラフから、フラッド ゲート イベント中に、スプール テーブルすばやいバックログを構築することに注意してください。 ただし、イベントが比較的短い存続期間と最大持続可能な速度より下のイベントの後、後続の受信レートが、ため、クリーンアップ ジョブを実行し、システムを必要とせずにイベントから回復することの停止を受信します。 SQL Server 2005; に格納されていました、メッセージ ボックスのこの特定のテストこのテストを最初から最後までの期間は、約 45 分でした。  
  
 もちろん、すべてのシステムは異なるので、「自分のマイレージは異なります」 回復できることを確認する最善の方法では、実稼働に移行する前に、典型的な負荷でテストです。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [オーバー ドライブ ロード テスト](../core/overdrive-load-test.md)   
 [維持可能なロード テスト](../core/sustainable-load-test.md)