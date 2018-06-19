---
title: 受信クエリ通知を使用して、SQL アダプターに関する考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0142f385-3d55-41a7-a50e-dda94b96d0a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02d7aa9eadc5e639e56cc526bfd5763abc432a4f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963008"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>受信クエリ通知を使用して、SQL アダプターに関する考慮事項
このトピックでは、いくつかの考慮事項とベスト プラクティスを使用しているときに留意する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server データベースからクエリ通知を受信します。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>アダプターを使用して通知を受信するときの考慮事項  
 使用しているときに、次を考慮する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クエリ通知を受信します。  
  
-   [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、SQL Server から、クエリ通知を受信し、通知のアダプターのクライアントを単に渡します。 アダプターはさまざまな操作の通知によって区別されません (つまり、アダプターはありません、情報の挿入操作または更新操作は、特定の通知するかどうか)。  
  
-   操作の通知メッセージは、その操作によって影響を受けたレコードの数の影響を受けません。 たとえば、アダプター クライアントは、数に関係なく、挿入、更新、または SQL Server データベース テーブルで削除されたレコード、1 つだけの通知メッセージを受信します。  
  
-   アダプターのクライアント アプリケーションが、SQL Server から受信した通知の種類を解釈するためのロジックを含めることをお勧めします。 情報を抽出することで、通知の種類を決定できます、 **\<情報\>** 通知を受信したメッセージの要素。 挿入操作用に受信した通知メッセージの例を次に示します。  
  
    ```  
    <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
      <Info>Insert</Info>  
      <Source>Data</Source>  
      <Type>Change</Type>  
    </Notification>  
    ```  
  
     内の値に注意してください、 **\<情報\>** 要素。 この値は、通知メッセージを受信した操作について説明します。 アプリケーション内の値を抽出する機能を持つ必要があります、 **\<情報\>** 要素し、値に基づいて、後続のタスクを実行します。 トピック[を BizTalk Server を使用して SQL の特定のタスクを完了する通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)内の値を抽出する方法の手順を持つ、 **\<情報\>** 要素. 同様のタスクを実行する詳細なチュートリアルについてはでも[チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)です。  
  
-   理想的には、クライアント アプリケーションが特定のレコードの通知を受信した後そのレコードが更新されますできるように、追加の通知が受信されていません。 たとえば、**従業員**を持つテーブル、**ステータス**列です。 すべての新しいレコードが挿入されるため、**従業員**テーブル内の値、**ステータス**列は常になど、次のテーブルが表示されるので、「0」。  
  
    |従業員の名前|[状態]|  
    |-------------------|------------|  
    |John|0|  
  
     アダプターのクライアントを設定する新しく挿入したレコードの通知を受信する、 **NotificatonStatement**バインディングとしてのプロパティ。  
  
    ```  
    SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
    ```  
  
    > [!NOTE]
    >  具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。 また、スキーマ名と共に、テーブル名を必ず指定する必要があります。 たとえば、dbo します。従業員。  
  
     通知を受信した後、クライアント アプリケーションがの値をリセットする必要があります、**ステータス**列「1」をできるように、通知のステートメントはもう一度レコードで動作しません。 そのため、クライアント アプリケーションは、の更新操作を実行する必要があります、**従業員**テーブル。 内のレコード、同じ更新操作の完了後、**従業員**テーブルは、次のようになります。  
  
    |従業員の名前|[状態]|  
    |-------------------|------------|  
    |John|1|  
  
     興味深いことに、更新操作は、アダプターのクライアントに通知を再度送信します。 プロセス全体はもう一度繰り返されます、したがって、クライアント アプリケーションは必要なロジックをこのような不要な通知を破棄する必要があります。  
  
-   場合、 **NotifyOnListenerStart**プロパティのバインドは、アダプターのクライアント、受信場所を開始するたびに通知メッセージが表示されます。 バインディング プロパティを使用し、通知メッセージを解釈する方法の詳細については、次を参照してください。[受信クエリ通知の後に、受信場所の内訳で BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)です。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>通知を受信するための一般的なオーケストレーション  
 このセクションで説明を使用して通知を受信するための一般的なオーケストレーション フロー、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
1.  オーケストレーションが行う必要がありますまず受信されると、通知の種類を決定を含みます。  
  
    -   後に、通知を受信したかどうか、受信場所を再起動します。  
  
    -   Insert などのデータベース テーブル上の操作に対して、通知を受信したかどうかは、更新、または削除します。  
  
     オーケストレーションを含める必要があります、**式**図形、受信メッセージの種類を決定する xpath クエリです。  
  
2.  通知後の型が決定、オーケストレーションが受信した通知の種類に基づいて特定のアクションを実行する判断ブロックを含める必要があります。 これを実現する、オーケストレーションを含める必要があります、**判断**、図形が含まれる、**ルール**ブロックと**Else**ブロック。  
  
    -   内で、**ルール**ブロック、条件を指定して、条件が満たされた場合、特定の操作を実行するオーケストレーション図形を含める必要があります。  
  
    -   内で、 **Else**ブロック、条件の場合は、特定の操作を実行するオーケストレーション図形を含める必要があります*されません*満たされています。  
  
 上記の要件の詳細については、「[を BizTalk Server を使用して SQL 特定タスクを完了する通知メッセージを処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)です。 使用できる詳細なチュートリアルについても[チュートリアル 2: 従業員の発注プロセスには、SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)です。