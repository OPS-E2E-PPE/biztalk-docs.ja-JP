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
ms.openlocfilehash: d17d8d38323f7933c8e60cb2b87e0ec312d270c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015651"
---
# <a name="sustainable-load-test"></a>維持可能なロード テスト
このトピックの情報を指すで説明されているテスト[エンジンの MST を測定するテストのシナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)します。  
  
 最初のテストでは、健全なシステムの監視を行えるように、MST に到達するまでシステムを駆動しました。  
  
 次の図に、テスト システムの維持可能な最大スループットを見つけるためにこのアプローチを使用した後の主要な指標を示します。  
  
 **維持可能なロード テストのロード プロファイル**  
  
 ![パフォーマンス モニターの測定の維持可能なロード](../core/media/bts06-sustainable-load.gif "BTS06_Sustainable_Load")  
  
 このグラフは、テスト中、スプールの深さが安定し、増大しなかったことを示しています。  
  
- グラフの最上部の黒い線は、1 秒あたりに受信したメッセージ総数をシステム別 (たとえば、両方の受信サーバーのシステムごと) に示しています。  
  
- グラフの下部の線は、各 SQL Server のメッセージ ボックス スプールの深さを示しています。  
  
  安定したスプールの深さの最大値に到達するまでシステムを駆動すると、MST は 1 秒あたりに受信したメッセージ数で測定されます。 このシナリオでは、記載してあるハードウェアで 290 メッセージ/秒の MST に到達しました。  
  
> [!NOTE]
>  時間の経過と共に、スプールの深さが安定しなくなる点までシステムを駆動すると、MST を超えます。 スプールの深さの安定状態が保たれ、追加のメッセージ バックログを発生しないで、システムでメッセージ バックログを処理できる最大負荷を評価するには、さまざまな負荷を使用して複数のテストを実行する場合もあります。  
  
 BizTalk 展開パフォーマンスを分析する際には、常にリソースのボトルネックについて理解するために主要な指標を確認する必要があります。 維持可能な最大スループットで実行されているこの展開で使用する主要な指標とその値は、次のとおりです。  
  
 **CPU 使用率**  
  
|[サーバー]|CPU の平均使用率|  
|------------|-----------------------------|  
|BizTalk Server|55%|  
|SQL Server (マスター メッセージ ボックス サーバー)|76%|  
|SQL Server (その他のメッセージ ボックス サーバー)|83%|  
  
 **物理ディスクのアイドル時間**  
  
|[サーバー]|ディスク アイドル平均時間|  
|------------|----------------------------|  
|すべての SQL Server の平均|69%|  
  
 **SQL Server の SQL ロック**  
  
|パラメーター|値|  
|---------------|-----------|  
|1 秒あたりのロック タイムアウト合計平均 (SQL Server ごと)|1980|  
|ロック待機時間合計平均 (ms)|495|  
  
 このテスト中、BizTalk または SQL Server アプリケーション ログではエラーは生成されませんでした。  
  
 このデータから、次の結論を下すことができます。  
  
- システムには明らかなリソース ボトルネックはありません。  
  
- これらの指標はすべて健全な制限範囲内です。  
  
- CPU とディスク アイドル時間には、十分なヘッドルームがあり、いっぱいになるまでにはかなりの余裕があります。  
  
- SQL ロック インジケーターは見栄え**Lock timeouts/sec**までおよそ 5000 (SQL Server) によって問題なく起動しないロック待機時間 1 秒以下でされても正常な状態です。  
  
  維持可能な最大スループットを確認する方法を説明し、維持可能な健全なシステムの主要な指標がどのようなものかを確認しました。次に、ガベージの処理と収集よりも受信の速度が速いシステムに関連する動作について検討します。 続行する[ロード テストをオーバー ドライブ](../core/overdrive-load-test.md)します。  
  
## <a name="see-also"></a>参照  
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [オーバードライブ ロード テスト](../core/overdrive-load-test.md)