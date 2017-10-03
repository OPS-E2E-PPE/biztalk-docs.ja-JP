---
title: "インターフェイスのテーブルとのインターフェイス ビューでの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c7f3453-848f-42df-b092-725d9ff466cf
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ec9b7c5f952b6be60a3c3463e6ea0682faa9d4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-interface-tables-and-interface-views"></a>インターフェイスのテーブルとのインターフェイス ビューでの操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]一連の標準的な操作 (Select、Insert、Update、および各インターフェイス テーブルの削除) および Oracle E-business Suite では、各インターフェイス ビューの選択操作を表示します。 これらの操作を使用すると、SELECT、INSERT、UPDATE を実行し、対象のインターフェイス テーブルに対する WHERE 句で修飾されたステートメントおよび対象のインターフェイス ビューの WHERE 句で修飾された SELECT ステートメントを削除できます。 これらの操作は、データ操作言語 (DML) 操作とも呼ばれます。  
  
> [!IMPORTANT]
>  インターフェイスのテーブルとのインターフェイス ビューでの操作を行うことができます、前にでこれらの成果物のアプリケーションのコンテキストを設定する必要があります[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定、およびアイテムのアクセス制御を設定して Oracle E-business Suite でセキュリティ保護されたトランザクションを容易にするためです。 アプリケーションのコンテキストおよびそれを設定する方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  

## <a name="supported-dml-operations"></a>サポートされている DML 操作  
 次の表は、DML 操作を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をサポートしています。  
  
|操作|Description|  
|---------------|-----------------|  
|Select|指定された列名と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいてターゲット インターフェイス テーブルまたはインターフェイス ビューで選択操作を実行します。<br /><br /> Select 操作の戻り値は、指定された列と行を含む厳密に型指定された結果セットです。|  
|Insert|対象のインターフェイス テーブルに対する挿入操作を実行します。 Insert 操作サポートしている複数のレコードは、指定されたレコード セットに基づくインターフェイス テーブルに挿入します。<br /><br /> 挿入操作の戻り値は、挿入された行の数です。<br /><br /> **InlineValue**<br /><br /> 挿入操作ですべての単純なデータ レコードを選択できますと呼ばれる省略可能な属性の値を指定することによって、レコードの値をオーバーライドする**InlineValue**です。 InlineValue 属性は、日付の列に主キー列のシーケンスまたは (SYSDATE を使用して) システムの日付を挿入することを設定するなどのインターフェイス テーブルに計算値を挿入を使用することができます。 たとえば、次のステートメントを挿入します。<br /><br /> `<Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/AR/AR_ARCHIVE_PURGE_INTERIM">   <RECORDSET>     <InsertRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/AR/AR_ARCHIVE_PURGE_INTERIM">       <TRNS_DATE InlineValue="sysdate">2008-06-21T15:52:19</TRNS_DATE>       <EMPNAME>John</EMPNAME>     </InsertRecord>   </RECORDSET>   </Insert>`<br /><br /> にもかかわらず"2008-06-21T15:52:19"TRNS_DATE の値を値として指定された、 **InlineValue**属性では、"SYSDATE、"(システムの日付) は、対象のインターフェイス テーブルに挿入されます。<br /><br /> InlineValue の使用中に次のように属性します。<br /><br /> -InlineValue 属性の定数値を使用しないでください。 たとえばを指定する場合に、INSERT ステートメントで`<EMPNAME InlineValue="John"/>`エラーが発生し、します。 これは、として InlineValue 属性の値が渡されるため-ここでは、oracle、 *John* Oracle E-business Suite は、予期される値ではないに渡される (期待される値は*"John"*)。 従業員名を囲む単一引用符を使用する必要があります。 たとえば、 `<EMPNAME InlineValue="’John’"/>`のようにします。<br /><br /> -InlineValue 属性の選択クエリを使用する場合、SELECT ステートメントをかっこで囲みますも select クエリが単一のレコードだけをフェッチすることを確認してください。 たとえば、 `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`のようにします。<br /><br /> **注:**要素は、Oracle E-business Suite で NOT NULL としてマークすると、インライン値を指定した場合でも、その要素の値を指定する必要があります。 これを行うがスキーマ検証が失敗します。|  
|Update|対象のインターフェイス テーブルの更新操作を実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。<br /><br /> 更新操作の戻り値は、更新された行の数です。|  
|DELETE|SQL の WHERE 句に基づいてフィルター文字列で指定されている対象のインターフェイス テーブルに対して Delete 操作を実行します。<br /><br /> 削除操作の戻り値は、削除された行の数です。|  

## <a name="important-details"></a>重要な詳細情報  
  -   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]標準的な操作 (Select、Insert、Update、および各テーブルの削除) と、基になる Oracle データベース内の各ビューの選択操作の同じセットを表示します。 上記の DML 操作も、基になる Oracle データベース テーブルやビューに対して有効です。  

 -   Oracle データベースでテーブルおよびビューの操作を実行するアプリケーションのコンテキストを設定する必要はありません。 ただし、カスタム Oracle E-business Suite アプリケーションでのユーザーは、インターフェイス テーブルとして基本データベースのテーブルは登録できません。 データベース テーブルが、インターフェイス テーブルとして登録されていない場合で使用可能な**テーブル**にサブノード、**成果物ベース ビュー**ノードまたは、**スキーマ ベース ビュー**ノード使用しているときにデザイン時に[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
    これらのテーブルは、Oracle E-business アプリケーションに関連付けられます。 それでこれらのテーブルのすべての操作に対して、アプリケーションのコンテキストを設定する必要があります。 アプリケーション コンテキストの設定を参照して[リンクは、ここの説明を入力](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)