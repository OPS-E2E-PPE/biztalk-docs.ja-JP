---
title: SWIFT に送信するための FRR 送信ポートを作成する |Microsoft Docs
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
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138fef11bd271979edb564b8639bffb6acc6e7a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378349"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>SWIFT に送信するための FRR 送信ポートを作成します。
FIN Response Reconciliation を実行するのからのメッセージを送信する送信ポートを作成する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT ネットワークにします。  

 **まとめ**  

 次のプロパティおよびコンポーネントで、送信ポートを作成します。  


|     プロパティ/コンポーネント      |                                                               設定                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          送信ポート          |                                                         静的な一方向ポート                                                          |
|       トランスポートの種類        |                                                               MQSeries                                                               |
| キュー定義 (MQSeries) |                                                 MQSeries server キュー マネージャー キュー                                                  |
|        [送信パイプライン]        | [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプライン |
|           フィルター           |                                                     次の表に示すように                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>SWIFT に送信するためのカスタムの送信ポートを追加するには  

1. BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的 1 waySend ポート**します。  

2. 送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTSendPort など、送信ポートの名前を入力します。  

3. **型**、 **MQSeries**します。  

4. をクリックして**構成**です。  

5. [MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、省略記号 () ボタンをクリックします。  

6. キュー定義 ダイアログ ボックスで、MQSeries サーバー、キュー マネージャー、およびキューを入力します。 **[OK]** をクリックします。  

7. MQSeries トランスポートのプロパティ ダイアログ ボックスでプロパティが必要なであることを確認します。 **[OK]** をクリックします。  

   > [!NOTE]
   >  MQSeries トランスポートのプロパティの詳細については、MQSeries のドキュメントを参照してください。  

8. 送信ポートのプロパティ ダイアログ ボックスでの**送信ハンドラー**、biztalkserverapplication が選択されていることを確認します。  

9. **送信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成した送信パイプラインです。  

10. クリックして**フィルター**左側のウィンドウで、次の操作を行います。  


    |   プロパティ   |                            目的                             |
    |--------------|-------------------------------------------------------------------|
    | **プロパティ** |  選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**します。  |
    | **[演算子]** |                          選択 **==** します。                           |
    |  **[値]**   |                          型**False**します。                          |
    |  **[グループ]**   |                          選択**と**します。                          |
    | **プロパティ** | 型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**します。 |
    | **[演算子]** |                          選択 **==** します。                           |
    |  **[値]**   |                          型**True**します。                           |


11. クリックして**適用**、順にクリックします**OK**します。  

12. 送信ポートを右クリックし、**開始**します。
