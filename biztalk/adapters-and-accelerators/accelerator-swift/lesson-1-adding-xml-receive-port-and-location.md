---
title: "レッスン 1: は、ポートと受信場所に表示される XML の追加 |Microsoft ドキュメント"
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
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01f9457404e135027f35f1402575efeec311e2e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a>レッスン 1: XML の受信ポートと受信場所を追加します。
受信ポートとは、類似する受信場所の論理的なグループです。 受信場所は、受信メッセージとメッセージを処理するために使用するパイプラインの特定のアドレス (URL またはファイルの場所) などを定義します。  
  
### <a name="to-add-a-receive-port"></a>受信ポートを追加するには  
  
1.  開始**BizTalk Server 管理コンソール**コンソールです。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。  
  
2.  BizTalk Server 管理コンソールで、展開、 **BizTalk Server 管理コンソール** ノード、 **BizTalk グループ** ノード、**アプリケーション**ノード、し、**BizTalk アプリケーション 1**ノード。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_ReceivePort**です。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**[ok] です。**  
  
6.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
7.  [受信ポート] ダイアログ ボックスのをクリックして**MT103_XML_ReceivePort**、クリックして**OK**です。  
  
8.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_ReceiveLocation**です。  
  
9. **トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。  
  
10. クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。 移動、 **\<ドライブ\>: \Labs**フォルダー、およびクリック**新しいフォルダーの作成**です。  
  
12. フォルダーの参照 ダイアログ ボックスで、作成、**受信**フォルダー **\<ドライブ\>: \Labs**、し、作成、 **XMLFile** 内のフォルダー**\<ドライブ\>: \Labs\Inbound**です。 **[OK]**をクリックします。  
  
13. FILE トランスポートのプロパティ ダイアログ ボックスでいることを確認 **\*.xml**で入力した、**ファイル マスク**ボックスし、をクリックして**OK**です。  
  
14. 受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。  
  
15. **受信パイプライン**ボックスで、 **XMLReceive**ドロップダウン リストからです。  
  
16. をクリックして**適用**、順にクリック**OK**です。  
  
17. BizTalk Server 管理コンソールで、をクリックして**受信場所**を右クリックして**MT103_XML_ReceiveLocation**、クリックして**を有効にする**です。  
  
    > [!NOTE]
    >  受信場所を有効にすると、BizTalk は積極的に自分のファイル フォルダーをポーリングします。  
  
 進みます[レッスン 2: フラット ファイル送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md)です。