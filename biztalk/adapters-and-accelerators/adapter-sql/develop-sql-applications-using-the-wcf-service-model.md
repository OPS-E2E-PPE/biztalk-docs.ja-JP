---
title: "WCF サービス モデルを使用して SQL アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645b783ad23d79b4f6be177f6d38287e62abab1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL アプリケーションを開発します。
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]WCF チャネル モデルをプログラミングする代わりに、WCF サービス モデルと呼ばれるプログラミング モデルを提供します。  
  
 WCF サービス モデルでは、使い慣れた .NET パラダイムを使用して、チャネル経由で SOAP メッセージを交換するための複雑さを非表示にします。 サービス モデルは、.NET データ構造体に情報をコピーする前に、SOAP メッセージ全体をメモリに読み取るでこの簡素化を実現します。 時間の長いメッセージをメモリに読み込み、ただしが実用的ではない一部のアプリケーションです。 このような場合は、開発者は、WCF チャネル モデルを使用してください。 詳細については、WCF チャネル モデルを使用して、次を参照してください。 [WCF チャネル モデルを使用して SQL の開発アプリケーション](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)です。  
  
 最下位のレベル[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]をクライアントがクライアントとサービスのエンドポイント間で確立されたチャネル経由で SOAP メッセージを交換することで、サービスに対して操作を呼び出す、WCF チャネル モデルを表示します。 WCF チャネル モデルでは、データ型とすると、WCF チャネル アーキテクチャを直接操作できるようにするメソッドを公開します。 WCF チャネル モデルを使うと、直接的な制御を作成する SOAP メッセージの内容および両方方法、アプリケーションを介して、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]それらを使用します。 ただし、チャネル経由で送信する整形式の SOAP メッセージを作成して、返される応答メッセージの検証は、詳細で正確なタスクを指定できます。  
  
 WCF サービス モデルは、発信先サービスに対する操作を呼び出すか、クライアントからの受信操作に、プロキシ クラスを使用します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]するには、操作を呼び出すことができますを WCF サービスとして、SQL Server データベースを公開します。  
  
-   発信先サービスに対する操作の呼び出しに使用するプロキシ クラスには、WCF クライアント クラスが呼び出されます。 このクラスは、厳密に型指定されたパラメーターを使用して .NET メソッドとして、サービスによって公開される操作をモデル化します。 WCF サービス モデルを使用すると、によって公開される操作を呼び出すことができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF クライアント上の .NET メソッドとして。 WCF クライアントの詳細については、次を参照してください。 [WCF クライアントの概要](https://msdn.microsoft.com/library/ms735103.aspx)です。
  
 WCF クライアント クラスを生成する、次のツールのいずれかを使用して、関連付けられているサービス メタデータからヘルパー コードを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を公開します。  
  
-   **ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)**WCF に付属しています。  
  
-   **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**に付属している[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と統合し、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]エクスペリエンスをデザインします。 このツールは、強力な参照および検索、アダプターが公開される操作で機能を提供する標準的な Microsoft Windows のインターフェイスを表示します。 WCF クライアント アプリケーションを作成する方法に関する詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
     このセクションのトピックでは、情報、プロシージャ、および例を作成してモデルを使用して、WCF サービスを使用してアプリケーションを開発する際に役立ちますが含まれて、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [メタデータと、SQL アダプターで WCF サービス モデル](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [SQL アダプタのクライアントのバインディングを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して SQL の大規模なデータ型を持つテーブルとビューの操作を実行します。](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [WCF サービス モデルを使用して SQL ストアド プロシージャを呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [WCF サービスのモデルを使用して SQL の ExecuteReader、ExecuteScalar、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [WCF サービス モデルを使用して SQL のクエリ通知を受信します。](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)