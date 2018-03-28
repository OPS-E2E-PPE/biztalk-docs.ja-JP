---
title: 受信場所の作成、A4SWIFT |Microsoft ドキュメント
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
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c77b7b28c65c4743998f7d4c54d9c7cd48437f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="creating-an-a4swift-receive-location"></a>受信場所の A4SWIFT の作成
作成する必要があります、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SWIFT ネットワークからのメッセージの受信を有効にする受信場所[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、次の図に示すようにします。 受信場所は、受信ファイル フォルダーからフラット ファイル メッセージを受信します。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")  
  
 **概要**  
  
 作成し、一方向の受信ポートにバインドする作成して次のプロパティおよびコンポーネントで受信場所を有効にします。  
  
|プロパティ/コンポーネント|設定|  
|--------------------------|-------------|  
|受信ポート|一方向のポート|  
|トランスポートの種類|FILE|  
|アドレスの URI|メッセージを受信するフォルダーの名前|  
|ファイル マスク|\*.*\<拡張子\>*ここで、 \<*拡張子*\>入力方向の拡張機能は、フラット ファイル メッセージ|  
|[受信ハンドラー]|BizTalkServerApplication|  
|受信パイプライン。|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信パイプラインを作成します。|  
  
### <a name="to-add-the-receive-port-and-location"></a>受信ポートと受信場所を追加するには  
  
1.  開始**BizTalk Server 管理コンソール**コンソールです。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。  
  
2.  管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**です。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスで、受信ポートの名前を入力します。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
6.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
7.  受信ポート ダイアログ ボックスの選択 で、作成した受信ポート をクリックし、をクリックして**OK**です。  
  
8.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスで、受信場所の名前を入力します。  
  
9. **トランスポート**] セクションの**型**テキスト ボックスがドロップダウン リストをクリックし、[**ファイル**です。  
  
10. クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。 メッセージを受信するフォルダーに移動します。 **[OK]**をクリックします。  
  
    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**新しいフォルダーの作成**コマンド。  
  
12. ファイル トランスポートのプロパティ ダイアログ ボックスで、**ファイル マスク**ボックスに、入力 **\*.\<*拡張子*\>**ここで、 \<*拡張子*\>入力方向の拡張機能は、などのフラットファイルメッセージ**.txt**です。 **[OK]**をクリックします。  
  
13. 受信場所のプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**として入力された、**受信ハンドラー**ボックス。  
  
14. **受信パイプライン**ボックスで、ドロップダウン リストから、カスタム受信パイプラインを選択します。  
  
15. をクリックして **適用**, 、 をクリックし、 **OK**します。  
  
16. BizTalk Server 管理コンソールで、をクリックして**受信場所**作成した受信場所を右クリックし、クリックして**を有効にする**です。  
  
    > [!NOTE]
    >  受信場所を有効にすると、BizTalk は積極的に自分のファイル フォルダーをポーリングします。