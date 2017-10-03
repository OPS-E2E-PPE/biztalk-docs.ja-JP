---
title: "TIBCO Rendezvous から BizTalk Server を使用してメッセージを受信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- receiving messages
- memory use
ms.assetid: 4eee9c3a-2966-4d5f-ba49-201bb488458c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac81f269e19526f5466e8c12115d617b8171da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a>TIBCO Rendezvous から BizTalk Server を使用してメッセージを受信する
Microsoft BizTalk Adapter for TIBCO Rendezvous は、複数のスレッドのキューからイベントをディスパッチします。 BizTalk Server の受信場所は、1 つの TIBCO Rendezvous イベント キューおよびそのディスパッチャー スレッドのプールと関連付けられています。  
  
## <a name="memory-use-and-errors"></a>メモリの使用とエラー  
 イベントの処理中、アダプターは使用されるリソースを監視します。 メモリの使用量が上限 Watermark を超えると、アダプターはメモリ使用量が下限 Watermark に達するまでイベントのディスパッチを停止します。 これにより TIBCO Rendezvous メッセージが未証明メッセージとして失われる場合があることに注意してください (TIBCO RV コンシューマーは 60 秒経過したらメッセージをキューから削除します)。 このデータ損失はエラーとして報告されます。 アダプターが TIBCO Rendezvous のシステム通知 NO_MEMORY メッセージを受け取ったら、メッセージは既に失われています。  
  
 BizTalk Adapter for TIBCO Rendezvous は状態を保持しており、状態に応じて異なるタスクを実行します。 BizTalk メッセージ エンジンがエラーを報告し、アダプターが証明されたリスナーとして構成されている場合、アダプターは TIBCO Rendezvous にエラーを報告してメッセージを再送信できるようにします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md)   
 [作成元の TIBCO Rendezvous 受信ハンドラー](../core/creating-tibco-rendezvous-receive-handlers.md)