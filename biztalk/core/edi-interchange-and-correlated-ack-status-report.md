---
title: EDI インターチェンジと関連する ACK の状態レポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7a1246da341cc984995b2222681cb8164919e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350622"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a>EDI インターチェンジし、関連する ACK の状態レポート
このレポートでは、それらのインターチェンジに関連した確認し、EDI で処理される EDI インターチェンジが送信および受信パイプラインをすべて表示されます。  
  
## <a name="fields-in-the-status-report"></a>状態レポート内のフィールド  
 EDI インターチェンジと関連する ACK の状態レポートは、それらを受信または送信したインターチェンジと関連付けられる受信確認の次の情報が表示されます。  
  
- 送信者パーティ  
  
  > [!NOTE]
  >  送信者パーティように決定されます。  
  > 
  > - インターチェンジのパーティ名には、パーティの EDI のプロパティで構成されている名前が一致すると、構成されている名前が表示されます。  
  >   -   インターチェンジのパーティ名が一致しない構成済みの EDI のプロパティのいずれかの既存のパーティのインターチェンジに指定されたパーティ名が表示されます。  
  
- 受信者パーティ  
  
  > [!NOTE]
  >  受信者パーティ名は、次のように決定されます。  
  > 
  > - インターチェンジのパーティ名には、パーティの EDI のプロパティで構成されている名前が一致すると、構成されている名前が表示されます。  
  >   -   インターチェンジのパーティ名が一致しない構成済みの EDI のプロパティのいずれかの既存のパーティのインターチェンジに指定されたパーティ名が表示されます。  
  
- 制御 ID  
  
- Direction  
  
- インターチェンジの日時  
  
- EDI エンコードの種類  
  
- インターチェンジの状態  
  
- グループ数  
  
- ポート ID  
  
- 送信者パーティ エイリアス  
  
- 受信者パーティ エイリアス  
  
- トランザクション セット関連付け ID  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状態レポートのクエリ式のフィールド  
 表示されるデータを指定するクエリ式のフィールドを変更することにより、EDI インターチェンジと関連する ACK の状態レポートをカスタマイズできます。 使用できるフィールドは以下のとおりです。  
  
|||||  
|-|-|-|-|  
|クエリ式のフィールド|有効な演算子|潜在的な値|既定で含まれますか。|  
|検索|[等しい]|インターチェンジ/確認の状態|指定あり (必須)|  
|状態|[等しい]<br /><br /> 等しくないです。|受理<br /><br /> 受理 (ただしエラーが発生)<br /><br /> 送信済み<br /><br /> All<br /><br /> 確認が必要<br /><br /> 確認は不要<br /><br /> 拒否されました。<br /><br /> (これらの値は、以下に定義されます)。|はい|  
|インターチェンジの日時|[以下]<br /><br /> [以上]|特定の日時<br /><br /> [今日]<br /><br /> 昨日|はい<br /><br /> 注:できますに含めることが 1 回以上のクエリ式です。|  
|[最大一致数]|[等しい]|整数 (既定値 50)|はい|  
|制御 ID|[等しい]|インターチェンジ制御 ID|いいえ|  
|Direction|[等しい]|すべて (既定)<br /><br /> Receive<br /><br /> Send|いいえ|  
|受信者パーティ|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名|いいえ|  
|送信者パーティ|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名|いいえ|  
  
## <a name="status-definitions"></a>ステータスの定義  
 EDI 状態レポートで使用される状態値は、次の定義を持ちます。  
  
- 使用できます。有効なインターチェンジ  
  
- エラーありで受理します。セグメントにエラーが検出されました  
  
- 送信。インターチェンジが正常に送信されました  
  
- すべての：その他の値のいずれかでメッセージを表示します。  
  
- 確認が必要  
  
  > [!NOTE]
  >  インターチェンジの状態と確認の詳細ステータス レポートの [インターチェンジの状態] フィールドに設定されます「確認が必要」は送信メッセージの場合、メッセージが送信されるときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]技術確認が必要です。 これは、場合に発生、 **TA1 が必要**プロパティで設定されて**受信確認**一方向アグリーメント タブのページ。技術確認を受信し、検証、状態を「受理」に変更されます。 これのみ、技術確認、機能確認ではないために起こることに注意してください。  
  
- 確認は不要  
  
- 拒否。インターチェンジはエラーのため無効です。  
  
## <a name="additional-reports-displayed-from-this-report"></a>このレポートで表示されるその他のレポート  
 トランザクション セットのトランザクション セットの詳細レポートに表示されるは、次の追加のステータス レポートを表示できます。 インターチェンジまたは確認が EDI インターチェンジと関連する ACK の状態レポートに記載を右クリックし、適切なコマンドをクリックしてレポートにアクセスします。  
  
-   [インターチェンジの状態と確認の詳細の状態レポート](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [トランザクション セットの詳細の状態レポート](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a>次のステップ
  
-   [インターチェンジの状態と確認の詳細の状態レポート](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [トランザクション セットの詳細の状態レポート](../core/transaction-set-details-status-report.md)  
  
-   [EDI メッセージ コンテンツの状態レポート](../core/edi-message-content-status-report.md)  
  
