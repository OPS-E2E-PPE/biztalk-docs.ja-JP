---
title: "レッスン 1: のフラット ファイルを追加する受信ポートと場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fcd41cd38074377fa179e3a414b278521c31f26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a>レッスン 1: フラット ファイルの追加の受信ポートと受信場所
受信ポートは、常に、受信ポートを追加するときに構成する必要がある、関連付けられている受信場所を持ちます。 受信場所では、受信メッセージとメッセージの処理に使用するパイプラインの特定のアドレスを定義します。  
  
### <a name="to-add-a-receive-port"></a>受信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
2.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_ReceivePort**です。  
  
3.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
4.  BizTalk Server 管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
5.  [受信ポート] ダイアログ ボックスのをクリックして**MT103_FlatFile_ReceivePort**、クリックして**OK**です。  
  
6.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_ReceiveLocation**です。  
  
7.  **トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。  
  
8.  クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
9. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
10. フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ >: \Labs\Inbound**フォルダー、およびクリック**新しいフォルダーの作成**です。  
  
11. 作成、 **FlatFile**フォルダー **\<ドライブ >: \Labs\Inbound**、順にクリック**[ok]**です。  
  
12. **ファイル マスク**ボックスに、入力 **\*.txt**、順にクリック**OK**です。  
  
13. 受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。  
  
14. **受信パイプライン**ボックスで、 **MT103ReceivePipeline**ドロップダウン リストからです。  
  
15. をクリックして**適用**、順にクリック**OK**です。  
  
16. BizTalk Server 管理コンソールで、をクリックして**受信場所**を右クリックして**MT103_FlatFile_ReceiveLocation**、クリックして**を有効にする**です。  
  
 進みます[レッスン 2: XML 送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)です。