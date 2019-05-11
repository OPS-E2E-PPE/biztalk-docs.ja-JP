---
title: MLLP 送信アダプターの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- send adapters
- MLLP adapters, send adapters
ms.assetid: b8e47c7f-4a69-4f0c-86b4-26ed9c70613c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180e11f3f4c4c0406927614d4351eb19fef1fb95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290394"
---
# <a name="mllp-send-adapter-processing"></a>MLLP 送信アダプターの処理
最小限の下位レイヤー プロトコル (MLLP) 送信アダプターでは、次の構成で一方向と双方向トランスポート モードをサポートしています。  
  
-   双方向の送信請求-応答送信アダプター  
  
-   一方向の送信アダプターの受信確認 (Ack) を受信するように構成  
  
-   一方向の送信アダプターが構成されている戻りメッセージが表示されません。  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>双方向の送信請求-応答送信の MLLP アダプター  
 エンド ツー エンドの真の同期シナリオでは、このアダプターを使用します。 そのため、このアダプターは、1 つの送信先パーティでのみ使用できます。 送信アダプターはリモート パーティ (URL) に対して開いている接続を維持して継続的に要求の応答を返信メッセージにルーティングされるまで受信ポート。 要求応答/送信請求-応答処理のアーキテクチャの次の図を参照してください。  
  
 このアダプタを使用する場合は、ACK または応答メッセージを基幹業務アプリケーションに返されるシステムに送信できます。 そのためには受信確認をルーティングする送信パイプラインで要求-応答受信ポートの設定、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 ACK を返すには、このプロパティを選択するかを返す応答の会議の選択を解除します。  
  
 このアダプターを使用して送信ポートには、元のメッセージが正常に送信されたら[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]そのメッセージを削除します。 この送信ポートに関連付けられている受信パイプラインに ACK が生成されます。 BizTalk では、その応答の MSA2 フィールドの値に関係なく、ソース アプリケーションに、クエリの応答を転送します。  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>一方向の送信の MLLP アダプターに Ack を受信するように構成  
 このアダプターは、同じソケット接続、元のメッセージを送信し、Ack を受信場所に配信することで、Ack を受信します。 送信アダプターはリモート パーティ (URL) に対して開いている接続を継続的に維持の待機中のメッセージがない場合でも[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ことにお送りします。 いくつかのポートは、同じリモート パーティを指している、送信アダプターは送信ポートごとに 1 つの接続を保持します。  
  
 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信場所、TwoWayAckReceiveLocation が既定のインストールをセットアップします。 これを使用することができますの Ack を受信するための受信場所、MLLP 送信アダプター。 このアダプターを使用して、送信ポートのこの構成では、送信ポートと受信場所を関連付けることが必要です。  
  
 MSA フィールドでは、応答メッセージを受信する、または複数の送信先をサポートするためを設定する場合は、この送信ポートを使用します。 双方向の送信請求-応答アダプターでは、MSA フィールドまたは複数の送信先は機能しません。  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>一方向の MLLP で受信した受信確認の送信アダプター  
 Ack 用に構成されたの一方向 MLLP 送信アダプターは、1 つは受信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]元のメッセージをメッセージ ボックス データベースから削除、再試行、または ACK の種類に応じて、これを中断します [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2 つのフェーズでは、ACK を解析します。  
  
- 最初のフェーズは、送信アダプターで行われる場所[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSA1 ACK の種類を決定するフィールドを解析します。  
  
- 2 番目のフェーズで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK の完全な解析を実行し、メッセージ ボックス データベースに ACK に送信します。  
  
  双方向の送信アダプターではの ACK を構成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
  次の表は、元のメッセージの MLLP 送信アダプターが受信できる Ack および動作の結果を示します。  
  
|受信した ACK|元のメッセージに対するアクション|  
|------------------|------------------------------------|  
|コミットが受け入れるか、アプリケーションがそのまま使用|メッセージ ボックス データベースから削除します。|  
|コミット/アプリケーション、拒否、ACK または ACK が無効です。|[中断]|  
|コミット/アプリケーション エラー|バックアップ トランスポート/中断するには、再試行/移動|  
|静的な確認成功|メッセージ ボックス データベースから削除します。|  
|静的な確認エラー|[中断]|  
  
 次の表は、無効な条件を確認します。  
  
|Instance|条件|  
|--------------|---------------|  
|HL7 (強化された、元の遅延)|1.XML は含まれません。<br />2.構造を持っていないため、MSA1 フィールドを取得することはできません。または、(CA、AA、CR、AR、CE、AE) に指定できる値のいずれかの MSA1 フィールドを含んでいません。|  
|スタティック|確認の失敗または成功した場合に指定できる値のいずれかと一致しません|  
|XML が含まれています|(コンテンツ) に関係なく受け入れ ACK として扱われ、元のメッセージを削除しています。|  
  
### <a name="error-conditions"></a>エラー条件  
 エラー状態または非アクティブ状態が存在とは、次の処理を発生することができます。  
  
- 送信メッセージにシリアル化に失敗した場合、送信アダプターはメッセージを送信、メッセージのバッチである場合を除き[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をストリーミングします。 場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアル化の障害を検出、メッセージの途中で、アダプターは送信しません EB/CR 以降[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が完全なメッセージを送信していません。 パイプラインは、エラーを記録し、アダプターがバッチ メッセージを再送信しようとします。  
  
- 送信操作に失敗した場合、アダプターは送信ポートの構成設定で指定された回数まで、もう一度メッセージを送信しようとします。 再試行を試みた後、メッセージに存在する場合をバックアップ トランスポートに移動します。 すべてうまくいかなかった場合は、メッセージは中断されます。 保留メッセージは、元の (XML) 形式になります。  
  
  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] エラー条件を記述する次のイベントを生成できます。  
  
|        イベント        |  ID  |                                                                                                                                   エラー条件                                                                                                                                   |
|---------------------|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ErrorSendingMessage | 8450 | リモート パーティにメッセージを送信できませんでした。 最も一般的な理由は、ネットワーク障害またはタイムアウトです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] サイズの大きいメッセージをシリアル化中に、送信パイプラインが失敗した場合、このエラーを報告する可能性があります。 |
|  ErrorReceivingAck  | 8451 |                                                                                                       ネットワークの障害またはタイムアウトのため、受信確認を受信しませんでした。                                                                                                       |
|   ErrorConnecting   | 8453 |                                                    リモート パーティへの TCP 接続を確立できませんでした: ホスト名を解決できませんでした」または「リモート パーティがポートでリッスンしていないか、接続が拒否しています。                                                     |
  
> [!NOTE]
>  送信先パーティ (元のメッセージの MSH5) での構成を決定するかどうか[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 または静的の確認が必要です 、一致しない場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を無効として扱われます。  
  
 MLLP 送信アダプターのプロセスと ACK、ACK が独自のメッセージとして受信場所に配信されます。 逆アセンブラーは、受信パイプラインによって報告されたエラーを解析中になる可能性があります、ACK や、ACK が中断されるの完全な解析を実行します。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [ACK を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)