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
ms.openlocfilehash: 45a115ed95546b99c52358d9cf15e51882991406
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352930"
---
# <a name="data-stored-for-as2-status-reports"></a>AS2 状態レポート用に格納されるデータ
レポートの 2 つのレベルが AS2 状態レポートで使用可能: 最初の場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている (から、**全般プロパティ**のページ、**全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、アグリーメントに対して否認不可データベース ストレージのプロパティが選択されている場合、もう 1 つ。  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a>AS2 レポートが有効な場合に格納されているデータ  
 場合、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信されるすべてのレコードを受信した AS2 メッセージおよび Mdn が保持されます。  
  
 受信した AS2 メッセージは、BizTalk Server は、次の情報を格納します。  
  
- AS2 メッセージのレコード。  
  
  受信または送信した MDN (同期または非同期)、BizTalk Server は、次の情報を格納します。  
  
- MDN のレコード。  
  
  状態レポート UI には、適切な MDN レコードに AS2 メッセージ レコードの相関関係ができます。  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a>AS2 メッセージを再送信 MDN を受信しないが有効な場合のデータが格納されています。  
 場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報が記録されます。  
  
-   各再送信の時間  
  
-   各再送信の状態  
  
-   各再送信のインデックス  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a>否認不可データベース ストレージが有効になっている場合に格納されているデータ  
 否認不可データベース ストレージは、次で有効にアグリーメントのプロパティが選択されています。  
  
- エンコードされた送信の AS2 メッセージに対して有効な NRR  
  
- 送信のデコードされた AS2 メッセージに対して有効な NRR  
  
- 受信 MDN に対して有効な NRR  
  
- 受信のエンコードされた AS2 メッセージに対して有効な NRR  
  
- 受信のデコードされた AS2 メッセージに対して有効な NRR  
  
- 送信 MDN に対して有効な NRR  
  
  上記のプロパティの 1 つ以上を選択すると場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は次の情報を格納します。  
  
- AS2 メッセージと (または AS2 ヘッダーのない)、MDN のコンテンツのコンテンツ。  
  
## <a name="data-stored-for-edi-over-as2"></a>AS2 経由で EDI 用に格納されるデータ  
 場合、**レポートを有効にする**プロパティには、EDI アグリーメントと AS2 アグリーメントの両方が選択されているし、EDI メッセージ レコードの AS2 メッセージ レコード (EDI ペイロードを含む) を関連付けることができます。  
  
 トランザクション セットの格納が有効になっている場合は、状態レポート UI にトランザクション セットの詳細と AS2 メッセージ コンテンツの詳細を表示できます。  
  
> [!NOTE]
>  AS2EdiReceive または AS2EdiSend パイプラインを使用して、これらのレポートにアクセスする必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [EDI 状態レポート用に格納されているデータ](../core/data-stored-for-edi-status-reports.md)   
 [バッチの状態レポート用に格納されるデータ](../core/data-stored-for-batching-status-reports.md)