---
title: "インターチェンジの状態と確認の詳細の状態レポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc596a99d1a49b01ccc417abccb73d12ed34ad5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interchange-status-and-ack-details-status-report"></a>インターチェンジの状態と確認の詳細の状態レポート
この状態レポートには、インターチェンジの詳細と、関連するインターチェンジの (技術) 確認および機能確認が表示されます。 インターチェンジ/確認の状態レポート内のインターチェンジを右クリックし、このレポートを表示する**インターチェンジの状態と確認の詳細**です。  
  
 このレポートでは、インターチェンジと、関連する確認について、それぞれ別のビューが提供されます。  
  
## <a name="interchange-status"></a>インターチェンジの状態  
 このビューには、次のフィールドの値を示すテーブルが含まれています。  
  
-   送信者パーティ ID  
  
-   受信者パーティ ID  
  
-   制御 ID  
  
-   受信者パーティ名  
  
-   送信者パーティ名  
  
-   Direction  
  
-   インターチェンジの日時  
  
    > [!NOTE]
    >  受け取ったドキュメントで、インターチェンジに指定された日付が YYMMDD 形式であり、YY が 75 以上である場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では年を 19YY と表示します。 日付が 75 未満である場合は、20YY として表示されます。  
    >   
    >  たとえば、ISA09 の値が 991113 であるインターチェンジを受信した場合、インターチェンジの日付は 11/13/1999 としてレポートに表示されます。  
  
-   グループ数  
  
-   ポート ID  
  
-   インターチェンジの状態  
  
-   EDI エンコードの種類  
  
-   トランザクション セット関連付け ID  
  
 インターチェンジの受信者であるパーティに対して技術確認が有効になっている場合 ([EDI のプロパティ] ダイアログ ボックスの [確認の処理と検証の設定] ページ)、BizTalk Server は、送信したインターチェンジへの応答として技術 (インターチェンジ) 確認が返されることを要求します。 送信インターチェンジのインターチェンジ状態エントリを最初に作成するとき、[インターチェンジの状態] フィールドには [確認が必要] が設定されます。 技術確認を受信し、それを元のインターチェンジに関連付けると、[インターチェンジの状態] フィールドは確認を受信したことを示す内容に更新されます。  
  
## <a name="interchange-ack-status"></a>インターチェンジ確認の状態  
 このビューには、インターチェンジの (技術) 確認の状態の値が表示されます。  
  
-   確認のインターチェンジ制御 ID  
  
-   受信者パーティ  
  
-   送信者パーティ  
  
-   Direction  
  
-   確認のインターチェンジ日付  
  
-   確認のインターチェンジ時刻  
  
-   確認の状態  
  
-   状態コード  
  
-   確認通知コード 1  
  
-   確認通知コード 2  
  
## <a name="functional-acks"></a>[機能確認]  
 このビューには、機能確認の状態の値が表示されます。  
  
-   グループ制御番号  
  
-   受信者パーティ  
  
-   送信者パーティ  
  
-   Direction  
  
-   [状態]  
  
-   状態コード  
  
-   機能 ID コード  
  
-   トランザクション セット数  
  
-   確認のインターチェンジ制御 ID  
  
-   確認のインターチェンジ日付  
  
-   確認のインターチェンジ時刻  
  
-   配信されたトランザクション セットの数  
  
-   受理されたトランザクション セットの数  
  
-   ErrorCode 1  
  
-   ErrorCode 2  
  
-   ErrorCode 3  
  
-   ErrorCode 4  
  
-   エラー コード 5  
  
-   受信された時刻