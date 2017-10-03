---
title: "BizTalk Server で SQL アプリケーションの開発 |Microsoft ドキュメント"
description: "WCF, を使用して SQL アダプターのアプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fac4b5b0-2980-4784-a081-e795654292ed
caps.latest.revision: "39"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e5be1f01a9d8180dea60f508cba1c4ff7c0964f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-your-sql-applications"></a>SQL アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のアイテムの上操作を呼び出します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消費されることができます。  
  
-   物理ポートのバインディングを介して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   クライアント プロキシのインスタンス上のメソッドの呼び出しです。  
  
-   としてホストされる WCF サービスを使用します。  
  
-   WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk と WCF サービスと WCF チャネル    
 次の表では:  
  
-   SQL Server で実行できるさまざまな操作の一覧を使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   選択した方法を使用するタスクの実行に関する情報を含むトピックへのリンクを示します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービスのモデル、WCF チャネル モデル)。  
  
|タスク|BizTalk Server|WCF サービスのモデル|WCF チャネル モデル|  
|----------|--------------------|-----------------------|-----------------------|  
|基本的な Insert、Update、Delete、およびテーブルおよびビューに対する Select 操作を実行します。|[挿入、更新、削除、または BizTalk Server アダプターを使用して、SQL 操作の選択](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)|[挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[WCF チャネル モデルを使用して SQL でのテーブルに対して挿入操作の実行します。](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)|  
|テーブルと大きなデータのビューに対する操作の種類の列<br /><br /> (も、アダプターを使用して FILESTREAM 操作に関する情報を含む)|[テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューでの操作](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)|[WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行します。](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)|-|  
|ストアド プロシージャの実行|[BizTalk Server を使用して SQL Server でストアド プロシージャを実行します。](execute-stored-procedures-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)|-|  
|BizTalk オーケストレーションを使用せず 1 つのパラメーターを持つストアド プロシージャを実行します。|[BizTalk Server を使用して SQL Server で 1 つの XML パラメーターを持つストアド プロシージャを実行します。](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)|-|-|  
|定義での FOR XML 句を含むストアド プロシージャの実行|[BizTalk Server を使用して SQL Server での FOR XML 句を持つストアド プロシージャを実行します。](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)|-|-|  
|SQL Server で合成の操作の実行|[BizTalk Server を使用して SQL Server での複合操作を実行します。](run-composite-operations-on-sql-server-using-biztalk-server.md)|-|-|  
|SQL Server のスカラー関数の呼び出し|[BizTalk Server を使用して SQL Server のスカラー関数を呼び出す](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|SQL Server でのテーブル値関数の呼び出し|[BizTalk Server を使用して SQL Server でのテーブル値関数を呼び出す](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|実行する**ExecuteReader**、 **ExecuteScalar**、または**ExecuteNonQuery**操作|[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して SQL の ExecuteNonQuery 操作](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)|[WCF サービスのモデルを使用して SQL の ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)|-|  
|データの変更のポーリングに基づくメッセージの受信|[BizTalk Server と SQL アダプタを使用して SQL サーバーにポーリング](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)|[WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)|[WCF チャネル モデルを使用して SQL Server からデータ変更のポーリングに基づいたメッセージを受信します。](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)|  
|SQL Server の通知の受信|[BizTalk Server を使用して SQL クエリ通知を受信します。](receive-sql-query-notifications-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL のクエリ通知を受信します。](receive-query-notifications-from-sql-using-the-wcf-service-model.md)|-|  

## <a name="next-steps"></a>次の手順  
 このセクションのトピックでは提供情報、プロシージャ、および例を使用するアプリケーションを開発するため、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].NET ソリューションのプログラミングとします。 

- [SQL Server への接続を作成します。](create-a-connection-to-sql-server.md)
- [Visual Studio での SQL Server 操作のメタデータを取得します。](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
- [メタデータのノード Id](metadata-node-ids2.md)
- [バインドのプロパティの使用](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
- [MSDTC を構成して前提条件。](configure-msdtc-on-sql-server-and-adapter-client.md)
- [SQL アダプターを使用して BizTalk アプリケーションを開発します。](develop-biztalk-applications-using-the-sql-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発します。](develop-sql-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発します。](develop-sql-applications-using-the-wcf-channel-model.md)
- [サンプル](samples-for-the-sql-adapter.md)
- [トランザクション分離レベルとトランザクションのタイムアウトを構成します。](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
  
