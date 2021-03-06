---
title: インターチェンジの状態と確認の詳細ステータス レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167162a47516279c22bd250589246b3dbd12f109
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381930"
---
# <a name="interchange-status-and-ack-details-status-report"></a>インターチェンジの状態と確認の詳細ステータス レポート
この状態レポートには、インターチェンジとその関連するインターチェンジの (技術) 確認と機能確認の詳細が表示されます。 このレポートには、インターチェンジ/確認の状態レポート内のインターチェンジを右クリックして表示する**インターチェンジの状態と確認の詳細**します。  
  
 このレポートは、インターチェンジと関連する確認をそれぞれ別のビューを提供します。  
  
## <a name="interchange-status"></a>インターチェンジの状態  
 このビューは、次のフィールドの値を示すテーブルを提供します。  
  
- 送信者パーティ ID  
  
- 受信者パーティ ID  
  
- 制御 ID  
  
- 受信者パーティ名  
  
- 送信者パーティ名  
  
- Direction  
  
- インターチェンジの日時  
  
  > [!NOTE]
  >  受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。 日付が 75 未満である場合は、20YY として表示されます。  
  > 
  >  たとえば、ISA09 の値が 991113 でインターチェンジを受信する場合そのインターチェンジ日付は 11/13/1999 としてで、レポートに表示します。  
  
- グループ数  
  
- ポート ID  
  
- インターチェンジの状態  
  
- EDI エンコードの種類  
  
- トランザクション セット関連付け ID  
  
  BizTalk Server への応答で返される技術 (インターチェンジ) 確認が必要ですが (EDI のプロパティ ダイアログ ボックスの 確認の処理と検証の設定 ページ) のインターチェンジ受信者としてのパーティで技術確認を有効にする場合、送信インターチェンジの場合。 最初に、送信インターチェンジのインターチェンジ状態エントリを作成するときに確認が必要インターチェンジの状態 フィールドに入力します。 技術確認を受信し、元のインターチェンジに関連していることを示す受信確認を受信したインターチェンジの状態フィールド更新されます。  
  
## <a name="interchange-ack-status"></a>インターチェンジ確認の状態  
 このビューには、インターチェンジの (技術) 確認の状態の値が表示されます。  
  
-   確認のインターチェンジ制御 ID  
  
-   受信者パーティ  
  
-   送信者パーティ  
  
-   Direction  
  
-   確認のインターチェンジ日付  
  
-   確認のインターチェンジ時刻  
  
-   Ack の状態  
  
-   状態コード  
  
-   確認通知コード 1  
  
-   確認通知コード 2  
  
## <a name="functional-acks"></a>[機能確認]  
 このビューには、機能確認の状態の値が表示されます。  
  
-   グループ制御番号  
  
-   受信者パーティ  
  
-   送信者パーティ  
  
-   Direction  
  
-   状態  
  
-   状態コード  
  
-   機能 ID コード  
  
-   トランザクション セットの数  
  
-   確認のインターチェンジ制御 ID  
  
-   確認のインターチェンジ日付  
  
-   確認のインターチェンジ時刻  
  
-   配信されたトランザクション セットの数  
  
-   受理されたトランザクション セット数  
  
-   エラー コード 1  
  
-   エラー コード 2  
  
-   エラー コード 3  
  
-   エラー コード 4  
  
-   エラー コード 5  
  
-   受信時刻