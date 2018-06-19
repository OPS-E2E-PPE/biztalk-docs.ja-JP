---
title: BizTalk メッセージングを使用してエンジン |Microsoft ドキュメント
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
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288042"
---
# <a name="using-the-biztalk-messaging-engine"></a>BizTalk メッセージング エンジンの使用
メッセージング エンジンのアーキテクチャを次の図に示します。 メッセージがアダプターによって受信され、BizTalk Server に送信されるシナリオを示しています。  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
メッセージング エンジンのアーキテクチャ  
  
 各アダプターには、独自のインスタンス、 **TransportProxy**メッセージング エンジンとの対話に使用されるオブジェクト。 アダプターとメッセージング エンジンとの対話はバッチ単位で実行され、バッチには分離的な処理が適用されます。 バッチとは、SubmitMessage、SuspendMessage、DeleteMessage などの操作をひとまとめにしたものです。  
  
 アダプターがメッセージング エンジンにメッセージを送信するときに、具体的にどのような処理が行われるかを次に示します。  
  
1.  アダプターが新しいメッセージを作成し、データ ストリームをメッセージに接続します。  
  
2.  アダプターが新しいバッチをメッセージング エンジンから取得します。  
  
3.  送信対象のバッチに対し、アダプターがメッセージを追加します。  
  
4.  バッチがコミットされ、メッセージング エンジンのスレッド プールのキューに格納されます。  
  
5.  メッセージング エンジンのスレッド プールが新しいバッチの処理を開始します。  
  
6.  メッセージが受信パイプラインで処理されます。  
  
7.  受信パイプラインがメッセージ (ゼロ個以上) を生成します。 パイプラインでは、エラーが発生しない限り、メッセージを処理できます。 受信パイプラインで複数のメッセージが生成される場合もあります。複数のメッセージが生成される典型的なケースとしては、逆アセンブラー コンポーネントが、単一のインターチェンジを複数のメッセージに逆アセンブルする場合などが考えられます。 通常、送信されたメッセージは、受信パイプラインによって XML として正規化されます。  
  
8.  マッピングが構成されていた場合、パイプラインによって生成されたメッセージが、マッパーで処理されます。  
  
9. メッセージがメッセージ エージェントまたはメッセージ ボックス データベースに公開されます。  
  
10. メッセージング エンジンが、アダプターをコールバックし、バッチの処理結果を通知します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)  
  
-   [メッセージの順次配送](../core/ordered-delivery-of-messages.md)  
  
-   [エラー処理](../core/error-handling.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がサイズの大きいメッセージを処理する方法](../core/how-biztalk-server-processes-large-messages.md)   
 [エンジン パフォーマンスの特性](../core/engine-performance-characteristics.md)   
 [維持可能な最大のエンジン スループットの測定](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [エンジンの MST を測定するためのシナリオをテストします。](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [Microsoft BizTalk LoadGen 2007 ツールの使用](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)