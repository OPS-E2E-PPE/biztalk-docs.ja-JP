---
title: BizTalk Server を使用して Oracle データベースの変更通知を受け取る |Microsoft ドキュメント
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
ms.openlocfilehash: 69d4b4b3a0b528109caac60ecec3c3614e5d7a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215226"
---
# <a name="receive-oracle-database-change-notifications-using-biztalk-server"></a>BizTalk Server を使用して Oracle データベースの変更通知を受信します。
構成することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからデータベース変更の通知メッセージを受信します。 Oracle データベースがある通知に対して、アダプターを登録に使用する SELECT ステートメントを指定することができます。 通知の登録、SELECT ステートメントの結果セットが変更されたときに通知メッセージを受信します。 アダプターで通知をサポートする方法の詳細については、次を参照してください。[データベースの変更通知の受信、Oracle データベース アダプターの使用に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)です。  
  
 次に、いくつかのシナリオを構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベースから通知を受け取る。  
  
-   アダプターのクライアントは、最後の通知以降、データベース テーブルに加えられた変更についてのみなど「インクリメント」の通知のみを取得します。  
  
-   データベース テーブルには、大量の行が挿入される、アダプターのクライアントは複数を構成できます受信通知の負荷を分散する場所を受信します。  
  
 アダプターのクライアントは、通知メッセージを受信、受信した通知の種類に基づいて特定のタスクを実行できます。 たとえば、このような形で実行される挿入の通知を受信した場合のタスクの 1 つのセットと別の一連のタスクの更新通知を受信した場合、BizTalk オーケストレーションを設計できます。  
  
> [!CAUTION]
>  Oracle データベースとアダプタのクライアント間でネットワーク障害がある場合、通知は送信されませんアダプター クライアントへのネットワークの停止の期間中に、Oracle データベースで行われる変更とそれ以降。 したがって、重要なシナリオの通知操作ではなくポーリング操作を使用する必要があります。  
  
 このセクションのトピックでは、これらの各シナリオのアダプターを構成する方法について説明します。 使用して Oracle データベースから通知の取得を開始する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、特定のバインディング プロパティを指定する必要があります。 通知に関連するバインドのプロパティの詳細については、次を参照してください。[バインドのプロパティの使用](https://msdn.microsoft.com/library/dd788467.aspx)です。 通知メッセージの構造に関する詳細については、次を参照してください。[通知操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)です。  
  
 Oracle データベースから通知を受信するためには、ことを確認してください。  
  
-   10.2 またはそれ以降の Oracle データベースのバージョンに接続するには、アダプターを使用します。 10.2 より前の oracle データベースのバージョンは、通知をサポートしていません。  
  
-   通知の Oracle への接続に使用する資格情報が`change notification`特権です。 この特権は、データベースの変更通知を受け取る必要があります。 これを行うには、管理者特権を使用して Oracle データベースに接続し、SQL のプロンプトで次のコマンドを入力します。  
  
    ```  
    grant change notification to <user name>  
    ```  
  
-   使用して Oracle データベースからデータベースの変更通知を受信する ODP.NET する TCP ポートで決定します。 Windows ファイアウォールの例外リストにそのポートを追加します。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196959](http://go.microsoft.com/fwlink/?LinkID=196959)です。 同じポート番号を指定する必要があります、 **NotificationPort**プロパティをバインドします。 バインディング プロパティの詳細については、次を参照してください。[バインドのプロパティの使用](https://msdn.microsoft.com/library/dd788467.aspx)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Oracle データベース アダプターを使用してデータベースの変更通知を受信するための考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [BizTalk Server を使用して Oracle データベースで特定のタスクを実行する通知メッセージの処理](../../adapters-and-accelerators/adapter-oracle-database/process-notification-messages-to-run-specific-tasks-in-oracle-db-using-biztalk.md)  
  
-   [BizTalk Server を使用して増分値 Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)  
  
-   [複数の受信側の Oracle データベースの変更通知の受信場所](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-on-multiple-receive-locations.md)  
  
-   [後に Oracle データベースの変更通知の受信、受信場所の内訳](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-after-a-receive-location-breakdown.md)  
  
## <a name="see-also"></a>参照  
[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)