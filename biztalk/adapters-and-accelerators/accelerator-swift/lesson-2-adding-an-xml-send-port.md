---
title: 'レッスン 2: XML の送信ポートの追加 |Microsoft Docs'
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
ms.openlocfilehash: 63d955b46ca007aea7ea74960e756520a82f43b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005331"
---
# <a name="lesson-2-adding-an-xml-send-port"></a>レッスン 2: XML の送信ポートの追加
送信メッセージを表示する方法を定義するのにには、送信ポートを使用します。 このレッスンでは、XML メッセージを送信する方法を定義する送信ポートを作成します。  

### <a name="to-add-an-xml-send-port"></a>XML の送信ポートを追加するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. 送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_XML_SendPort**します。  

3. **トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。  

4. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  

5. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  

6. フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs\Outbound**フォルダー、およびクリック**ok**します。  

7. ファイル トランスポートのプロパティ ダイアログ ボックスで、ことを確認します **%MessageID%.xml**が入力されて、**ファイル名**ボックスをクリックして**OK**。  

8. 送信ポートのプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**が選択されている、**送信ハンドラー**ボックスで、 **PassThruTransmit**が選択されている、**送信パイプライン**ボックス。  

9. 左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。  


   |   プロパティ   |              目的              |
   |--------------|--------------------------------------|
   | **プロパティ** |   選択**BTS します。ReceivePortName**します。    |
   | **[演算子]** |            選択 **==** します。            |
   |  **[値]**   | 型**MT103_FlatFile_ReceivePort**します。 |
   |  **[グループ]**   |           選択**と**します。            |


10. プロパティの次の行の内側をクリックして、次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**False**の有効なメッセージ。|  

    > [!NOTE]
    >  追加する、 **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="** フィルター式の句、送信ポートを送信できるようのみ正常に解析し、メッセージを検証します。 ネイティブを使用して受信パイプラインとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーによって、失敗した (誤った) メッセージが中断されないが、代わりに、メッセージ ボックスと昇格させたプロパティを使用して、失敗としてマークに発行します。 A4SWIFT は、失敗したメッセージをメッセージ ボックスに公開する前に収集されたエラーの XML 表現をアタッチします。  
    > を含めなくても、"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="フィルター式の句、送信ポートには、すべてのメッセージが送信されます。 成功または失敗します。 失敗したメッセージのサブスクリプションの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。  

11. クリックして**適用**、順にクリックします**OK**します。  

12. BizTalk Server 管理コンソールで**送信ポート**を右クリックして**MT103_XML_SendPort**、順にクリックします**開始**します。  

    進みます[モジュール 6: ビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)します。