---
title: "SWIFT から受信するための受信場所の作成、FRR |Microsoft ドキュメント"
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
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e43ac2ac0fab9b2a29a44784032f9d3369833ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a>SWIFT から受信するための受信場所の FRR を作成します。
FIN 対応調整を実行するには、A4SWIFT に SWIFT ネットワークからメッセージを受信する受信場所を作成する必要があります。  
  
> [!NOTE]
>  お勧め SAA からメッセージを受信するための場所が表示される 2 つを設定する: パン/nans 値や 1 つの他のすべてのメッセージを受信する受信します。 設定するには 2 つの受信場所、SAA で 2 つの MQSeries キューからメッセージを受信する必要があります: パン/nans 値やその他のすべてのメッセージ型のいずれかのいずれか。  
  
 **概要**  
  
 次のプロパティおよびコンポーネントで受信場所を作成します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|受信ポート|一方向のポート|  
|トランスポートの種類|MQSeries|  
|キュー定義 (MQSeries)|MQSeries server<br />キュー マネージャー<br />キュー|  
|[受信ハンドラー]|BizTalkServerApplication|  
|受信パイプライン。|A4SWIFT FRR 用に作成したパイプラインを受信します。|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a>SWIFT から、FRR 受信受信するための場所を追加  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。  
  
2.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
3.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRSWIFTReceivePort など、受信ポートの名前を入力します。  
  
4.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
5.  管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
6.  受信ポート ダイアログ ボックスの 選択した受信ポートを作成し、をクリックして**OK**です。  
  
7.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックス FRRSWIFTReceiveLocation など、受信場所の名前を入力します。  
  
8.  **トランスポート** セクションの**型**テキスト ボックスで、 **MQSeries**です。  
  
9. をクリックして**構成**です。  
  
10. [MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
11. **キュー定義**ダイアログ ボックスで、MQSeries サーバー、キュー マネージャーでは、入力をキューに登録します。 **[OK]**をクリックします。  
  
12. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、プロパティが必要なことを確認します。 **[OK]**をクリックします。  
  
    > [!NOTE]
    >  MQSeries トランスポートのプロパティの詳細については、MQSeries のマニュアルを参照してください。  
  
13. 受信場所のプロパティ] ダイアログ ボックスの**受信ハンドラー**[ **BizTalkServerApplication**です。  
  
14. **受信パイプライン** セクションで、選択、A4SWIFT 受信パイプライン FRR 用に作成します。  
  
15. をクリックして**適用**、クリックして**OK**  
  
16. BizTalk エクスプローラを右クリックした受信場所を作成し、をクリックして**を有効にする**です。