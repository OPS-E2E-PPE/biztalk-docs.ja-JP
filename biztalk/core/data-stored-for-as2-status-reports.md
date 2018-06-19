---
title: AS2 状態レポートに格納されているデータ |Microsoft ドキュメント
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
ms.openlocfilehash: 2341004abe65864b2fceb90985871ecad0cf1e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238514"
---
# <a name="data-stored-for-as2-status-reports"></a>AS2 状態レポート用に格納されるデータ
2 つのレベルのレポートを AS2 状態レポートで使用できます: 最初の場合、**レポートをオンに**、アグリーメントのプロパティが選択されている (から、**全般プロパティ**のページ、**全般**  タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、アグリーメントに対して否認不可データベース ストレージ プロパティが選択されている場合、2 番目です。  
  
## <a name="data-stored-if-as2-reporting-is-activated"></a>AS2 レポートがアクティブになっている場合に格納されるデータ  
 場合、**レポートをオンに**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信されるすべてのレコードまたは受信した AS2 メッセージと Mdn が保持されます。  
  
 受信した AS2 メッセージについては、BizTalk Server は次の情報を格納します。  
  
-   AS2 メッセージのレコード  
  
 受信または送信した MDN (同期または非同期) については、BizTalk Server は次の情報を格納します。  
  
-   MDN のレコード  
  
 状態レポート UI により、AS2 メッセージ レコードを適切な MDN レコードに関連付けることができます。  
  
## <a name="data-stored-if-resend-as2-message-if-mdn-not-received-is-enabled"></a>"MDN を受信しない場合は AS2 メッセージを再送信する" が有効になっている場合に格納されるデータ  
 場合、 **MDN を受信しない場合は再送信 AS2 メッセージ**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の情報が記録されます。  
  
-   各再送信の時刻  
  
-   各再送信の状態  
  
-   各再送信のインデックス  
  
## <a name="data-stored-if-non-repudiation-database-storage-is-enabled"></a>否認不可データベース ストレージが有効になっている場合に格納されるデータ  
 否認不可データベース ストレージは、次のアグリーメントのプロパティが選択されている場合に有効になります。  
  
-   エンコードされた送信 AS2 メッセージに対して有効な NRR  
  
-   デコードされた送信 AS2 メッセージに対して有効な NRR  
  
-   受信 MDN に対して有効な NRR  
  
-   エンコードされた受信 AS2 メッセージに対して有効な NRR  
  
-   デコードされた受信 AS2 メッセージに対して有効な NRR  
  
-   送信 MDN に対して有効な NRR  
  
 上記のうち、1 つ以上のプロパティが選択されていると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の情報を格納します。  
  
-   すべての AS2 メッセージのコンテンツ、およびすべての MDN のコンテンツ (AS2 ヘッダーの有無にかかわらず)  
  
## <a name="data-stored-for-edi-over-as2"></a>EDI Over AS2 に格納されるデータ  
 場合、**レポートをオンに**プロパティには、EDI アグリーメントだけでなく、AS2 アグリーメントの両方が選択されているし、EDI メッセージ レコードに AS2 メッセージ レコード (EDI ペイロードを含む) を関連付けることができます。  
  
 トランザクション セットの格納が有効になっている場合は、状態レポート UI にトランザクション セットの詳細と AS2 メッセージ コンテンツの詳細を表示できます。  
  
> [!NOTE]
>  これらのレポートにアクセスするには、AS2EdiReceive または AS2EdiSend パイプラインを使用する必要があります。  
  
## <a name="see-also"></a>参照  
 [格納されている EDI および AS2 状態レポートのデータ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [EDI 状態レポートに格納されているデータ](../core/data-stored-for-edi-status-reports.md)   
 [格納されているバッチの状態レポートのデータ](../core/data-stored-for-batching-status-reports.md)