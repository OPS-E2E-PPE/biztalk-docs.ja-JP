---
title: BizTalk Server を使用して SQL クエリ通知を受け取る |Microsoft ドキュメント
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
ms.openlocfilehash: 1632bde50a0daf9df22b9c1cfb7aaca8d59fbce7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223818"
---
# <a name="receive-sql-query-notifications-using-biztalk-server"></a>BizTalk Server を使用して SQL クエリ通知を受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のテーブルまたはビューの通知メッセージを受信します。 SQL Server 通知を登録するアダプターを使用する SQL ステートメントを指定することができます。 通知のステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを指定できます。 クエリ通知の詳細についてを参照してください「を使用してクエリ通知」 [http://go.microsoft.com/fwlink/?LinkId=122159](http://go.microsoft.com/fwlink/?LinkId=122159)です。 クエリ通知のために使用するクエリについてを参照してください「を作成するクエリ通知の」 [http://go.microsoft.com/fwlink/?LinkId=122160](http://go.microsoft.com/fwlink/?LinkId=122160)です。  
  
 SQL Server からクエリ通知の受信は、いくつかの重要な違いと、SQL Server のポーリングに似ています。 相違点の一覧で、次を参照してください。[に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)です。  
  
 次に、いくつかのシナリオを構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SQL Server から通知を受け取る。  
  
-   アダプターのクライアントは、最後の通知以降、データベース テーブルに加えられた変更についてのみなど「インクリメント」の通知のみを取得します。  
  
-   データベース テーブルには、多くの行が挿入される、アダプターのクライアントは複数を構成できます受信通知の負荷を分散する場所を受信します。  
  
-   アダプターのクライアントが通知を受信、受信場所がダウンした場合、アダプターのクライアントは、通知が受信されるとすぐに、受信場所をもう一度アダプターを構成できます。 クライアントは、可能性がありますが挿入、更新、または削除された受信場所がダウンしたときにレコードを処理するアプリケーションのロジックを実装する必要がありますもします。  
  
 アダプターのクライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。 たとえば、このような形で実行される挿入の通知を受信した場合のタスクの 1 つのセットと別の一連のタスクの更新通知を受信した場合、BizTalk オーケストレーションを設計できます。  
  
 このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法に関する情報を提供します。 使用して SQL サーバーからの通知の取得を開始する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、特定のバインディング プロパティを指定する必要があります。 アダプターがメッセージの受信をサポートする方法の詳細については、次を参照してください。[に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)です。 通知に関連するバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 通知メッセージの構造に関する詳細については、次を参照してください。[クエリ通知のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)です。  
  
 また、SQL Server クエリ通知を有効にに対して、次のタスクを実行する必要があります。  
  
-   SQL Server データベースの Service Broker を有効にする必要があります。  
  
-   アダプターのクライアントが通知を要求するコマンドを実行するために必要な権限を持つことを確認する必要があります。  
  
 これらのタスクの詳細についてを参照してください「クエリ通知を有効にする」 [http://go.microsoft.com/fwlink/?LinkID=122323](http://go.microsoft.com/fwlink/?LinkID=122323)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [に関する考慮事項を受け取るクエリ通知を使用して、SQL アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)  
  
-   [BizTalk Server を使用して SQL の特定のタスクを完了する通知メッセージの処理](../../adapters-and-accelerators/adapter-sql/process-notification-messages-to-complete-specific-tasks-in-sql-using-biztalk.md)  
  
-   [BizTalk Server を使用して SQL からの受信通知の差分クエリ](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)  
  
-   [クエリ通知の複数受信場所の BizTalk Server を使用して SQL 送受信します。](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-on-receive-locations-from-sql-server-using-biztalk.md)  
  
-   [BizTalk Server を使用して SQL のクエリ通知した後、受信場所の内訳が表示されます。](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-after-a-sql-receive-location-stops-in-biztalk.md)  
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)