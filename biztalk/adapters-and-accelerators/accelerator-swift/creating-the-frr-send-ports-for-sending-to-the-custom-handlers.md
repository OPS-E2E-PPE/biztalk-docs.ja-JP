---
title: "カスタム ハンドラーに送信するための FRR 送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6326ae6e82e819d3cdf76ecc4d81e2a377ea65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>カスタム ハンドラーに送信するための FRR 送信ポートの作成
FIN 対応調整を実行する必要があります (元のメッセージまたは応答) メッセージを送信するの各送信ポートの系列を作成するから[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]相関関係を持つメッセージを処理するカスタム ハンドラーにします。  
  
 **概要**  
  
 次のプロパティとコンポーネント、BTS の値で識別される 1 つずつ一連の送信ポートを作成します。フィルターの操作:  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|送信ポート|静的な一方向ポート|  
|トランスポートの種類|FILE|  
|コピー先フォルダー (アドレス URI)|メッセージを送信する先のフォルダー|  
|ファイル名 (アドレス URI)|%MessageID%.txt|  
|[送信パイプライン]|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].BizTalk.DefaultPipelines です。 PassThruTransmit|  
|フィルター|次の表に示すように|  
  
 さまざまなメッセージの送信ポートは、BTS の値で識別されます。操作は、送信ポートのフィルターです。  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>カスタム ハンドラーに送信するための FRR 送信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的なポートを 1 つ waySend**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRCustomHandlersSendPort など、送信ポートの名前を入力します。  
  
3.  **型****ファイル**です。  
  
4.  をクリックして**構成**です。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
6.  フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。 **[OK]**をクリックします。  
  
    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。  
  
7.  **ファイル名**ボックスに、入力**%MessageID%.txt**、順にクリック**OK**です。  
  
    > [!NOTE]
    >  メッセージの種類ごとに別のフォルダーを作成することができます。  
  
8.  送信ポートのプロパティ ダイアログ ボックスの送信ハンドラーであることを確認**BizTalkServerApplication**が選択されています。  
  
9. **送信パイプライン** **PassThruTransmit**です。  
  
10. をクリックして**フィルター**左側のウィンドウで、次の操作。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**A4SWIFT_FrrService**です。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**BTS です。操作**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|BTS のいずれかを入力します。次の表の値を操作します。|  
  
     BTS です。操作では、次の値のいずれかを入力します。  
  
    |メッセージ型|BTS です。操作の値|  
    |------------------|-------------------------|  
    |すべてのカテゴリ、0 ~ 9 SWIFT FIN メッセージ型|**A4SWIFT_FrrSendMTMsg**|  
    |MQ 系列パン/NAN (MQ Series トランスポート レベル ACK/NAK)|**A4SWIFT_FrrSendTransport**|  
    |MT010 (配信不能警告)|**A4SWIFT_FrrSend010NDW**|  
    |MT011 (配信通知)|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 (送信者 Notification)|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 (DNK、または遅延 NAK)|**A4SWIFT_FrrSend015DNK**|  
    |MT019 (通知を中止)|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK (LT (ACK) によって送信された FIN メッセージの受信確認|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK (否定、LT (NAK) によって送信された FIN メッセージの受信確認|**A4SWIFT_FrrSendS21NAK**|  
  
11. 次の操作を正常に送信されていない、カテゴリ、0 ~ 9 SWIFT FIN メッセージに対して、**フィルター**ウィンドウ。  
  
    > [!NOTE]
    >  **A4SWIFT_FRRFailedReason**次のフィルターのプロパティをグループ化する必要があります。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**A4SWIFT_FrrService**です。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**True**です。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**BTS です。操作**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**A4SWIFT_FrrSendMTMsg**です。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型 *\<NAKErrorCode\>*、"Y01"などです。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**TimedOut**です。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**TransportError**です。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**DelayedNAK**です。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**AbortMessage**です。|  
  
12. をクリックして**適用**、順にクリック**OK**です。  
  
13. 送信ポートを右クリックし、をクリックして**開始**です。  
  
14. 手順 2. ~ 13. を必要なメッセージの種類ごとの送信ポートを作成します。