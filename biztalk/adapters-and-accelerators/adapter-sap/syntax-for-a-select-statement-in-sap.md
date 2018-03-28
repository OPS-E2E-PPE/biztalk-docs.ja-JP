---
title: SAP の SELECT ステートメントの構文 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SELECT statement, syntax for
ms.assetid: 47120d74-bf41-4622-a6bc-7b8ddc959305
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f57cac0673a6520de4b0d881527bbc7b670ca1b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="syntax-for-a-select-statement-in-sap"></a>SAP の SELECT ステートメントの構文
次のセクションでは、文法仕様に対する SELECT クエリを実装するための記述、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]です。 いくつかのケースでは、構文は、基本の TRANSACT-SQL 構文から若干異なることを確認します。  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 各要素の説明は次のとおりです。  
  
-   **<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`  
  
-   **<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`  
  
-   **\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`  
  
 サポートされている条件と式は、次のようには。  
  
-   **\<condition\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`  
  
-   **\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`  
  
 ここで **\<const\>** = `integer | real | string | ? | NULL | xml_element`です。  
  
 **オプションのキーワードの値**  
  
 としてオプションを指定できます`OPTION '<option>'`ここで、 `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`  
  
-   **No_conversion**オプション。  
  
    -   場合、 **no_conversion**オプションを使用し、同等の .NET 型を使用して、テーブルのフィールドが公開されます。 SAP のデータ型の同等の .NET 関数については、次を参照してください。 [SAP の基本データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)です。  
  
    -   場合、 **no_conversion**フィールドに、変換がないかどうかは、定義されている終了オプションは使用されませんし、同等の .NET 型を使用して、テーブル内のそれらのフィールドが公開されます。 SAP のデータ型の同等の .NET 関数については、次を参照してください。 [SAP の基本データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)です。  
  
    -   ときに、 **no_conversion**フィールドに、変換があるかどうかとは、定義されている終了オプションは使用されませんし、テーブル内のそれらのフィールドが .NET 文字列として公開されます。  
  
-   設定すると**batchsize\<サイズ\>**、SELECT ステートメントの実行により複数の呼び出しを SAP システム的に各呼び出しでのみ行われる\<サイズ\>レコードの数取得されます。 例では、指定した場合の ' 100'、SELECT クエリ batchsize が SAP システムへの各呼び出しでのみ 100 のレコードを取得します。 場合**batchsize\<サイズ\>**が指定されていない、10,000 の既定値は、バッチ サイズと見なされます。 SAP システムでコンピューターと行の数の物理メモリに基づくバッチ サイズの最適な値を指定する必要があることに注意してください。 バッチ サイズの最適な値を指定するときにエラーは、メモリ不足の例外、可能性があります。  
  
-   設定すると**disabledatavalidation**、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] DATS、TIM、NUMC 列に存在する値を検証しませんが、代わりに文字列として公開します。  
  
     これは、DATS、TIM、および NUMC 列に無効なデータを持つ SAP テーブルからデータを取得する ADO.NET クライアントが失敗する場合に便利です。 SAP DATS、TIM、および NUMC 列に存在するデータが無効なため、データの読み取りを試みている ADO.NET クライアントは、無効なデータを解析することはできませんし、例外がスローされます。 場合、 **disabledatavalidation** 、SELECT クエリでオプションを設定、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]無効なデータを解析しませんが、それらを文字列として抽出します。  
  
> [!IMPORTANT]
>  たとえば、常に 1 つの引用符で囲まれたオプションのキーワードの値を提供する必要があります '*disabledatavalidation*' です。  
  
 たとえば、ステートメントを参照してください[SELECT ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)です。  
  
## <a name="predicates-syntax"></a>述語の構文  
 次の例は、SELECT ステートメントの述語を使用するための文法を指定します。  
  
 `Predicate`:   
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 `Condition`:   
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 `Expr`:   
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 `LExpr`:   
  
```  
ColumnName  
```  
  
 `RExpr`:   
  
```  
Const | PlaceHolder  
```  
  
 `ColumnName`:   
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 `Tablename`:   
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a>SELECT ステートメントを呼び出す際の考慮事項  
 このセクションの内容を含む SELECT ステートメントを使用する場合は、点に注意する必要がありますポイントを一覧表示[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。  
  
-   をパラメーターまたはクエリの日付と時刻の値を指定する場合は、文字列として値を提供します。 SAP の日付と時刻の形式で日付と時刻の文字列を提供します。  
  
    -   `SAP date format`: YYYYMMDD 形式で指定  
  
         たとえば、2004 年の日 11 月 10 日 SAP クエリでは表された '20041110' です。  
  
         2004 年の日文字列 p1 は SAPParameter p1 の 11 月 10 日のです。値 '20041110' を = です。  
  
    -   `SAP time format`: HHMMSS 形式で指定  
  
         たとえば、時間 10時 34分: 32 SAP クエリでは表された '103432' です。  
  
         時間 10時 34分: 32 SAPParameter p2 では、文字列 p2 です。値 '103432' を = です。  
  
     SELECT ステートメントで、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を返します`DATE`.NET として値をフィールド`System.DateTime`オブジェクト、および返します`TIME`フィールドの値として`System.TimeSpan`オブジェクト。 場合、SAP の値`DATE`オブジェクトが許容される SQL Server の最小値より小さい (`1/1/1753`) では、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]この最小値を返します`1/1/1753`です。  
  
-   特殊文字「#」を使用する場合、SELECT クエリの TOP 句の"^"、"&"と「%」前に、または整数の後に、特殊文字、無視されますが、エラー メッセージは発生しません。 たとえば、次は無視されます、SELECT クエリの TOP 句で。  
  
     \#5, 5 ^、% 5%、または 5 &  
  
     ただし、5 と同様に、整数の間でこれらの文字を使用して、5 ドルはエラーをスローします。  
  
-   テーブルのスキーマで返される列名は大文字をすべてとして返されます。 フィールドに、クエリ結果を設定するなど、`Last Name`列見出しを返します`LAST NAME`です。 一意性を避けるために SELECT ステートメントではすべて大文字を使用して、競合の使用をお勧めします。  
  
-   選択クエリの LIKE 句でのみ、パーセント記号 (任意の文字列に 0 個以上の文字)、「%」、アンダー スコア、 **「_」** (任意の 1 文字) が使用できる特殊文字。 他のすべての特殊文字は、文字列値が考慮され、無視されます。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC を使用して SAP システムで SELECT クエリを実行します。 RFC は、次の条件を満たすテーブルからデータを読み取りをサポートします。  
  
    -   テーブルの TabClass は TRANSP、クラスター、またはプールです。  
  
    -   TabClass ビューは、ViewClass D または P. のいずれか  
  
     SELECT ステートメントでは、これらの条件を満たすテーブルからデータを読み取ることを確認してください。  
  
-   255 文字より長い、たとえば文字列、RAWSTRING、LRAW、VARC、および LCHAR が実行できるデータ型の値は、SELECT クエリでは使用できません。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]付属のカスタム RFC を使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Z_EXTRACT_DATA_OO、SAP システムで SELECT クエリを実行します。 このカスタム RFC は 255 文字以上が実行できるデータ型をサポートしていません。  
  
-   SELECT ステートメントでサポートされているフィールドまたは列の最大数は 1000 です。  
  
-   WHERE 句でサポートされている述語の最大数は 100 です。  
  
-   同じ SELECT ステートメントで複数回の同じフィールドを選択することはサポートされていません。 によって使用されるカスタム RFC (Z_EXTRACT_DATA_OO)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]実行する前に、ステートメントから重複するフィールドを削除します。 たとえば、次のステートメント。  
  
     `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
     このステートメントと同様に書き込まれるように実行します。  
  
     `SELECT BUKRS from T001`  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントでは重複するエイリアス名はサポートされません。 したがって、次の SELECT ステートメントでは、エラーがスローされます。  
  
    ```  
    SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 重複する列名を含む SELECT ステートメントはサポートされません。 したがって、次の SELECT ステートメントでは、エラーがスローされます。  
  
    ```  
    SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
    ```  
  
-   SAP では、テーブルで NULL 値は格納されません。 その結果、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで、"IS NULL"値をサポートしていません。 したがって、次の SELECT ステートメントでは、エラーがスローされます。  
  
    ```  
    SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで ORDER BY 句はサポートされません。 したがって、次の SELECT ステートメントでは、エラーがスローされます。  
  
    ```  
    SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
    ```  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP テーブル内のすべてのフィールドを選択するアスタリスク (*) を指定することはできません。 したがって、次の SELECT ステートメントでは、エラーがスローされます。  
  
    ```  
    SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     すべてのフィールドを選択するには、個別にフィールド名を指定する必要があります。  
  
-   SELECT ステートメントの一部として、SELECT ステートメントの出力の書き込み先となるファイルを指定することができます。 ただし、出力ファイルがネットワーク共有上にある場合は、SAP サービスが実行されている SAP サービス アカウントにネットワーク共有に対する書き込み権限があることを確認してください。 以下に例を示します。  
  
    ```  
    SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
     前の例では、SAP のサービス アカウントが必要名「共有」とネットワーク共有への書き込みアクセス許可  
  
