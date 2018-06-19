---
title: SQL アダプターを使用してクエリ通知を受け取る |Microsoft ドキュメント
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
ms.openlocfilehash: 37d333a2248c943d1d404aa086565ae4b1662226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224506"
---
# <a name="receive-query-notifications-using-the-sql-adapter"></a>SQL アダプタを使用してクエリ通知を受信します。
アダプターのクライアントは、通知を受信するクエリ、データの変更について、SQL Server データベースでサブスクライブできます。 SQL SELECT ステートメントまたはストアド プロシージャは、クエリ通知のトリガー用のテーブルにデータ変更の条件を指定、SQL Server クエリ通知を送信して、SELECT ステートメントまたはストアド プロシージャの変更の結果を設定するとします。  
  
> [!IMPORTANT]
>  クエリ通知をサポートするには、アダプターのクライアントと SQL Server データベースが特定の要件を満たすためがします。 これらの要件の詳細についてを参照してください「クエリ通知を有効にする」 [http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)です。  
  
 一般的なクエリ通知には、次の項目が含まれます。  
  
-   アダプターのクライアントを指定する必要があります`Notification`で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
-   アダプターのクライアントでクエリ通知を登録する SQL ステートメントを指定する必要があります、 **NotificationStatement**プロパティをバインドします。 アダプターのクライアントでは、結果セットの指定された SQL ステートメントの変更をすぐに、SQL Server から通知を取得します。  
  
    > [!IMPORTANT]
    >  通知を通知サブスクリプションの SQL ステートメントを受信する*必要があります*特定の条件を満たしています。 クエリ通知のために使用する SQL ステートメントの概要については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)です。  
  
-   アダプターのクライアントがでリスナーを起動するとすぐに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定する必要があります、 **NotifyOnListenerStart**プロパティをバインドします。  
  
-   としてアダプター クライアントに通知が送信され、SQL ステートメントがで指定された結果セットがの場合、 **NotificationStatement**プロパティのバインドを変更します。  
  
 これらのバインド プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
> [!NOTE]
>  通知サブスクリプションは、ステートメントが実行されたトランザクションがコミットまたはロールバックするかどうかに関係なく、コミットは常にします。 そのため、通知操作では、通知のサブスクライブしているクエリの結果が変更されたことがあります限りません。 たとえば、トランザクションでは、(通知のサブスクライブ) テーブルの行のデータを挿入し、(insert) の変更について通知するアダプターをすぐに通知が送信されます。 なんらかの理由により、トランザクションがロールバックし、効果的にデータが挿入されないテーブルの行にします。 ただし、SQL Server では、トランザクションのロールバックはアダプターに通知が送信はできません。 SQL server クエリ通知の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=145367](http://go.microsoft.com/fwlink/?LinkId=145367)です。  
  
## <a name="differences-between-query-notification-and-polling"></a>クエリ通知とポーリングの相違点  
 クエリ通知のポーリング、両方の受信操作とは、SQL Server データベースのデータ変更に関して、アダプターをクライアントに通知を次の表には、2 つの間には、いくつか違いが一覧表示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|クエリ通知|ポーリング|  
|------------------------|-------------|  
|クエリ通知は、SQL Server によって開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セットの変更がある場合に通知を開始するように指示します。|ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングを使用し、ポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証するステートメントを実行します。|  
|クエリ通知のステートメントを使用すると、SQL Server データベース テーブルにデータを読み取るだけです。|ポーリング ステートメントを使用して、読み取るまたは SQL Server データベース テーブル内のデータを更新することができます。|  
|クエリ通知が、Insert などのデータ変更の種類にのみ通知は、更新、および削除します。|ポーリングでは、実際のデータが変更されたことについて通知されます。|  
|データの変更通知は瞬時に発生します。|アダプター クライアントは、すべてのポーリング間隔の最後にデータの変更に関する通知は、データの変更通知は、ポーリング間隔によって異なります。 **ヒント:** ポーリングすれば、スループットを向上させる、データの変更が、継続的に行われていると、発生したタイミングととしてそれぞれの変更の通知を受けるたくないシナリオでします。 代わりに、前回の変更通知以降に行われたすべての変更の通知されるようにすた後ポーリング間隔を指定します。|  
  
 クエリ通知の詳細については[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]を参照してください[を使用して BizTalk Server での SQL クエリ通知の受信](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)