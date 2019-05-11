---
title: レッスン 2:フラット ファイル送信ポートの追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7a9be734f2b4f360dd006492a9c9298bd0658b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377490"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a>レッスン 2:フラット ファイル送信ポートの追加
このレッスンでは、送信ポートおよび送信場所を構成できます。 メッセージを送信する方法を定義するのにには、送信ポートを使用します。 送信されたメッセージのファイル フォルダーの場所を作成します。  

### <a name="to-add-a-flat-file-send-port"></a>フラット ファイル送信ポートを追加するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. 送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_SendPort**します。  

3. **トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。  

4. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  

5. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  

6. フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs**フォルダー、およびクリック**フォルダの新規**。  

7. 作成、**送信**フォルダー **\<ドライブ\>: \Labs**、順にクリックします**OK**します。  

8. **ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。  

9. 送信ポートのプロパティ ダイアログ ボックスで、クリックしてのドロップダウン リスト、**送信パイプライン**ボックスを選び**MT103SendPipeline**します。  

10. 左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。  


    |   プロパティ   |           目的            |
    |--------------|---------------------------------|
    | **プロパティ** | 選択**BTS します。ReceivePortName**します。 |
    | **[演算子]** |         選択 **==** します。          |
    |  **[値]**   | 型**MT103_XML_ReceivePort**します。 |


11. クリックして**適用**、順にクリックします**ok をクリックします。**  

12. **送信ポート**ウィンドウで、右クリックして**MT103_FlatFile_SendPort**、順にクリックします**開始**します。  

    続行する[第 5 章。受信場所と XML 送信ポートのフラット ファイルを追加](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)します。