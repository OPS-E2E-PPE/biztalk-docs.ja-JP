---
title: 送信アダプターの処理中の MLLP |Microsoft ドキュメント
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
ms.openlocfilehash: 1644d699014f23ce90568034c4bd90f6f0c7b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207530"
---
# <a name="mllp-send-adapter-processing"></a>MLLP 送信アダプターの処理
最小限の下位層プロトコル (MLLP) 送信アダプターは、次の構成で、一方向と双方向トランスポート モードをサポートします。  
  
-   双方向の送信請求-応答送信アダプター  
  
-   一方向の送信アダプターの受信確認 (Ack) を受信するように構成  
  
-   戻り値メッセージが表示されない用に構成された一方向の送信アダプター  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>双方向の送信請求-応答送信 MLLP アダプター  
 True のエンド ツー エンド同期シナリオでは、このアダプタを使用します。 そのため、このアダプターは、1 つの送信先パーティにのみ使用できます。 送信アダプターは、リモート パーティ (URL) に対して開いている接続を継続的に維持要求の応答を返信メッセージをルーティングするまでは、ポートを受信します。 要求応答/送信請求-応答処理のアーキテクチャの次の図を参照してください。  
  
 このアダプタを使用する場合は、ACK または応答メッセージを基幹業務アプリケーションに返されるシステムに送信できます。 これを行うと、確認をルーティング送信パイプラインに要求-応答受信ポートでの設定、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 ACK を取得するには、このプロパティを選択するかを返す応答会議の選択を解除します。  
  
 このアダプターを使用して送信ポートには、元のメッセージが正常に送信されたら[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]そのメッセージを削除します。 この送信ポートに関連付けられている受信パイプラインは ACK を生成していません BizTalk では、その応答の MSA2 フィールドの値に関係なく、ソース アプリケーションへのクエリ応答を転送します。  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>一方向の送信 MLLP アダプターの Ack を受信するように構成  
 このアダプターは、同じソケット接続で、元のメッセージを送信し、受信場所に Ack を配信ことで、Ack を受信します。 送信アダプターは、の待機中のメッセージがない場合でも継続的に、リモート パーティ (URL) に対して開いている接続を維持[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に送信します。 いくつかのポートは、同じリモート パーティを指している、送信アダプターによって送信ポートごとに 1 つの接続が保持されます。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信場所、TwoWayAckReceiveLocation が既定のインストールをセットアップします。 これを行うこともできますでの受信場所、送信アダプターが MLLP の Ack を受信するためです。 このアダプターを使用して、送信ポートのこの構成では、送信ポートと受信場所に関連付ける必要があります。  
  
 MSA フィールドでは、応答メッセージを受信する、または複数の変換先をサポートするためを設定する場合は、この送信ポートを使用します。 双方向の送信請求-応答アダプターでは、MSA フィールドまたは複数の変換先では機能しません。  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>一方向の MLLP で受信した受信確認の送信アダプター  
 Ack 用に構成された一方向 MLLP 送信アダプターでは、1 つは受信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]元のメッセージをメッセージ ボックス データベースから削除、再試行、または ACK の種類に応じて、それを一時停止 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 つのフェーズでは、ACK を解析します。  
  
-   最初のフェーズが、送信アダプターで行われる場所[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSA1 ACK の種類を決定するフィールドを解析して  
  
-   2 番目のフェーズで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK の完全な解析を実行し、MessageBox データベースに ACK を送信します。  
  
 双方向の送信アダプターを求めて、ACK を構成する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
 次の表は、元のメッセージの Ack MLLP 送信アダプターが受け取ることができると結果の動作を示します。  
  
|受信確認|元のメッセージのアクション|  
|------------------|------------------------------------|  
|コミットが受け入れるか、アプリケーションがそのまま使用|メッセージ ボックス データベースから削除します。|  
|コミット/アプリケーション、却下、ACK、無効な ACK|[中断]|  
|コミット/アプリケーション エラー|バックアップ トランスポート/中断する再試行/移動|  
|静的 ACK 成功|メッセージ ボックス データベースから削除します。|  
|静的 ACK エラー|[中断]|  
  
 次の表は、無効な ACK 条件を示します。  
  
|Instance|条件|  
|--------------|---------------|  
|HL7 (元の強化、遅延)|1.XML は含まれません。<br />2.構造体を持っていないため、MSA1 フィールドを取得することはできません。または、MSA1 フィールドを含んでいません (カナダ、AA、CR、AR、CE、AE) に指定できる値のいずれか。|  
|静的|確認の失敗または成功した場合に指定できる値のいずれかと一致しません|  
|XML が含まれています|(コンテンツ) に関係なく受け入れ ACK として扱われ、元のメッセージを削除します。|  
  
### <a name="error-conditions"></a>エラー条件  
 エラー状態または非アクティブ状態がある場合に、次のメッセージは発生します。  
  
-   送信メッセージは、シリアル化に失敗した場合、送信アダプターはメッセージを送信、バッチ メッセージがある場合を除き、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をストリーミングします。 場合と[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアル化の失敗を検出、メッセージの途中で、アダプターは送信しません EB/CR 以降[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は完全なメッセージを送信していません。 パイプラインが、エラーを記録し、アダプターがバッチ メッセージを再送信しようとします。  
  
-   送信操作が失敗すると、アダプターは送信ポートの構成設定で指定された再試行の数に達するまで、メッセージを送信しようとします。 再試行を試みた後は、いずれかが存在する場合も、メッセージは、バックアップ トランスポートに移動します。 他のすべてが失敗した場合は、メッセージは中断されます。 保留メッセージは、元の (XML) 形式になります。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラー条件を記述する次のイベントを生成できます。  
  
|イベント|ID|エラー条件|  
|-----------|--------|---------------------|  
|ErrorSendingMessage|8450|リモート パーティにメッセージを送信できませんでした。 最も一般的な理由は、ネットワーク障害またはタイムアウトです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]サイズの大きいメッセージをシリアル化中に、送信パイプラインが失敗した場合、このエラーを報告することがあります。|  
|ErrorReceivingAck|8451|ネットワーク障害またはタイムアウトのため、受信確認を受信しませんでした。|  
|ErrorConnecting|8453|リモート パーティへの TCP 接続を確立できませんでした: ホスト名を解決できませんでした、またはリモート パーティがポートでリッスンしていないか、接続を拒否します。|  
  
> [!NOTE]
>  送信先パーティ (元のメッセージの MSH5) での構成を決定するかどうか[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 または静的な確認が必要です 不一致が発生した場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を無効として扱われます。  
  
 MLLP アダプター プロセス ACK、送信後に ACK が独自のメッセージとして受信場所に配信されます。 逆アセンブラーは、ACK では、受信パイプラインによって報告されるエラーを解析中に発生する可能性がありますや中断される ACK の完全解析を実行します。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP の受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)