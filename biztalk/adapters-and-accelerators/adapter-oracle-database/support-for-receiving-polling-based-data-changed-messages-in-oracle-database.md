---
title: Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信するためのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- notifications, polling-based
- post-polling
- POLLINGSTMT
- polling interval
- polling
ms.assetid: 9ff29d3f-ebb1-4d82-9106-150f939cbd9e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8a29901672ba11f3ac48220f7096b2c355fc2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218802"
---
# <a name="support-for-receiving-polling-based-data-changed-messages-in-oracle-database"></a>Oracle データベースでデータ変更のポーリングに基づいたメッセージを受信するためのサポート
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースに格納されたデータへの変更を知らせる Oracle データベースからメッセージを受信するクライアント プログラムを有効にします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターが指定された選択クエリ、ストアド プロシージャ、関数、またはプロシージャまたはパッケージ内の関数を実行する場合、「ポーリング ベース」のメッセージの受信をサポートしていますが、データを取得しでは、通常、クライアントに結果を提供時間間隔。 これを有効にする、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] POLLINGSTMT 操作を公開します。 さらに、すべてのストアド プロシージャ、関数、およびプロシージャおよびパッケージ内の関数は、ポーリングの受信操作として公開されます。  
  
 アダプターは、Oracle データベースをポーリングする 2 つの方法を提供します。  
  
-   **SELECT ステートメントを使用して**です。 テーブルと、Oracle データベースでビューをポーリングする単純な SELECT ステートメントを指定することができます。 アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。  
  
-   **ストアド プロシージャ、関数、プロシージャ、またはパッケージ内で関数を使用して**です。 ストアド プロシージャ、関数、またはプロシージャまたは Oracle データベースをポーリングするパッケージ内で関数を指定することができます。 アダプターは、指定した間隔で要求メッセージを実行し、アダプターのクライアントに結果を返します。  
  
## <a name="polling-operation-workflow"></a>ポーリング操作のワークフロー  
 使用して一般的なポーリング操作、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次が含まれます。  
  
1.  アダプターのクライアントを指定する必要があります**ポーリング**で受信操作として、 **InboundOperationType**プロパティをバインドします。 このバインドのプロパティの既定値は**ポーリング**です。  
  
2.  アダプターのクライアントでの SELECT ステートメントを指定する必要があります、 **PolledDataAvailableStatement**ポーリングの使用可能なデータがあるかどうかを判断するプロパティをバインドします。 このステートメントの実行に、返される結果セットの最初の行の最初の列には、正の整数値が含まれている場合は日付のポーリングに使用できます。 既定では、このバインドのプロパティの値に設定が`Select 1 FROM DUAL`、か、アダプターにかどうかをポーリングするテーブルにデータに関係なく、ポーリングを続ける必要がありますが含まれています。  
  
3.  アダプターのクライアントのポーリング間隔を指定する必要があります、 **PollingInterval**間隔を秒単位で指定されたステートメントを定義するプロパティのバインド、 **PolledDataAvailableStatement**プロパティのバインドが実行されます。 ポーリング間隔の最後に、ポーリングされたデータの使用可能なステートメントが実行され、結果セットが返されます。  
  
4.  SELECT ステートメントまたはストアド プロシージャのアダプターのクライアントを指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
    -   テーブルまたはビューをポーリングする場合は、このバインディングのプロパティで選択クエリを指定する必要があります。  
  
    -   ポーリング ストアド プロシージャ、関数、またはプロシージャまたはパッケージ内で関数を使用する場合は、このバインディングのプロパティで、該当する操作の要求全体メッセージを指定する必要があります。  
  
     内のステートメント、 **PollingStatement**によって決定される、ポーリングに使用できるデータが場合にのみ実行プロパティのバインド、 **PolledDataAvailableStatement**手順 1. でプロパティをバインドします。  
  
5.  アダプターのクライアントがポーリング操作に対してアクションを指定する必要があります、 **PollingAction**プロパティをバインドします。 特定の操作のポーリング アクションは、アダプター サービスのアドインを使用して、操作によって生成されるメタデータから判断されます。  
  
    > [!NOTE]
    >  テーブルをポーリングしてで SELECT ステートメントを使用して表示するか、 **PollingStatement**バインディング プロパティ必要はありませんすべての値を指定する、 **PollingAction**プロパティをバインドします。 既定値、Null の場合、この場合は渡されます。  
  
