---
title: "フラッド ゲート ロード テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- LoadGen tool, simulating floodgate events
- performance, floodgate peaks
- floodgate events [performance]
ms.assetid: 937f2478-339b-4ae2-b107-56f3a4bfc579
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74954d8b94207832ceee5bbb699a7de1a245f61b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="floodgate-load-test"></a>フラッドゲート ロード テスト
このトピックの情報は、参照で説明されているテスト[エンジンの MST の測定のテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)です。  
  
## <a name="what-causes-floodgate-events"></a>フラッドゲート イベントの原因  
 場所だけで、さまざまなシナリオがあるいくつかの大きなピーク (とも呼ばれる**フラッド ゲート イベント**) メッセージの到着、システムを 1 日にします。 これらのピークの合間のスループットは非常に低くなっています。 このようなタイプのシナリオの例を次に示します。  
  
-   証券取引で、市場の開始時や終了時など  
  
-   銀行システムで、1 日の終わりに行われる当日取引の照合時など  
  
 その他のタイプのイベントにより、フラッドゲート イベントに似たバックログ動作が発生する場合もあります。 たとえば、パートナーの送信アドレスがオフラインになり、そのアドレスに宛てたメッセージを再送信または保留する必要が生じた場合、バックログが蓄積されます。 パートナーがオンラインに戻ると、再送信する必要のある保留メッセージが多く蓄積されているので、別のタイプのフラッドゲート イベントが発生します。 次のシステム テストでこの動作を示します。  
  
## <a name="simulating-a-floodgate-event"></a>フラッドゲート イベントのシミュレーション  
 このテストでは、維持可能な最大スループットの約半分でシステムを初期駆動しました。これは非常に安定したスループットです。 次に、フラッドゲート イベントをシミュレートするために、短時間に約 410 メッセージ/秒で送信するように負荷生成ツールを構成しました (オーバードライブ テストと同様)。 1 秒間に受信したメッセージとスプールの深さを測定するロード プロファイルの結果を以下に示します。  
  
 **フラッド ゲート ロード テストのロード プロファイル**  
  
 ![飽和による負荷のパフォーマンス モニター画面](../core/media/bts06-floodgate-load.gif "BTS06_Floodgate_Load")  
  
 このグラフから、フラッドゲート イベントの発生中に、スプール テーブルに急速にバックログが蓄積されたことがわかります。 ただし、イベントの発生は比較的短時間で、その後の受信レートは維持可能な最大受信レート以下になったので、クリーンアップ ジョブを実行して、システム受信障害を引き起こさずにイベントから回復することができました。 このテストでは、メッセージ ボックスは SQL Server 2005 に格納されていました。このテストの開始から終了までの時間は約 45 分でした。  
  
 もちろん、システムはそれぞれ異なるので、結果も異なります。 回復可能かどうかを確認するには、実稼働に移行する前に通常の負荷を使用してテストしてください。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [オーバー ドライブ ロード テスト](../core/overdrive-load-test.md)   
 [維持可能なロード テスト](../core/sustainable-load-test.md)