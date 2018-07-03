---
title: Ack を受信するための送信ポートの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f70be6d66d0ba8aa3385760bfc17b4b19f50351a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984747"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>Ack を受信するための送信ポートの設定
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 一方向の送信ポートで受信確認 (ACK) を受信することができます。 同じ接続の Ack を受信するための新しい一方向の送信ポートを設定するときは、その送信を関連付ける必要があります、一方向のポートの受信ポート。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] セットアップを作成、一方向受信ポート (と呼ばれる**TwoWayAckReceivePort**) と受信場所 (と呼ばれる**TwoWayAckReceiveLocation**)。 受信場所、最小限の下位レイヤー プロトコル (MLLP) トランスポートの種類を使用して「127.0.0.1:65535」の URI を使用する、 **BTAHL72XReceivePipeline**します。 これらは、受信するために必要な設定とによって送信されたメッセージに対して受信した ACK を処理、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]双方向のモードでアダプターを送信します。 これは、受信場所を削除またはその他の目的では使用しないでください。 このデータの受信場所を送信しないでください。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 既定のこの受信場所で有効にします。  
  
 **TwoWayAckReceiveLocation**を[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップ ウィザードを作成、使用して、 **BizTalkServerApplication**受信ハンドラーとして。 ただし、新しいホストを作成した MLLP の受信ハンドラーとして使用する場合、行う必要がありますを新規作成するには、次**TwoWayAckReceiveLocation**:  
  
1.  作成、一方向受信ポート。  
  
2.  作成、一方向受信場所の MLLP します。  
  
3.  MLLP トランスポートのプロパティの適切な値を指定します。  
  
4.  適切な受信ハンドラーを指定します。  
  
5.  受信場所を有効化します。  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>同じソケットで ACK の受信を有効になっている送信ポートを作成するには  
  
1.  BizTalk 管理コンソールを開き、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalkアプリケーション 1**します。 右クリックして**送信ポート**に新規作成 をポイントしてクリックして**静的な一方向送信ポート**します。  
  
2.  **名前**ボックスに、送信ポートの名前を入力します。  
  
3.  **トランスポート**セクションの**型**を選択します**MLLP**します。  
  
4.  クリックして**構成**します。  
  
5.  MLLP トランスポートのプロパティ ダイアログ ボックスで、ホストと接続の名前を入力します (たとえば、 **localhost**)。  
  
6.  **送信請求-応答が有効になって**を選択します**はい**します。 ままに**送信受信場所 (URI) を確認**空をクリックして**OK**します。  
  
    > [!NOTE]
    >  ままにした場合**受信場所の送信**空白、BTAHL7 入力 URI、既定の**TwoWayAckReceiveLocation**します。 その後のクリックを確認する **[ok]** の手順 6 でをクリックして**構成**もう一度です。 URI **TwoWayAckReceiveLocation** (127.0.0.1:65535) を入力するは**送信受信場所 (URI) を確認**します。  
  
    > [!NOTE]
    >  受信確認をサブスクライブする送信ポートを作成する必要があります。 または ACK は、サブスクリプションが見つからなかったため、中断された状態で表示されます。 をサブスクライブする送信ポートで受信した ACK 場合は、たとえば、フィルター、を使用して**BTS します。MessageType = = \< *MessageType* \>** と**BTS します。ReceivePortName = = \< *ReceivePort*\>** します。 静的の Ack メッセージの種類は**StaticAck**します。  
  
7.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [メッセージの受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [受信確認エラーの条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)