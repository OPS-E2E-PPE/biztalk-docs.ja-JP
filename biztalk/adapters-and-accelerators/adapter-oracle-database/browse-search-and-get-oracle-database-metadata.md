---
title: 参照、検索、および Oracle データベースのメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e67a1b1357798333cef8ccdd37074482fb06a29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966131"
---
# <a name="browse-search-and-get-oracle-database-metadata"></a>参照、検索、および Oracle データベースのメタデータを取得します。
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターを使用して Oracle データベースと通信するためのメッセージ構造を記述する Oracle データベースからのサーフェスのメタデータ。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メタデータを取得するための 2 つのインターフェイスをサポートしています。  
  
- によって提供される MetadataExchange[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。 WCF は、クライアントが Oracle データベースからメタデータを取得できるようにするにすべての WCF バインドのメタデータ交換エンドポイントに提供します。  
  
- によって提供される IMetadataRetrievalContract、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、閲覧と検索機能を備えたアダプターのメタデータをサポートしています。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス、Oracle データベース成果物とそれぞれの操作をアダプターのクライアントが呼び出すことができます。 アダプターでは、Oracle データベースで特定の操作を実行するために使用できる、SQLEXECUTE、POLLINGSTMT、および通知の操作も表示されます。 このトピックの後半では、これらの操作について説明します。  
  
  アダプター クライアントは、参照、検索、および WCF チャネル モデルを使用して、WCF サービス モデルを使用して、または Visual Studio で BizTalk プロジェクトを作成して、メタデータを取得できます。 使用する必要があります、WCF サービス モデルを使用する場合、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] Oracle データベースでの操作を実行するためのプロキシ クラスを生成します。 使用する必要がある BizTalk プロジェクトを使用する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle データベースで実行する操作のメタデータを生成します。 参照、検索、およびメタデータを使用した取得の詳細については[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。  
  
## <a name="browsing-metadata"></a>メタデータの参照  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントがデータベース テーブル、テーブルのビュー、ストアド プロシージャ、関数、および Oracle データベースで使用可能なパッケージを参照できるようにします。 メタデータの参照操作の一環として、アダプターでは、アダプターでサポートされているいくつかのカスタム操作など、Oracle データベースで実行できる操作も表示されます。 これらの操作はから利用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスの次の操作。  
  
 **送信操作**  
  
 基になる Oracle データベースのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。  
  
- **テーブル**: スキーマ内のすべてのテーブルの一覧。 Insert、Select、Update、表示するテーブルを選択し、操作を削除します。  
  
- **プロシージャ**: 操作として公開されるスキーマ内のストアド プロシージャの一覧。  
  
- **関数**: スキーマの操作として公開される関数の一覧。  
  
- **パッケージ**: スキーマ内のすべてのパッケージの一覧。 プロシージャと、パッケージ内の操作として公開されている関数を表示するためのパッケージを選択します。  
  
- **ビュー**: スキーマ内のすべてのビューの一覧。 Insert、Select、Update、表示するビューを選択し、操作を削除します。  
  
  別に、この、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]も公開、 **SQLEXECUTE**アダプター クライアントが Oracle データベースで任意の汎用的なデータ操作言語 (DML) またはストアド プロシージャを実行できるように、送信操作。 SQLEXECUTE 操作は、ルート ノード (/) を選択するときに使用できます。 SQLEXECUTE の出力はデータ リーダー (汎用レコードの配列として出力) の配列であることに注意してください。 その結果、out パラメーターの任意の単純は表示されません SQLEXECUTE 操作を使用しています。 操作の詳細については、[Oracle データベースで SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)を参照してください。  
  
  **受信操作**  
  
  基になる Oracle データベースのスキーマの一覧が含まれています。 次の成果物を表示するスキーマ ノードを展開します。  
  
- **プロシージャ**: ポーリングするための操作として公開されるスキーマ内のストアド プロシージャの一覧。  
  
- **関数**: ポーリングするための操作として公開されるスキーマ内の関数の一覧。  
  
- **パッケージ**: スキーマ内のパッケージの一覧。 パッケージ化されたプロシージャとポーリングするための操作として公開されている関数を表示するためのパッケージを選択します。  
  
  また、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]も公開、 **POLLINGSTMT**と**通知**受信操作。 POLLINGSTMT 操作には、アダプターによってサポートされているメカニズムのポーリング クエリに基づく Oracle データベースからの受信データを取得するアダプターのクライアントが使用できます。 通知操作により、SELECT ステートメントをデータベースに対して、通知クエリとして登録するクライアントはアダプターとアダプター クライアントとしてを使用して、SELECT ステートメントの変更の結果セットは、データベースが、通知を送信します。 POLLINGSTMT および通知の操作は、ルート ノード (/) を選択するときに使用可能です。 操作に関する詳細については、次を参照してください[ポーリングの受信に基づいたデータ変更メッセージのサポート](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md).md) と[受信チェンジャー通知を使用してデータベース、Oracle Database アダプターに関する考慮事項。](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
  メタデータの分類方法の詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)を参照してください。  
  
## <a name="searching-metadata"></a>メタデータの検索  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、LIKE 演算子と互換性がある Oracle 検索式を使用して Oracle データベースで検索クエリを実行することができます。 アダプター クライアントが「EMP %」など、検索式を使用するなど、以降では、EMP テーブルを取得します。 アダプターは、SQL クエリを次に、これを変換します。  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 ここで、SCOTT は、Oracle データベース アイテムのコレクションとスキーマを示します。  
  
 次の表に、検索とその解釈で使用できる特殊文字、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、<curses.h は AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味でのエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!IMPORTANT]
>  メタデータの検索スコープは、検索操作を実行するノードのすぐ下にあるレベルに限定されます。 たとえば、関数を検索するをする必要があります検索する\\[Schema] \Functions します。 再帰的な検索がサポートされていません。  
  
## <a name="retrieving-metadata"></a>メタデータの取得  
 メタデータを取得するときに、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]またはデータベースのサブセットがそれぞれのオブジェクトと操作のパラメーターを使用してオブジェクトがすべてを含むスキーマの下でメタデータを抽出することができます。 アダプターは、XML 内の要素名としての Oracle データベースからエンティティを表示します。 アンダー スコアを含めることができますのみ指定できる特殊文字であるために、要素名でその他のすべての特殊文字はアンダー スコアを使用してエンコードされます。 たとえば、`emp$name`としてエンコードされます`emp_x0024_name`します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)   
 [Oracle データベースの BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)   
[Visual Studio での Oracle データベース操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)