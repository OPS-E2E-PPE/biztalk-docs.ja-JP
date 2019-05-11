---
title: EDI 状態レポート用に格納されているデータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 498af225f64d58cdff962b34f276814f55f4498e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389790"
---
# <a name="data-stored-for-edi-status-reports"></a>EDI 状態レポート用に格納されるデータ
レポートの 2 つのレベルが EDI 状態レポートで使用可能: 最初の場合、**レポートを有効にする**アグリーメント、および 2 番目の場合は、プロパティが選択されている、**ストア トランザクション セット/ペイロードを reporting**アグリーメントのプロパティが選択されます。 これらのプロパティは、**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a>EDI レポートが有効な場合に格納されているデータ  
 場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信または受信したインターチェンジ、技術確認、および機能確認のレコードが保持されます。  
  
 受信したインターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。  
  
- インターチェンジを受信したすべての記録します。 これは、最初に状態レポートの EDI の UI に表示される情報です。  
  
- インターチェンジに含まれているすべてのトランザクション セットのレコード。 これは、トランザクション セットの格納が有効な場合に格納されているすべての詳細には含まれません。  
  
- 受信したインターチェンジにあるすべての技術確認のレコード  
  
- 受信したインターチェンジにあるすべての機能確認のレコード  
  
  > [!NOTE]
  >  インターチェンジに複数の機能グループがある場合は、複数の機能確認は状態レポート UI に格納されます。 ただし場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、重複する機能確認を受け取る[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状態レポート UI に、最後の機能確認だけを格納します。  
  
- 技術確認を受信したインターチェンジに対して生成される必要があるかどうか  
  
- 機能確認を受信したトランザクション セットに対して生成される必要があるかどうか  
  
  送信インターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。  
  
- 送信インターチェンジのレコード  
  
- インターチェンジに含まれているすべてのトランザクション セットのレコード  
  
- 送信インターチェンジにあるすべての技術確認のレコード  
  
- 送信インターチェンジにあるすべての機能確認のレコード  
  
  EDI 状態レポート UI には、完全な情報を表示するこれらのレコードがによって関連付けられます。 たとえば場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信インターチェンジ、技術確認と状態レポート UI に、この情報を簡単に見つけることができます、元のメッセージの送信者に送信する機能確認が必要です。  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a>トランザクション セットの格納が有効になっている場合に格納されているデータ  
 場合、**メッセージ ペイロードを格納するレポートの**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は送信または受信したインターチェンジにあるすべてのトランザクション セットの詳細を格納します。 このレベルの状態レポートでは、すべての EDI レポートがアクティブの場合に実行される、レポートの最初のレベルとトランザクション セット固有の情報を実装します。 EDI 受信パイプラインとパイプライン作成のエントリを BAM データベースに受信および送信グループ/トランザクション セットごとの送信 (中に、"**ストア メッセージ ペイロード reporting**プロパティが選択されている)。 インターチェンジが拒否された場合、エントリは行われません。  
  
 送信または受信したインターチェンジの場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報を格納します。  
  
-   トランザクション セットのコンテンツ。 レポートの UI 状態で、インターチェンジに含まれるトランザクション セットを見てし、実際のトランザクション セットのコンテンツを表示できます。  
  
-   については、次を含む、トランザクション セットの詳細。  
  
|||  
|-|-|  
|[情報]|フィールドまたは値|  
|ApplicationSender|(GS02 または\<UNG2.1(UNG2.2)\>|  
|ApplicationReceiver|GS03 または\<UNG3.1(UNG3.2)\>|  
|GroupDate|GS04 または UNG2.4|  
|GroupTime|GS05 または UNG2.5|  
|TransactionSetId|ST01 または UNH2.1 (AN 文字列)|  
|InterchangeControlNo|ISA13|  
|GroupControlNo|GS06|  
|BtsDocType|NameSpace + ルート ノード名|  
|TransactionSetControlID|ST02 または UNH1|  
|TransactionSetStatus|Accepted、AcceptedWithError、または拒否|  
|Direction|送信または受信|  
|BtsProcessingTime|受信側。Btsreceivetime (ローカル時刻)、パイプラインで設定された時刻<br /><br /> 送信側。ASM コンポーネントによってエンベロープに設定 (ローカル時刻) BTSSendTime|  
|BTS.MessageId|受信側。メッセージ プロパティの BTSMessageId<br /><br /> 送信側。<br /><br /> トランザクションの 1 つの設定。BTSMessageId<br /><br /> 送信バッチの場合。バッチ (バッチ メッセージの BTSMessageId でなく) で各メッセージの TransactionSet BTSMessageId**に注意してください。** 記憶域のみ – はない UI に表示します。|  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [バッチの状態レポートの格納されているデータ](../core/data-stored-for-batching-status-reports.md)   
 [AS2 状態レポート用に格納されるデータ](../core/data-stored-for-as2-status-reports.md)