---
title: 受信場所を作成、A4SWIFT |Microsoft Docs
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6754b53bc12e7231b35327017831d3591fbde6b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378484"
---
# <a name="creating-an-a4swift-receive-location"></a>受信場所を A4SWIFT の作成
作成する必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信場所で行う SWIFT ネットワークからのメッセージの受信を有効にする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、次の図に示すようにします。 受信場所は、受信ファイルのフォルダーからフラット ファイル メッセージを受信します。  

 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")  

 **まとめ**  

 作成し、一方向の受信ポートのバインドを作成し、次のプロパティおよびコンポーネントの受信場所を有効にします。  


| プロパティ/コンポーネント |                                                             設定                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
|    受信ポート     |                                                          一方向のポート                                                           |
|   トランスポートの種類    |                                                              FILE                                                               |
|     アドレスの URI     |                                     メッセージを受信するフォルダーの名前                                     |
|      ファイル マスク      |                  \*.*\<拡張子\>* ここで、 \<*拡張子*\>入力方向の拡張機能は、フラット ファイル メッセージ                   |
|   [受信ハンドラー]   |                                                    BizTalkServerApplication                                                     |
|  受信パイプライン。   | [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信パイプラインを作成します。 |

### <a name="to-add-the-receive-port-and-location"></a>場所と受信ポートを追加するには  

1.  開始**BizTalk Server 管理**コンソール。  

    > [!NOTE]
    >  BizTalk Server 管理コンソールで開くこともできますから Visual Studio 内でクリックして**BizTalk Server 管理**で、**ツール**メニュー。  

2.  管理コンソールで、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**します。  

3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

4.  受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、受信ポートの名前を入力します。  

5.  をクリックして**適用**をクリックして、ポートのバインド**OK**します。  

6.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  

7.  受信ポートのダイアログ ボックスの選択 で、作成した受信ポート をクリックし、順にクリックします**OK**します。  

8.  受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、受信場所の名前を入力します。  

9. **トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。  

10. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  

11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。 メッセージを受信するフォルダーに移動します。 **[OK]** をクリックします。  

    > [!NOTE]
    >  このフォルダーが存在しない場合を使用してそれを作成、**フォルダの新規**コマンド。  

12. ファイル トランスポートのプロパティ ダイアログ ボックスでの**ファイル マスク**ボックスに、入力 **\*.\<*拡張子*\>** ここで、 \<*拡張子*\>入力方向の拡張機能は、などのフラットファイルメッセージ **.txt**します。 **[OK]** をクリックします。  

13. 受信場所のプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**の入力、**受信ハンドラー**ボックス。  

14. **受信パイプライン**ボックスで、ドロップダウン リストから、カスタム受信パイプラインを選択します。  

15. クリックして**適用**、順にクリックします**OK**します。  

16. BizTalk Server 管理コンソールで、次のようにクリックします。**受信場所**作成した受信場所を右クリックし、クリック**を有効にする**します。  

    > [!NOTE]
    >  受信場所を有効にすると、BizTalk は、ファイル フォルダーを積極的にポーリングします。