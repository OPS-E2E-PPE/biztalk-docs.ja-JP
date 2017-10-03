---
title: "BizTalk Server を使用して SQL からクエリ通知の複数受信場所を受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9afbe98e-8901-417c-a807-8db97fd7a24b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa858483914b8325e9250e1e41f99ae03226f3ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-on-multiple-receive-locations-from-sql-using-biztalk-server"></a>BizTalk Server を使用して SQL からのクエリ通知の複数受信場所の受信します。
同じデータベース内の複数の受信場所が同じテーブル (例: 従業員) のクエリ通知を受信するように構成の異なる BizTalk アプリケーションの一部として作成が存在するシナリオを検討してください。 同じテーブルには、数百のレコードを挿入、すべての受信場所は、通知メッセージを受け取ります。 効果的に間で通知を受信する複数の受信場所、このような形でその受信場所のいずれかで、通知が受信した場合、BizTalk アプリケーションから、操作を呼び出すことができます、その他の受信場所、同じ通知を取得できません。 そのため、できます。 実質的に複数の場所で受信した負荷分散通知します。  
  
 受信通知の負荷を分散するためのオーケストレーションを設定するために必要なタスクは、のものと同じ[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)です。 このトピックの一覧のみ、2 つの方法の違い。  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>受信場所を複数のクエリ通知の負荷分散  
 などのトピックで[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)、既に通知を受け取るレコードに UPDATE ステートメントを実行することによってインクリメンタル通知を構成します。 負荷分散を構成するに通知しているレコードを削除するストアド プロシージャを実行する可能性があります。 たとえば、次の定義を持つストアド プロシージャ PROCESS_EMPLOYEE があるとします。  
  
```  
DECLARE @var int  
SELECT TOP 1 @var = Employee_ID FROM Employee  
SELECT * FROM Employee WHERE Employee_ID=@var  
DELETE FROM Employee WHERE Employee_ID=@var  
```  
  
 BizTalk アプリケーションの一部としてこのストアド プロシージャを実行するときに通知が受信した既にレコードは削除されます。 そのため、他の通知の場所を取得次のレコードの。  
  
 通知を受信するための負荷分散を構成する必要がありますの大まかな手順のとおりです。  
  
1.  スキーマを作成**通知**(受信操作) と**PROCESS_EMPLOYEE**ストアド プロシージャ (送信操作)。  
  
2.  オーケストレーションを追加し、通知を受け取ると、ストアド プロシージャを実行し、ストアド プロシージャの応答を取得の 3 つのメッセージを追加します。  
  
3.  オーケストレーションを作成するには、送信図形と受信図形、メッセージの構築図形、およびポートを追加します。 メッセージを構築するため、同じのサンプル コードを使用するには PROCESS_EMPLOYEE ストアド プロシージャを呼び出します。 操作を実行中に注意してください[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、する必要があります C:\TestLocation\MessageIn の場所にストアド プロシージャを PROCESS_EMPLOYEE の要求メッセージ。 これを行うで作成されたオーケストレーションの一部として、コード スニペットを呼び出すので[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)XML C:\ 内に存在した要求に基づいて要求メッセージを作成TestLocation\MessageIn です。  
  
4.  構築し、アプリケーションを展開します。 負荷分散を示すためには、展開する必要ありますこのオーケストレーションには、少なくともを持つ 2 つの異なるコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]両方のコンピューターで、管理コンソールでは、バインドのプロパティ、Wcf-custom または WCF SQL の受信場所を指定します。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定して**通知**です。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0`<br /><br /> **注:**通知ステートメントのスキーマ名と共にテーブル名を常に指定する必要があります。 たとえば、 `dbo.Employee`のようにします。|  
    |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
6.  BizTalk アプリケーションを起動します。  
  
7.  通知の受信を開始するには、EMPLOYEE テーブルに数百のレコードを挿入します。 中に、要求 XML ストアド プロシージャの呼び出し、PROCESS_EMPLOYEE を使用できる C:\TestLocation\MessageIn でいることを確認します。  
  
8.  ここで、BizTalk アプリケーションによって通知メッセージが削除されて (両方のコンピューター) 上の場所を監視します。 挿入、数百レコードの 1 つの場所を取得するレコードの一部の通知、他の場所は、残りのレコードの通知を取得中に表示されます。 同時に、両方の場所では、数百のすべてのレコードの通知を受け取ります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受信します。](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)