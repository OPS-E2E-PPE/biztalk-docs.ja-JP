---
title: 参照、検索、および Oracle E-business Suite のメタデータの取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b516c6e9-dbb3-4977-bb27-aa039e021912
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce665ef71cbf0849caab334cf62c5f7a659ea96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218298"
---
# <a name="browse-search-and-get-oracle-e-business-suite-metadata"></a>参照、検索、および Oracle E-business Suite のメタデータを取得
メタデータを[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite と基になる Oracle データベースからのサーフェスがアダプターを使用して Oracle E-business Suite と通信するためのメッセージの構造について説明します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
-   によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。 WCF は、クライアントが Oracle E-business Suite からメタデータを取得することができますにすべての WCF バインドをメタデータ交換エンドポイントに提供します。  
  
-   によって提供される IMetadataRetrievalContract、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]をサポートするメタデータ参照とアダプターの機能を検索します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と基になるデータベースの成果物、およびアダプターのクライアントが呼び出すことのできるそれぞれの操作を表示します。 このトピックの後半では、これらの操作について説明します。  
  
 アダプターのクライアントを使用して、参照、検索、およびでメタデータを取得することができます。  
  
-   Visual Studio で BizTalk プロジェクトを作成します。  
  
-   WCF チャネル モデルを使用します。  
  
-   WCF サービス モデルを使用します。  
  
 使用する必要があります、BizTalk プロジェクトを使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle E-business Suite で実行する操作のメタデータを生成します。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Oracle E-business Suite で操作を実行するためのプロキシ クラスを生成します。 閲覧、検索、およびを使用してメタデータの取得の詳細については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)です。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプターをインターフェイス テーブル、インターフェイス ビュー、同時実行のプログラム、[参照]、Oracle E-business Suite とテーブル、ビュー、ストアド プロシージャ、関数、および基になるデータベース内のパッケージ内のセットを要求できるようにします。 メタデータの参照操作の一環として、アダプターは、アダプターでサポートされている一部のカスタム操作を含む、Oracle データベースで実行できる操作も明らかです。 これらの操作はから利用可能な[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスのほとんどの次の 3 つのノードの下にある操作。  
  
1.  **アプリケーション ベースのビュー**: Oracle E-business Suite 成果物のためには、各アプリケーションでグループ化操作が含まれます。  
  
2.  **ビューの成果物に基づく**: (インターフェイス テーブル、インターフェイス ビューなど) と基になるデータベースの Oracle E-business Suite でのアイテムの種類別にグループ化操作が含まれます。  
  
3.  **ビューのスキーマに基づく**: 基になるデータベース成果物のためには、各スキーマ別にグループ化操作が含まれます。  
  
 両方のノードに適用可能なをする、ルート レベルで公開されている汎用操作があります。 さらに、さまざまな操作が表示される操作の種類に基づいて: 送信または受信します。  
  
 次の表は、送信および受信操作の側に表示される、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
|送信操作|受信操作|  
|-------------------------|------------------------|  
|**アプリケーション ベースのビュー**:<br /><br /> 基になる Oracle E-business Suite で Oracle アプリケーションの一覧が含まれています。 次の成果物を表示するには、Oracle アプリケーション ノードを展開します。<br /><br /> <ul><li>**テーブルをインターフェイス**: すべてのインターフェイス テーブルの一覧です。 Insert、Select、Update、表示するインターフェイスのテーブルを選択し、操作を削除します。</li><li>**ビューのインターフェイス**: すべてのインターフェイス ビューの一覧です。 ビューを選択操作インターフェイスを選択します。</li><li>**同時実行プログラム**: 同時実行プログラムの次の操作。<br /><br /> <ul><li>すべての同時実行プログラムの Oracle アプリケーションに固有の操作として公開されているセット。</li><li>同時実行プログラムの状態を取得する Get_Status 操作。</li><li>状態を返す前に完了する要求を待機する Wait_For_Request 操作。</li><li>呼び出しまたは同時実行プログラムの実行に必要なパラメーターを指定して、同時実行プログラムを実行する Submit_Request 操作します。</li></ul></li><li>**セットを要求**: 操作として公開されている Oracle アプリケーションに固有のすべての要求のセットを設定します。</li></ul>|**アプリケーション ベースのビュー**:<br /><br /> 基になる Oracle E-business Suite で Oracle アプリケーションの一覧が含まれています。 次の成果物を表示するには、Oracle アプリケーション ノードを展開します。<br /><br /> -   **テーブルをインターフェイス**: アダプター クライアントは、Oracle E-business Suite から受信データを取得できるようにするインターフェイス テーブルの ポーリング操作、アダプターによってサポートされるクエリ ポーリング機構に基づいています。<br />-   **ビューのインターフェイス**: アダプター クライアントは、Oracle E-business Suite から受信データを取得できるようにするインターフェイス ビューの ポーリング操作、アダプターによってサポートされるクエリ ポーリング機構に基づいています。|  
|**ビューの成果物に基づく**:<br /><br /> Oracle E-business Suite と基になるデータベース内のすべての成果物が含まれています。 Oracle アプリケーション、または成果物 (アプリケーションまたはデータベース) の配信元に基づくスキーマの一覧を表示する成果物ノードを展開します。 たとえば、**インターフェイス テーブル**ノードが Oracle アプリケーションの一覧が表示されます、**テーブル**ノードのデータベース スキーマの一覧が表示されます。<br /><br /> **成果物に基づいたビュー**下に表示するアイテムが表示されます**アプリケーション ベースのビュー**と**ビューのスキーマに基づく**です。 各成果物ノードには、Oracle アプリケーションまたはデータベース スキーマの関連する操作が一覧表示します。|**ビューの成果物に基づく**:<br /><br /> 同時実行プログラム、要求のセットを除く、Oracle E-business Suite でのすべての成果物と、基になるデータベース内のすべての成果物が含まれています。 Oracle アプリケーション、または成果物 (アプリケーションまたはデータベース) の配信元に基づくスキーマの一覧を表示する成果物ノードを展開します。 たとえば、**インターフェイス テーブル**ノードが Oracle アプリケーションの一覧が表示されます、**テーブル**ノードのデータベース スキーマの一覧が表示されます。<br /><br /> **成果物に基づいたビュー**下に表示するアイテムが表示されます**アプリケーション ベースのビュー**と**ビューのスキーマに基づく**です。 各成果物ノードには、Oracle アプリケーションまたはデータベース スキーマの関連する操作が一覧表示します。|  
|**ビューのスキーマに基づく**:<br /><br /> 基になる Oracle データベースでのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。<br /><br /> -   **PL/SQL Api**: すべての PL/SQL Api の一覧です。 パッケージ化したプロシージャと操作として公開されている関数を表示する PL/SQL API を選択します。<br />-   **プロシージャ**: 操作として公開されるスキーマのプロシージャの一覧です。<br />-   **関数**: 操作として公開されているスキーマ内の関数の一覧です。<br />-   **テーブル**: すべてのテーブルの一覧です。 Insert、Select、Update、表示するテーブルを選択し、操作を削除します。<br />-   **ビュー**: すべてのビューの一覧です。 選択操作を表示するビューを選択します。|**ビューのスキーマに基づく**:<br /><br /> 基になる Oracle データベースでのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。<br /><br /> -   **PL/SQL Api**: すべての PL/SQL Api の一覧です。 パッケージ化したプロシージャとポーリング操作として公開されている関数を表示する PL/SQL API を選択します。<br />-   **プロシージャ**: ポーリングの操作として公開されるスキーマのプロシージャの一覧です。<br />-   **関数**: ポーリングの操作として公開されるスキーマ内の関数の一覧です。<br />-   **テーブル**: すべてのテーブルの一覧です。 テーブルのポーリング操作を表示するテーブルを選択します。<br />-   **ビュー**: すべてのビューの一覧です。 ビューのポーリング操作を表示するビューを選択します。|  
|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ルート レベルで、次の汎用送信操作を公開: ExecuteReader、ExecuteScalar、および ExecuteNonQuery です。 これらの操作については、次を参照してください。 [ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)です。|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター Oracle E-business Suite からデータベースの変更の通知メッセージを受信できるようにするルート レベルで通知の操作を公開します。 通知操作の詳細については、次を参照してください。[データベースの変更通知の受信に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)です。|  
  
 メタデータを分類する方法の詳細については、次を参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 使用して、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、Oracle E-business Suite で検索クエリを実行して、Oracle を使用して、基になる Oracle データベースで LIKE 演算子と互換性がある式を検索できます。 アダプターのクライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 ここで、SCOTT は、Oracle データベース アイテムの一連のスキーマです。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、AB、ac 電源と AD a _ に一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB、ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味をエスケープします。 \ (エスケープ) 文字がワイルドカード文字の前に、ワイルドカード文字を通常の文字として解釈することを示すために使用します。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!IMPORTANT]
