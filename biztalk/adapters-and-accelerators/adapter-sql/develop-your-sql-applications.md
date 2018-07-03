---
title: BizTalk Server で、SQL アプリケーションの開発 |Microsoft Docs
description: WCF を使用して SQL アダプターのアプリケーションを作成または BizTalk Server と BizTalk アダプター パック (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac4b5b0-2980-4784-a081-e795654292ed
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b003010ae8cb9394dd956a97bd3e05ef855d3e73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978459"
---
# <a name="develop-your-sql-applications"></a>SQL アプリケーションを開発します。

## <a name="overview"></a>概要
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]バインドします。 クライアント アプリケーションが使用できる、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のアイテムの操作を呼び出します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]消費されることができます。  
  
- 物理ポートのバインドを使用する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。  
  
- クライアント プロキシのインスタンスでメソッドの呼び出し。  
  
- としてホストされる WCF サービスを使用します。  
  
- によって、WCF チャネル モデルを使用するコードでのチャネル インスタンス経由で SOAP メッセージを送信します。  

## <a name="biztalk-vs-wcf-service-vs-wcf-channel"></a>BizTalk と WCF サービスと WCF チャネル    
 次の表では:  
  
- SQL Server で実行できるさまざまな操作の一覧を使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- 選択した方法を使用して、タスクの実行に関する情報を格納しているトピックへのリンクを提供します ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF サービス モデル、WCF チャネル モデル)。  
  
|タスク|BizTalk Server|WCF サービス モデル|WCF チャネル モデル|  
|----------|--------------------|-----------------------|-----------------------|  
|基本的な Insert、Update、Delete、およびテーブルおよびビューに対する Select 操作を実行します。|[挿入、更新、削除、または SQL アダプターを使用した BizTalk Server を使用して操作を選択します。](insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)|[挿入、更新、削除、またはインターフェイス テーブルと、WCF サービス モデルを使用してビューで操作を選択します。](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)|[WCF チャネル モデルを使用して SQL テーブルで挿入操作を実行します。](run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model.md)|  
|テーブルと大きなデータのビューに対する操作の入力列<br /><br /> (また、アダプターを使用して FILESTREAM 操作に関する情報を含む)|[テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューに対する操作](supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)|[WCF サービス モデルを使用して SQL に大規模なデータ型を持つテーブルとビューで操作を実行します。](read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)|-|  
|ストアド プロシージャの実行|[BizTalk Server を使用して SQL Server でのストアド プロシージャを実行します。](execute-stored-procedures-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す](invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)|-|  
|BizTalk オーケストレーションを使用せず 1 つのパラメーターを使用したストアド プロシージャを実行します。|[BizTalk Server を使用して SQL Server での XML パラメーターを 1 つのストアド プロシージャを実行します。](execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)|-|-|  
|定義での FOR XML 句を含むストアド プロシージャの実行|[BizTalk Server を使用して SQL Server での FOR XML 句を含むストアド プロシージャを実行します。](execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)|-|-|  
|SQL Server での複合操作を実行します。|[BizTalk Server を使用して SQL Server での複合操作を実行します。](run-composite-operations-on-sql-server-using-biztalk-server.md)|-|-|  
|SQL Server のスカラー関数の呼び出し|[BizTalk Server を使用して SQL Server のスカラー関数を呼び出す](invoke-scalar-functions-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す](invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|SQL Server でのテーブル値関数の呼び出し|[BizTalk Server を使用して SQL Server でのテーブル値関数を呼び出す](invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す](invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)|-|  
|実行する**ExecuteReader**、 **ExecuteScalar**、または**ExecuteNonQuery**操作|[ExecuteReader、executescalar、ExecuteNonQuery 操作では、BizTalk Server を使用した SQL](executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)|[WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作](executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)|-|  
|データの変更のポーリングに基づいたメッセージの受信|[BizTalk Server と SQL アダプタを使用して SQL Server をポーリング](poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)|[SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用](poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)|[WCF チャネル モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。](receive-polling-based-data-changed-messages-from-sql-server-using-a-wcf-channel.md)|  
|SQL Server の通知の受信|[BizTalk Server を使用して SQL クエリ通知を受け取る](receive-sql-query-notifications-using-biztalk-server.md)|[WCF サービス モデルを使用して SQL のクエリ通知を受信します。](receive-query-notifications-from-sql-using-the-wcf-service-model.md)|-|  

## <a name="next-steps"></a>次のステップ  
 このセクションのトピックでは提供情報、手順、および例を使用するアプリケーションの開発に役立つ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]両方で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].NET ソリューションのプログラミングとします。 

- [SQL Server への接続を作成する](create-a-connection-to-sql-server.md)
- [Visual Studio で SQL Server 操作のメタデータを取得する](get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)
- [メタデータ ノード ID](metadata-node-ids2.md)
- [バインド プロパティの操作](read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)
- [前提条件: MSDTC を構成する](configure-msdtc-on-sql-server-and-adapter-client.md)
- [SQL アダプターを使用して BizTalk アプリケーションを開発する](develop-biztalk-applications-using-the-sql-adapter.md)
- [WCF サービス モデルを使用してアプリケーションを開発する](develop-sql-applications-using-the-wcf-service-model.md)
- [WCF チャネル モデルを使用してアプリケーションを開発する](develop-sql-applications-using-the-wcf-channel-model.md)
- [サンプル](samples-for-the-sql-adapter.md)
- [トランザクション分離レベルとトランザクション タイムアウトを構成する](configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)
  
