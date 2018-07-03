---
title: BizTalk Server を使用して Oracle データベースの変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495a29bc-72f6-4140-8160-0b917d935503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8bd67791e56d941d58cb0b221bf7ad63bb3778f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985043"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースの変更通知を受信します。
構成することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからデータベース変更通知のメッセージを受信します。 アダプターが Oracle データベースを使用した通知の登録を使用する SELECT ステートメントを指定することができます。 登録通知の場合、SELECT ステートメントの結果セットが変更されたときに通知メッセージを受信します。 アダプターが通知をサポートする方法の詳細については、次を参照してください。[データベース変更通知の受信、Oracle データベース アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)します。  
  
 構成することがいくつかのシナリオを次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースから通知を受け取る。  
  
- アダプター クライアントの最後の通知以降、データベース テーブルに加えられたこれらの変更だけなど「インクリメント」の通知のみを取得します。  
  
- アダプター クライアントが複数を構成する場合は、データベース テーブルに多数の行を挿入して、受信負荷分散通知を受信する場所。  
  
  アダプターのクライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。 たとえばが実行される挿入の通知を受信した場合、タスクの 1 つのセットと別の一連のタスク、更新通知を受信した場合は、このような方法で、BizTalk オーケストレーションを設計できます。  
  
> [!CAUTION]
>  Oracle データベースとアダプター クライアントの間のネットワークの停止がある場合、通知は送信されませんアダプター クライアントのネットワークの停止の期間中に Oracle データベースで行われた変更で、その後です。 したがって、重要なシナリオの通知の操作ではなく、ポーリング操作を使用する必要があります。  
  
 このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法について説明します。 使用して Oracle データベースからの通知の取得を開始する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、特定のバインド プロパティを指定する必要があります。 通知に関連するバインド プロパティの詳細については、次を参照してください。[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。 通知メッセージの構造に関する詳細については、次を参照してください。[通知操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)します。  
  
 Oracle データベースから通知を受信することを確認します。  
  
-   10.2 以降の Oracle データベースのバージョンに接続するには、アダプターを使用します。 10.2 より前の oracle データベースのバージョンでは、通知はサポートされません。  
  
-   通知の Oracle への接続に使用する資格情報が`change notification`特権。 この特権は、データベース変更通知を受け取る必要があります。 これを行うには、管理者特権を使用して Oracle データベースへの接続し、SQL プロンプトで次のコマンドを入力します。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   Oracle データベースからデータベース変更通知を受信するために使用する ODP.NET する TCP ポートで決定します。 Windows ファイアウォールの例外リストには、そのポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)します。 同じポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。[バインドのプロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターを使用して、データベース変更通知を受信するための考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [BizTalk Server を使用して Oracle データベースで特定のタスクを実行する通知メッセージの処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [段階的に BizTalk Server を使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [複数の受信側の Oracle データベースの変更通知の受信場所](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [後の Oracle データベース変更通知を受信する受信場所のブレーク ダウン](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)