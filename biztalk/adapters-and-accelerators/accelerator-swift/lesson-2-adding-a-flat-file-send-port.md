---
title: "レッスン 2: フラット ファイル送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1370b4877c2e32055e2ee0a0aca1f922bd8668a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a>レッスン 2: フラット ファイル送信ポートの追加
このレッスンでは、送信ポートと送信場所を構成します。 メッセージを送信する方法を定義するのにには、送信ポートを使用します。 送信メッセージのファイル フォルダーの場所を作成します。  
  
### <a name="to-add-a-flat-file-send-port"></a>フラット ファイル送信ポートを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_FlatFile_SendPort**です。  
  
3.  **トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。  
  
4.  クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
5.  [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。  
  
6.  フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ >: \Labs**フォルダー、およびクリック**新しいフォルダーの作成**です。  
  
7.  作成、**送信**フォルダーに**\<ドライブ >: \Labs**、順にクリック**OK**です。  
  
8.  **ファイル名**ボックスに、入力**%MessageID%.txt**、順にクリック**OK**です。  
  
9. 送信ポートのプロパティ] ダイアログ ボックスのドロップダウン リストをクリックして、**送信パイプライン**ボックスし、[ **MT103SendPipeline**です。  
  
10. 左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|選択**BTS です。ReceivePortName**です。|  
    |**演算子**|選択 **==**です。|  
    |**値**|型**MT103_XML_ReceivePort**です。|  
  
11. をクリックして**適用**、クリックして**[ok] です。**  
  
12. **送信ポート** ウィンドウを右クリックして**MT103_FlatFile_SendPort**、クリックして**開始**です。  
  
 進みます[第 5 章: フラット ファイルを追加する受信場所および送信ポートの XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)です。