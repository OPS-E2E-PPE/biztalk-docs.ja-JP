---
title: MLLP 受信アダプターの処理 |Microsoft Docs
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
ms.openlocfilehash: 37cf1deb1ce956c94ffd44cc416cdf6970c81341
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290406"
---
# <a name="mllp-receive-adapter-processing"></a>MLLP 受信アダプターの処理
最小下位レイヤー プロトコル (MLLP) では、両方の一方向と双方向の要求応答モード アダプターのサポートを受信します。 アダプターをリッスンし、接続を受け入れます。  
  
 MLLP 受信アダプターは双方向のモードで動作、アダプターしないメッセージが表示されます、新しい接続から、パイプラインの前のメッセージの受信確認 (ACK) が生成されるまで。  
  
## <a name="configuration-parameters"></a>構成パラメーター  
 受信ハンドラーのパラメーターは、BizTalk ホスト レベルで構成されているし、関連付けられているすべての MLLP 受信場所に適用されます。  
  
|パラメーター|新しく使用する機能|  
|---------------|---------|  
|*最大接続数の上限をそのまま使用します。*|受信アダプターが受け入れる同時実行の開いている接続の数を制限します。|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>双方向の MLLP の受信確認の受信アダプター  
 アダプターが Microsoft BizTalk Accelerator 用 HL7 メッセージを受信する双方向の MLLP の受信時に ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 次の種類の確認を生成できます。  
  
- HL7 強化されたコミットの確認:このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同じ接続上でコミットの確認を送信します。 これは、別の送信ポートでアプリケーションを受け入れる ACK を送信します。  
  
- アプリケーションには、ACK がそのまま使用します。このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同じ接続上でアプリケーションに同意の確認を送信します。  
  
- 静的な確認:このシナリオで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ACK を同じ接続で送信します。  
  
- 生成された確認の種類によって異なります、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージを送信するパーティのエクスプ ローラーの構成設定。 MSH 15 のフィールドと個々 のメッセージの 16 の値は、この設定を上書きできます。 ただし、静的 Ack を想定するアプリケーションでは、構成できるでのみ設定[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="error-conditions"></a>エラー条件  
 次のイベントは、エラー状態または非アクティブ状態がある場合に発生します。  
  
- 受信場所が無効になっている場合または[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]シャット ダウンし、次のようにします。  
  
  - 受信場所は新しい接続を使用できなくなります。  
  
  - 既存の接続の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]完全に現在のメッセージを受信し、接続を閉じます。  
  
- 非アクティブ状態が検出された場合 (指定されたタイムアウト内で受信場所で受信したペイロード データ)、アダプターが接続を閉じます。  
  
- 場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不完全なメッセージを受信受信部分は中断されます。 外部 (EB/CR と SB、次のメッセージの間の新しい接続で最初の SB) の前にメッセージを受信したすべてのバイトは無視されます。  
  
- パイプラインは、メッセージの解析に失敗した場合、メッセージが、昇格させたプロパティを付けて MessageBox データベースにまだ配信**ParseError = true**します。  
  
- サブスクリプションがないのため、またはヘッダーの構造化エラーにより、メッセージが失敗した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](解析されていた) より前の元の「回線」形式でメッセージを中断します。 いいえ-サブスクリプションの失敗の理由を頻繁には、昇格させたプロパティがないことです。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]未解析のメッセージを保留、 **BTS します。MessageType**は空白になります。  
  
  次の表を、MLLP 受信アダプターを返します。 エラーを示します。  
  
|            イベント             |  ID  |                                                                                                          エラー条件                                                                                                           |
|------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **ErrorListening**      | 8448 |                                                   (多くの場合その他のローカル アプリケーションは同じ IP アドレスとポート ID の組み合わせを使用して) ローカル ソケットにバインドできませんでした。                                                    |
| **ErrorAcceptingConnection** | 8449 | リモート パーティとの TCP 接続を確立できませんでした。 いずれか[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]最大接続数制限に達するか、リソースが十分な。 |
|  **ErrorSubmittingMessage**  | 8452 |                   メッセージ ボックス データベースは、メッセージを受け入れませんでした。 いずれか[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]がないか、リソースが十分なできなかった。                   |
|     **ErrorSendingAck**      | 8454 |                                [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接続が使用できないため、受信確認を返しませんでした。                                 |
  
## <a name="performance-counters"></a>パフォーマンス カウンター  
 MLLP アダプターを使用するパフォーマンス カウンターを次の表に示します。  
  
|カウンター|説明|  
|-------------|-------------|  
|Bytes|受信または送信されたすべてのドキュメントのペイロードのサイズ。|  
|バイト数/秒|受信または送信されたペイロードの現在のスループット。|  
|処理されたドキュメント|**MLLP 受信**:<br /><br /> ドキュメントの数は、メッセージ ボックス データベースに正常に配信します。<br /><br /> **MLLP 送信**:<br /><br /> ドキュメントの数は、リモート アプリケーションに正常に配信します。|  
|失敗したドキュメント|**MLLP 受信**:<br /><br /> ドキュメントの数は、メッセージ ボックス データベースに正常に配信します。<br /><br /> **MLLP 送信**:<br /><br /> ドキュメントの数は、リモート アプリケーションに正常に配信します。|  
|[接続状態]|アダプターの接続の状態 1 または 0 (1 = 接続されている)。|  
  
 パフォーマンス カウンターのインスタンスは、次の名前付けスキームを使用します。  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 MLLP の受信場所は、アダプターは、「受信」プレフィックスを使用し、MLLP 送信アダプターは、「トランザクション」を使用します。  
  
> [!NOTE]
>  によって送信される Ack では、受信ポート (たとえば、双方向のモードで動作しているアダプター) と、送信ポートが (同じソケット接続の Ack を受信する操作) はカウントされません。  
  
## <a name="see-also"></a>参照  
 [MLLP でエンコードされたメッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [ACK を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)