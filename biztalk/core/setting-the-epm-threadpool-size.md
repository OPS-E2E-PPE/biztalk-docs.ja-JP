---
title: "EPM スレッド プール サイズを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54afa88b51876d0ee56f548f263be1b00c37967a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-epm-threadpool-size"></a>EPM スレッドプール サイズの設定
このトピックでは、エンド ポイント マネージャー (EPM) のスレッドプール サイズの設定方法について説明します。  
  
 **詳細** タブで、**ホストのプロパティ**ダイアログ ボックスで、というプロパティがある**CPU あたりのスレッドをメッセージング エンジンの最大数**です。 このダイアログ ボックスにアクセスする方法については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)です。 このプロパティを使用すると、メッセージを処理するためにメッセージング エンジンが使用するプロセス スレッドのプールのサイズを制御できます。 このプロパティの既定値は 20 です。つまり、サーバー上の CPU ごとに最大 20 個のスレッドを使用できます。  
  
 各スレッド プールでは、メッセージのバッチが処理される、ための値を調整する**CPU あたりのスレッドをメッセージング エンジンの最大数**サーバー上のリソース使用のダイナミクスを変更することでパフォーマンスに影響することができます。 Threadpool のしくみの詳細については、次を参照してください。 [BizTalk メッセージング エンジンを使用して](../core/using-the-biztalk-messaging-engine.md)です。  
  
 テストによれば、または SQL サーバーの CPU が過負荷の場合の値を小さく**CPU あたりのスレッドをメッセージング エンジンの最大数**スループットが向上になります。 たとえば、メッセージ ボックス データベース サーバーで CPU の使用率が 90% 以上と示されている場合、または SQL のロック待機時間が 500 ～ 1000 ミリ秒以上に上がった場合、プールのスレッド数が減り、SQL Server に接続している全体の接続数が少なくなります。このため、効率的なメッセージ処理が実現します。 最大スレッド プール サイズを 2 に設定すると、明確なスループットの向上が実現する場合があります。  
  
## <a name="recommendation"></a>推奨  
 BizTalk Server のインストールを最適化するときは、設定した値を調整微調整することをお勧め**CPU あたりのスレッドをメッセージング エンジンの最大数**です。  メッセージ ボックス データベース サーバーを使用する割合を減らす場合は、このプロパティの値を小さくすることを検討してください。  
  
 BizTalk server またはメッセージ ボックス データベース サーバーがない使用率の高い、追加の負荷を適用することは行われませんスループットがさらに、再試行の値を大きく**CPU あたりのスレッドをメッセージング エンジンの最大数**過小使用されたリソースの利用します。  
  
## <a name="see-also"></a>参照  
 [新しいホストを作成する方法](../core/how-to-create-a-new-host.md)   
 [BizTalk メッセージング エンジンを使用します。](../core/using-the-biztalk-messaging-engine.md)