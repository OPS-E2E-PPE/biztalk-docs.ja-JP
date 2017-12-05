---
title: "FRR オーケストレーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f56b16f59b967ccd9e57d03d38f86e64795da477
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="frr-orchestration"></a>FRR オーケストレーション
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR オーケストレーションで FRR を実装します。 オーケストレーションでは、FIN 応答の相関トークンと一致するどうか、元のメッセージのメッセージ ID を決定します。 SAA にメッセージを送信する送信ポートで実行される送信機能と SAA からメッセージを受信する受信場所で実行される受信機能は、並列でメッセージを処理します。  
  
 最上位のレベルでは、オーケストレーションのインスタンスは、以下の処理を行います。  
  
1.  元の送信メッセージのコピーはキャッシュ SAA のメッセージ ボックス データベースをリッスンしてバインドされます。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションのインスタンスを作成時に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスに、元のメッセージをルーティングします。  
  
2.  待機[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA からメッセージ ボックス データベースへの FIN 応答を発行します。  
  
3.  セットは、FIN 応答の性質によって、元のメッセージのコピーのプロパティを昇格します。  
  
4.  元のメッセージのコピーをメッセージ ボックス データベースに発行します。 カスタム ハンドラーを取得するサブスクライブし、必要に応じてメッセージを処理します。  
  
## <a name="subscription-to-outbound-messages"></a>送信メッセージへのサブスクリプション  
 FRR オーケストレーションはメッセージ ボックスに直接バインドします。 FRR オーケストレーションは、すべての送信メッセージに SWIFT ネットワークは、バインドされている次のプロパティをサブスクライブすることによって検証エラーを含まないをサブスクライブします。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed false を = = (されている SWIFT の逆アセンブラーの検証プロセスで)  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Swiftbound true を = = (プロセスによって設定された、SWIFT 逆アセンブラーの構成)  
  
## <a name="messageresponse-correlation"></a>メッセージと応答の相関関係  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次のプロパティを比較することによって元の送信 FIN メッセージを受信 FIN 応答メッセージを相互に関連付けます。  
  
-   FIN 応答の MQMD_CorrelID コンテキスト プロパティ  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MTXYY の送信メッセージの _FRRCorrelationToken プロパティです。 このプロパティは、受信パイプラインのパーティの解決ステージによって昇格されます。  
  
 これらのプロパティの値を同一にする必要があります。 メッセージの送信パイプラインのエンコーダーの段階に SWIFT の値を送信メッセージの MQMD_MsgID プロパティを設定するがバインドされている、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken プロパティです。 SAA は、MQMD_MsgID の値を応答メッセージの MQMD_CorrelID プロパティを設定します。  
  
## <a name="setting-of-promoted-properties"></a>昇格させたプロパティの設定  
 FIN 応答の受信と、元のメッセージのコピーへの関連付け、FRR オーケストレーションは応答の性質によって、元のメッセージのコピーの次の昇格させたプロパティを設定します。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]応答が NAK 場合の応答が ACK または False の場合は True に _FRRFailed  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]応答が NAK であった場合、次の値のいずれかの _FRRFailedReason:  
  
    -   *\<ErrorCode\>*  (MTS21_FIN_ACKNAK 負受信確認メッセージの 405 フィールド) から  
  
    -   (MQ 系列パン/NAN メッセージ) から TransportError  
  
    -   (MT015 (DNK) メッセージ) から DelayedNAK  
  
    -   AbortReceived (、MT019 から (中止通知) メッセージ)  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]TimedOut に _FRRFailedReason 場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]タイムアウト期間内の応答を受信しませんでした。 FRR 遅延タイムアウトの詳細については、後述の「「調整タイムアウト」を参照してください。 または[FRR 遅延タイムアウトの設定](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)です。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS です。応答メッセージの種類に対応する値を操作します。 詳細については、次を参照してください。 [FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MQ 系列パン/NAN メッセージ (MQ Series トランスポート レベル ACK/NAK) _FrrSendTransport  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend010NDW MT010 メッセージ (警告の配信不能)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend011Delivered MT011 メッセージ (配信通知)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend012SenderACK MT012 メッセージ (通知の送信側)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend015DNK MT015 メッセージ (DNK、または遅延 NAK)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend019Abort MT019 メッセージ (通知の中止)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21ACK MTS21_FIN_ACKNAK 受信確認メッセージ (、LT によって送信された FIN メッセージの ACK)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21NAK MTS21_FIN_ACKNAK 負受信確認メッセージ (NAK、LT によって送信された FIN メッセージの)  
  
## <a name="direct-binding"></a>直接バインド  
 オーケストレーションがメッセージ ボックスには、オーケストレーションはサブスクリプションによって定義されているは、入力を受け取ります。 コンテキスト プロパティと、オーケストレーションによって昇格された値は、オーケストレーションがメッセージ ボックスに公開されるメッセージの送信の出力を定義します。 メッセージ ボックスに直接このバインディングのため、オーケストレーションは、次の中から切り離されます。  
  
-   物理受信 SAA へのルーティング用のバックエンド アプリケーションから送信メッセージを受信する場所  
  
-   送信する送信ポートからのメッセージの FIN[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]に SWIFT Alliance アクセス (SAA)  
  
-   SAA から着信 FIN 応答メッセージを受信する受信場所  
  
-   SAA によって FIN 応答を格納する場所、物理 MQSeries キュー  
  
## <a name="reconciliation-time-out"></a>調整のタイムアウト  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]FRR オーケストレーション、FIN 応答を待機しているオーケストレーションの開始の新しいインスタンスを作成します。 実行時に、それが待機するようにいない応答を無期限にいくつかの期間の後にタイムアウトにオーケストレーションを構成する必要があります。 タイムアウト期間が経過すると、FRR オーケストレーションが昇格、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason プロパティし TimedOut に設定します。 メッセージ ボックスにメッセージを公開し、終了します。 タイムアウトする場合は、相関 ID が削除されます。  
  
 タイムアウトになったメッセージ (元の送信メッセージのコピー) を処理するためのカスタム ハンドラーを作成することができます。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]そのためのオーケストレーションの待ち受け図形を使用して、します。 詳細については、次を参照してください。 [FRR 遅延タイムアウトの設定](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)です。