>  -   検索文字列では大文字小文字を区別します。  
> -   検索は、別のビュー (アプリケーション ベースのビュー、成果物に基づいたビュー、およびビューのスキーマに基づく) で異なる方法で動作します。 アイテムおよび操作で各ビューの下で検索する方法を参照してください「別のビューの下の検索」に[Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)です。  
> -   アプリケーションを検索するには、フレンドリ名またはアプリケーションの短い名前を指定できます。 たとえば、検索するため、**債権**アプリケーションのいずれかとして検索文字列を指定することができます**受信 %** または**AR**です。 AR は、アプリケーションの短い名前です。  
> -   同時実行プログラムを検索するには、フレンドリ名または同時実行プログラムの実際の名前を指定できます。 例については、検索する、**顧客インターフェイス**検索文字列を指定するにはいずれかとしてプログラムを同時 **% 顧客インターフェイス**または **%racust**です。 RACUST は、同時実行プログラムの実際の名前です。 また、検索結果は、その名が指定した検索文字列と一致するかどうかに関係なく、標準的な同時実行プログラムを常に含まれます。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]すべてを含むスキーマの下でメタデータを抽出できますか、データベースのサブセットのオブジェクトそれぞれのオブジェクトと操作のパラメーターを使用します。 アダプターは、XML 内の要素名として、Oracle E-business Suite と基になる Oracle データベースからエンティティを表示します。 アンダー スコアが含まれることができるのみ許容の特殊文字であるため、要素名に他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされた`emp_x0024_name`です。 詳細については、次を参照してください。[取得操作のメタデータの SQL Server、SQL アダプターを使用して Visual Studio で](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [Oracle E-business Suite の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)   
 [参照、検索、および Oracle E-business 操作のメタデータの取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)   
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)