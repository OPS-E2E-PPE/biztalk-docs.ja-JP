---
title: "SWIFT に送信するための FRR 送信ポートの作成 |Microsoft ドキュメント"
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
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75cbda5d505f17f2dd7462cb0b16868a340f625c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>SWIFT に送信するための FRR 送信ポートを作成します。
FIN 対応調整を実行するのからメッセージを送信する送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT ネットワークにします。  
  
 **概要**  
  
 次のプロパティおよびコンポーネントで、送信ポートを作成します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|送信ポート|静的な一方向ポート|  
|トランスポートの種類|MQSeries|  
|キュー定義 (MQSeries)|MQSeries server キュー マネージャ キュー|  
|[送信パイプライン]|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプライン|  
|フィルター|次の表に示すように|  
  
### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>SWIFT に送信するためのカスタムの送信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的なポートを 1 つ waySend**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRSWIFTSendPort など、送信ポートの名前を入力します。  
  
3.  **型** **MQSeries**です。  
  
4.  をクリックして**構成**です。  
  
5.  [MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、省略記号ボタン () ボタンをクリックします。  
  
6.  キュー定義 ダイアログ ボックスで、MQSeries サーバー、キュー マネージャー、およびキューを入力します。 **[OK]**をクリックします。  
  
7.  MQSeries トランスポートのプロパティ ダイアログ ボックスで、プロパティが必要なことを確認します。 **[OK]**をクリックします。  
  
    > [!NOTE]
    >  MQSeries トランスポートのプロパティの詳細については、MQSeries のマニュアルを参照してください。  
  
8.  送信ポートのプロパティ ダイアログ ボックスの**送信ハンドラー**BizTalkServerApplication が選択されていることを確認します。  
  
9. **送信パイプライン**、select、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプラインです。  
  
10. をクリックして**フィルター**左側のウィンドウで、次の操作。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**False**です。|  
    |**[グループ]**|選択**と**です。|  
    |**プロパティ**|型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**True**です。|  
  
11. をクリックして**適用**、順にクリック**OK**です。  
  
12. 送信ポートを右クリックし、をクリックして**開始**です。