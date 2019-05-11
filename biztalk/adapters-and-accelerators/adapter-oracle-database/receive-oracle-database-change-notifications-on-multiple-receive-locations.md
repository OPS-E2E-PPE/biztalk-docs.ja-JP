---
title: Oracle データベースの変更が複数の通知の受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d273517-9527-4208-99be-97c8a92f176d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce52404e04b8820d63035c0328969100967c4e16
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529589"
---
# <a name="receive-oracle-database-change-notifications-on-multiple-receive-locations"></a>Oracle データベースの変更が複数の通知の受信場所
同じデータベース内の複数の受信場所が同じテーブル (例: ACCOUNTACTIVITY) のクエリ通知を受信するように構成の異なる BizTalk アプリケーションの一部として作成する必要があるシナリオを検討してください。 100 個のレコードを挿入して、同じテーブルに、すべての受信場所で、通知メッセージが表示されます。 効果的に間での通知を受信する複数の受信場所、その受信場所のいずれかで通知を受信した場合、このような方法で BizTalk アプリケーションから操作を呼び出すことが、その他の受信場所と同じ通知を取得できません。 そのため、複数の場所で受信した負荷分散通知すること効果的にできます。  

 負荷分散通知を受信するオーケストレーションを設定するために必要なタスクがの場合と同じ[受信 Oracle データベース変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)します。 このトピックの一覧のみ、2 つのアプローチの違い。  

## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>複数のクエリ通知の負荷分散の受信場所  
 などのトピックで[受信 Oracle データベース変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)、PROCESS_RECORDS プロシージャを実行してインクリメンタル通知を構成します。 負荷分散を構成するには、レコードの通知を削除するストアド プロシージャを実行できます。 たとえば、次の定義のストアド プロシージャ NOTIFY_LOAD_BALANCE を検討してください。  

```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  

 BizTalk アプリケーションの一部としてこのストアド プロシージャを実行するときに通知が受信した既にレコードが削除されます。 そのため、この他は、次のレコードの場所を取得の通知を受信します。  

 通知を受信するための負荷分散を構成する必要がありますを実行する手順の概要を次に示します。  

1. スキーマを作成**通知**(入力方向の操作) と**NOTIFY_LOAD_BALANCE**プロシージャ (送信操作)。  

2. オーケストレーションを追加し、通知の受信、プロシージャを実行および応答を取得する手順については 3 つのメッセージを追加します。  

3. オーケストレーションを作成するには、送信および受信図形、メッセージの構築図形、およびポートを追加します。 メッセージを構築するための同じサンプル コードを使用すると、NOTIFY_LOAD_BALANCE ストアド プロシージャを呼び出します。 操作を実行中に注意して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、場所 C:\TestLocation\MessageIn NOTIFY_LOAD_BALANCE 手順については、要求メッセージがあります。 作成されたオーケストレーションの一部として、コード スニペットを呼び出すため、これは[受信 Oracle データベース変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md) C:\ に存在する XML 要求に基づいて要求メッセージを作成します。TestLocation\MessageIn します。  

4. 構築し、アプリケーションをデプロイします。 負荷分散を示すためには、する必要がありますを展開するこのオーケストレーションを少なくとも 2 つの異なるコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]をインストールします。  

5. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]両方のコンピューターでの管理コンソールは、Wcf-custom または Wcf-oracledb の次のバインド プロパティの受信場所を指定します。  


   |     プロパティのバインド      |                                                                                                                                                                                                                                                                         値                                                                                                                                                                                                                                                                         |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **InboundOperationType**  |                                                                                                                                                                                                                                                             これを設定**通知**します。                                                                                                                                                                                                                                                             |
   |   **NotificationPort**    | Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。 **重要:** これを既定値は-1 に設定した場合は通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。 |
   | **NotificationStatement** |                                                                                                                                                                 これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’` **注:** スキーマ名とテーブル名を指定する必要があります。 たとえば、`SCOTT.ACCOUNTACTIVITY` のようにします。                                                                                                                                                                 |
   | **NotifyOnListenerStart** |                                                                                                                                                                                                                                                                 これを設定**True**します。                                                                                                                                                                                                                                                                 |


6. BizTalk アプリケーションを起動します。  

7. 通知の受信を開始するには、ACCOUNTACTIVITY テーブルに 100 個のレコードを挿入します。 中に、XML NOTIFY_LOAD_BALANCE プロシージャを呼び出すための要求が C:\TestLocation\MessageIn で使用できるになっていることを確認します。  

8. BizTalk アプリケーションによって通知メッセージが削除されます (両方のコンピューター) での場所を監視します。 挿入されたレコードの数百の 1 つの場所を取得するレコードの一部の通知、他の場所が、残りのレコードの通知を取得中に表示されます。 同時に、両方の場所には、数百のすべてのレコードの通知が届きます。  

## <a name="see-also"></a>参照  
 [段階的に BizTalk Server を使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)