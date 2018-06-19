---
title: MLLP の受信アダプターの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, receive adapters
- MLLP adapters, send adapters
- receive adapters
ms.assetid: 03c9a5f6-6f23-454f-8bab-e7c7b6057efa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28713e22c37c12ef6f2cb9f8df8d228759d00c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207450"
---
# <a name="mllp-receive-adapter-processing"></a>MLLP の受信アダプターの処理
最小下位層プロトコル (MLLP) は、両方の一方向と双方向の要求応答モード アダプターのサポートを受信します。 アダプターはリッスンし、接続を受け入れます。  
  
 MLLP の受信アダプターは双方向のモードで動作し、アダプター メッセージは表示されません、新しい接続からパイプラインには、前のメッセージの受信確認 (ACK) が生成されるまで。  
  
## <a name="configuration-parameters"></a>構成パラメータ  
 受信ハンドラーのパラメーターは、BizTalk ホスト レベルで構成され、関連付けられているすべての MLLP の受信場所に適用。  
  
|パラメーター|新しく使用する機能|  
|---------------|---------|  
|*最大接続数の制限をそのまま使用します。*|受信アダプターはそのまま使用する同時実行の開いている接続の数を制限します。|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>双方向の MLLP の受信確認の受信アダプター  
 アダプターがメッセージを受信する双方向の MLLP の受信時に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 次の種類の Ack を生成できます。  
  
-   HL7 エンハンス コミット ACK: このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同じ接続でコミット確認を送信します。 これは、別の送信ポートでアプリケーションを受け入れる ACK を送信します。  
  
-   アプリケーションの同意 ACK: このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]アプリケーションに同意 ACK を同じ接続で送信します。  
  
-   静的 ACK: このシナリオでは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を同じ接続で送信します。  
  
-   生成された確認の種類によって異なります、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージを送信するパーティの エクスプ ローラーの構成設定。 MSH 15 のフィールドと個々 のメッセージの 16 の値は、この設定を上書きできます。 ただし、静的 Ack を指定して、アプリケーション構成のみを設定できるを通じて[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="error-conditions"></a>エラー条件  
 次のイベントは、エラー状態または非アクティブ状態がある場合に発生します。  
  
-   受信場所が無効になっている場合または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がシャット ダウンは、次のようにします。  
  
    -   受信場所は、新しい接続を使用できなくなります。  
  
    -   既存の接続の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]完全に現在のメッセージを受信し、接続を閉じます。  
  
-   非アクティブ状態が検出された場合 (ペイロード データは指定されたタイムアウト内で受信場所で受信した)、アダプターが接続を閉じます。  
  
-   場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不完全なメッセージを受信受信部分は中断します。 (EB/CR と、次のメッセージ SB 間での新しい接続で最初の SB) の前に、メッセージの外部で受信したすべてのバイトは無視されます。  
  
-   パイプラインは、メッセージの解析に失敗すると場合、メッセージは、昇格させたプロパティを使用して、MessageBox データベースには配信も**ParseError = true**です。  
  
-   または、ヘッダー内の構造のエラーにより、サブスクリプションがないのため、メッセージが失敗した場合は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](解析) より前の元の「回線」形式でメッセージを中断します。 頻繁に失敗の理由、いいえ-サブスクリプションは、昇格させたプロパティがないことです。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]未解析のメッセージを中断、 **BTS です。MessageType**は空白になります。  
  
 次の表では、MLLP アダプターを返しますが表示されること、エラーが一覧表示します。  
  
|イベント|ID|エラー条件|  
|-----------|--------|---------------------|  
|**ErrorListening**|8448|(おそらく他のローカル アプリケーションが同じ IP アドレスとポート ID の組み合わせを使用して) ローカル ソケットにバインドできませんでした。|  
|**ErrorAcceptingConnection**|8449|リモート パーティとの TCP 接続を確立できませんでした。 いずれか[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]最大接続制限に達したか、リソースが十分ななかった。|  
|**ErrorSubmittingMessage**|8452|メッセージ ボックス データベースは、メッセージを受け入れませんでした。 いずれか[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]を利用できなかったか、リソースが十分ななかった。|  
|**ErrorSendingAck**|8454|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接続が利用できなかったために、受信確認を返信できませんでした。|  
  
## <a name="performance-counters"></a>パフォーマンス カウンター  
 次の表は、MLLP アダプターを使用するパフォーマンス カウンターを一覧表示します。  
  
|カウンター|意味|  
|-------------|-------------|  
|バイト|受信または送信されたすべてのドキュメントのペイロードのサイズ。|  
|バイト数/秒|受信または送信されたペイロードの現在のスループット。|  
|Documents processed|**MLLP の受信**:<br /><br /> ドキュメントの数は、メッセージ ボックス データベースに正常に配信します。<br /><br /> **MLLP 送信**:<br /><br /> ドキュメントの数は、リモート アプリケーションを正常に配信します。|  
|失敗したドキュメント|**MLLP の受信**:<br /><br /> メッセージ ボックス データベースに正常に配信されたドキュメント数。<br /><br /> **MLLP 送信**:<br /><br /> リモート アプリケーションを正常に配信されたドキュメント数。|  
|[接続状態]|アダプターの接続の状態 1 または 0 (1 = 接続)。|  
  
 パフォーマンス カウンターのインスタンスは、次の名前付けスキームを使用します。  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 MLLP の受信場所は、アダプターが、「受信」というプレフィックスを使用し、MLLP 送信アダプターが「トランザクション」を使用します。  
  
> [!NOTE]
>  によって送信される Ack では、受信ポート (たとえば、双方向のモードで動作しているアダプター) と、送信ポート (同じソケット接続の Ack を受信する動作) はカウントされません。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)