-   SELECT ステートメントを使用して、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]選択クエリで引数の値のパラメーターの名前をサポートしています。 ただし、パラメーター名に関してこれらの規則に従うことを確認してください。  
  
    -   SELECT クエリで、"@"記号はパラメーターの名前を付ける必要があります。  
  
    -   "@"記号は、英字 (A ~ Z または a ~ z) の後になければなりません。  
  
    -   パラメーター名は英数字文字を含めることができます (A ~ Z、a ~ z、または 0 ~ 9) と特殊文字。 パラメーター名に含めることができる唯一の特殊な文字は、アンダー スコア「_」と「#」のハッシュです。  
  
-   ビューで SELECT クエリを実行すると、ベース テーブルの主キー列がビューに存在してもすることを確認します。 プラクティスとして、また、ビューの主キー列として列もマークする必要があります。  
  
     主キー列がビューに存在しない場合、ビューで SELECT クエリ、例外が発生します。  
  
-   LRAW の種類のフィールドを選択するテーブルに対する SELECT クエリを実行するときに対応する PREC フィールドを選択することを確認します。 また、SELECT 句で LRAW フィールドの直前 PREC フィールドが表示されます必要があります。  
  
     テーブル内の各 LRAW フィールドには、LRAW フィールドにデータの長さを格納する対応する PREC フィールドがあります。 SELECT 句なしで PREC フィールドで LRAW フィールドだけを指定すると、不適切なデータが抽出されている可能性があります。  
  
