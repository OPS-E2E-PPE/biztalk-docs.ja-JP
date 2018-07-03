---
title: BizTalk Server を使用して SQL からのクエリ通知で複数受信場所の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 231d5f83e673a7af2594c3f6f49e4457fcd9573e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010467"
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL のクエリ通知で複数受信場所を受信します。
同じデータベース内の複数の受信場所が同じテーブル (例: 従業員) のクエリ通知を受信するように構成の異なる BizTalk アプリケーションの一部として作成する必要があるシナリオを検討してください。 100 個のレコードを挿入して、同じテーブルに、すべての受信場所で、通知メッセージが表示されます。 効果的に間での通知を受信する複数の受信場所、その受信場所のいずれかで通知を受信した場合、このような方法で BizTalk アプリケーションから操作を呼び出すことが、その他の受信場所と同じ通知を取得できません。 そのため、複数の場所で受信した負荷分散通知すること効果的にできます。  

 負荷分散通知を受信するオーケストレーションを設定するために必要なタスクがの場合と同じ[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)します。 このトピックの一覧のみ、2 つのアプローチの違い。  

## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>複数のクエリ通知の負荷分散の受信場所  
 などのトピックで[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)、既にを受け取るレコードで UPDATE ステートメントを実行してインクリメンタル通知を構成します。 負荷分散を構成するには、レコードの通知を削除するストアド プロシージャを実行できます。 たとえば、次の定義のストアド プロシージャ PROCESS_EMPLOYEE を検討してください。  

```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  

 BizTalk アプリケーションの一部としてこのストアド プロシージャを実行するときに通知が受信した既にレコードが削除されます。 そのため、この他は、次のレコードの場所を取得の通知を受信します。  

 通知を受信するための負荷分散を構成する必要がありますを実行する手順の概要を次に示します。  

1. スキーマを作成**通知**(入力方向の操作) と**PROCESS_EMPLOYEE**ストアド プロシージャ (送信操作)。  

2. オーケストレーションを追加し、追加の 3 つのメッセージの通知を受け取る、ストアド プロシージャを実行するストアド プロシージャの応答を取得します。  

3. オーケストレーションを作成するには、送信および受信図形、メッセージの構築図形、およびポートを追加します。 メッセージを構築するための同じサンプル コードを使用すると、PROCESS_EMPLOYEE ストアド プロシージャを呼び出します。 操作を実行中に注意して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]が必要な管理コンソールで、場所 C:\TestLocation\MessageIn でストアド プロシージャを PROCESS_EMPLOYEE の要求メッセージ。 作成されたオーケストレーションの一部として、コード スニペットを呼び出すため、これは[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)C:\ に存在する XML 要求に基づいて要求メッセージを作成します。TestLocation\MessageIn します。  

4. 構築し、アプリケーションをデプロイします。 負荷分散を示すためには、する必要がありますを展開するこのオーケストレーションを少なくとも 2 つの異なるコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]をインストールします。  

5. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]両方のコンピューターでの管理コンソールは、バインドのプロパティ、Wcf-custom または WCF SQL の受信場所を指定します。  


   |     プロパティのバインド      |                                                                                                                  値                                                                                                                  |
   |---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **InboundOperationType**  |                                                                                                      これを設定**通知**します。                                                                                                      |
   | **NotificationStatement** | これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:** 通知のステートメントは、スキーマ名とテーブル名常に指定する必要があります。 たとえば、 `dbo.Employee`のようにします。 |
   | **NotifyOnListenerStart** |                                                                                                          これを設定**True**します。                                                                                                          |


6. BizTalk アプリケーションを起動します。  

7. 通知の受信を開始するには、EMPLOYEE テーブルに 100 個のレコードを挿入します。 中に、XML 要求、PROCESS_EMPLOYEE を呼び出すストアド プロシージャを使用できる C:\TestLocation\MessageIn でいることを確認します。  

8. BizTalk アプリケーションによって通知メッセージが削除されます (両方のコンピューター) での場所を監視します。 挿入されたレコードの数百の 1 つの場所を取得するレコードの一部の通知、他の場所が、残りのレコードの通知を取得中に表示されます。 同時に、両方の場所には、数百のすべてのレコードの通知が届きます。  

## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受け取る](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)