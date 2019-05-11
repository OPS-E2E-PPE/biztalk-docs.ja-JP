---
title: BizTalk server、Oracle データベース アプリケーションの開発 |Microsoft Docs
description: WCF を使用して Oracle DB アプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a685b2-ac17-4949-bc77-001f56450847
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdb80fad3bc0be528a561dbee46a43b656c40c59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376591"
---
# <a name="develop-your-oracle-database-applications"></a>Oracle データベース アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベース アイテムの操作を呼び出します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]消費されることができます。  
  
- 物理ポートのバインドを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- インスタンス上のメソッドを呼び出すことによって、[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]クライアント プロキシ。  
  
- ホストされたとして[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス。  
  
- 使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信することによって、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデル。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk と WCF サービスと WCF チャネル  
 次の表では:  
  
- 使用して Oracle データベースで実行できるさまざまな操作を一覧表示、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- 選択した方法を使用して、タスクの実行に関する情報を格納しているトピックへのリンクを提供します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、または WCF チャネル モデル)。  
  
|タスク|BizTalk Server|WCF サービス モデル|WCF チャネル モデル|  
|----------|--------------------|-----------------------|-----------------------|  
|基本的な Insert、Update、Delete、およびテーブルおよびビューに対する Select 操作|[挿入、更新、削除、または Oracle データベースと BizTalk Server を使用して操作を選択します。](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)|[挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作を選択します。](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)|[WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|LOB データを持つテーブルまたはビューに対する操作|[Oracle データベース内のラージ オブジェクト データ型を持つテーブルに対する操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-object-data-types-in-oracle-database.md)|[WCF サービス モデルを使用して Oracle データベースでの大規模なデータ型を持つテーブルに対する操作を完了します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-large-data-types-in-oracle-db-using-a-wcf-service.md)||  
|関数とストアド プロシージャに対する操作|[関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[関数と WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して Oracle データベースで関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)|  
|オーバー ロードされた関数およびプロシージャの呼び出し|[オーバー ロードされた関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)|[関数と WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)||  
|REF CURSOR のパラメーターの関数およびプロシージャに対する操作|[BizTalk Server を使用して Oracle データベース内の REF CURSOR で関数とプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-ref-cursors-in-oracle-db-using-biztalk-server.md)|[WCF サービス モデルを使用して Oracle データベースでの操作を使用して REF CURSOR の実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)||  
|レコード型で、関数およびプロシージャに対する操作|[BizTalk Server を使用して Oracle データベースでレコードの種類で関数とプロシージャを呼び出す](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)|[WCF サービス モデルを使用して Oracle データベースでの操作を使用してレコードの種類の実行します。](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)||  
|BFILE データ型を持つテーブルとビューに対する操作|[BizTalk Server を使用して Oracle データベースで BFILE データ型を持つテーブルに対する操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-operations-on-tables-with-bfile-data-types-in-oracle-db-using-biztalk.md)|||  
|SQLEXECUTE 操作|[BizTalk Server を使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)|[WCF サービス モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)|[WCF チャネル モデルを使用して Oracle データベースで SQLEXECUTE 操作を実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)|  
|データの変更のポーリングに基づいたメッセージの受信|[BizTalk Server を使用してポーリング Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-biztalk-server.md)|[WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-service.md)|[WCF チャネル モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)|  
|Oracle データベースでの複合操作を実行します。|[BizTalk Server を使用して Oracle データベースでの複合操作の実行します。](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)|||  
|受信側のデータベース変更通知|[BizTalk Server を使用して Oracle データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)|[WCF サービスの Model1 を使用して Oracle データベースの変更通知を受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-the-wcf-service-model1.md)||  
  

  
## <a name="next-steps"></a>次のステップ
 このセクションのトピックでは提供情報、手順、および使用するアプリケーションの開発に役立つ例、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューションをプログラミングします。 
  
-   [Oracle データベースへの接続の作成](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)
  
-   [Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md) 
  
-   [Oracle データベースのバインド プロパティを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)
  
-   [Oracle データベース アダプターのラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)
  
-   [Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信します。](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)
  
-   [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)
  
-   [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)  
  
-   [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)  
  
-   [Oracle データベースからメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)  
  
-   [SharePoint での Oracle データベース アダプターを使用します。](../../adapters-and-accelerators/adapter-oracle-database/use-the-oracle-database-adapter-with-sharepoint.md)
  
-   [アダプター サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)  
  
-   [Oracle データベースとトランザクション分離レベルとトランザクションのタイムアウトを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)

- [Svcutil.exe の使用](use-the-servicemodel-metadata-utility-with-the-oracle-db-adapter-in-biztalk.md)