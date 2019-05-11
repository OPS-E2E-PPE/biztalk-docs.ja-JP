---
title: カスタム ハンドラーに送信するための FRR 送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeddd040dd3cfb0c423eea149a81a1395a468087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378384"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a>カスタム ハンドラーに送信するための FRR 送信ポートの作成
FIN Response Reconciliation を実行する必要があります (元のメッセージまたは応答) メッセージを送信する各送信ポートの系列を作成するから[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]相関メッセージを処理するカスタム ハンドラーにします。  

 **まとめ**  

 次のプロパティとコンポーネントをそれぞれ 1 つが BTS の値によって識別して、一連の送信ポートを作成します。フィルターの操作:  


|        プロパティ/コンポーネント        |                                             設定                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            送信ポート             |                                       静的な一方向ポート                                        |
|          トランスポートの種類          |                                               FILE                                               |
| コピー先フォルダー (アドレス URI) |                         メッセージを送信するフォルダー                          |
|     ファイル名 (アドレス URI)      |                                         %MessageID%.txt                                          |
|          [送信パイプライン]           | Microsoft。BizTalk.DefaultPipelines します。 PassThruTransmit |
|             フィルター              |                                   次の表に示すように                                   |

 さまざまなメッセージの送信ポートは、BTS の値によって識別されます。操作は、送信ポートのフィルターです。  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a>カスタム ハンドラーに送信するための FRR 送信ポートを追加するには  

1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的 1 waySend ポート**します。  

2.  送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRCustomHandlersSendPort など、送信ポートの名前を入力します。  

3.  **型**、**ファイル**します。  

4.  をクリックして**構成**です。  

5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  

6.  フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。 **[OK]** をクリックします。  

    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。  

7.  **ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。  

    > [!NOTE]
    >  メッセージの種類ごとに別のフォルダーを作成することができます。  

8.  送信ポートのプロパティ ダイアログ ボックスの送信ハンドラーであることを確認**BizTalkServerApplication**が選択されています。  

9. **送信パイプライン**、 **PassThruTransmit**します。  

10. クリックして**フィルター**左側のウィンドウで、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**A4SWIFT_FrrService**します。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**BTS します。操作**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|BTS のいずれかを入力します。次の表からの値を操作します。|  

     BTS の.操作では、次の値のいずれかを入力します。  

    |メッセージ型|BTS します。操作の値|  
    |------------------|-------------------------|  
    |すべてのカテゴリ 0 ~ 9 SWIFT FIN メッセージの種類|**A4SWIFT_FrrSendMTMsg**|  
    |MQ Series パン/NAN (MQ Series トランス ポート レベル ACK/NAK)|**A4SWIFT_FrrSendTransport**|  
    |MT010 (警告の配信不能)|**A4SWIFT_FrrSend010NDW**|  
    |MT011 (配信通知)|**A4SWIFT_FrrSend011Delivered**|  
    |MT012 (送信者の通知)|**A4SWIFT_FrrSend012SenderACK**|  
    |MT015 (DNK、または遅延 NAK)|**A4SWIFT_FrrSend015DNK**|  
    |MT019 (通知を中止)|**A4SWIFT_FrrSend019Abort**|  
    |MTS21_FIN_ACKNAK (、LT (ACK) によって送信された FIN メッセージの受信確認|**A4SWIFT_FrrSendS21ACK**|  
    |MTS21_FIN_ACKNAK (否定、LT (NAK) によって送信された FIN メッセージの受信確認|**A4SWIFT_FrrSendS21NAK**|  

11. 次の操作が正常に送信されていないカテゴリ 0 ~ 9 の SWIFT FIN メッセージに対して、**フィルター**ウィンドウ。  

    > [!NOTE]
    >  **A4SWIFT_FRRFailedReason**で次のフィルターのプロパティをグループ化する必要があります。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**A4SWIFT_FrrService**します。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**True**します。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**BTS します。操作**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**A4SWIFT_FrrSendMTMsg**します。|  
    |**[グループ]**|**And**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型 *\<NAKErrorCode\>*、"Y01"など。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**TimedOut**します。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**TransportError**します。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**DelayedNAK**します。|  
    |**[グループ]**|**Or**|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**AbortMessage**します。|  

12. クリックして**適用**、順にクリックします**OK**します。  

13. 送信ポートを右クリックし、**開始**します。  

14. 手順 2. ~ 13 に必要なメッセージの種類ごとの送信ポートを作成する.