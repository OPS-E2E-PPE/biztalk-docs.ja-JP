---
title: "既知の問題をバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47246662c5945f8ef09040ec7a8aa49326f59db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batching-known-issues"></a>バッチ処理に関する既知の問題
このセクションには、バッチ処理のエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a>文字列にある場合でも、バッチ トレーラー セグメント (FTS および BTS) フィールドが受け入れられます  
 HL7 は、HL7 のさまざまなバージョンの異なる方法で FTS および BTS セグメント内のフィールドを指定します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]として文字列データ型の不整合を回避するには、すべてのフィールドを定義します。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>バッチ メッセージに ACK のデータ型  
 バッチ メッセージを送信元パーティの断片化がオフの場合、MSH10 への応答で生成された確認 (ACK) メッセージには、フィールド (メッセージ コントロール ID) はバッチ メッセージの MSH10 フィールドの他の任意のデータ型ではなく、GUID になります。  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a>BTAHL7 構成エクスプ ローラーとバッチの作成のオーケストレーションが双方向ではない同期  
 F5 キーを押した場合でも、バッチ コントロール スケジュールの現在の状態を表示できない可能性がある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、両方を確認する必要がありますと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]現在の構成のエクスプ ローラーおよび状態と動作状況の追跡 (HAT) ツールバッチ コントロール スケジュールの状態です。  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a>ときに 2 つの解析エラーのログ記録のメッセージでバッチ/バッチをシナリオに検証エラーを含める  
 バッチ内の最初のメッセージのバッチをシナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています/[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラーをログに記録します。 最初のエラーが、バッチの最初のメッセージに関連し、メッセージの残りの部分に関連する 2 番目のエラーです。  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a>サブスクリプションは、BTS を使用します。バッチの MessageType プロパティで無効になっている断片化のバッチをシナリオがサポートされていません  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用してサブスクリプションをサポートしていません、 **BTS です。MessageType**バッチのプロパティで複数のメッセージ型から構成されるインターチェンジとして無効になっている断片化とシナリオをバッチ/です。  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a>バッチ内のエラー メッセージの後に中断されているバッチ全体のシナリオをバッチ処理/  
 場合、致命的なパーサー エラーがメッセージ (たとえば、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9、または読み込めませんでしたメッセージのスキーマを MSH 12 または本文を解析しません) が断片化されるバッチ内で発生したでバッチ アウト シナリオでは、すべてのデータは、エラー メッセージが中断された後でも/場合、。回復可能なインターチェンジのサポートが有効になっています。  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a>Ack のバッチのバッチの最初のメッセージの送信元パーティにルーティングのシナリオをバッチ処理/  
 内でバッチ/Ack のシナリオ バッチのバッチを取得、最初のメッセージのソース パーティ情報に基づくのでルーティング受信内のすべてのメッセージ バッチのソースと変換先のパーティが同じにすると、この機能プログラムがあると想定します。  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a>Ack のバッチと双方向の送信元パーティにルーティングされませんは受信ポートはバッチで使用のシナリオをバッチ処理/  
 要求-応答が発生した場合の受信ポート、ACK または NACK バッチは BIBO シナリオの送信元パーティにルーティングされません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)