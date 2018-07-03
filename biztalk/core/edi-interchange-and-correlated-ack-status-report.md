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
ms.openlocfilehash: 08a94eeb97b731f38d5785ab733d50d0edaa1a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982939"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a>EDI インターチェンジと関連する ACK の状態レポート
このレポートでは、EDI 送信パイプラインおよび受信パイプラインで処理されるすべての EDI インターチェンジ、およびそれらのインターチェンジに関連した確認を示します。  
  
## <a name="fields-in-the-status-report"></a>状態レポート内のフィールド  
 EDI インターチェンジと関連する ACK の状態レポートには、受信インターチェンジや送信インターチェンジ、および関連した確認に関する次の情報が表示されます。  
  
- 送信者パーティ  
  
  > [!NOTE]
  >  送信者パーティは、次のように決定する必要があります。  
  > 
  > - インターチェンジのパーティ名がパーティの EDI プロパティで構成された名前と一致する場合、構成済みの名前が表示されます。  
  >   -   インターチェンジのパーティ名が既存のパーティの EDI プロパティで構成された名前のいずれにも一致しない場合、インターチェンジで指定されたパーティ名が表示されます。  
  
- 受信者パーティ  
  
  > [!NOTE]
  >  受信者パーティ名は、次のように決定する必要があります。  
  > 
  > - インターチェンジのパーティ名がパーティの EDI プロパティで構成された名前と一致する場合、構成済みの名前が表示されます。  
  >   -   インターチェンジのパーティ名が既存のパーティの EDI プロパティで構成された名前のいずれにも一致しない場合、インターチェンジで指定されたパーティ名が表示されます。  
  
- 制御 ID  
  
- Direction  
  
- インターチェンジの日時  
  
- EDI エンコードの種類  
  
- インターチェンジの状態  
  
- グループ数  
  
- ポート ID  
  
- 送信者パーティ エイリアス  
  
- 受信者パーティ エイリアス  
  
- トランザクション セットの関連付け ID  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状態レポートのクエリ式のフィールド  
 表示されるデータを指定するクエリ式のフィールドを変更することにより、EDI インターチェンジと関連する ACK の状態レポートをカスタマイズできます。 使用できるフィールドは以下のとおりです。  
  
|||||  
|-|-|-|-|  
|クエリ式のフィールド|有効な演算子|潜在的な値|既定で含まれますか。|  
|検索|[等しい]|インターチェンジ/確認の状態|指定あり (必須)|  
|状態|[等しい]<br /><br /> 等しくないです。|受理<br /><br /> 受理 (ただしエラーが発生)<br /><br /> 送信済み<br /><br /> All<br /><br /> 確認が必要<br /><br /> 確認は不要<br /><br /> 拒否されました。<br /><br /> (それぞれの値とその定義を次に示します。)|はい|  
|インターチェンジの日時|[以下]<br /><br /> [以上]|特定の日時<br /><br /> [今日]<br /><br /> 昨日|はい<br /><br /> メモ: クエリ式に 1 回以上含めることができます。|  
|[最大一致数]|[等しい]|整数 (既定値 50)|はい|  
|制御 ID|[等しい]|インターチェンジ制御 ID|いいえ|  
|Direction|[等しい]|すべて (既定)<br /><br /> Receive<br /><br /> Send|いいえ|  
|受信者パーティ|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名|いいえ|  
|送信者パーティ|[等しい]|すべて (既定)<br /><br /> 特定のパーティ名|いいえ|  
  
## <a name="status-definitions"></a>状態の定義  
 EDI 状態レポートに使用される状態値には、次の定義があります。  
  
- 受理: 有効なインターチェンジ。  
  
- 受理 (ただしエラーが発生): セグメントにエラーが検出されました。  
  
- 送信済み: インターチェンジの送信に成功しました。  
  
- すべて: 他のいずれかの値を持つメッセージを表示します。  
  
- 確認が必要  
  
  > [!NOTE]
  >  [インターチェンジの状態と確認の詳細] の状態レポートの "インターチェンジの状態" フィールドは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が技術確認を要求する場合は、送信メッセージが送信されるときに、そのメッセージについて [確認が必要] に設定されます。 これは、場合に発生、 **TA1 が必要**プロパティで設定されて**受信確認**一方向アグリーメント タブのページ。状態は、技術確認が受信および検証されると、[受理] に変更されます。 この処理は、技術確認に対してだけ行われ、機能確認に対しては行われないことに注意してください。  
  
- 確認は不要  
  
- 拒否: インターチェンジはエラーのため無効でした。  
  
## <a name="additional-reports-displayed-from-this-report"></a>このレポートで表示されるその他のレポート  
 トランザクション セットの詳細レポートに表示されるトランザクション セットについて、次のその他の状態レポートを表示できます。 レポートにアクセスするには、[EDI インターチェンジと関連する ACK の状態] レポートに記載されたインターチェンジまたは確認を右クリックし、該当するコマンドをクリックします。  
  
-   [インターチェンジの状態と確認の詳細の状態レポート](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [トランザクション セットの詳細の状態レポート](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a>次のステップ
  
-   [インターチェンジの状態と確認の詳細の状態レポート](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [トランザクション セットの詳細の状態レポート](../core/transaction-set-details-status-report.md)  
  
-   [EDI メッセージ コンテンツの状態レポート](../core/edi-message-content-status-report.md)  
  
