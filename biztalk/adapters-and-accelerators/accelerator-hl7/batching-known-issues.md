---
title: 既知の問題をバッチ処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae2c9fb3abf43d7eb62c0c78d03c30a33b45995c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251800"
---
# <a name="batching-known-issues"></a>バッチ処理に関する既知の問題
このセクションには、エラーをバッチ処理を回避するために役立つ有用な情報が含まれています。  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a>文字列にある場合でも、バッチ トレーラー セグメント (FTS および BTS) フィールドが受け入れられます  
 HL7 の HL7 のさまざまなバージョンの異なる方法で FTS および BTS のセグメントが、フィールドを指定します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 不整合を回避するために文字列データ型としては、すべてのフィールドを定義します。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>ACK をバッチ メッセージのデータ型  
 フィールド (メッセージのコントロール ID)、受信確認 (ACK) メッセージのバッチ メッセージには、送信元パーティの断片化がオフの場合、その後、MSH10 への応答で生成されたバッチ メッセージの MSH10 フィールドの他の任意のデータ型ではなく、GUID になります。  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a>BTAHL7 構成エクスプ ローラーと作成のバッチ オーケストレーションは双方向同期  
 F5 キーを押す場合でも、バッチのコントロールのスケジュールの現在の状態を表示することができない可能性がある[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、両方をチェックする必要がありますと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーと、状態と動作状況の追跡 (HAT) ツールで、現在のバッチのコントロールのスケジュールの状態です。  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a>ときに 2 つの解析エラーのログ記録のメッセージのバッチ処理/バッチ アウト シナリオは、検証エラーを含めることが  
 バッチ内の最初のメッセージで/バッチ アウト シナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラー ログに記録します。 最初のエラーが、バッチの最初のメッセージに関連し、2 番目のエラーに関連するメッセージの残りの部分。  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a>サブスクリプションは、BTS を使用します。バッチの MessageType プロパティで無効になっている断片化とバッチ アウト シナリオはサポートされていません  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 使用してサブスクリプションをサポートしていません、 **BTS します。MessageType**バッチのプロパティで/バッチ アウト シナリオと複数のメッセージの種類で構成されるインターチェンジとしては無効に断片化が発生します。  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a>バッチ内のエラーのあるメッセージの後に中断されたバッチ全体で/バッチ アウト シナリオ  
 致命的なパーサー エラーのあるメッセージの場合 (たとえば、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9 または読み込みに失敗したメッセージのスキーマを MSH 12 または本文を解析しません) が断片化したバッチで発生したで/バッチ アウト シナリオ、エラー メッセージが中断された後、すべてのデータも場合、回復可能なインターチェンジのサポートが有効になっています。  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a>バッチの最初のメッセージの送信元パーティにルーティングされる Ack のバッチで/バッチ アウト シナリオ  
 内でバッチ処理/バッチ アウト シナリオ バッチ Ack のルーティング、最初のメッセージのソースのパーティ情報に基づいて受信ですべてのメッセージ バッチのソースおよび変換先のパーティが同じにするこの機能仮定できないためです。  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a>Ack のバッチと双方向の送信元パーティにルーティングされませんは受信ポートはバッチで使用で/バッチ アウト シナリオ  
 要求-応答が発生した場合の受信ポート、ACK または NACK バッチは BIBO シナリオでは、ソース パーティにルーティングされません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)