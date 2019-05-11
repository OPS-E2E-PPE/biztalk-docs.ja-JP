---
title: SWIFT からの受信用の受信場所の作成、FRR |Microsoft Docs
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
- FRR, creating receive locations
ms.assetid: e10857f4-21cb-4c09-8eed-cb6e9b0a0aa9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1912187c299e959c1a4f56c6650201efc5b37246
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378403"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-swift"></a>SWIFT からの受信用の受信場所の FRR を作成します。
FIN Response Reconciliation を実行するには、A4SWIFT に SWIFT ネットワークからメッセージを受信する受信場所を作成する必要があります。  
  
> [!NOTE]
>  お勧めを設定するには、2 つの受信 SAA からメッセージを受信するための場所: パン/Nan と 1 つの他のすべてのメッセージの受信を受信する 1 つ。 設定する 2 つの受信場所、SAA で 2 つの MQSeries キューからメッセージを受信する必要があります。 パン/Nan とその他のすべてのメッセージの種類のいずれかのいずれか。  
  
 **まとめ**  
  
 次のプロパティおよびコンポーネントで受信場所を作成します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|受信ポート|一方向のポート|  
|トランスポートの種類|MQSeries|  
|キュー定義 (MQSeries)|MQSeries server<br />キュー マネージャー<br />キュー|  
|[受信ハンドラー]|BizTalkServerApplication|  
|受信パイプライン。|A4SWIFT 受信 FRR 用に作成したパイプライン|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-swift"></a>SWIFT から、FRR 受信の受信場所を追加  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。  
  
2.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
3.  受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTReceivePort など、受信ポートの名前を入力します。  
  
4.  をクリックして**適用**をクリックして、ポートのバインド**OK**します。  
  
5.  管理コンソールで、右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
6.  受信ポートのダイアログ ボックスの 選択した受信ポートを作成し、 **OK**します。  
  
7.  受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRSWIFTReceiveLocation など、受信場所の名前を入力します。  
  
8.  **トランスポート**セクションの**型**テキスト ボックスで、 **MQSeries**します。  
  
9. をクリックして**構成**です。  
  
10. [MQSeries トランスポートのプロパティ] ダイアログ ボックスで、**キュー定義**、クリックして、省略記号 (**.**) ボタンをクリックします。  
  
11. **キュー定義**ダイアログ ボックスで、MQSeries サーバー、キュー マネージャー、入力し、キューします。 **[OK]** をクリックします。  
  
12. **MQSeries トランスポートのプロパティ** ダイアログ ボックスで、プロパティが必要なであることを確認します。 **[OK]** をクリックします。  
  
    > [!NOTE]
    >  MQSeries トランスポートのプロパティの詳細については、MQSeries のドキュメントを参照してください。  
  
13. 受信場所のプロパティ ダイアログ ボックスでの**受信ハンドラー**、 **BizTalkServerApplication**。  
  
14. **受信パイプライン** セクションで、選択、A4SWIFT 受信 FRR 用に作成したパイプライン。  
  
15. クリックして**適用**、 をクリックし、 **OK**  
  
16. BizTalk エクスプ ローラーで右クリックした受信場所を作成し、**を有効にする**します。