-   SAP システムで文字の比較、大文字小文字を区別します。 そのため、次の 2 つのクエリでは、異なる結果を返すことがあります。  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
    ```  
  
     And  
  
    ```  
    SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
    ```  
  
     Select クエリのフレーム化時に、右側のケースを使用することを確認します。 また、SAP システムでは、必ずしもすべての列が小文字または大文字の文字を含めることができます。 SAP の GUI を使用すると、テーブル内の列が小文字または大文字の文字を格納するかどうかを確認します。 SAP の GUI を使用する方法の詳細については、次を参照してください。[を決定するかどうか、列ストア小文字または大文字の値](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)です。  
  
-   WHERE 条件はいくつかのデータ値を持つフィールドの値の比較に対してのみサポートと*いない*他のテーブルのフィールド値を使用します。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]サポートしている 1 つのテーブル SELECT クエリ、テーブルのフィールド クエリの結合条件では、同じをサポートするために、結合条件を使用する必要があります。  
  
-   結合条件では、テーブル名を含める必要があります。  
  
     適切な SELECT ステートメントを次に示します  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     正しくない SELECT ステートメントを次に示します  
  
    ```  
    select A.x, B.y from A inner join B on m = n  
    ```  
  
-   結合条件で結合条件で、左側のテーブルは、条件の左側にする必要があり、結合条件の右側にある、結合条件の右側のテーブルを指定する必要があります。  
  
     結合条件を指定するための正しい方法を次に示します。  
  
    ```  
    select A.x, B.y from A inner join B on A.m = B.n  
    ```  
  
     結合条件を指定した場合の誤った方法を次に示します。  
  
    ```  
    select A.x, B.y from A inner join B on B.n = A.m  
    ```  
  
-   SELECT ステートメントには、JOIN 句で「と等しい」の条件のみを含めることができます。 以下に例を示します。  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
-   SELECT ステートメントは、SAP システムから文字列型の列を取得できません。  
  
-   SELECT ステートメントでは、1 つの結合だけを含める必要があります。 以下に例を示します。  
  
    ```  
    select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
    ```  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)