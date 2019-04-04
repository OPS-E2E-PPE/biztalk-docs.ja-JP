---
title: BizTalk Server を使用して SQL クエリ通知を受け取る |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69444df7-f2ae-4d1a-9b49-817b437517d8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc8174db5193702e512f5f8b01c2a8ecfbeeee5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988891"
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>BizTalk Server を使用して SQL クエリ通知を受け取る
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server テーブルまたはビューの通知メッセージを受信します。 アダプターが SQL Server を使用した通知の登録に使用する SQL ステートメントを指定することができます。 通知のステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。 クエリ通知の詳細についてを参照してください「を使用してクエリ通知」 [ http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159)します。 クエリ通知の使用できるクエリについてを参照してください「を作成するクエリ通知の」 [ http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)します。  
  
 SQL Server からクエリ通知を受信することは、いくつかの主な相違点と、SQL Server をポーリングに似ています。 相違点の一覧で、[に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)を参照してください。  
  
 構成することがいくつかのシナリオを次に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server から通知を受け取る。  
  
- アダプター クライアントの最後の通知以降、データベース テーブルに加えられたこれらの変更だけなど「インクリメント」の通知のみを取得します。  
  
- アダプター クライアントが複数を構成する場合は、データベース テーブルに多数の行を挿入して、受信負荷分散通知を受信する場所。  
  
- アダプター クライアントが通知を受信、受信場所がダウンした場合、アダプターのクライアントは、通知が受信されるとすぐに、受信場所をもう一度アダプターを構成できます。 クライアントでは、する可能性がありますが挿入、更新、または削除された受信場所がダウンしていたときにレコードを処理するには、そのアプリケーション内でまた、ロジックを実装する必要があります。  
  
  アダプターのクライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。 たとえばが実行される挿入の通知を受信した場合、タスクの 1 つのセットと別の一連のタスク、更新通知を受信した場合は、このような方法で、BizTalk オーケストレーションを設計できます。  
  
  このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法に関する情報を提供します。 使用して SQL Server からの通知の取得を開始する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、特定のバインド プロパティを指定する必要があります。 アダプターがメッセージの受信がサポートする方法の詳細については、[に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)を参照してください。 通知に関連するバインド プロパティの詳細については、[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)を参照してください。 通知メッセージの構造の詳細については、[クエリ通知のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)を参照してください。  
  
  クエリ通知を有効にする SQL Server で、次のタスクを実行することも必要があります。  
  
- Service Broker は、SQL Server データベースを有効にする必要があります。  
  
- アダプターのクライアントが通知を要求するためのコマンドを実行するために必要な権限を持っていることを確認する必要があります。  
  
  これらのタスクの詳細についてを参照してください「のクエリ通知を有効にする」 [ http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [BizTalk Server を使用して SQL の特定のタスクを実行するプロセスの通知メッセージ](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [BizTalk Server を使用して SQL から段階的クエリ通知を受け取る](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [BizTalk Server を使用して SQL からのクエリ通知で複数受信場所の受信します。](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [BizTalk Server を使用した SQL でクエリ通知した後、受信場所のブレーク ダウンを受け取る](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)