---
title: "参照、検索、および SQL Server のメタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 368dd5ca-456c-4cae-9e85-bcf504c4e7ed
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abb42ff1cae700077c44c391a1112c7309048c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-sql-server-metadata"></a>参照、検索、および SQL Server のメタデータの取得
メタデータを[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]SQL Server データベースからのサーフェスがアダプターを使用して、SQL Server データベースと通信するためのメッセージの構造について説明します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 WCF は、クライアントが、SQL Server データベースからメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   によって提供される IMetadataRetrievalContract、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]をサポートするメタデータ参照とアダプターの機能を検索します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェス SQL Server データベースの成果物とアダプターのクライアントが呼び出すことのできる該当する操作。 アダプターでは、SQL Server データベースで特定の操作を実行するために使用できます (ExecuteNonQuery、ExecuteReader、ExecuteScalar など) の操作も明らかです。 このトピックの後半では、これらの操作について説明します。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]現在接続しているユーザー アクセス権を持つ SQL Server データベース内のすべてのスキーマ内のアイテムを表示します。 つまり、こととは別に既定のスキーマ (dbo) では、アダプターのクライアント操作も実行できます成果物に SQL Server データベースの他のスキーマでユーザーの資格情報を使用して接続するために使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]でこれらのスキーマにアクセスします。SQL Server データベースです。 SQL Server データベースのスキーマについては、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148)です。  
  
 アダプターのクライアントを使用して、参照、検索、およびでメタデータを取得することができます。  
  
-   Visual Studio で BizTalk プロジェクトを作成します。  
  
-   WCF サービス モデルを使用します。  
  
-   WCF チャネル モデルを使用します。  
  
 使用する必要があります、BizTalk プロジェクトを使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を SQL Server データベースで実行する操作のメタデータを生成します。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] SQL Server データベースで操作を実行するためのプロキシ クラスを生成します。 閲覧、検索、およびを使用してメタデータの取得の詳細については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントがデータベース テーブル、ビュー、ストアド プロシージャ、および SQL Server データベースで使用できる関数を参照できるようにします。 メタデータの参照操作の一環として、アダプターは、アダプターでサポートされている一部のカスタム操作を含む、SQL Server データベースで実行できる操作も明らかです。 これらの操作はから利用可能な[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェスを次の操作。  
  
-   テーブル、ビュー、プロシージャ、スカラー関数、およびテーブル値関数では、操作します。 たとえば、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェス Insert、Update、Select、および削除の EMPLOYEE テーブルの操作可能性があります。  
  
-   セット\<列名 > をストリーミング方式で大量のデータ値を書き込むためのアダプターのクライアントを有効にするテーブルとビューを操作します。 設定操作は、これらのテーブルと次のデータ型の列を含むビューのみ返されます。 varchar (max)、nvarchar (max)、または varbinary (max)。 詳細については、次を参照してください。[テーブルとビューを SQL アダプターを使用して大規模なデータ型を含む Operations](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)です。  
  
-   SQL Server の任意の SQL ステートメントを実行するアダプターのクライアントを有効にする ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作です。 これらの操作の詳細については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。  
  
-   SQL Server から受信メッセージを受信するポーリングおよび Notification の操作です。 ポーリング操作については、次を参照してください[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)通知操作に関する情報を参照してください。[受信クエリ通知を使用して、SQL に関する考慮事項。アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)です。  
  
 メタデータを分類する方法の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)です。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、LIKE 演算子と互換性がある SQL Server 検索式を使用して、SQL Server データベースの検索クエリを実行することはできます。 アダプターのクライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、「a _」は、"AB"、"AC"、"AD"と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、「%」は、"A"、"AB"、"ABC"と一致します。|  
|[ ]|-_ および % の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。<br /><br /> 例:<br /><br /> -% [%] % 記号を含むすべての名前に一致します。<br />-[a ~ f] の文字間 'a' と 'f' を持つすべての名前に一致します。<br />-一致する文字を含む 'a', 'b' すべての名前を [abc] と 'c' です。|  
|[^]|範囲が存在している文字のセットを指定します。<br /><br /> 例:<br /><br /> -[^ a ~ f] の文字間 'a' および 'f' が存在しないすべての名前に一致します。<br />-[^ abc] 一致するすべての名前を持たない文字 'a', 'b' および 'c' です。|  
  
> [!IMPORTANT]
>  検索スコープのメタデータは、検索操作を実行するノードのすぐ下にあるレベルに制限されます。 たとえば、スカラー関数を検索するにする必要があります 検索/スカラー関数/[Schema] です。 複数レベルの検索がサポートされていません。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]すべてを含むスキーマの下でメタデータを抽出できますか、データベースのサブセットのオブジェクトそれぞれのオブジェクトと操作のパラメーターを使用します。 アダプターは、XML 内の要素名として、SQL Server データベースからエンティティを表示します。 アンダー スコアが含まれることができるのみ許容の特殊文字であるため、要素名に他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされた`emp_x0024_name`です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [SQL Server の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)