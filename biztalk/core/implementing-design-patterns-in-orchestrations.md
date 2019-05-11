---
title: オーケストレーションでの設計パターンの実装 |Microsoft Docs
description: アグリゲーター、コンテンツ ベース ルーティング、動的ルーター、エラー処理、メッセージ ブローカー、および BizTalk Server でより多くの設計パターン
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f62ba955-018a-40e7-b303-497acc906019
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 932a9563c338be0e5e29a2968ea4da52e1b65045
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332429"
---
# <a name="implement-design-patterns-in-orchestrations"></a>オーケストレーションでの設計パターンを実装します。
このセクションでは、BizTalk Server のエンタープライズ統合パターンとプログラミングの一般的なパターンについて説明します。 1 つのパターンを活用したり、ビジネス プロセスを設計し、BizTalk オーケストレーション デザイナーで図形を使用して、デザインを実装する複数のパターンを結合できます。  
  
## <a name="design-patterns"></a>設計パターン  
 次のエントリの簡単な各パターンについて説明し、トピックまたは BizTalk オーケストレーション デザイナーを使用してパターンを実装する方法を示すサンプル をポイントします。  
  
### <a name="aggregator"></a>アグリゲーター  
 アグリゲーターは、複数のソースから情報を受け取って、1 つのメッセージに統合するパターンです。 このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)します。  
  
### <a name="calling-pipelines-from-an-orchestration"></a>オーケストレーションからパイプラインを呼び出す  
 送信を呼び出すし、オーケストレーションから受信パイプラインことができます。 パイプラインの再利用は、このパイプライン ステージからオーケストレーションの分離の維持にも役立ちます。 このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)します。 別の例は」の CMP.odx[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)します。 参照してください[パイプラインを実行する式を使用する方法](../core/how-to-use-expressions-to-execute-pipelines.md)します。  
  
### <a name="composed-message-processor"></a>構成済みメッセージ プロセッサ  
 構成済みメッセージ プロセッサは、処理、集計またはバッチ化されたインターチェンジ メッセージから個々 の項目のパターンです。 このパターンの例は、」の CMP.odx を参照してください。[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)します。  
  
### <a name="content-based-router"></a>コンテンツ ベースのルーター  
 コンテンツ ベースのルーターは、メッセージの内容の一部に基づいてメッセージの受信者を決定するパターンです。 このパターンの例は、次を参照してください。 [CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)します。  
  
### <a name="dynamic-router"></a>動的ルーター  
 動的ルーターは、送信先アドレスとメッセージの処理の結果に基づいて、トランスポート プロトコルを決定するパターンです。 動的送信ポートを使用する、または**ロール リンク**図形をこのパターンを実装します。 このパターンの例は、」の ReceiveSend.odx を参照してください。 [SendMail](../core/sendmail.md)します。 別の例は、SupplierProcess.odx [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)します。  
  
### <a name="error-handling"></a>エラー処理  
 BizTalk Server では、保留キューに配置の失敗したメッセージの既定の動作の代替としてのエラーのメッセージの自動処理を指定できます。 失敗したメッセージは、レポートまたは処理のためにサブスクライブしているポートにルーティングできます。 このパターンの例は、」の ResubmitLogic.odx を参照してください。[エラー処理 (BizTalk Server Samples フォルダー)](../core/error-handling-biztalk-server-samples-folder.md)します。  
  
### <a name="exception-handling-and-compensation"></a>例外処理と補正  
 例外ハンドラーを使用して、**例外のスロー**図形または**式**例外処理の形状。 次のコードを配置するなど、**式**例外をスローする図形:  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 補正ブロックを使用して、**補正**図形でコミットされたトランザクション、補正を実行します。 このパターンの例は、」の UpdateContact.odx を参照してください。[補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)します。 別の例は[カスタム例外](../core/custom-exceptions.md)します。  
  
### <a name="message-broker"></a>メッセージ ブローカー  
 メッセージ ブローカーは、メッセージの送信先を判断して、メッセージ フローの制御を維持しのパターンです。 詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)します。  
  
### <a name="message-filter"></a>メッセージ フィルター  
 メッセージ フィルター パターンは、処理のための特定の条件を満たすメッセージを選択します。 このパターンを実装するには、アクティブなにフィルター式を追加して**受信**図形。 詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)します。  
  
### <a name="message-translator"></a>メッセージ トランスレーター  
 メッセージ トランスレーター パターンは、メッセージを 1 つの形式から別の形式に変換します。 使用して BizTalk マップを使用してこのパターンを実装することができます、**変換**のオーケストレーションの図形。 このパターンの例は、」の HelloOrchestration.odx を参照してください。 [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)します。  
  
### <a name="parallel-convoy"></a>パラレルなコンボイ  
 パラレルなコンボイ パターンでは複数の単一項目を結合して、個々 の項目が単独で実現できないことを実現します。 関連項目のセットは、任意の順序で受信されることは、プロセスを開始する前にすべての BizTalk Server で受信する必要があります。 
  
### <a name="scatter-and-gather"></a>スキャッター/ギャザー  
 スキャッター/ギャザー パターンは、複数の受信者に送信されるメッセージと各受信者から受信されるメッセージを使用できます。 分割パターンおよびアグリゲーター パターンを使用して、このパターンを実装することができます。 アグリゲーター パターンを使用して、分割パターンの使用から結果をアセンブルし、下に配置する、**並列アクション**図形。 
  
### <a name="sequential-convoy"></a>シーケンシャルなコンボイ  
 シーケンシャルなコンボイ パターンにより、複数の単一項目を結合して、個々 の項目が単独で実現できないことを実現します。 シーケンシャルなコンボイには、定義済み順序を持つ関連する項目のセットです。 項目が正確に同じである必要はありませんが、BizTalk Server は、順番に項目を受け取る必要があります。 
  
### <a name="splitter"></a>分割線  
 分割パターンは、1 つのメッセージを受け取り、複数のメッセージに分割されます。  
  
### <a name="suspend-with-retry"></a>中断後再試行  
 中断後再試行パターンは、エラーがある場合にメッセージを中断するオーケストレーションを使用できます。 オーケストレーションを中断します、オペレーターの介入を要求し、固定回数だけ操作を再試行できるように、ループ内で中断が発生します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション フローの設計](../core/designing-orchestration-flow.md)