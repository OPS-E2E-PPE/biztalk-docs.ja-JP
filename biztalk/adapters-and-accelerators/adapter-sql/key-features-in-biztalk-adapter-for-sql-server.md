---
title: SQL Server の重要な機能によって BizTalk Adapter |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6beab8d-c2c4-4add-860c-054b9aed8d70
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af3177e3004c81d368eab8738a201e90c95d1b69
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967824"
---
# <a name="key-features-in-biztalk-adapter-for-sql-server"></a>BizTalk Adapter for SQL Server の主要な機能
このセクションでは、機能を一覧表示[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。  
  
> [!NOTE]
>  このトピックの内容が以前のバージョンから使用された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ヘルプします。  
  
## <a name="features-in-the-sql-adapter"></a>SQL アダプタの機能  
 以前のリリースで導入された機能は次のとおり、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
### <a name="technology-related-features"></a>テクノロジに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|Windows Communication Foundation (WCF) の使用|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の上に構築された、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ([!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)])。 さらに、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF に基づいて構築されます。 アダプターは、アダプターのクライアントへの WCF チャネルとして公開されます。 これにより、接続、メタデータ交換、および外部システムとビジネス データを交換します。|  
|WCF チャネル モデルと WCF サービス モデルのサポート|モデルでは、WCF チャネル、アダプターのクライアントが使用できる、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]直接 XML メッセージを送受信しています。 モデルでは、WCF サービス、アダプターのクライアント クラスを生成できます .NET プロキシから、Web サービス記述言語 (WSDL) を使用して取得した、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。|  
|64 ビット プラットフォームのサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は 64 ビット プラットフォームで利用できるようになりました。|  
  
### <a name="metadata-related-features"></a>メタデータに関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|参照、検索、およびメタデータの取得|アダプターのクライアントでは、参照でき、バッチ サイズを指定することによって、バッチでメタデータを検索することができます。 この機能は、アダプターとではなくアダプター サービスの使用する BizTalk プロジェクト アドインのプログラミング場合にのみ使用します。 メタデータの検索は、テーブル、ビュー、プロシージャ、スカラー関数、およびテーブル値関数のレベルでサポートされます。 検索文字列は、SQL ステートメント内で直接使用されます。|  
|異なるデータベースで同じ名前を持つ成果物を呼び出すためのサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、名前と、一部のスキーマの場合、オブジェクト名のみが含まれている XML スキーマ定義 (XSD) ファイルの名前空間。 ただし、アプリケーションは、異なるデータベースでメタデータの異なる同じ名前を持つ成果物の操作を実行する必要がある場合、生成されたメタデータは競合します。 メタデータを区別する唯一の方法では、XSD 名前空間で、データベース名を使用します。<br /><br /> 現在のバージョン、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] XSD 名前空間内の値を設定してデータベース名を指定することができます、 **UseDatabaseNameInXsdNamespace**バインディング プロパティを TRUE に設定します。 バインディング プロパティの既定値は、XSD 名前空間にはデータベース名が含まれていないことを意味する false です。 詳細については、 **UseDatabaseNameInXsdNamespace**バインディング プロパティを参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。|  
  
### <a name="performance-related-features"></a>パフォーマンス関連の機能  
  
|機能|解説|  
|-------------|-------------|  
|パフォーマンス カウンターのサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SQL アダプターで使用するパフォーマンス カウンター](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)です。|  
  
### <a name="operations-related-features"></a>操作に関連する機能  
  
|機能|解説|  
|-------------|-------------|  
|SQL Server 2005 および SQL Server 2008 のデータ型のサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で導入された次のデータ型をサポートしています。<br /><br /> -   **SQL Server 2005**: XML、varchar (max)、および varbinary (max)。<br />-   **SQL Server 2008**: Date、Time、Datetimeoffset、Datetime2、Hierarchyid、Geography、Geometry、および FILESTREAM です。|  
|ユーザー定義型 (Udt) のサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]テーブルと Udt を含むビューで操作の実行をサポートしています。 Udt のサポートについては、次を参照してください。[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)です。|  
|Transact SQL と CLR を実行するためのサポートはストアド プロシージャと関数|アダプターのクライアントには、Transact SQL と CLR を実行できます。<br /><br /> の SQL Server データベース内ストアド プロシージャはします。<br />スカラーおよびテーブル値関数の SQL Server データベース。<br /><br /> 詳細については、次を参照してください。[アダプターを使用して実行する操作ができますか。](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)です。|  
|FOR XML 句の有無のストアド プロシージャを実行するためのサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]または FOR XML 句を使用せずに、SELECT ステートメントがあるストアド プロシージャを実行することができます。 アダプターの以前のバージョンでは、SELECT ステートメントで FOR XML 句をいたストアド プロシージャのみをサポートします。 ストアド プロシージャの実行方法の詳細については、次を参照してください。 [SQL アダプタを使用して SQL Server でストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-the-sql-adapter.md)です。|  
|ラージ オブジェクトのストリーミングをサポートします。|アダプターのクライアントは、大きなサイズの文字とバイナリ型のフィールド セットを使用して SQL Server データベースにストリーム配信できます\<列名\>型 varchar (max)、nvarchar (max) または varbinary (max) の列の名前を < column_name > がここでは、操作. セット\<列名\>操作でを挿入または SQL Server 2008 データベース内の FILESTREAM データを更新することもできます。 詳細については、次を参照してください。[テーブルおよびビューを含む大きなデータ型を SQL アダプターを使用して操作を](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)です。 **注:** 文字と SQL Server のテーブルとビューのバイナリ型のフィールドを読み取り、アダプターのクライアントが選択操作を使用します。|  
|クエリ通知のサポート|アダプターのクライアントは、トリガーを起動する SELECT ステートメントまたはストアド プロシージャに基づいて SQL Server からクエリ通知を受信できます。 としてアダプター クライアントと、結果セットの SELECT ステートメントまたはストアド プロシージャの変更時に、SQL Server で通知が送信されます。 クエリ通知の詳細については、次を参照してください。[クエリ通知の受信 BizTalk Server を使用して](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)です。|  
|任意の SQL ステートメントを実行するためのサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作を使用して任意の SQL ステートメントを実行するアダプターのクライアントを有効にします。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。|  
|複合操作のサポート|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントが、SQL Server データベースでの複合操作を実行できるようにします。 複合操作は、次の操作、および任意の順序で任意の数を含めることができます。<br /><br /> -Insert、Update、および Delete 操作で、テーブルおよびビュー。<br />-アダプターでの操作として表示されたストアド プロシージャです。<br /><br /> 複合操作の詳細については、次を参照してください。[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)です。|  
|強化されたポーリング|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]他の 2 つの種類のポーリングのようになりました: **TypedPolling**と**XmlPolling**です。 これらのポーリングの種類については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。|  
|複数のスキーマの成果物の操作を実行するためのサポート|別に既定のスキーマ (dbo) では、アダプターのクライアント操作も実行できます成果物に SQL Server データベースの他のスキーマでユーザーの資格情報を使用して接続するために使用する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server が、これらのスキーマへのアクセスデータベースです。 SQL Server データベースのスキーマについては、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148)です。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)