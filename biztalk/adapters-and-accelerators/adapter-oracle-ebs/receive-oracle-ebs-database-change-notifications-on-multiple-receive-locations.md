---
title: データベースの変更が Oracle E-business Suite で複数の通知の受信場所 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d25faa52-e0a4-4593-8449-3ec93d5887e9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5023dddeaab02c86db5507bc0f96ccfddd82c76e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217026"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-on-multiple-receive-locations"></a>データベースの変更が Oracle E-business Suite の受信場所を複数の通知
同じデータベース内の複数の受信場所が同じテーブル (例: ACCOUNTACTIVITY) のクエリ通知を受信するように構成の異なる BizTalk アプリケーションの一部として作成が存在するシナリオを検討してください。 同じテーブルには、数百のレコードを挿入、すべての受信場所は、通知メッセージを受け取ります。 効果的に間で通知を受信する複数の受信場所、このような形でその受信場所のいずれかで、通知が受信した場合、BizTalk アプリケーションから、操作を呼び出すことができます、その他の受信場所、同じ通知を取得できません。 そのため、できます。 実質的に複数の場所で受信した負荷分散通知します。  
  
 受信通知の負荷を分散するためのオーケストレーションを設定するために必要なタスクは、のものと同じ[受信 Oracle E-business Suite 変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)です。 このトピックの一覧のみ、2 つの方法の違い。  
  
## <a name="load-balancing-query-notifications-across-multiple-receive-locations"></a>受信場所を複数のクエリ通知の負荷分散  
 などのトピックの「[受信 Oracle E-business Suite 変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)、PROCESS_RECORDS プロシージャを実行してインクリメンタル通知を構成します。 負荷分散を構成するに通知しているレコードを削除するストアド プロシージャを実行する可能性があります。 たとえば、次の定義を持つストアド プロシージャ NOTIFY_LOAD_BALANCE があるとします。  
  
```  
PROCEDURE NOTIFY_LOAD_BALANCE (TABLE_DATA OUT SYS_REFCURSOR) IS  
  var int;  
BEGIN  
  SELECT TID INTO var FROM ACCOUNTACTIVITY WHERE ROWNUM = 1 FOR UPDATE;  
  OPEN TABLE_DATA FOR SELECT * FROM ACCOUNTACTIVITY WHERE TID = var;  
  DELETE FROM ACCOUNTACTIVITY WHERE TID = var;  
END NOTIFY_LOAD_BALANCE;  
```  
  
 BizTalk アプリケーションの一部としてこのストアド プロシージャを実行するときに通知が受信した既にレコードは削除されます。 そのため、他の通知の場所を取得次のレコードの。  
  
 通知を受信するための負荷分散を構成する必要がありますの大まかな手順のとおりです。  
  
1.  スキーマを作成**通知**(受信操作) と**NOTIFY_LOAD_BALANCE**プロシージャ (送信操作)。  
  
2.  オーケストレーションを追加し、通知を受け取る、プロシージャを実行および手順については、応答を取得する 3 つのメッセージを追加します。  
  
3.  オーケストレーションを作成するには、送信図形と受信図形、メッセージの構築図形、およびポートを追加します。 メッセージを構築するため、同じのサンプル コードを使用するには NOTIFY_LOAD_BALANCE ストアド プロシージャを呼び出します。 操作を実行中に注意してください[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、NOTIFY_LOAD_BALANCE 手順については、要求メッセージ C:\TestLocation\MessageIn の場所にする必要があります。 これを行うで作成されたオーケストレーションの一部として、コード スニペットを呼び出すので[受信 Oracle E-business Suite 変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-change-notifications-incrementally-using-biztalk-server.md)要求 XML の存在に基づいて、要求メッセージを作成で C:\TestLocation\MessageIn です。  
  
4.  構築し、アプリケーションを展開します。 負荷分散を示すためには、展開する必要ありますこのオーケストレーションには、少なくともを持つ 2 つの異なるコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インストールします。  
  
5.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Wcf-oracleebs、Wcf-custom 受信場所の両方のコンピューターで、管理コンソールが次のバインドのプロパティを指定します。  
  
    |プロパティのバインド|値|  
    |----------------------|-----------|  
    |**InboundOperationType**|これを設定して**通知**です。|  
    |**NotificationPort**|ODP.NET が Oracle データベースからデータベースの変更通知をリッスンするように開く必要があるポート番号を指定します。 これは、Windows ファイアウォールの例外一覧に追加する必要があります同じポート番号を設定します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。 **重要:** これを既定値は-1 を設定する場合は、通知メッセージを受け取るための Windows ファイアウォールを完全に無効にする必要があります。|  
    |**NotificationStatement**|これを設定します。<br /><br /> `SELECT TID,ACCOUNT,PROCESSED FROM SCOTT.ACCOUNTACTIVITY WHERE PROCESSED = ‘n’`**注:** スキーマ名とテーブル名を指定する必要があります。 たとえば、 `SCOTT.ACCOUNTACTIVITY`のようにします。|  
    |**NotifyOnListenerStart**|これを設定して**True**です。|  
  
6.  BizTalk アプリケーションを起動します。  
  
7.  通知の受信を開始するには、ACCOUNTACTIVITY テーブルに数百のレコードを挿入します。 中に、NOTIFY_LOAD_BALANCE プロシージャを呼び出すことの要求 XML が C:\TestLocation\MessageIn で使用できるになっていることを確認します。  
  
8.  ここで、BizTalk アプリケーションによって通知メッセージが削除されて (両方のコンピューター) 上の場所を監視します。 挿入、数百レコードの 1 つの場所を取得するレコードの一部の通知、他の場所は、残りのレコードの通知を取得中に表示されます。 同時に、両方の場所では、数百のすべてのレコードの通知を受け取ります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle E-business Suite データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-ebs/receive-oracle-ebs-database-change-notifications-using-biztalk-server.md)