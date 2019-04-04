---
title: 参照、検索、および SQL Server のメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 368dd5ca-456c-4cae-9e85-bcf504c4e7ed
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37308bf4f5a1d6bedba061337b2352f198354dd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994155"
---
# <a name="browse-search-and-get-sql-server-metadata"></a>参照、検索、および SQL Server のメタデータを取得します。
メタデータを[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]SQL Server データベースからのサーフェスがアダプターを使用して SQL Server データベースと通信するためのメッセージの構造について説明します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
- によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 WCF は、クライアントが SQL Server データベースからメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
- によって提供される IMetadataRetrievalContract、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、閲覧と検索機能を備えたアダプターのメタデータをサポートしています。  
  
  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェス SQL Server データベースの成果物とそれぞれの操作をアダプターのクライアントが呼び出すことができます。 アダプターでは、SQL Server データベースの特定の操作を実行するために使用できます (ExecuteNonQuery、ExecuteReader、executescalar) などの操作も表示されます。 このトピックの後半では、これらの操作について説明します。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を現在接続しているユーザーへのアクセスを持つ SQL Server データベース内のすべてのスキーマ内のアイテムを表示します。 つまり、こととは別に既定のスキーマ (dbo) では、アダプターのクライアント操作も実行できます成果物に、SQL Server データベースの他のスキーマでユーザーの資格情報を使用して接続するために使用される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]これらのスキーマにアクセスします。SQL Server データベース。 SQL Server データベース内のスキーマについては、[ http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148)を参照してください。  
  
 アダプターのクライアントを使用して、参照、検索、および、メタデータを取得することができます。  
  
- Visual Studio での BizTalk プロジェクトの作成  
  
- WCF サービス モデルの使用  
  
- WCF チャネル モデルを使用します。  
  
  使用する必要がある BizTalk プロジェクトを使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SQL Server データベースで実行する操作のメタデータを生成します。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] SQL Server データベースの操作を実行するためのプロキシ クラスを生成します。 参照、検索、およびメタデータを使用した取得の詳細については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントがデータベース テーブル、ビュー、ストアド プロシージャ、および SQL Server データベースで使用できる関数を参照できるようにします。 メタデータの参照操作の一環として、アダプターでは、アダプターでサポートされているいくつかのカスタム操作など、SQL Server データベースで実行できる操作も表示されます。 これらの操作はから利用可能な[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェスの次の操作。  
  
- テーブル、ビュー、プロシージャ、スカラー関数、およびテーブル値関数に対する操作。 たとえば、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サーフェスの Insert、Update、Select、および従業員テーブルに対する削除操作を可能性があります。  
  
- セット\<列名\>アダプター クライアント ストリーミング方式で大きなデータ値を書き込むことができるテーブルおよびビューの操作。 設定操作は、これらのテーブルと、次のデータ型の列を含むビューにのみ返されます。 varchar (max)、nvarchar (max) または varbinary (max)。 詳細については、[テーブルと、SQL アダプターを使用して大規模なデータ型を含むビューで操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)を参照してください。  
  
- SQL Server の任意の SQL ステートメントを実行するアダプターのクライアントを有効にする ExecuteNonQuery、ExecuteReader、executescalar 操作。 これらの操作の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。  
  
- SQL Server から受信メッセージを受信するポーリングと通知の操作です。 ポーリング操作については、次を参照してください[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)通知の操作に関する情報を参照してください。 [SQL 使用クエリ通知の受信に関する考慮事項。アダプター](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)します。  
  
  メタデータの分類方法の詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)を参照してください。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、LIKE 演算子と互換性がある SQL Server 検索式を使用して、SQL Server データベースの検索クエリを実行することができます。 アダプター クライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 つだけの文字と一致します。<br /><br /> たとえば、「a _」は、"AB"、"AC"、"AD"と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、「%」は、"A"、"AB"、"ABC"と一致します。|  
|[ ]|-_ % の特別な意味をエスケープします。<br />-範囲または存在する文字のセットを指定します。<br /><br /> 以下に例を示します。<br /><br /> -[%] % が、"%"記号を含むすべての名前と一致します。<br />-[a ~ f] と 'a' などの文字と 'f' を持つすべての名前に一致します。<br />-[abc] と 'a'、'b' 文字を含むすべての名前を一致して、'c'。|  
|[^]|範囲または存在しない文字のセットを指定します。<br /><br /> 以下に例を示します。<br /><br /> -[^ a ~ f] と 'a' などの文字または 'f' に存在しないすべての名前と一致します。<br />-[^ abc] 一致するすべての名前がない文字 'a '、'b'、'c' とします。|  
  
> [!IMPORTANT]
>  メタデータの検索スコープは、検索操作を実行するノードのすぐ下にあるレベルに限定されます。 たとえば、スカラー関数を検索するにする必要があります 検索/スカラー関数/[Schema] です。 複数レベルの検索がサポートされていません。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]またはデータベースのサブセットがそれぞれのオブジェクトと操作のパラメーターを使用してオブジェクトがすべてを含むスキーマの下でメタデータを抽出することができます。 アダプターは、XML 内の要素名として、SQL Server データベースからエンティティを表示します。 アンダー スコアを含めることができますのみ指定できる特殊文字であるために、要素名でその他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされます`emp_x0024_name`します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [BizTalk Adapter for SQL Server についてください。](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)