6.  アダプターのクライアントが使用できる、 **PollWhileDataFound**ポーリング間隔を無視して継続的に使用可能な場合と、データをポーリングするプロパティをバインドします。  
  
    > [!IMPORTANT]
    >  値を設定した場合、 **PollWhileDataFound**バインド プロパティを True に、アダプターのクライアントを継続的にポーリング プロセスで Oracle からのデータがループ内での Oracle データベースへの接続を開いたり閉じたりします。 ODP.NET によって接続が開かれてレートが閉じられている接続よりも大きいため、しばらく待ってから、接続が使い果たされ、例外がスローされます。 回避策としては、ことを確認の値、 **UseOracleConnectionPool**を True に設定されている適切な値に記載されて、 **IncrPoolSize**接続の数を制御するプロパティのバインドアダプターのクライアントが開けます。  
  
7.  アダプターのクライアントは、用、Oracle PL/SQL ブロック、ポーリング後ステートメントを指定できます、 **PostPollStatement**プロパティをバインドします。 指定されたステートメントの後にこのバインドのプロパティで指定されたステートメントが実行される、 **PollingStatement**プロパティのバインドを実行します。  
  
 アダプターがトランザクションでは、ポーリング ステートメントとポーリング後ステートメントをラップし、トランザクションのタイムアウト値が指定された値として設定されて、 **PollingInterval**プロパティをバインドします。 したがって、することが重要には、受信メッセージを処理して、応答の送信に必要な時間より大きいタイムアウト値を指定します。 メッセージが処理または後のポーリング クエリを実行するクライアント プログラムにかかる時間がタイムアウト値を超える場合は、トランザクションがロールバックします。 かかった時間がタイムアウト値より小さい場合は、アダプターはトランザクションをコミットし、次のポーリングを実行する前に、ポーリングの残り時間の「スリープ」です。  
  
 アダプターは、Oracle データベースから空のポーリング応答を抑制します。  
  
## <a name="differences-between-polling-and-notification"></a>ポーリングと通知の相違点  
 ポーリング通知、両方の受信操作とは、Oracle データベースでデータの変更について、アダプターをクライアントに通知を次の表は、2 つの間の違いを示します。 次の相違点を使用すると、要件に応じて、操作を決定できます。  
  
|ポーリング|Notification|  
|-------------|------------------|  
|サポートされているすべての Oracle データベース バージョンのポーリングがサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。|通知は、Oracle データベース バージョン 10.2 に対してのみサポートされているおよびそれ以降です。|  
|一定の間隔でポーリングの使用可能なデータを確認するポーリング間隔を構成するか、または瞬時に、そのデータが使用可能です。 **ヒント:** ポーリングすれば、スループットを向上させる、データの変更が、継続的に行われていると、発生したタイミングととしてそれぞれの変更の通知を受けるたくないシナリオでします。 代わりに、前回の変更通知以降に行われたすべての変更の通知されるようにすた後ポーリング間隔を指定します。|データの変更通知は瞬時では常にします。|  
|ポーリングは、アダプターによって開始されます。 アダプターでは、データのポーリングを使用し、ポーリングの一部のデータがある場合は、ポーリング ステートメントを実行してポーリングを開始するかどうかを検証する SQL ステートメントを実行します。|通知は、Oracle データベースで開始されます。 だけ、アダプターによって発行された通知のステートメントでは、データベース ステートメントの結果セットの変更がある場合に通知を開始するように指示します。 通知は、Oracle データベースの機能です。|  
|ポーリング ステートメントを使用して、読み取るまたは Oracle データベース内のデータを更新することができます。|通知のステートメントを使用すると、Oracle データベースでデータを読み取るだけです。|  
|ポーリングでは、実際のデータが変更されたことについて通知されます。|Insert などのデータ変更の種類のみ通知を通知は、更新、および削除します。|  
  
 詳細については。  
  
-   アダプターは、Oracle データベースからのポーリングに基づいたメッセージの受信をサポートする方法を参照してください。[データ変更のポーリングに基づいたメッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)です。  
  
-   使用して Oracle データベースからのポーリングに基づいたメッセージを受信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しおよび Biztalk Server を使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)です。  
  
-   WCF サービスのモデルを使用して Oracle データベースからのポーリングに基づいたメッセージを受信を参照してください[WCF チャネル モデルを使用して SQL Server からのデータ変更メッセージの受信のポーリングに基づく](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)です。  
  
-   WCF チャネル モデルを使用して Oracle データベースからのポーリングに基づいたメッセージを受信を参照してください[WCF チャネル モデルを使用して SQL Server からのデータ変更メッセージの受信のポーリングに基づく](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)です。  
  
-   メッセージの構造と、ポーリング クエリを実行するための SOAP アクションを参照してください[ポーリング操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)