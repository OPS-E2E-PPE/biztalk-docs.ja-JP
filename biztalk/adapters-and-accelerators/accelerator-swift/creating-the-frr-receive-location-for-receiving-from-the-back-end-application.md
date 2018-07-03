---
title: バックエンド アプリケーションから受信するための受信場所の作成、FRR |Microsoft Docs
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
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ac72c9d122b626411e67cfc6e18f76de226415
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002859"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a>バックエンド アプリケーションから受信するための受信場所の FRR を作成します。
FIN Response Reconciliation を実行するバック エンド アプリケーションからメッセージを受信する受信場所を作成する必要があります。[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。  

 **概要**  

 次のプロパティおよびコンポーネントで受信場所を作成します。  


| プロパティ/コンポーネント |                                                                 設定                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    受信ポート    |                                                              一方向のポート                                                               |
|   トランスポートの種類   |                                           バックエンド アプリケーションで使用されるトランスポートの種類                                           |
|    アドレスの URI     |                                                   トランスポートの種類の必要に応じて                                                    |
|  [受信ハンドラー]   |                                                        BizTalkServerApplication                                                         |
|  受信パイプライン。  | [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインの受信 |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a>バックエンド アプリケーションから、FRR 受信場所の受信を追加  

1. BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**ノード。  

2. 右クリック**パイプライン**、 をクリックし、**更新**します。  

3. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

4. 受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに、FRRBackEndReceivePort など、受信ポートの名前を入力します。  

5. をクリックして**適用**をクリックして、ポートのバインド**OK**します。  

6. 管理コンソールで、右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  

7. 受信ポートのダイアログ ボックスの 選択した受信ポートを作成し、 **OK**します。  

8. 受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに、受信場所の名前を入力します。  

9. **トランスポート**セクションの**型**テキスト ボックスで、バックエンド アプリケーションで使用されるトランスポートの種類を選択します。  

10. クリックして**構成**します。  

11. クリックして、FILE トランスポートのプロパティ ダイアログ ボックスで、トランスポートの種類に必要なプロパティを入力**OK**します。  

12. 受信場所のプロパティ ダイアログ ボックスでの**受信ハンドラー**、 **BizTalkServerApplication**。  

13. 受信場所のプロパティ ダイアログ ボックスでの**受信パイプライン**を選択、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR 用に作成したパイプラインを受信します。  

14. をクリックして**適用**、順にクリックします**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。  

15. BizTalk エクスプ ローラーで右クリックした受信場所を作成し、**を有効にする**します。
