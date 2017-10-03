---
title: "オーバー ドライブ ロード テスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overdrive load test
- LoadGen tool, overdrive load test
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54ea40d17bdb59fa3fcdc2db31a18b3286b70659
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overdrive-load-test"></a>オーバー ドライブ ロード テスト
このトピックの情報は、参照で説明されているテスト[エンジンの MST の測定のテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)です。  
  
 負荷生成ツール LoadGen 2007 を使用すると、BizTalk Server システム上の大きな負荷をシミュレートできます。  
  
> [!NOTE]
>  LoadGen 2007 ツールはダウンロード[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841)です。 このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールは、ダウンロード[http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)です。  
  
 続けて負荷の多いシステムをシミュレートするため、LoadGen 2007 は、測定された維持可能な最大のスループットよりも 120 メッセージ/秒多い約 410 メッセージ/秒の送信で構成されました。  
  
 このテストは、システムの負荷だけではなく、約 200 万レコードという深さのスプール バックログから回復する時間も考慮しています。  
  
 これを実現するため、システムは、スプールの深さが約 200 万レコードになるまで、高速で動作します。 スプールの深さが適切なレベルになると、負荷は生成されなくなります。  
  
 BizTalk 制限メカニズムがスプール テーブル バックログの蓄積をできなくなる、受信ホストを制限しないことを確認する、 **DB 内の数をメッセージ**から受信ホストが変更されたために、しきい値を調整します既定値の 50000 から 2000000 にします。 変更する方法について、 **DB 内の数をメッセージ**しきい値を調整するを参照してください[リソース ベースの調整設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)です。 既定のホスト設定の制限については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)です。  
  
 次の図は、上図と同じインジケーターを示しています。  
  
 **オーバー ドライブ ロード テストのロード プロファイル**  
  
 ![オーバー ドライブ ロードのパフォーマンス監視画面](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")  
  
 図に示されているように、スプールがすぐに深くなっていきます。約 200 万レコードが最大です。 この場合、目標とした 200 万レコードのバックログに達するのに約 2.5 時間かかりました。 負荷が止まると、クリーンアップ ジョブによるバックログからの回復に約 8 時間かかりました。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [維持可能なロード テスト](../core/sustainable-load-test.md)