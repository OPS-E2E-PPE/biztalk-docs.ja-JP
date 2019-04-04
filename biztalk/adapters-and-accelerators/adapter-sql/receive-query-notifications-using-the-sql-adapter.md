---
title: SQL アダプターを使用してクエリ通知を受け取る |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2ed0f0-d005-4eec-b1a6-97a0c94678dc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 786bbf556acb3a30e652a7ecb29723f40566cb06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999747"
---
# <a name="receive-query-notifications-using-the-sql-adapter"></a>SQL アダプターを使用してクエリ通知を受け取る
SQL Server データベースのデータの変更についてのクエリ通知を受信するアダプターのクライアントがサブスクライブできます。 SQL SELECT ステートメントまたはストアド プロシージャは、クエリ通知の送信をトリガーするためのテーブルのデータ変更の条件を指定および SQL Server クエリ通知を送信します、SELECT ステートメントまたはストアド プロシージャの変更の結果を設定するとします。  
  
> [!IMPORTANT]
>  クエリ通知をサポートするには、アダプターのクライアントと SQL Server データベースが、特定の要件を満たすが。 これらの要件の詳細についてを参照してください「のクエリ通知を有効にする」 [ http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)します。  
  
 一般的なクエリ通知には、次の項目が含まれます。  
  
- アダプターのクライアントを指定する必要があります`Notification`の受信の操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
- アダプター クライアントでのクエリ通知に登録する SQL ステートメントを指定する必要があります、 **NotificationStatement**プロパティをバインドします。 アダプター クライアントでは、指定された SQL ステートメントの変更の結果が設定されるとすぐに、SQL Server から通知を取得します。  
  
  > [!IMPORTANT]
  >  通知配信登録の SQL ステートメントの通知を受信する*する必要があります*特定の条件を満たしています。 クエリ通知の使用できる SQL ステートメントの詳細については、[ http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)を参照してください。  
  
- アダプター クライアントは、リスナーで開始するとすぐに、アダプターがアダプター クライアントに通知を送信するかどうかを指定する必要があります、 **NotifyOnListenerStart**プロパティをバインドします。  
  
- 通知としてアダプター クライアントに送信され、SQL ステートメントがで指定された結果セットがの場合、 **NotificationStatement**プロパティのバインドが変更されました。  
  
  これらのバインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。  
  
> [!NOTE]
>  通知配信登録は、ステートメントが実行されたトランザクションがコミットまたはロールバックするかどうかに関係なく、コミットは常にします。 そのため、通知の操作では、通知をサブスクライブしているクエリの結果が変更されたことがあります限りません。 たとえば、トランザクションでは、(通知のサブスクライブ) テーブルの行でデータを挿入および変更 (挿入) の詳細については、アダプターの通知をすぐに通知が送信されます。 なんらかの理由により、トランザクションがロールバックし、効率的にデータは挿入されません、表の行にします。 ただし、SQL Server はトランザクションのロールバックのアダプターに通知を送信しません。 SQL Server のクエリ通知の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=145367](http://go.microsoft.com/fwlink/?LinkId=145367)を参照してください。  
  
## <a name="differences-between-query-notification-and-polling"></a>クエリ通知とポーリング間の違い  
 クエリ通知とポーリングは、両方の受信操作し、SQL Server データベースのデータの変更について、アダプターをクライアントに通知、次の表は、2 つの間のいくつかの違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|クエリ通知|ポーリング|  
|------------------------|-------------|  
|クエリ通知は、SQL Server によって開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セット内の変更がある場合は、通知を開始するように指示します。|ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングに使用できるとポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証するステートメントを実行します。|  
|クエリ通知のステートメントを使用すると、SQL Server データベース テーブルにデータを読み取るだけです。|ポーリング ステートメントを使用して、読み取りまたは SQL Server データベース テーブル内のデータを更新することができます。|  
|クエリ通知が、Insert などのデータの変更の種類にのみ通知は、更新、および削除します。|ポーリングには、実際のデータが変更されたことについて通知されます。|  
|データの変更通知は瞬時です。|データの変更通知が、ポーリング間隔に依存し、アダプター クライアントは、ポーリング間隔の最後に、データの変更について通知されます。 **ヒント:** ポーリングが継続的に、データの変更が発生したありと設定されるタイミングとしては、各変更の通知しないシナリオでスループットを向上を提供します。 代わりに、その後の前回の変更の通知以降に発生したすべての変更を通知するポーリング間隔を指定します。|  
  
 クエリ通知の詳細については[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]を参照してください[を使用して BizTalk Server によって SQL クエリ通知の受信](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)