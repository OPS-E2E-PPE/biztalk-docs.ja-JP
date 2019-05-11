---
title: 'シナリオ 4: すべてのメッセージの追跡データベースのサイズ調整 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: db1126c7-0b86-4635-bfdc-3b69a82cc64b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 123423003377d199ebd2aea54674fe820d8debff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308566"
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a>シナリオ 4: すべてのメッセージの追跡データベースのサイズ調整
Microsoft® BizTalk Server® 2004 の実装に存在するすべての 3 つのメッセージ シナリオがある場合は一緒に追加する必要があります。 すべてのシナリオの結果を、BizTalk 追跡データベースのサイズを決定します。  
  
 前述の例: から  
  
|シナリオ|1 GB 単位、年、必要な領域|  
|--------------|-------------------------------------|  
|単純なメッセージ|4.78|  
|オーケストレーション内のメッセージ|7.18|  
|配布リストに送信されるオーケストレーション内のメッセージ|10.8|  
|**合計**|22.04|  
  
 さらに、メッセージ本文のすべての 3 つのシナリオの追跡を有効にすることと、次の結果が得は。  
  
|シナリオ|1 GB 単位、年、必要な領域|  
|--------------|-------------------------------------|  
|単純なメッセージ|50.1|  
|オーケストレーション内のメッセージ|50.1|  
|配布リストに送信されるオーケストレーション内のメッセージ|83.45|  
|**合計**|183.65|  
  
 これは、総計 205.69 GB 増加の前年比成長ごとに、BizTalk 追跡データベース。 この図では、コンティンジェンシーは含まれません。 お勧めこの合計に予備の 10% を追加する場合、BizTalk 追跡データベースが 1 年あたり 227.94 GB の成長に計画してください。 さらに、SQL のインデックスやストレージなどが原因のオーバーヘッドを検討してください。可能であれば、テストでテスト シナリオを実行した後、増加率基にする必要があります。  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a>その他の要因に影響を与える BizTalk 追跡データベースのサイズ  
 BizTalk 追跡データベースのサイズに影響を与えることも、オーケストレーション内で使用する図形などの他の項目があります。  
  
 オーケストレーション デバッガーのオプションがオンの場合、既定では、オーケストレーション内の各図形の状態保存されている BizTalk 追跡データベースにします。  
  
 図形の状態を追跡するために必要なサイズを決定する数式です。  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 たとえば、次の図の場合は、BizTalk 追跡サイズを決定するは次の数式を使用します。  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 ![オーケストレーションの例](../core/media/sample-orchestration.gif "Sample_orchestration")  
  
 このオーケストレーションで 350万メッセージを処理すると、想定した場合、このオーケストレーションを追跡するために必要な追加領域は次のようになります。  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 各オーケストレーションを BizTalk 追跡データベースのおおよそのサイズを取得する"on"に設定するオーケストレーション デバッガーを持つアカウントが必要になります。  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズにメッセージ変数を使用します。](../core/using-message-variables-to-size-the-tracking-database.md)   
 [メッセージ本文を追跡する追跡データベースのサイズ調整](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [シナリオ 1: 単純な BizTalk メッセージの追跡データベースのサイズ調整](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [シナリオ 2: オーケストレーション内のメッセージの追跡データベースのサイズ調整](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [シナリオ 3:配布リストに送信されるメッセージの追跡データベースのサイズ調整](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)