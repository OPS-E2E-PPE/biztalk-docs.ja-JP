---
title: A4SWIFT 送信ポートの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210250"
---
# <a name="creating-an-a4swift-send-port"></a>A4SWIFT 送信ポートを作成します。
有効にする送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT ネットワークは、次の図に示すようにメッセージを送信します。 この送信ポートは、送信ファイル フォルダーにフラット ファイル メッセージが送信されます。 この送信ポートは、Message Repair and New Submission の機能を使用するよう設計されています。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 **概要**  
  
 作成し、次のプロパティとコンポーネントの静的な一方向送信ポートを起動します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|送信ポート|静的な一方向ポート|  
|トランスポートの種類|FILE|  
|コピー先フォルダー (アドレス URI)|メッセージを送信するフォルダーの名前|  
|ファイル名 (アドレス URI)|%MessageID%.txt|  
|フィルター|次の表の説明に従って|  
  
### <a name="to-add-the-sent-port"></a>送信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスで、送信ポートの名前を入力します。  
  
3.  **トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。  
  
4.  クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
6.  フォルダーの参照 ダイアログ ボックスからメッセージを送信するフォルダーに移動します。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。  
  
7.  **ファイル名**ボックスに、入力 **%MessageID%.txt**、順にクリック**OK**です。  
  
8.  **送信ポートのプロパティ** ダイアログ ボックスで、ドロップダウン リストをクリックして、**送信パイプライン**ボックス、およびカスタムの送信パイプラインを選択します。  
  
9. 左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。操作**です。|  
    |**演算子**|選択 **==** です。|  
    |**値**|型**A4SWIFT_MRSRCompleted**です。|  
    |**[グループ]**|選択**またはします。**|  
    |**プロパティ**|選択**BTS です。操作**です。|  
    |**演算子**|選択 **==** です。|  
    |**値**|型**A4SWIFT_MRSRFailed**です。|  
    |**[グループ]**|選択**または**です。|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**です。|  
    |**演算子**|選択 **==** です。|  
    |**値**|型**True**です。|  
  
10. をクリックして**適用**、クリックして **[ok] です。**  
  
11. **送信ポート** ウィンドウでは、送信ポートを右クリックし、をクリックして**開始**です。