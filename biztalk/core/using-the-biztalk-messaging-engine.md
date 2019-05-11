---
title: BizTalk メッセージングを使用してエンジン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 598a7030b885057dc7781336c2925f0cb99b17fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395185"
---
# <a name="using-the-biztalk-messaging-engine"></a>BizTalk メッセージング エンジンを使用します。
次の図は、メッセージング エンジンのアーキテクチャを示しています。 メッセージがアダプターによって受信および BizTalk Server に送信されるシナリオを示しています。  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
メッセージング エンジンのアーキテクチャ  
  
 各アダプターに独自のインスタンスには、 **TransportProxy**メッセージング エンジンと対話するために使用するオブジェクト。 アダプターは、バッチ、アトミックに処理されますが、メッセージング エンジンに対する作業を実行します。 バッチは、SubmitMessage、suspendmessage、DeleteMessage などの操作のコレクションです。  
  
 以下は、一連のシナリオでは、アダプターがメッセージング エンジンにメッセージを送信するイベントです。  
  
1.  アダプターは、新しいメッセージを作成し、データ ストリームをメッセージに接続します。  
  
2.  アダプターは、メッセージング エンジンから新しいバッチを取得します。  
  
3.  アダプターでは、送信するバッチにメッセージを追加します。  
  
4.  バッチがコミットされ、メッセージング エンジン スレッドのプールでキューに登録します。  
  
5.  メッセージング エンジン スレッドのプールでは、新しいバッチの処理を開始します。  
  
6.  メッセージは、受信パイプラインで処理されます。  
  
7.  受信パイプラインは、0 個以上のメッセージを生成します。 パイプラインは、すべてのエラーを返さないを提供するメッセージを使用できます。 受信パイプラインは、1 つ以上のメッセージを生成できます通常は、逆アセンブラー コンポーネントがメッセージの数に 1 つのインターチェンジを逆アセンブルするときに発生します。 通常、受信パイプラインは、送信されたメッセージを XML に正規化します。  
  
8.  マッピングが構成されている場合、パイプラインによって生成されたメッセージは、マッパーで処理されます。  
  
9. メッセージは、メッセージ エージェントまたはメッセージ ボックス データベースに公開されます。  
  
10. メッセージング エンジンがアダプター バッチの処理の結果を通知するコールバックします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)  
  
-   [メッセージの配信を順序付け](../core/ordered-delivery-of-messages.md)  
  
-   [エラー処理](../core/error-handling.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がサイズの大きいメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md)   
 [エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [エンジンの MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Microsoft BizTalk LoadGen 2007 ツールを使用](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)