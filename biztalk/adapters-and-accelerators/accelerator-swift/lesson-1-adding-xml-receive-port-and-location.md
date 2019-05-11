---
title: レッスン 1:受信ポートと場所の XML の追加 |Microsoft Docs
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
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff076673967b6fcbd93cd18d7d6ec8c33688ae3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377283"
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a>レッスン 1:受信ポートと場所の XML を追加
受信ポートは、類似する受信場所の論理的なグループです。 受信場所は、受信メッセージとメッセージを処理するために使用するパイプラインの特定のアドレス (URL またはファイルの場所) などを定義します。  
  
### <a name="to-add-a-receive-port"></a>受信ポートを追加するには  
  
1. 開始**BizTalk Server 管理**コンソール。  
  
   > [!NOTE]
   >  BizTalk Server 管理コンソールで開くこともできますから Visual Studio 内でクリックして**BizTalk Server 管理**で、**ツール**メニュー。  
  
2. BizTalk Server 管理コンソールで、展開、 **BizTalk Server 管理**ノード、 **BizTalk グループ**ノード、**アプリケーション**ノード、し、**BizTalk アプリケーション 1**ノード。  
  
3. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
4. 受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_XML_ReceivePort**します。  
  
5. をクリックして**適用**をクリックして、ポートのバインド**ok をクリックします。**  
  
6. 右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
7. 受信ポートのダイアログ ボックスのをクリックして**MT103_XML_ReceivePort**、順にクリックします**OK**します。  
  
8. 受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_XML_ReceiveLocation**します。  
  
9. **トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。  
  
10. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  
  
11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。 移動、 **\<ドライブ\>: \Labs**フォルダー、およびクリック**フォルダの新規**します。  
  
12. フォルダーの参照 ダイアログ ボックスで、作成、**受信**フォルダー **\<ドライブ\>: \Labs**、し、作成、 **XMLFile** フォルダー**\<ドライブ\>: \Labs\Inbound**します。 **[OK]** をクリックします。  
  
13. FILE トランスポートのプロパティ ダイアログ ボックスで、ことを確認します **\*.xml**が入力されて、**ファイル マスク**ボックスをクリックして**OK**します。  
  
14. 受信場所のプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**の入力、**受信ハンドラー**ボックス。  
  
15. **受信パイプライン**ボックスで、 **XMLReceive**ドロップダウン リストから。  
  
16. クリックして**適用**、順にクリックします**OK**します。  
  
17. BizTalk Server 管理コンソールで、次のようにクリックします。**受信場所**、右クリック**MT103_XML_ReceiveLocation**、順にクリックします**を有効にする**します。  
  
    > [!NOTE]
    >  受信場所を有効にすると、BizTalk は、ファイル フォルダーを積極的にポーリングします。  
  
    続行する[レッスン 2。フラット ファイルの送信ポートを追加する](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md)します。