---
title: 'レッスン 2: XML 送信ポートの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d8aac412bf81492793eec2f4936d84b54fda0d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960704"
---
# <a name="lesson-2-adding-an-xml-send-port"></a>レッスン 2: XML 送信ポートの追加
送信ポートを使用して、メッセージを送信する方法を定義します。 このレッスンでは、XML メッセージを送信する方法を定義する送信ポートを作成します。  
  
### <a name="to-add-an-xml-send-port"></a>XML 送信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_SendPort**です。  
  
3.  **トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。  
  
4.  クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
6.  フォルダーの参照 ダイアログ ボックスに移動、 **\<ドライブ\>: \Labs\Outbound**フォルダーをクリックして**OK**です。  
  
7.  FILE トランスポートのプロパティ ダイアログ ボックスでいることを確認 **%MessageID%.xml**で入力した、**ファイル名**ボックスし、をクリックして**OK**です。  
  
8.  送信ポートのプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**が選択されて、**送信ハンドラー**ボックスで、 **PassThruTransmit**が選択されて、**送信パイプライン**ボックス。  
  
9. 左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。ReceivePortName**です。|  
    |**演算子**|選択 **==** です。|  
    |**値**|型**MT103_FlatFile_ReceivePort**です。|  
    |**[グループ]**|選択**と**です。|  
  
10. プロパティの次の行の内側をクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**|  
    |**演算子**|選択 **==** です。|  
    |**値**|型**False**の有効なメッセージです。|  
  
    > [!NOTE]
    >  追加する、 **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="** フィルター式の句、送信ポートが送信するようにのみ正常に解析し、メッセージを検証します。 ネイティブを使用して、受信パイプラインとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーは、失敗した (エラー) メッセージは中断されませんが、代わりに、メッセージ ボックスと昇格させたプロパティを使用して、失敗としてマークに公開します。 A4SWIFT は、メッセージ ボックスに公開する前に、失敗したメッセージに収集されたエラーの XML 表現をアタッチします。  
    > 含めずに、"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"フィルター式の句、送信ポートには、すべてのメッセージが送信されます。 成功または失敗します。 失敗したメッセージのサブスクリプションの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。  
  
11. をクリックして**適用**、順にクリック**OK**です。  
  
12. BizTalk Server 管理コンソールで**送信ポート**を右クリックして**MT103_XML_SendPort**、クリックして**開始**です。  
  
 進みます[第 6 章: ビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)です。