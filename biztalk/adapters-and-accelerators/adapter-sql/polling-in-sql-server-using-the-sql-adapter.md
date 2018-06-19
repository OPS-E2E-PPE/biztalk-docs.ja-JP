---
title: SQL アダプタを使用して SQL Server でのポーリング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c31b3cda-c05e-46db-827b-6c47a53d1a3a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d01bc3d004da60b98e0132aa3c8e04442a45426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225850"
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>SQL アダプタを使用して SQL Server でのポーリング
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]SQL Server データベースからデータ変更メッセージを受信アダプターのクライアントを有効にします。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を取得または、データを更新し、一定の間隔で、アダプターがクライアントに結果を提供アダプターが指定された SQL ステートメント (SELECT ステートメントまたはストアド プロシージャ) を実行する、「ポーリング ベース」のメッセージの受信をサポート時間です。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のポーリングは、次の操作を公開します。  
  
-   **ポーリング**: SQL Server のテーブルまたはビューのデータの定期的な変更メッセージを受信することができます。 メッセージがない厳密に型指定します。  
  
-   **TypedPolling**: SQL Server データベースから厳密に型指定されたメッセージを受信することができます。 ポーリング メッセージ内の要素を他の任意のスキーマにマップする場合は、この操作を使用する必要があります。  
  
-   **XmlPolling**です。 SELECT ステートメントまたはストアド プロシージャを FOR XML 句を使用して、XML メッセージとしてデータを返すを使用できます。 この操作は、XML メッセージとしてポーリング メッセージを返します。  
  
     FOR XML 句についての詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402)です。  
  
 ポーリングの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[ポーリング受信ベースのデータ変更のメッセージを使用して BizTalk Server で、SQL Server から](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)です。  
  
## <a name="polling"></a>ポーリング  
 使用して一般的なポーリング操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次が含まれます。  
  
1.  アダプターのクライアントを指定する必要があります`Polling`で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
2.  アダプターのクライアントの SQL ステートメントを指定する必要があります、 **PolledDataAvailableStatement**ポーリングの使用可能なデータがあるかどうかを決定するプロパティをバインドします。 このステートメントを実行で返される最初の結果の最初の行の最初の列には、整数値が含まれています。 ポーリングに使用できるデータがない、戻り値が 0 (ゼロです)。 データが使用可能な場合、戻り値は 0 より大きい値です。  
  
3.  アダプターのクライアントのポーリング間隔を指定する必要があります、 **PollingIntervalInSeconds**間隔を定義するプロパティのバインド内のステートメント、 **PolledDataAvailableStatement**バインディングプロパティは実行されます。 ポーリング間隔の最後に、ポーリングされたデータの使用可能なステートメントが実行され、結果セットが返されます。  
  
4.  アダプターのクライアントのポーリング SQL ステートメント (SELECT ステートメントまたはストアド プロシージャ) を指定する必要があります、 **PollingStatement**プロパティをバインドします。 ポーリングに使用できるデータが場合 (によって決定されます、 **PolledDataAvailableStatement**プロパティのバインド)、アダプターは実行されるポーリング ステートメント (該当する場合) を更新する SQL Server データベース内のデータ。 ときに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と共に使用される[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、同じトランザクションがメッセージを送信する使用も[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
5.  アダプターのクライアントが使用できる、 **PollWhileDataFound**ポーリング間隔を無視して継続的に使用可能な場合と、データをポーリングするプロパティをバインドします。  
  
6.  ポーリング ステートメントを実行すると、返される結果セットは、受信メッセージとして、アダプターのクライアントに送信されます。  
  
> [!NOTE]
>  XmlPolling 操作には、ポーリング操作と同じ手順が含まれます。  
  
## <a name="strongly-typed-polling"></a>厳密に型指定されたポーリング  
 使用して一般的な厳密に型指定されたポーリング操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次が含まれます。  
  
1.  アダプターのクライアントを指定する必要があります`TypedPolling`で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
2.  アダプターのクライアントは、接続 URI の一部として受信 ID を指定する必要があります。 受信 ID は、任意の文字列を使用する可能性があり、名前空間の競合を回避する TypedPolling 操作の標準の名前空間に追加されます。  
  
3.  残りの手順は、手順 2 ~ 6 の前のセクションで説明されているポーリング操作に一覧表示と同じです。  
  
 ポーリングと厳密に型指定されたポーリングに関連するバインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for SQL Server のアダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
> [!NOTE]
>  ポーリング ステートメントを実行すると、複数の結果セットが返されます。 結果セットには、すべての行は含まれていない場合、は、アダプターのクライアントにメッセージが送信されません。  
  
 次の図でポーリング ワークフローに関する情報を提供する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 ポーリング ワークフローの 2 つのシナリオに示します。  
  
1.  ときの値、 **PollWhileDataFound**が"False"(既定の設定) に設定します。  
  
2.  ときの値、 **PollWhileDataFound** "True"に設定されています。  
  
 ![ポーリング ワークフロー & #40 です。PollWhileDataFound & #61 です。False &#41;] (../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![ポーリング ワークフロー & #40 です。PollWhileDataFound & #61 です。True &#41;] (../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>ポーリングとクエリ通知の相違点  
 ポーリングとクエリ通知は、両方の受信操作であり、SQL Server データベースにデータの変更について、アダプターをクライアントに通知が次の表には、2 つの間には、いくつか違いが一覧表示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|ポーリング|クエリ通知|  
|-------------|------------------------|  
|ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングを使用し、ポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証するステートメントを実行します。|クエリ通知は、SQL Server によって開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セットの変更がある場合に通知を開始するように指示します。|  
|ポーリング ステートメントを使用して、読み取るまたは SQL Server データベース テーブル内のデータを更新することができます。|クエリ通知のステートメントを使用すると、SQL Server データベース テーブルにデータを読み取るだけです。|  
|ポーリングでは、実際のデータが変更されたことについて通知されます。|クエリ通知は、Insert などのデータ変更の種類についてのみ通知は、更新、および削除します。|  
|アダプター クライアントは、すべてのポーリング間隔の最後にデータの変更に関する通知は、データの変更通知は、ポーリング間隔によって異なります。 **ヒント:** ポーリングすれば、スループットを向上させる、データの変更が、継続的に行われていると、発生したタイミングととしてそれぞれの変更の通知を受けるたくないシナリオでします。 代わりに、最後のデータの変更通知以降で発生したすべての変更の通知されるようにすた後ポーリング間隔を指定します。|データの変更通知は瞬時に発生します。|  
  
 クエリ通知の詳細については[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]を参照してください[を使用して BizTalk Server での SQL クエリ通知の受信](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)