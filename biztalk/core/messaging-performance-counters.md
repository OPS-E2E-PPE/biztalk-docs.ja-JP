---
title: "メッセージングのパフォーマンス カウンター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 162d761a-fe69-45b0-a6af-c5d9f714e0ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72604822559d855f51bd24c6eacae3be3be4cbdd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="messaging-performance-counters"></a>メッセージングのパフォーマンス カウンター
パフォーマンス カウンターを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。 パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。  
  
 次のパフォーマンス カウンターは各ホスト インスタンスにアクセスできる、 **BizTalk: メッセージング**と**BizTalk: メッセージング遅延**パフォーマンス オブジェクト カテゴリ。  
  
|**カテゴリ**|**カウンター**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:メッセージング|Active receive locations|このホスト インスタンスで現在有効化されている受信場所の数。|  
||Active receive threads|メッセージング エンジンが、このホスト インスタンスで実行されているアダプターから受け取ったメッセージを処理するために現在使用しているスレッド数。 送信アダプターにより非同期的に処理されたメッセージが含まれます。|  
||Active send messages|メッセージング エンジンが現在送信処理を行っているメッセージ数。 現在、送信パイプライン処理に存在するメッセージや、受信アダプターの応答メッセージが含まれます。|  
||Active send threads|メッセージング エンジンが、アダプターに送信するメッセージを処理するために現在使用しているスレッド数。 受信アダプターに対する応答メッセージが含まれます。|  
||Documents processed|処理されたドキュメント。|  
||Documents processed/Sec|1 秒あたりに処理されたドキュメント。|  
||Documents received|受信したドキュメント。|  
||Documents received/Sec|1 秒あたりに受信されたドキュメント。|  
||Documents resubmitted|送信アダプターによって再送信されたドキュメントの総数。|  
||Documents submitted/Batch|バッチごとに送信されたドキュメントの平均数。|  
||Documents suspended|保留にされたドキュメント数。|  
||Documents suspended/Sec|1 秒あたりに保留されたドキュメント数。|  
||Documents transmitted/Batch|バッチごとに送信されたメッセージの平均数。|  
||ID Process|このホスト インスタンスのプロセス識別子。|  
||Pending receive batches|メッセージング エンジンが受信したバッチのうち、処理が未完了のバッチ数。 送信アダプターにより非同期的に処理されたバッチが含まれます。|  
||Pending transmitted messages|メッセージング エンジンから送信アダプターに送られたバッチのうち、処理が未完了のバッチ数。 これにより、応答が含まれます。 メッセージの受信アダプター。|  
||Request/Response timeouts|アダプターによって指定された時間内に応答メッセージを受け取らなかった要求メッセージ数。|  
||Throttled receive batches|メッセージング エンジンが、サービスの負荷が高くなったために受信時にブロックしたバッチ数。 これらのバッチには、処理対象の新しいメッセージが含まれます。|  
|BizTalk:メッセージング遅延|Inbound Latency (sec)|アダプターからメッセージング エンジンへと渡されたドキュメントが、メッセージ ボックスに公開されるまでの平均待機時間 (ミリ秒)。|  
||Outbound Adapter Latency (sec)|メッセージング エンジンからアダプターに渡されたドキュメントが、アダプターによって送信されるまでの平均待機時間 (ミリ秒)。|  
||Outbound Latency (sec)|メッセージ ボックスからメッセージング エンジンへと渡されたドキュメントが、アダプターによって送信されるまでの平均待機時間 (ミリ秒)。|  
||Request-Response Latency (sec)|アダプターからメッセージング エンジンへと渡された要求が、応答ドキュメントとしてアダプターに返されるまでの平均待機時間 (ミリ秒)。|  
  
## <a name="to-access-performance-counters"></a>パフォーマンス カウンターにアクセスするには  
 パフォーマンス カウンターにアクセスするには、次の手順を実行します。  
  
#### <a name="if-you-are-using-windows-2008"></a>Windows 2008 を使用している場合  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**パフォーマンス モニター**です。  
  
2.  **パフォーマンス モニター** ] ダイアログ ボックスで、展開**の監視ツールを**[**パフォーマンス モニター**、順にクリック**追加**です。  
  
3.  **カウンターの追加** ダイアログ ボックスから、**使用可能なカウンター**一覧で、展開、 **BizTalk: メッセージング**パフォーマンス カウンター オブジェクトおよび監視するカウンターの選択  
  
4.  **インスタンスの選択したオブジェクト**一覧をクリックして、選択したカウンターを監視する特定のインスタンスを選択**追加**です。  使用可能なカウンターのすべてのインスタンスを選択するには、次のように選択します。 \<**すべてのインスタンス**\>です。  
  
5.  カウンターを追加すると、をクリックして**OK**です。  
  
     選択したパフォーマンス カウンターが表示されます、**パフォーマンス モニター**画面。  
  
## <a name="see-also"></a>参照  
 [パフォーマンスのヒントとテクニック](../core/performance-tips-and-tricks.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [維持可能な最大の追跡スループットの測定](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [ホスト制限によるリソース使用率の最適化](../core/optimizing-resource-usage-through-host-throttling.md)