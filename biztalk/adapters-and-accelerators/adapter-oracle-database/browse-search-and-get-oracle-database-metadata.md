---
title: "参照、検索、および Oracle データベースのメタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MetadataExchange
- metadata, searching
- metadata, browsing
- POLLINGSTMT
- metadata, retrieving
- IMetadataRetrievalContract
- SQLEXECUTE
ms.assetid: 828d5a8e-f0a3-47b4-8298-5571cff64b52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765663d51fa1bab4f700aa3aff726085e5464716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-oracle-database-metadata"></a>参照、検索、および Oracle データベースのメタデータの取得
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターを使用して Oracle データベースと通信するためのメッセージ構造を記述する Oracle データベースからのサーフェス メタデータ。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 WCF は、クライアントが Oracle データベースからメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   によって提供される IMetadataRetrievalContract、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]をサポートするメタデータ参照とアダプターの機能を検索します。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス Oracle のデータベース成果物とアダプターのクライアントが呼び出すことのできる該当する操作。 アダプターでは、Oracle データベースで特定の操作を実行するために使用する、SQLEXECUTE、POLLINGSTMT、および通知の操作も明らかです。 このトピックの後半では、これらの操作について説明します。  
  
 アダプターのクライアントは、参照、検索、および WCF チャネル モデルを使用して、モデルを使用して、WCF サービス、または Visual Studio で BizTalk プロジェクトを作成することで、メタデータを取得できます。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Oracle データベースで操作を実行するプロキシ クラスを生成します。 BizTalk プロジェクトを使用する場合は、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle データベースで実行する操作のメタデータを生成します。 閲覧、検索、およびを使用してメタデータの取得の詳細については[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントがデータベース テーブル、テーブルのビュー、ストアド プロシージャ、関数、および Oracle データベースで使用可能なパッケージを参照できるようにします。 メタデータの参照操作の一環として、アダプターは、アダプターでサポートされている一部のカスタム操作を含む、Oracle データベースで実行できる操作も明らかです。 これらの操作はから利用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスを次の操作。  
  
 **送信操作**  
  
 基になる Oracle データベースでのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。  
  
-   **テーブル**: スキーマ内のすべてのテーブルの一覧です。 Insert、Select、Update、表示するテーブルを選択し、操作を削除します。  
  
-   **プロシージャ**: 操作として公開されるスキーマ内のストアド プロシージャの一覧です。  
  
-   **関数**: 操作として公開されているスキーマ内の関数の一覧です。  
  
-   **パッケージ**: スキーマ内のすべてのパッケージの一覧です。 手順と操作として公開されている、パッケージ内の関数を表示するパッケージを選択します。  
  
-   **ビュー**: スキーマ内のすべてのビューの一覧です。 Insert、Select、Update、表示するビューを選択し、操作を削除します。  
  
 別に、この、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]も公開、 **SQLEXECUTE**アダプター クライアントが Oracle データベースで任意の汎用的なデータ操作言語 (DML) またはストアド プロシージャを実行できるように、送信操作です。 SQLEXECUTE 操作は、ルート ノード (/) を選択するときに使用できます。 SQLEXECUTE の出力はデータ リーダー (ジェネリック レコードの配列として出力) の配列であることに注意してください。 その結果、out パラメーターの任意の単純されません現さ SQLEXECUTE 操作を使用します。 操作の詳細については、次を参照してください。 [Oracle データベースで SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)です。  
  
 **受信操作**  
  
 基になる Oracle データベースでのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。  
  
-   **プロシージャ**: ポーリングの操作として公開されるスキーマ内のストアド プロシージャの一覧です。  
  
-   **関数**: ポーリングの操作として公開されるスキーマ内の関数の一覧です。  
  
-   **パッケージ**: スキーマ内のパッケージの一覧です。 パッケージ化したプロシージャとポーリング操作として公開されている関数を表示するパッケージを選択します。  
  
 これとは別、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]も公開、 **POLLINGSTMT**と**通知**受信操作します。 POLLINGSTMT 操作では、ポーリング機構、アダプターによってサポートされるクエリに基づいている Oracle データベースからの受信データを取得するアダプターのクライアントを使用できます。 通知操作により、SELECT ステートメントをデータベースに対する通知のクエリとして登録するクライアントはアダプターとアダプターのクライアントとしてを使用して、SELECT ステートメントの変更の結果セットは、データベースが通知を送信します。 POLLINGSTMT および Notification の操作は、ルート ノード (/) を選択するときに使用可能です。 操作に関する詳細については、次を参照してください[データ変更のポーリングの受信に基づいたメッセージのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md).md) および[受信チェンジャー通知を使用してデータベース、Oracle Database アダプターに関する考慮事項。](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
 メタデータを分類する方法の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)です。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、LIKE 演算子と互換性がある Oracle 検索式を使用して Oracle データベースでの検索クエリを実行することはできます。 アダプターのクライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 ここで、SCOTT は、Oracle データベース アイテムの一連のスキーマです。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、a _ は、AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB、ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味をエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!IMPORTANT]
>  検索スコープのメタデータは、検索操作を実行するノードのすぐ下にあるレベルに制限されます。 たとえば、関数を検索するにする必要がありますを検索できる\\[Schema] \Functions です。 再帰的な検索がサポートされていません。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]すべてを含むスキーマの下でメタデータを抽出できますか、データベースのサブセットのオブジェクトそれぞれのオブジェクトと操作のパラメーターを使用します。 アダプターは、XML 内の要素名として、Oracle データベースからエンティティを表示します。 アンダー スコアが含まれることができるのみ許容の特殊文字であるため、要素名に他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされた`emp_x0024_name`です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)   
 [Oracle データベースの BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)   
[Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)