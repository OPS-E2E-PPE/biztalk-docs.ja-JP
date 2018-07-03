---
title: FRR オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad5d9dd1b582aefa9a440508650ecd0e653dbfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998378"
---
# <a name="frr-orchestration"></a>FRR オーケストレーション
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR オーケストレーションを通じて FRR を実装します。 オーケストレーションは、FIN 応答の相関トークン一致、元のメッセージのメッセージ ID かどうかを判断します。 SAA にメッセージを送信する送信ポートで実行される送信機能と SAA からメッセージを受信する受信場所で実行される受信機能は、並列にメッセージを処理します。  
  
 最上位のレベルでは、オーケストレーションのインスタンスは、以下の処理を行います。  
  
1. SAA の元の送信メッセージのコピーをバインド、メッセージ ボックスをリッスンしてキャッシュします。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] オーケストレーションのインスタンスを作成時に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ ボックスに、元のメッセージをルーティングします。  
  
2. 待機[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SAA からメッセージ ボックス データベースへの FIN 応答を発行します。  
  
3. セットは、FIN 応答の性質によって、元のメッセージのコピーのプロパティを昇格します。  
  
4. 元のメッセージのコピーをメッセージ ボックス データベースに発行します。 カスタム ハンドラーはサブスクライブ、取得、必要に応じてメッセージを処理します。  
  
## <a name="subscription-to-outbound-messages"></a>送信メッセージへのサブスクリプション  
 FRR オーケストレーションは直接メッセージ ボックスにバインドされます。 FRR オーケストレーションは、次のプロパティをサブスクライブすることによって検証エラーを含まないすべての送信メッセージの SWIFT ネットワーク バインドをサブスクライブします。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed (SWIFT 逆アセンブラーの検証プロセスで設定) として false を = =  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Swiftbound true を = = (プロセスによって設定された、SWIFT 逆アセンブラーの構成)  
  
## <a name="messageresponse-correlation"></a>メッセージと応答の相関関係  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 次のプロパティを比較することによって元の送信 FIN メッセージを受信 FIN 応答メッセージを関連付けます。  
  
- FIN 応答の MQMD_CorrelID コンテキスト プロパティ  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MTXYY の送信メッセージの _FRRCorrelationToken プロパティ。 このプロパティは、受信パイプラインのパーティの解決ステージによって昇格されます。  
  
  これらのプロパティの値を同一にする必要があります。 SWIFT の値に、送信メッセージの MQMD_MsgID プロパティを設定するメッセージの送信パイプラインのエンコーダーの段階にバインドされた、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken プロパティ。 SAA は、MQMD_MsgID の値を応答メッセージの MQMD_CorrelID プロパティを設定します。  
  
## <a name="setting-of-promoted-properties"></a>昇格させたプロパティの設定  
 FIN 応答の受信と、コピー元のメッセージを相関させる、FRR オーケストレーションは、応答の性質に応じて、元のメッセージのコピーの次の昇格させたプロパティを設定します。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]応答が NAK であった場合、応答が ACK または False の場合は True に _FRRFailed  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]応答が NAK であった場合、次の値のいずれかの _FRRFailedReason:  
  
  -   *\<ErrorCode\>*  (405 MTS21_FIN_ACKNAK 負では受信確認メッセージのフィールド) から  
  
  -   (MQ Series パン/NAN メッセージ) から TransportError  
  
  -   DelayedNAK (から MT015 (DNK) メッセージの場合)  
  
  -   AbortReceived (、MT019 から (中止通知) メッセージ)  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]TimedOut に _FRRFailedReason 場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]タイムアウト期間内の応答を受信しませんでした。 FRR 遅延タイムアウトの詳細については、以下の"調整のタイムアウト セクションを参照してください。 または[FRR 遅延タイムアウト](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)します。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
- BTS します。応答メッセージの種類に対応する値を操作します。 詳細については、次を参照してください。[カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendTransport MQ Series パン/NAN メッセージ (MQ Series トランス ポート レベル ACK/NAK)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend010NDW MT010 メッセージ (警告の配信不能)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend011Delivered MT011 メッセージ (通知の配信)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend012SenderACK MT012 メッセージ (通知の送信側)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend015DNK MT015 メッセージ (DNK、または遅延 NAK)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend019Abort MT019 メッセージ (通知の中止)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21ACK MTS21_FIN_ACKNAK 受信確認メッセージ (FIN メッセージを送信して、LT ACK)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21NAK MTS21_FIN_ACKNAK 負では受信確認メッセージ (NAK FIN メッセージを送信して、LT)  
  
## <a name="direct-binding"></a>直接バインド  
 オーケストレーションがメッセージ ボックスには、オーケストレーションはサブスクリプションで定義されている入力を受け取ります。 コンテキスト プロパティと、オーケストレーションによって昇格された値は、オーケストレーションがメッセージ ボックスに公開されるメッセージの送信の出力を定義します。 メッセージ ボックスに直接このバインディングにより、オーケストレーションは、次の分離します。  
  
- 物理的な SAA へのルーティングのバック エンド アプリケーションからの送信メッセージの受信場所を受信します。  
  
- 送信する送信ポートからメッセージを FIN [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SWIFT Alliance アクセス (SAA) する  
  
- SAA から FIN 応答の受信メッセージを受信する受信場所  
  
- SAA によって FIN 応答を格納する場所、物理 MQSeries キュー  
  
## <a name="reconciliation-time-out"></a>調整のタイムアウト  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]FIN 応答を待機しているオーケストレーションの開始、FRR オーケストレーションの新しいインスタンスを作成します。 実行時に、無期限に応答を待機するがないことをいくつかの期間の後にタイムアウトにオーケストレーションを構成する必要があります。 FRR オーケストレーションが昇格タイムアウト期間を過ぎると、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason プロパティ TimedOut に設定します。 メッセージを MessageBox に公開し、終了します。 タイムアウトする場合は、関連付け ID はなくなっています。  
  
 タイムアウト メッセージ (元の送信メッセージのコピー) を処理するためのカスタム ハンドラーを作成することができます。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 待ち受け図形をオーケストレーションを使用してこれを実現なります。 詳細については、次を参照してください。 [FRR 遅延タイムアウト](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)します。