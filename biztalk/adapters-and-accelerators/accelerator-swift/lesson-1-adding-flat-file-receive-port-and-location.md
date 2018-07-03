---
title: 'レッスン 1: は、受信ポートと場所を受信フラット ファイルの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23525715be1816684ffa680f99cf8f8bd88ceca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966267"
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a>レッスン 1: フラット ファイルの追加の受信ポートと場所
受信ポートは、受信ポートを追加する際に構成する必要があります、関連付けられている受信場所を常に持ちます。 受信場所では、特定のアドレスの受信メッセージとメッセージの処理に使用するパイプラインを定義します。  
  
### <a name="to-add-a-receive-port"></a>受信ポートを追加するには  
  
1. 右クリックし、BizTalk Server 管理コンソールで**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**。  
  
2. 受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_ReceivePort**します。  
  
3. をクリックして**適用**をクリックして、ポートのバインド**OK**します。  
  
4. 右クリックし、BizTalk Server 管理コンソールで**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**。  
  
5. 受信ポートのダイアログ ボックスのをクリックして**MT103_FlatFile_ReceivePort**、順にクリックします**OK**します。  
  
6. 受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_FlatFile_ReceiveLocation**します。  
  
7. **トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。  
  
8. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  
  
9. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。  
  
10. フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs\Inbound**フォルダー、およびクリック**フォルダの新規**。  
  
11. 作成、 **FlatFile**フォルダー **\<ドライブ\>: \Labs\Inbound**、順にクリックします**OK**。  
  
12. **ファイル マスク**ボックスに「  **\*.txt**順にクリックします**OK**します。  
  
13. 受信場所のプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**の入力、**受信ハンドラー**ボックス。  
  
14. **受信パイプライン**ボックスで、 **MT103ReceivePipeline**ドロップダウン リストから。  
  
15. クリックして**適用**、順にクリックします**OK**します。  
  
16. BizTalk Server 管理コンソールで、次のようにクリックします。**受信場所**、右クリック**MT103_FlatFile_ReceiveLocation**、順にクリックします**を有効にする**します。  
  
    続行する[レッスン 2: XML の送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)します。