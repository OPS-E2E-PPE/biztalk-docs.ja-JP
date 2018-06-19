---
title: オーケストレーションのデザイン パターンを実装する |Microsoft ドキュメント
description: アグリゲーター、コンテンツ ベースのルーティング、動的ルーター、エラー処理、メッセージ ブローカー、および BizTalk Server での複数のデザイン パターン
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
ms.openlocfilehash: 290b31e8d5494c7a00eb02517e910fc877da9124
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014249"
---
# <a name="implement-design-patterns-in-orchestrations"></a>オーケストレーションのデザイン パターンを実装します。
ここでは、BizTalk Server の一般的なプログラミング パターンとエンタープライズ統合パターンについて説明します。 単一のパターン、または複数のパターンの組み合わせを利用してビジネス プロセスをデザインし、そのデザインを BizTalk オーケストレーション デザイナーの図形によって実装することができます。  
  
## <a name="design-patterns"></a>デザイン パターン  
 次のエントリでは、各パターンについて簡潔に説明し、BizTalk オーケストレーション デザイナーを使用したパターンの実装方法を説明した他のトピックやサンプルについても記載しています。  
  
### <a name="aggregator"></a>アグリゲーター  
 アグリゲーターは、複数のソースから情報を取得して単一のメッセージに統合するパターンです。 このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。  
  
### <a name="calling-pipelines-from-an-orchestration"></a>オーケストレーションからのパイプラインの呼び出し  
 使用しているオーケストレーションから送信パイプラインおよび受信パイプラインを呼び出すことができます。 これによって、パイプラインの再利用が可能になり、パイプライン ステージからオーケストレーションを分離できます。 このパターンの例は、」の Aggregate.odx を参照してください。[アグリゲーター (BizTalk Server サンプル)](../core/aggregator-biztalk-server-sample.md)です。 別の例は」の CMP.odx[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)です。 関連項目[式を使用してパイプラインを実行する方法](../core/how-to-use-expressions-to-execute-pipelines.md)です。  
  
### <a name="composed-message-processor"></a>構成済みメッセージ プロセッサ  
 構成済みメッセージ プロセッサは、集計またはバッチ化されたインターチェンジ メッセージの個別の項目を処理するパターンです。 このパターンの例を参照してください」の CMP.odx[で構成されるメッセージ プロセッサ (BizTalk Server サンプル)](../core/composed-message-processor-biztalk-server-sample.md)です。  
  
### <a name="content-based-router"></a>コンテンツ ベースのルーター  
 コンテンツ ベースのルーターは、メッセージのコンテンツの一部に基づいてメッセージの受信者を決定するパターンです。 このパターンの例は、次を参照してください。 [CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)です。  
  
### <a name="dynamic-router"></a>動的ルーター  
 動的ルーターは、メッセージ処理の結果に基づいて送信先アドレスとトランスポート プロトコルを決定するパターンです。 動的送信ポートを使用する、または**ロール リンク**図形をこのパターンを実装します。 このパターンの例は、」の ReceiveSend.odx を参照してください。 [SendMail](../core/sendmail.md)です。 別の例は、SupplierProcess.odx に[PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)です。  
  
### <a name="error-handling"></a>エラー処理  
 BizTalk Server を使用すると、失敗したメッセージを保留キューに配置する既定の処理の代わりに、失敗したメッセージの自動処理を指定できます。 報告用または処理用のサブスクライブの対象となるポートに失敗したメッセージをルーティングすることができます。 このパターンの例は、」の ResubmitLogic.odx を参照してください。[エラー処理 (BizTalk Server Samples フォルダ)](../core/error-handling-biztalk-server-samples-folder.md)です。  
  
### <a name="exception-handling-and-compensation"></a>例外処理と補正  
 例外ハンドラーを使用して、**例外のスロー**図形または**式**例外処理の図形。 たとえばで次のコードを配置することができます、**式**例外をスローする図形:  
  
```  
excp = new System.Exception();  
throw(excp);  
```  
  
 補正ブロックを使用することができます、**補正**図形をトランザクションがコミットされましたが、補正を実行します。 このパターンの例は、」の UpdateContact.odx を参照してください。[補正 (BizTalk Server サンプル)](../core/compensation-biztalk-server-sample.md)です。 別の例では、[カスタム例外](../core/custom-exceptions.md)です。  
  
### <a name="message-broker"></a>メッセージ ブローカー  
 メッセージ ブローカーは、メッセージ フローの制御を維持しながらメッセージの宛先を決定するパターンです。 詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。  
  
### <a name="message-filter"></a>メッセージ フィルター  
 メッセージ フィルターは、処理の特定の基準を満たすメッセージを選択するパターンです。 このパターンを実装するには、アクティブなにフィルター式を追加して**受信**図形です。 詳細については、次を参照してください。[を使用してフィルターと、受信メッセージ図形](../core/using-filters-with-the-receive-message-shape.md)です。  
  
### <a name="message-translator"></a>メッセージ トランスレーター  
 メッセージ トランスレーターは、メッセージの形式を別の形式に変換するパターンです。 BizTalk マップを使用して、このパターンを実装することができます、**変換**オーケストレーションの図形です。 このパターンの例は、」の HelloOrchestration.odx を参照してください。 [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)です。  
  
### <a name="parallel-convoy"></a>パラレルなコンボイ  
 パラレルなコンボイは、複数の単一項目を結合し、個々の項目が単独では実現できない処理を可能にするパターンです。 関連する一連の項目は任意の順序で受信されることがありますが、BizTalk Server は、プロセスの開始前にそのメッセージのすべてを受信する必要があります。 
  
### <a name="scatter-and-gather"></a>スキャッター/ギャザー  
 スキャッター/ギャザーは、複数の受信者にメッセージを送信し、各受信者から返されるメッセージを受信できるようにするパターンです。 このパターンは、分割パターンおよびアグリゲーター パターンを使用して実装できます。 アグリゲーター パターンを使用して、分割パターンを使用してから、結果をアセンブルし、下に配置する**並列アクション**図形です。 
  
### <a name="sequential-convoy"></a>シーケンシャルなコンボイ  
 シーケンシャルなコンボイは、複数の単一項目を結合し、個々の項目が単独では実現できない処理を可能にするパターンです。 シーケンシャルなコンボイは、事前定義された順序を持つ一連の関連する項目です。 項目は完全に同一である必要はありませんが、BizTalk Server は各項目を順番に受け取る必要があります。 
  
### <a name="splitter"></a>スプリッター  
 分割は、1 つのメッセージを複数のメッセージに分割するパターンです。  
  
### <a name="suspend-with-retry"></a>中断後再試行  
 中断後再試行は、オーケストレーションがエラー発生時にメッセージを中断できるようにするパターンです。 中断はループ内で発生するので、オーケストレーションでは中断してオペレーターの介入を求め、一定の回数だけ操作を再試行します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション フローの設計](../core/designing-orchestration-flow.md)