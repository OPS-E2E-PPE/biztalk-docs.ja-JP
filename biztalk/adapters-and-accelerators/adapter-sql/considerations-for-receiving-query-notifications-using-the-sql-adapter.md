---
title: SQL アダプタ使用クエリ通知の受信に関する考慮事項 |Microsoft Docs
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
ms.openlocfilehash: 21b3cc0056bf8105618aac7a9c47056d3e493c49
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004347"
---
# <a name="considerations-for-receiving-query-notifications-using-the-sql-adapter"></a>SQL アダプタ使用クエリ通知の受信に関する考慮事項
このトピックではいくつかの考慮事項とベスト プラクティスを使用しているときに考慮する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server データベースからクエリ通知を受信します。  
  
## <a name="considerations-while-using-the-adapter-to-receive-notifications"></a>アダプターを使用して通知を受信する場合の考慮事項  
 使用しているときに、次を考慮する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]クエリ通知を受信します。  
  
- [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、SQL Server からクエリ通知を受信し、通知をアダプター クライアントに単に渡します。 アダプターは、さまざまな操作を通知する間隔と区別しません (つまり、アダプターはありませんすべての情報、特定の通知は、挿入操作または更新操作かどうか)。  
  
- 操作の通知メッセージは、その操作によって影響を受けたレコードの数の影響を受けません。 たとえば、アダプター クライアントで挿入、更新、または SQL Server データベースのテーブルで削除されたレコードの数に関係なく 1 つだけの通知メッセージを受け取ります。  
  
- アダプターのクライアント アプリケーションが SQL Server から受信した通知の型を解釈するためのロジックを含めることをお勧めします。 情報を抽出することで、通知の種類を決定できます、 **\<情報\>** 受信した通知メッセージの要素。 挿入操作では受信した通知メッセージの例を次に示します。  
  
  ```  
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification/">  
    <Info>Insert</Info>  
    <Source>Data</Source>  
    <Type>Change</Type>  
  </Notification>  
  ```  
  
   内の値に注意してください、 **\<情報\>** 要素。 この値は、通知メッセージを受信した操作について説明します。 アプリケーション内で値を抽出するための機能があります、 **\<情報\>** 要素し、値に基づき、後続のタスクを実行します。 トピック[BizTalk Server を使用して SQL の特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)が内の値を抽出する方法について説明されています、 **\<情報\>** 要素. 同様のタスクを実行する詳細なチュートリアルはでも[チュートリアル 2: 従業員 - 発注プロセス SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。  
  
- 理想的には、クライアント アプリケーションが特定のレコードの通知を受け取った後そのレコードが更新されますできるように、追加の通知が受信されていません。 たとえば、**従業員**を持つテーブルを**状態**列。 すべての新しいレコードに挿入されるため、**従業員**テーブル内の値、**状態**列は常に、次のように、テーブルになりますが、「0」。  
  
  |従業員の名前|状態|  
  |-------------------|------------|  
  |John|0|  
  
   アダプターのクライアントを設定する新しく挿入されたレコードの通知を受信する、 **NotificatonStatement**としてプロパティをバインドします。  
  
  ```  
  SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0  
  ```  
  
  > [!NOTE]
  >  具体的には、これで示すように、ステートメント内の列名の SELECT ステートメントを指定する必要があります。 また、スキーマ名とテーブル名を必ず指定する必要があります。 たとえば、dbo です。従業員。  
  
   クライアント アプリケーション通知を受信するには後の値をリセットする必要があります、**状態**「1」を列 notification ステートメントがもう一度レコードで動作しないようにします。 これを実現する、クライアント アプリケーションは、の更新操作を実行する必要があります、**従業員**テーブル。 更新操作の後で同じ記録、**従業員**テーブルは、次のようになります。  
  
  |従業員の名前|状態|  
  |-------------------|------------|  
  |John|1|  
  
   更新操作では、通知をアダプターのクライアントに送信もう一度興味深いことに、プロセス全体がもう一度繰り返されますと、そのため、クライアント アプリケーションでは、必要なロジックをこのような不要な通知を破棄する必要があります。  
  
- 場合、 **NotifyOnListenerStart**プロパティのバインドは、アダプターのクライアント受信場所を開始するたびに通知メッセージが表示されます。 バインド プロパティを使用し、通知メッセージを解釈する方法の詳細については、次を参照してください。[受信クエリ通知した後、受信場所のブレーク ダウンでは、BizTalk Server を使用して SQL](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)します。  
  
## <a name="typical-orchestration-for-receiving-notifications"></a>通知を受信するための一般的なオーケストレーション  
 このセクションを使用して通知を受信するための一般的なオーケストレーション フローの概要、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
1. オーケストレーションを行う必要があります最初に行うことは、受信した通知の種類を決定するなど。  
  
   - 後に、通知を受信したかどうか、受信場所を再起動します。  
  
   - Insert などのデータベース テーブルで操作の通知を受信したかどうかは、更新、または削除します。  
  
     オーケストレーションを含める必要があります、**式**図形、およびを受信したメッセージの種類を決定する xpath クエリ内で。  
  
2. 通知の種類が決定されますと、オーケストレーションが受信した通知の種類に基づいて特定のアクションを実行するための判断ブロックを含める必要があります。 これを実現するオーケストレーションを含める必要があります、**判断**、図形が含まれていますが、**ルール**ブロックと**Else**ブロック。  
  
   -   内で、**ルール**ブロックする条件を指定して、条件が満たされる場合は、特定の操作を実行するオーケストレーション図形を含める必要があります。  
  
   -   内で、 **Else**ブロック、条件の場合は、特定の操作を実行するオーケストレーション図形を含める必要があります*いない*満たします。  
  
   上記の要件の詳細については、後述[BizTalk Server を使用して SQL の特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)します。 詳細なチュートリアルについても記載されて[チュートリアル 2: 従業員 - 発注プロセス SQL アダプターを使用して](../../adapters-and-accelerators/adapter-sql/tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)します。