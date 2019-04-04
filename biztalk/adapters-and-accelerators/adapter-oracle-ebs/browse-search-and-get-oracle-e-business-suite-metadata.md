---
title: 参照、検索、および Oracle E-business Suite のメタデータの取得 |Microsoft Docs
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
ms.openlocfilehash: 28a22fa00b859a6ee44505a008b2c1912097a568
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976307"
---
# <a name="browse-search-and-get-oracle-e-business-suite-metadata"></a>参照、検索、および Oracle E-business Suite のメタデータを取得します。
メタデータを[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite と基になる Oracle データベースからのサーフェスがアダプターを使用して Oracle E-business Suite と通信するためのメッセージの構造について説明します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
- によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 WCF は、クライアントが Oracle E-business Suite からメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
- によって提供される IMetadataRetrievalContract、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、閲覧と検索機能を備えたアダプターのメタデータをサポートしています。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と基になるデータベース成果物、およびアダプター クライアントが呼び出すことができるそれぞれの操作を表示します。 このトピックの後半では、これらの操作について説明します。  
  
  アダプターのクライアントを使用して、参照、検索、および、メタデータを取得することができます。  
  
- Visual Studio での BizTalk プロジェクトの作成  
  
- WCF チャネル モデルを使用します。  
  
- WCF サービス モデルの使用  
  
  使用する必要がある BizTalk プロジェクトを使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle E-business Suite で実行する操作のメタデータを生成します。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Oracle E-business Suite の操作を実行するためのプロキシ クラスを生成します。 参照、検索、およびメタデータを使用した取得の詳細については[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータの取得](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントのインターフェイス テーブル、インターフェイス ビュー、同時実行プログラムを参照し、Oracle E-business Suite とテーブル、ビュー、ストアド プロシージャ、関数、および基になるデータベース内のパッケージ内のセットを要求できるようにします。 メタデータの参照操作の一環として、アダプターでは、アダプターでサポートされているいくつかのカスタム操作など、Oracle データベースで実行できる操作も表示されます。 これらの操作はから利用可能な[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェスのほとんどの操作を次の 3 つのノードの下。  
  
1. **アプリケーション ベースのビュー**: Oracle E-business Suite の成果物の各アプリケーションによるグループ化操作が含まれます。  
  
2. **成果物ベースのビュー**: (インターフェイス テーブル、ビューのインターフェイスなど) と基になるデータベースの Oracle E-business Suite での成果物の種類別にグループ化操作が含まれます。  
  
3. **ビューのスキーマに基づく**: 基になるデータベース成果物の各スキーマ別にグループ化操作が含まれます。  
  
   維持両方のノードに適用される、ルート レベルで公開されている一般的な操作がいくつかがあります。 さらに、さまざまな操作が操作の種類を基に表示されます。 送信または受信します。  
  
   次の表に、送信および受信操作が表示されます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            送信操作                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                     受信操作                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **アプリケーション ベースのビュー**:<br /><br /> 基になる Oracle E-business Suite での Oracle アプリケーションの一覧が含まれています。 次の成果物を表示する、Oracle アプリケーション ノードを展開します。<br /><br /> <ul><li>**インターフェイス テーブル**: すべてのインターフェイス テーブルの一覧。 Insert、Select、Update、表示するインターフェイスのテーブルを選択し、操作を削除します。</li><li>**インターフェイス ビュー**: すべてのインターフェイス ビューの一覧。 ビューを選択操作インターフェイスを選択します。</li><li>**同時実行プログラム**: 同時実行プログラムの次の操作。<br /><br /> <ul><li>すべての同時実行プログラムの Oracle アプリケーションに固有の操作として公開されているセット。</li><li>同時実行プログラムの状態を取得する Get_Status 操作。</li><li>要求の状態の取得が完了するを待機する Wait_For_Request 操作。</li><li>呼び出すか、同時実行プログラムの実行に必要なパラメーターを指定して、同時実行プログラムを実行する Submit_Request 操作。</li></ul></li><li>**要求セット**: 一連のすべての要求の設定操作として公開されている Oracle アプリケーションを特定します。</li></ul> |                                                 **アプリケーション ベースのビュー**:<br /><br /> 基になる Oracle E-business Suite での Oracle アプリケーションの一覧が含まれています。 次の成果物を表示する、Oracle アプリケーション ノードを展開します。<br /><br /> -   **インターフェイス テーブル**: アダプターのクライアントを Oracle E-business Suite から受信データを取得できるようにするインターフェイス テーブル、ポーリング操作、アダプターでサポートされるクエリのポーリング メカニズムに基づきます。<br />-   **インターフェイス ビュー**: アダプターのクライアントを Oracle E-business Suite から受信データを取得できるようにするインターフェイス ビューの ポーリング操作、アダプターでサポートされるクエリのポーリング メカニズムに基づきます。                                                  |
|                                                                                                                                                                                                                                                                    **成果物ベースのビュー**:<br /><br /> Oracle E-business Suite と基になるデータベース内のすべての成果物が含まれています。 Oracle のアプリケーションまたは成果物 (アプリケーションまたはデータベース) の配信元に基づくスキーマの一覧を表示する、成果物ノードを展開します。 たとえば、**インターフェイス テーブル**ノードは Oracle のアプリケーションの一覧が表示されます、**テーブル**ノード データベース スキーマの一覧が表示されます。<br /><br /> **成果物ベースのビュー**下に表示するアイテムを表示します。**アプリケーション ベースのビュー**と**ビューのスキーマに基づく**します。 各成果物ノードには、Oracle アプリケーションまたはデータベース スキーマの関連する操作が一覧表示されます。                                                                                                                                                                                                                                                                     |            **成果物ベースのビュー**:<br /><br /> 同時実行プログラムと要求のセットを除く、Oracle E-business Suite でのすべての成果物と、基になるデータベース内のすべての成果物が含まれています。 Oracle のアプリケーションまたは成果物 (アプリケーションまたはデータベース) の配信元に基づくスキーマの一覧を表示する、成果物ノードを展開します。 たとえば、**インターフェイス テーブル**ノードは Oracle のアプリケーションの一覧が表示されます、**テーブル**ノード データベース スキーマの一覧が表示されます。<br /><br /> **成果物ベースのビュー**下に表示するアイテムを表示します。**アプリケーション ベースのビュー**と**ビューのスキーマに基づく**します。 各成果物ノードには、Oracle アプリケーションまたはデータベース スキーマの関連する操作が一覧表示されます。             |
|                                                                                                                                                                                                                                       **ビューのスキーマに基づく**:<br /><br /> 基になる Oracle データベースのスキーマの一覧が含まれています。 次の成果物を表示するスキーマのノードを展開します。<br /><br /> -   **PL/SQL Api**: すべての PL/SQL Api の一覧。 パッケージ化されたプロシージャと操作として公開されている関数を表示する PL/SQL API を選択します。<br />-   **プロシージャ**: 操作として公開されるスキーマのプロシージャの一覧。<br />-   **関数**: スキーマの操作として公開される関数の一覧。<br />-   **テーブル**: すべてのテーブルの一覧。 Insert、Select、Update、表示するテーブルを選択し、操作を削除します。<br />-   **ビュー**: すべてのビューの一覧。 選択操作を表示するビューを選択します。                                                                                                                                                                                                                                       | **ビューのスキーマに基づく**:<br /><br /> 基になる Oracle データベースのスキーマの一覧が含まれています。 次の成果物を表示するスキーマのノードを展開します。<br /><br /> -   **PL/SQL Api**: すべての PL/SQL Api の一覧。 パッケージ化されたプロシージャとポーリングするための操作として公開されている関数を表示する PL/SQL API を選択します。<br />-   **プロシージャ**: ポーリングするための操作として公開されるスキーマのプロシージャの一覧。<br />-   **関数**: ポーリングするための操作として公開されるスキーマ内の関数の一覧。<br />-   **テーブル**: すべてのテーブルの一覧。 テーブルのポーリング操作を表示するテーブルを選択します。<br />-   **ビュー**: すべてのビューの一覧。 ビューのポーリング操作を表示するビューを選択します。 |
|                                                                                                                                                                                                                                                                                                                                                              [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ルート レベルで、次の汎用的な送信操作を公開します: ExecuteReader、ExecuteScalar、ExecuteNonQuery します。 これらの操作については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。                                                                                                                                                                                                                                                                                                                                                               |                                                                                                             [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアント Oracle E-business Suite からデータベース変更通知のメッセージを受信できるようにする、ルート レベルで通知の操作を公開します。 通知操作の詳細については、[データベース変更通知の受信に関する考慮事項](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)を参照してください。                                                                                                             |
  
 メタデータの分類方法の詳細については、[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)を参照してください。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 使用して、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、Oracle E-business Suite で検索クエリを実行して、Oracle を使用して、基になる Oracle データベースで LIKE 演算子と互換性がある式を検索できます。 アダプター クライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 ここで、SCOTT は、Oracle データベース アイテムのコレクションとスキーマを示します。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、AB、AC、および AD <curses.h に一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味をエスケープします。 \ (エスケープ) 文字は、ワイルドカード文字の前に、ワイルドカード文字を通常の文字として解釈することを示すために使用されます。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!IMPORTANT]
> - 検索文字列が大文字小文字を区別します。  
>   -   検索は、(アプリケーション ベースのビュー、成果物ベースのビューおよびビューのスキーマに基づく) は、別のビューで異なる方法で動作します。 成果物と各ビューで操作を検索する方法については、「別のビューの下の検索」を参照してください[Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)します。  
>   -   アプリケーションを検索するには、フレンドリ名またはアプリケーションの短い名前を指定できます。 たとえば、検索するため、 **Receivables**検索文字列を指定するにはいずれかとしてアプリケーション**受信 %** または**AR**。 AR は、アプリケーションの短い名前です。  
>   -   同時実行プログラムを検索するには、フレンドリ名または同時実行プログラムの実際の名前を指定できます。 たとえば、検索するため、**顧客インターフェイス**同時実行プログラムのいずれかとして検索文字列を指定することができます **% 顧客インターフェイス**または **%racust**。 RACUST は、同時実行プログラムの実際の名前です。 また、検索結果は標準の同時実行プログラムの名前が指定した検索文字列と一致するかどうかに関係なく常に含まれます。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]またはデータベースのサブセットがそれぞれのオブジェクトと操作のパラメーターを使用してオブジェクトがすべてを含むスキーマの下でメタデータを抽出することができます。 アダプターは、XML 内の要素名として、Oracle E-business Suite と基になる Oracle データベースからエンティティを表示します。 アンダー スコアを含めることができますのみ指定できる特殊文字であるために、要素名でその他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされます`emp_x0024_name`します。 詳細については、[SQL アダプタを使用して Visual Studio で SQL Server 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle E-business Suite についてください。](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)   
 [参照、検索、および Oracle E-business 操作のメタデータの取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)   
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)