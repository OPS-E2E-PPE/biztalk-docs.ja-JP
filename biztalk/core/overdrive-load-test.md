---
title: ロード テストをオーバー ドライブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d16d0a8-4255-4f5a-86a2-26cc11bb9a70
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734c0dffc64ca7efd52b6325227a26ee0387b50e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393409"
---
# <a name="overdrive-load-test"></a>オーバー ドライブ ロード テスト
このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。  
  
 負荷生成ツール LoadGen 2007 では、BizTalk Server システム上の負荷をシミュレートすることができます。  
  
> [!NOTE]
>  ダウンロード[LoadGen](https://www.microsoft.com/download/details.aspx?id=14925)します。 このツールの以前のバージョン、BizTalk Server 2004 負荷生成ツールがダウンロードできる[ http://go.microsoft.com/fwlink/?linkid=108999](http://go.microsoft.com/fwlink/?linkid=108999)します。  
  
 続けて負荷の多いシステムをシミュレートするには、LoadGen 2007 よりも最大測定された維持可能なスループットの約 410 メッセージ/秒、120 メッセージ/秒の送信構成されました。  
  
 テストは、システムをオーバー ドライブするだけでなく、どのくらいの時間がかかる約 200万レコードのスプール バックログの深さから回復するを把握するも設計されています。  
  
 これを行うには、スプールの深さが約 200万レコードまでシステムが、高速で駆動します。 スプールの深さではそれ以上の負荷が生成された後、必要なレベルに達するとします。  
  
 BizTalk 制限メカニズムがスプール テーブル バックログが蓄積されるように、受信ホストを制限しないことを確認する、 **DB のメッセージ カウント**から受信ホストが変更されたは、しきい値を調整します既定値の 50000 から 2000000 にします。 変更する方法について、 **DB のメッセージ カウント**しきい値を調整するを参照してください[リソース ベースのスロットル設定の変更方法](../core/how-to-modify-resource-based-throttling-settings.md)します。 既定のホスト制限設定については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。  
  
 次のグラフでは、上のグラフと同じインジケーターを示します。  
  
 **オーバー ドライブ ロード テストのロード プロファイル**  
  
 ![オーバー ドライブ ロードのパフォーマンス監視画面](../core/media/bts06-overdrive-load.gif "BTS06_Overdrive_Load")  
  
 グラフからわかるように、スプールの深さは、構築すぐに、2 件のレコードのすぐ上にピークとなるを開始します。 この速度で対象となる 200万レコードのバックログを表示するには約 2.5 時間がかかりました。 負荷が停止した後、クリーンアップ ジョブ バックログから回復するのに約 8 時間がかかりました。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)   
 [維持可能なロード テスト](../core/sustainable-load-test.md)