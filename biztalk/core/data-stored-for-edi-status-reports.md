---
title: "EDI 状態レポートに格納されているデータ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9395cb3895675e586576088f3d257dbf4115948f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="data-stored-for-edi-status-reports"></a>EDI 状態レポート用に格納されるデータ
2 つのレベルのレポートを EDI 状態レポートで利用可能: 最初の場合、**レポートをオンに**アグリーメント、および 2 番目の場合は、プロパティが選択されている、**ストア トランザクション セット/ペイロードを reporting**アグリーメントのプロパティが選択されます。 これらのプロパティで使用可能な**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a>EDI レポートがアクティブになっている場合に格納されるデータ  
 場合、**レポートをオンに**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信または受信したインターチェンジ、技術確認、および機能確認のレコードが保持されます。  
  
 受信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。  
  
-   受信したすべてのインターチェンジのレコード。 EDI の状態レポートの UI に表示される最初の情報です。  
  
-   インターチェンジに含まれているすべてのトランザクション セットのレコード。 ここには、トランザクション セットの格納が有効になっている場合に格納される詳細は含まれません。  
  
-   受信したインターチェンジにあるすべての技術確認のレコード。  
  
-   受信したインターチェンジにあるすべての機能確認のレコード。  
  
    > [!NOTE]
    >  インターチェンジに複数の機能グループが存在する場合、状態レポートの UI には複数の機能確認が格納されます。 ただし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が 1 つのグループに対して重複する機能確認を受信した場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は状態レポートの UI に最後の機能確認だけを格納します。  
  
-   受信したインターチェンジに対して技術確認を生成する必要があるかどうか。  
  
-   受信したトランザクション セットに対して機能確認を生成する必要があるかどうか。  
  
 送信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。  
  
-   送信インターチェンジのレコード。  
  
-   インターチェンジに含まれるすべてのトランザクション セットのレコード。  
  
-   送信したインターチェンジにあるすべての技術確認のレコード。  
  
-   送信したインターチェンジにあるすべての機能確認のレコード。  
  
 EDI 状態レポートの UI は、これらのレコードを関連付けて完全な情報を表示します。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインターチェンジを受信し、元のメッセージの送信者に対して技術確認と機能確認を送信する必要がある場合、この情報を状態レポートの UI で簡単に見つけることができます。  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a>トランザクション セットの格納が有効になっている場合に格納されるデータ  
 場合、 **reporting 用メッセージ ペイロードを格納**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は送信または受信したインターチェンジに含まれるすべてのトランザクション セットの詳細を格納します。 このレベルの状態レポートには、EDI レポートがアクティブになっている場合に作成される第 1 レベル レポートのすべての情報に加えて、トランザクション セットに固有の情報が含まれます。 EDI 受信パイプラインと、BAM データベースに着信および発信グループ/トランザクション セットごとのパイプラインの作成のエントリを送信 (中に、"**ストア メッセージ ペイロード reporting**プロパティが選択されている)。 インターチェンジが拒否される場合は、エントリは作成されません。  
  
 送信または受信したインターチェンジについて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。  
  
-   トランザクション セットのコンテンツ。 状態レポート UI でインターチェンジに含まれるトランザクション セットを参照し、実際のトランザクション セットのコンテンツを表示することができます。  
  
-   トランザクション セットの詳細情報には、次のものが含まれます。  
  
|||  
|-|-|  
|情報|フィールドまたは値|  
|ApplicationSender|(GS02 または\<UNG2.1(UNG2.2)\>|  
|ApplicationReceiver|GS03 または\<UNG3.1(UNG3.2)\>|  
|GroupDate|GS04 または UNG2.4|  
|GroupTime|GS05 または UNG2.5|  
|TransactionSetId|ST01 または UNH2.1 (AN 文字列)|  
|InterchangeControlNo|ISA13|  
|GroupControlNo|GS06|  
|BtsDocType|NameSpace + ルート ノード名|  
|TransactionSetControlID|ST02 または UNH1|  
|TransactionSetStatus|Accepted、AcceptedWithError、または Rejected|  
|Direction|Send または Receive|  
|BtsProcessingTime|受信側: BTSReceiveTime (ローカル時刻) (パイプラインで設定された時刻)<br /><br /> 送信側: BTSSendTime (ローカル時刻) (ASM コンポーネントによってエンベロープに設定された時刻)|  
|BTS.MessageId|受信側: メッセージ プロパティの BTSMessageId<br /><br /> 送信側 : <br /><br /> 単一のトランザクション セットの場合: BTSMessageId<br /><br /> 送信バッチの: (バッチ メッセージの BTSMessageId でなく) のバッチで各メッセージの TransactionSet BTSMessageId**注:**記憶域のみ – はない UI に表示します。|  
  
## <a name="see-also"></a>参照  
 [格納されている EDI および AS2 状態レポートのデータ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [格納されているバッチの状態レポートのデータ](../core/data-stored-for-batching-status-reports.md)   
 [AS2 状態レポート用に格納されるデータ](../core/data-stored-for-as2-status-reports.md)