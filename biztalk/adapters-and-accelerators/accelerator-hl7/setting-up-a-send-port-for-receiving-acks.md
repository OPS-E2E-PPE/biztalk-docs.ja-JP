---
title: Ack を受信するため、送信ポートの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: df0988a9edc2af81970237aad363315a778f821b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961608"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>Ack を受信するための送信ポートの設定
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 一方向の送信ポートで受信確認 (ACK) が表示されることができます。 同じ接続の Ack を受信するための新しい一方向の送信ポートを設定するときは、その送信を関連付ける必要があります、一方向のポートの受信ポート。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップを作成、一方向受信ポート (と呼ばれる**TwoWayAckReceivePort**) と受信場所 (と呼ばれる**TwoWayAckReceiveLocation**)。 受信場所、最小限の下位層プロトコル (MLLP) トランスポートの種類を使用して「127.0.0.1:65535」の URI を使用する、 **BTAHL72XReceivePipeline**です。 これらは、受信するために必要な設定とによって送信されたメッセージに対して受信 ACK の処理、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]双方向のモードで、アダプターを送信します。 これは、受信場所を削除またはの他の目的で使用しないでください。 データをこの受信場所に送信しないでください。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]既定のこの受信場所で有効にします。  
  
 **TwoWayAckReceiveLocation**、どの、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップ ウィザードを作成、使用して、 **BizTalkServerApplication**受信ハンドラーとして。 ただし、新しいホストを作成し、MLLP の受信ハンドラーとして使用する場合は、する必要があります、次の操作を新規作成する**TwoWayAckReceiveLocation**:  
  
1.  作成、一方向受信ポート。  
  
2.  一方向作成 MLLP の受信場所。  
  
3.  MLLP トランスポートのプロパティの適切な値を指定します。  
  
4.  適切な受信ハンドラーを指定します。  
  
5.  受信場所を有効化します。  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>同じソケットで ACK の受信を有効になっている送信ポートを作成するには  
  
1.  BizTalk 管理コンソールを開き、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalkアプリケーション 1**です。 右クリック**送信ポート**、新規作成 をポイントし、クリックして**静的な一方向送信ポート**です。  
  
2.  **名前**ボックスに、送信ポートの名前を入力します。  
  
3.  **トランスポート**] セクションの**型**[ **MLLP**です。  
  
4.  クリックして **構成**します。  
  
5.  MLLP トランスポートのプロパティ ダイアログ ボックスで、ホストと接続の名前を入力します (たとえば、 **localhost**)。  
  
6.  **送信請求-応答を有効に****はい**です。 ままにして**送信受信場所 (URI) を確認**空、クリックして**OK**です。  
  
    > [!NOTE]
    >  ままにした場合**受信場所の送信**空白、BTAHL7 URI の入力、デフォルト**TwoWayAckReceiveLocation**です。 その後のクリックを確認する **[ok]** の手順 6 でをクリックして**構成**もう一度です。 URI **TwoWayAckReceiveLocation**に入力されます (127.0.0.1:65535)**送信受信場所 (URI) を ACK**です。  
  
    > [!NOTE]
    >  受信確認をサブスクライブする送信ポートを作成する必要がありますか、ACK は、サブスクリプションが見つからなかったため、一時停止状態で表示されます。 送信ポートで受信確認をサブスクライブする場合は、たとえば、フィルターを使用して**BTS です。MessageType = = \< *MessageType* \>** と**BTS です。ReceivePortName = = \< *ReceivePort*\>** です。 メッセージの種類は、静的な確認の場合、 **StaticAck**です。  
  
7.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [受信確認エラーの条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)