---
title: SQL アダプターを使用して SQL Server でのポーリング |Microsoft Docs
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
ms.openlocfilehash: 73bb47bfd631576fe992ef072eee8ff3ff5ba5bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967131"
---
# <a name="polling-in-sql-server-using-the-sql-adapter"></a>SQL アダプターを使用して SQL Server でのポーリング
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] SQL Server データベースからデータ変更メッセージを受信アダプターのクライアントを有効にします。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 「ポーリング ベース」のメッセージの受信をサポート、アダプターが (SELECT ステートメントまたはストアド プロシージャ) は、指定された SQL ステートメントを実行する場合を取得または、データを更新し、一定の間隔でアダプター クライアントに結果を提供します。時間です。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリングの次の操作を公開します。  
  
- **ポーリング**: SQL Server テーブルまたはビューの定期的なデータ変更メッセージを受信することができます。 メッセージがない厳密に型指定します。  
  
- **TypedPolling**: SQL Server データベースから厳密に型指定されたメッセージを受信することができます。 ポーリング メッセージ内の要素を他の任意のスキーマにマップする場合は、この操作を使用する必要があります。  
  
- **XmlPolling**します。 SELECT ステートメントまたはストアド プロシージャを FOR XML 句を使用して、XML メッセージとしてデータを返すを使用できます。 この操作は、XML メッセージとしてポーリング メッセージを返します。  
  
   FOR XML 句の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402)します。  
  
  ポーリングの詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[を使用して BizTalk Server によって SQL Server からのデータ変更メッセージの受信のポーリングに基づいた](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)します。  
  
## <a name="polling"></a>ポーリング  
 使用して一般的なポーリング操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次が含まれます。  
  
1. アダプターのクライアントを指定する必要があります`Polling`の受信の操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
2. アダプター クライアントの SQL ステートメントを指定する必要があります、 **PolledDataAvailableStatement**ポーリングに使用できるデータがあるかどうかを決定するプロパティをバインドします。 このステートメントを実行で返される最初の結果の最初の行の最初の列には、整数値が含まれています。 ポーリングに使用できるデータがない、戻り値は 0 (ゼロ) です。 データが使用可能な場合、戻り値は 0 より大きいです。  
  
3. アダプター クライアントのポーリング間隔を指定する必要があります、 **PollingIntervalInSeconds**間隔を定義するプロパティのバインド内のステートメント、 **PolledDataAvailableStatement**バインドプロパティが実行されます。 ポーリング間隔の最後に、ポーリング済みデータの使用可能なステートメントを実行して、結果セットが返されます。  
  
4. アダプター クライアントのポーリング SQL ステートメント (SELECT ステートメントまたはストアド プロシージャ) を指定する必要があります、 **PollingStatement**プロパティをバインドします。 ポーリングに使用できるデータがある場合 (によって決定されます、 **PolledDataAvailableStatement**プロパティのバインド)、アダプターを取得し、(該当する場合) を更新するポーリング ステートメントを実行する SQL Server データベース内のデータ。 ときに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]併用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、メッセージを送信する、同じトランザクションを使用しても[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
5. アダプターのクライアントが使用できる、 **PollWhileDataFound**ポーリング間隔を無視し、継続的に使用可能な場合と、データをポーリングするプロパティをバインドします。  
  
6. ポーリング ステートメントを実行した結果として返される結果セットは、受信メッセージとしてアダプター クライアントに送信されます。  
  
> [!NOTE]
>  XmlPolling 操作には、ポーリング操作と同じ手順が含まれます。  
  
## <a name="strongly-typed-polling"></a>厳密に型指定されたポーリング  
 使用して厳密に型指定されたポーリングの一般的な操作、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次が含まれます。  
  
1. アダプターのクライアントを指定する必要があります`TypedPolling`の受信の操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は`Polling`します。  
  
2. アダプターのクライアントは、接続 URI の一部として受信 ID を指定する必要があります。 受信 ID では、任意の文字列を使用することし、名前空間の競合を防ぐために、TypedPolling 操作の標準名前空間に追加されます。  
  
3. 残りの手順では、2 ~ 6 の前のセクションで説明されているポーリング操作に記載の手順と同じです。  
  
   ポーリングと厳密に型指定されたポーリングに関連するバインドのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
> [!NOTE]
>  複数の結果セットは、ポーリング ステートメントを実行した結果として返されることができます。 結果セットに行が含まれない場合は、アダプターのクライアントにメッセージが送信されません。  
  
 次の図でポーリング ワークフローに関する情報を提供する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 ポーリング ワークフローの 2 つのシナリオを示します。  
  
1. ときの値、 **PollWhileDataFound**が"False"(既定の設定) に設定します。  
  
2. ときの値、 **PollWhileDataFound** "は True"に設定されている。  
  
   ![ポーリング ワークフロー &#40;PollWhileDataFound &#61; False&#41;](../../adapters-and-accelerators/adapter-sql/media/15598c14-3a62-4b8d-90bf-84e004a386db.gif "15598c14-3a62-4b8d-90bf-84e004a386db") ![ポーリング ワークフロー &#40;PollWhileDataFound &#61; &#41; ] (../../adapters-and-accelerators/adapter-sql/media/c20535be-ea45-4456-8b62-4d4585cb1d8c.gif "c20535be-ea45-4456-8b62-4d4585cb1d8c")  
  
## <a name="differences-between-polling-and-query-notification"></a>ポーリングとクエリ通知の違い  
 ポーリングとクエリ通知は、両方の受信操作で、SQL Server データベースのデータの変更について、アダプターをクライアントに通知、ただし、次の表は、いくつか 2 つの違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|ポーリング|クエリ通知|  
|-------------|------------------------|  
|ポーリングは、アダプターによって開始されます。 アダプターは、データのポーリングに使用できるとポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証するステートメントを実行します。|クエリ通知は、SQL Server によって開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セット内の変更がある場合は、通知を開始するように指示します。|  
|ポーリング ステートメントを使用して、読み取りまたは SQL Server データベース テーブル内のデータを更新することができます。|クエリ通知のステートメントを使用すると、SQL Server データベース テーブルにデータを読み取るだけです。|  
|ポーリングには、実際のデータが変更されたことについて通知されます。|クエリ通知は、Insert などのデータの変更の種類についてのみ通知は、更新、および削除します。|  
|データの変更通知が、ポーリング間隔に依存し、アダプター クライアントは、ポーリング間隔の最後に、データの変更について通知されます。 **ヒント:** ポーリングが継続的に、データの変更が発生したありと設定されるタイミングとしては、各変更の通知しないシナリオでスループットを向上を提供します。 代わりに後の最後のデータの変更の通知以降に発生したすべての変更を通知するポーリング間隔を指定します。|データの変更通知は瞬時です。|  
  
 クエリ通知の詳細については[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]を参照してください[を使用して BizTalk Server によって SQL クエリ通知の受信](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)