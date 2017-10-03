---
title: "バックエンド アプリケーションから受信するための受信場所の作成、FRR |Microsoft ドキュメント"
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
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46895ff64e6585c8b80979c09874dffb510cf049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>バックエンド アプリケーションから受信するための受信場所の FRR を作成します。
FIN 対応調整を実行するバックエンド アプリケーションからメッセージを受信する受信場所を作成する必要があります。[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。  
  
 **概要**  
  
 次のプロパティおよびコンポーネントで受信場所を作成します。  
  
|プロパティ/コンポーネント|設定|  
|-------------------------|-------------|  
|受信ポート|一方向のポート|  
|トランスポートの種類|バックエンド アプリケーションで使用されるトランスポートの種類|  
|アドレスの URI|必要に応じて、トランスポートの種類|  
|[受信ハンドラー]|BizTalkServerApplication|  
|受信パイプライン。|[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]受信 FRR 用に作成したパイプライン|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>バックエンド アプリケーションから、FRR 受信受信するための場所を追加  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。  
  
2.  右クリック**パイプライン**、クリックして**更新**です。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  受信ポートのプロパティ ダイアログ ボックスで、**名前**ボックス FRRBackEndReceivePort など、受信ポートの名前を入力します。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
6.  管理コンソールで、右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
7.  受信ポート ダイアログ ボックスの 選択した受信ポートを作成し、をクリックして**OK**です。  
  
8.  受信場所のプロパティ ダイアログ ボックスで、**名前**ボックスで、受信場所の名前を入力します。  
  
9. **トランスポート** セクションの**型**テキスト ボックスで、バックエンド アプリケーションで使用されるトランスポートの種類を選択します。  
  
10. をクリックして**構成**です。  
  
11. ファイル トランスポートのプロパティ ダイアログ ボックスで、トランスポートの種類に必要なプロパティを入力し、をクリックして**OK**です。  
  
12. 受信場所のプロパティ] ダイアログ ボックスの**受信ハンドラー**[ **BizTalkServerApplication**です。  
  
13. 受信場所のプロパティ ダイアログ ボックスの**受信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインを受信します。  
  
14. をクリックして**適用**、順にクリック**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  
  
15. BizTalk エクスプローラを右クリックした受信場所を作成し、をクリックして**を有効にする**です。