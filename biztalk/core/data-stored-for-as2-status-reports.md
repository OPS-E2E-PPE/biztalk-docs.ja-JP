---
title: AS2 状態レポート用に格納されているデータ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6aa4077-3768-436b-99b9-d203a86a7e69
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14fc95dfba5e29089653ef02dddd1b0b366ff8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012517"
---
# <a name="data-stored-for-as2-status-reports"></a>AS2 状態レポート用に格納されるデータ
レポートの 2 つのレベルが AS2 状態レポートで使用可能: 最初の場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている (から、**全般プロパティ**のページ、**全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、アグリーメントに対して否認不可データベース ストレージのプロパティが選択されている場合、もう 1 つ。  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a>AS2 レポートがアクティブになっている場合に格納されるデータ  
 場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信されるすべてのレコードを受信した AS2 メッセージおよび Mdn が保持されます。  
  
 受信した AS2 メッセージについては、BizTalk Server は次の情報を格納します。  
  
- AS2 メッセージのレコード  
  
  受信または送信した MDN (同期または非同期) については、BizTalk Server は次の情報を格納します。  
  
- MDN のレコード  
  
  状態レポート UI により、AS2 メッセージ レコードを適切な MDN レコードに関連付けることができます。  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a>"MDN を受信しない場合は AS2 メッセージを再送信する" が有効になっている場合に格納されるデータ  
 場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報が記録されます。  
  
-   各再送信の時刻  
  
-   各再送信の状態  
  
-   各再送信のインデックス  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a>否認不可データベース ストレージが有効になっている場合に格納されるデータ  
 否認不可データベース ストレージは、次のアグリーメントのプロパティが選択されている場合に有効になります。  
  
- エンコードされた送信 AS2 メッセージに対して有効な NRR  
  
- デコードされた送信 AS2 メッセージに対して有効な NRR  
  
- 受信 MDN に対して有効な NRR  
  
- エンコードされた受信 AS2 メッセージに対して有効な NRR  
  
- デコードされた受信 AS2 メッセージに対して有効な NRR  
  
- 送信 MDN に対して有効な NRR  
  
  上記のうち、1 つ以上のプロパティが選択されていると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。  
  
- すべての AS2 メッセージのコンテンツ、およびすべての MDN のコンテンツ (AS2 ヘッダーの有無にかかわらず)  
  
## <a name="data-stored-for-edi-over-as2"></a>EDI Over AS2 に格納されるデータ  
 場合、**レポートを有効にする**プロパティには、EDI アグリーメントと AS2 アグリーメントの両方が選択されているし、EDI メッセージ レコードの AS2 メッセージ レコード (EDI ペイロードを含む) を関連付けることができます。  
  
 トランザクション セットの格納が有効になっている場合は、状態レポート UI にトランザクション セットの詳細と AS2 メッセージ コンテンツの詳細を表示できます。  
  
> [!NOTE]
>  これらのレポートにアクセスするには、AS2EdiReceive または AS2EdiSend パイプラインを使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [EDI 状態レポート用に格納されているデータ](../core/data-stored-for-edi-status-reports.md)   
 [バッチの状態レポート用に格納されるデータ](../core/data-stored-for-batching-status-reports.md)