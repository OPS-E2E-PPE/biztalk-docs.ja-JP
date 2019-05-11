---
title: A4SWIFT 送信ポートを作成する |Microsoft Docs
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
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73a6b90f5b0fb6dcd3075c6ea1b0dc22e05934de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378503"
---
# <a name="creating-an-a4swift-send-port"></a>A4SWIFT 送信ポートを作成します。
有効にする送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]に次の図に示すように、SWIFT のネットワークにメッセージを送信します。 この送信ポートは、送信ファイル、フォルダーにフラット ファイル メッセージが送信されます。 この送信ポートは、Message Repair and New Submission の機能と連動する設計されています。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 **まとめ**  
  
 作成し、次のプロパティおよびコンポーネントで静的な一方向送信ポートを開始します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|送信ポート|静的な一方向ポート|  
|トランスポートの種類|FILE|  
|コピー先フォルダー (アドレス URI)|メッセージを送信するフォルダーの名前|  
|ファイル名 (URI アドレス)|%MessageID%.txt|  
|フィルター|次の表で説明されていると|  
  
### <a name="to-add-the-sent-port"></a>送信ポートを追加するには  
  
1.  右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  
  
2.  送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、送信ポートの名前を入力します。  
  
3.  **トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。  
  
4.  をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  
  
6.  フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。  
  
7.  **ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。  
  
8.  **送信ポートのプロパティ** ダイアログ ボックスで、ドロップダウン リストをクリックして、**送信パイプライン**ボックスし、カスタム送信パイプラインを選択します。  
  
9. 左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS します。操作**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**A4SWIFT_MRSRCompleted**します。|  
    |**[グループ]**|選択**またはします。**|  
    |**プロパティ**|選択**BTS します。操作**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**A4SWIFT_MRSRFailed**します。|  
    |**[グループ]**|選択**または**します。|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**します。|  
    |**[演算子]**|選択 **==** します。|  
    |**[値]**|型**True**します。|  
  
10. クリックして**適用**、順にクリックします**ok をクリックします。**  
  
11. **送信ポート**ウィンドウで、送信ポートを右クリックし、順にクリックします**開始**します。