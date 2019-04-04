---
title: SAP の SELECT ステートメントの構文 |Microsoft Docs
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b3cb47df9b151de741b0e64f21041a60b9c90d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970715"
---
# <a name="syntax-for-a-select-statement-in-sap"></a>SAP の SELECT ステートメントの構文
次のセクションでは、文法仕様に対する SELECT クエリを実装するための記述、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]します。 いくつかの場合、構文が少し異なる基本の TRANSACT-SQL 構文に注意してください。  
  
```  
SELECT {TOP <const> }[0,1] <select_list>  {INTO FILE [‘file_name’ | “file_name”]   
{DELIMITED}[0,1]}[0,1]  FROM table_name  {AS alias_name }[0,1]    
{INNER JOIN table_name {AS alias_name}[0,1] ON  <Join_Condition>}[0,1]  
{ WHERE <predicate> } [0,1] {;}[0,1]   
[OPTION 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'  
```  
  
 各要素の説明は次のとおりです。  
  
- **<select_list>** = `[ {table_name.}[0,1]column_name { AS alias_name } [0,1] } [ 1, …n ]`  
  
- **<Join_Condition>** = `[Alias_name.|table_name.]column_name <expr> [Alias_name.|table_name.]column_name`  
  
- **\<predicate\>** = `[ predicate [AND|OR] predicate [between|not between] predicate |  NOT predicate |  ‘(‘ predicate ‘)’ | condition ]`  
  
  サポートされている条件と式は。  
  
- **\<条件\>** = `[ expr | expr [NOT | ] BETWEEN const AND const | expr [NOT | ] LIKE const ]`  
  
- **\<expr\>** = `[ const | column_name [= | ! = | > | > = | ! > | < | < = | ! < ] const | column_name | - const  | const | column_name ]`  
  
  場所 **\<const\>** = `integer | real | string | ? | NULL | xml_element`します。  
  
  **オプションのキーワードの値**  
  
  としてオプションを指定できます`OPTION '<option>'`ここで、 `<option> = 'no_conversion' | 'batchsize <size>' | 'disabledatavalidation'`  
  
- **No_conversion**オプション。  
  
  -   場合、 **no_conversion**オプションを使用し、同等の .NET 型を使用して、テーブル内のフィールドが公開されます。 SAP のデータ型の .NET 相当するものについては、[SAP データ型の基本的な](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)を参照してください。  
  
  -   場合、 **no_conversion**フィールドに、変換がないかどうかは、定義された終了オプションは使用されませんし、同等の .NET 型を使用してテーブル内のこれらのフィールドが公開されます。 SAP のデータ型の .NET 相当するものについては、[SAP データ型の基本的な](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)を参照してください。  
  
  -   ときに、 **no_conversion**オプションを使用しないと変換されていないかどうかは、定義されている終了し、テーブル内のこれらのフィールドが .NET 文字列として公開されます。  
  
- 設定すると**batchsize\<サイズ\>**、SELECT ステートメントの実行と複数の呼び出しを SAP システムおよび各呼び出しでのみ\<サイズ\>レコードの数取得されます。 たとえば、指定した ' batchsize 100'、SELECT クエリは、SAP システムへの各呼び出しでのみ 100 個のレコードを取得します。 場合**batchsize\<サイズ\>** が指定されていない、10,000 の既定値は、バッチ サイズと見なされます。 SAP システムで、コンピューターと行の数の物理メモリに基づくバッチ サイズの最適の値を指定する必要がありますに注意してください。 バッチ サイズの最適の値を指定するときにエラーがメモリ不足例外があります。  
  
- 設定すると**disabledatavalidation**、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] DATS、TIM、NUMC 列に存在する値を検証しませんが、代わりに文字列として公開されます。  
  
   これは DATS、TIM、および NUMC 列に無効なデータを持つ SAP テーブルからデータを取得する ADO.NET クライアントが失敗するシナリオで役立ちます。 SAP DATS、TIM、および NUMC 列に存在するデータが無効なため、データの読み取りを試みている ADO.NET クライアントは、無効なデータを解析することはできませんし、例外がスローされます。 場合、 **disabledatavalidation** SELECT のクエリでは、オプションを設定してください。、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]無効なデータを解析しませんが、それらを文字列として抽出します。  
  
> [!IMPORTANT]
>  たとえば、常に単一引用符で囲まれたオプションのキーワードの値を指定する必要があります '*disabledatavalidation*'。  
  
 たとえば、ステートメントを参照してください[SELECT ステートメントの例](../../adapters-and-accelerators/adapter-sap/examples-for-select-statement.md)します。  
  
## <a name="predicates-syntax"></a>述語の構文  
 次の例は、SELECT ステートメントで述語を使用するための文法を指定します。  
  
 `Predicate`[ ] :  
  
```  
Predicates [AND | OR] Predicates [between|not between] Predicates | [NOT] Predicates | '(' Predicates ')' | Condition  
```  
  
 `Condition`[ ] :  
  
```  
Expr | LExpr [NOT] BETWEEN RExpr AND RExpr | LExpr [NOT] LIKE Const  
```  
  
 `Expr`[ ] :  
  
```  
LExpr [=|!=|>|>=|!>|<|<=|!<] RExpr>  
```  
  
 `LExpr`[ ] :  
  
```  
ColumnName  
```  
  
 `RExpr`[ ] :  
  
```  
Const | PlaceHolder  
```  
  
 `ColumnName`[ ] :  
  
```  
Column | TableName.Column | '['Column']'  
```  
  
 `Tablename`[ ] :  
  
```  
Table | '['Table']'  
```  
  
## <a name="considerations-when-calling-a-select-statement"></a>SELECT ステートメントを呼び出す際の考慮事項  
 このセクションに一覧表示されたポイントを含む SELECT ステートメントを使用する場合は、点に注意する必要があります[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。  
  
- をパラメーターまたはクエリの日付/時刻値を指定する場合は、文字列として値を指定します。 SAP の日付と時刻の形式で日付と時刻の文字列を提供します。  
  
  - `SAP date format`: YYYYMMDD  
  
     たとえば、2004 年の日 11 月 10 日 SAP クエリでは表現 '20041110' です。  
  
     2004 年日文字列 p1 は SAPParameter p1 の 11 月 10 日のです。値 = '20041110'。  
  
  - `SAP time format`: 時刻  
  
     たとえば、時間 10時 34分: 32 SAP クエリでは表現 '103432' です。  
  
     時間 10時 34分: 32 SAPParameter p2 では、文字列の p2 です。値 = '103432'。  
  
    SELECT ステートメントの[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]返します`DATE`フィールドの値として .NET`System.DateTime`オブジェクトを返します`TIME`フィールドの値として`System.TimeSpan`オブジェクト。 場合、SAP の値`DATE`オブジェクトが許容される SQL Server の最小値より小さい (`1/1/1753`)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]この最小値を返す`1/1/1753`します。  
  
- 特殊文字「#」を使用する場合、SELECT クエリの TOP 句で"^"、"&"、「%」とする前に、または整数の後に、特殊文字は無視されます、エラー メッセージは生成されませんが。 たとえば、次は無視されます、SELECT クエリの TOP 句で。  
  
   \#5, 5 ^、% 5%、または 5 (&)  
  
   ただし、5 のように、整数の間でこれらの文字を使用して、5 ドルが、エラーをスローします。  
  
- テーブルのスキーマで返される列名は、すべて大文字の文字として返されます。 クエリの結果がフィールドに設定するなど、`Last Name`列見出しを返します`LAST NAME`します。 一意性を回避するために SELECT ステートメントではすべて大文字を使用して、競合の使用をお勧めします。  
  
- SELECT クエリでは、LIKE 句で、パーセント記号、(0 個以上の文字の文字列) の「%」と、アンダー スコアのみ **「_」** (任意の 1 文字) が使用できる特殊文字。 その他のすべての特殊文字は、文字列値と見なされますが、無視されます。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] Z_EXTRACT_DATA_OO RFC を使用して SAP システムで SELECT クエリを実行します。 RFC では、次の条件を満たすテーブルからデータを読み取るサポートしています。  
  
  - テーブルの TabClass は TRANSP、クラスター、またはプールです。  
  
  - TabClass はビューと ViewClass が D または P.  
  
    SELECT ステートメントでは、これらの条件を満たすテーブルからデータを読み取ることを確認します。  
  
- 255 文字、たとえば文字列、RAWSTRING、LRAW、VARC、および LCHAR が実行できるデータ型の値は、SELECT クエリでは使用できません。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]に付属のカスタム RFC を使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]Z_EXTRACT_DATA_OO、SAP システムに対して SELECT クエリを実行します。 このカスタム RFC は 255 文字以上が実行できる任意のデータ型をサポートしていません。  
  
- 列または SELECT ステートメントでサポートされているフィールドの最大数は、1000 です。  
  
- WHERE 句でサポートされている述語の最大数は、100 です。  
  
- 同じ SELECT ステートメントで複数回、同じフィールドを選択することはサポートされていません。 使用されるカスタム RFC (Z_EXTRACT_DATA_OO)、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]実行する前に、ステートメントから重複するフィールドを削除します。 たとえば、次のステートメント。  
  
   `SELECT BUKRS, BUKRS, BUKRS from T001`  
  
   このステートメントのように記述できるように実行します。  
  
   `SELECT BUKRS from T001`  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントでは、エイリアスの重複名をサポートしません。 そのため、次の SELECT ステートメントでは、エラーがスローされます。  
  
  ```  
  SELECT KUNNR AS [MYKNA1], JMJAH AS MYKNA1 from KNA1 where KUNNR LIKE 'T-S62A08' AND JMJAH=1995  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 重複する列名を伴う SELECT ステートメントはサポートされません。 そのため、次の SELECT ステートメントでは、エラーがスローされます。  
  
  ```  
  SELECT KUNNR AS [MYKNA1], KUNNR AS MYKNA2 from KNA1 where MYKNA2='T-S62A08'  
  ```  
  
- SAP では、テーブルで NULL 値は格納されません。 結果として、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで、"IS NULL"値をサポートしていません。 そのため、次の SELECT ステートメントでは、エラーがスローされます。  
  
  ```  
  SELECT NAME1, PSTLZ  from KNA1 where CITY IS NULL AND NAME1 LIKE '%MODE%'  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT ステートメントで ORDER BY 句をサポートしません。 そのため、次の SELECT ステートメントでは、エラーがスローされます。  
  
  ```  
  SELECT NAME1  AS [MYNAME],  LAND1, KUNNR  from KNA1 where NAME1 LIKE '%MODE%'  ORDER BY NAME1  ASC  
  ```  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP テーブル内のすべてのフィールドを選択するアスタリスク (*) を指定することはできません。 そのため、次の SELECT ステートメントでは、エラーがスローされます。  
  
  ```  
  SELECT spfli.* from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   すべてのフィールドを選択するには、フィールド名を個別に指定する必要があります。  
  
- SELECT ステートメントの一部として、SELECT ステートメントの出力を書き込むファイルを指定できます。 ただし、出力ファイルがネットワーク共有上にある場合は、必ず、SAP サービスが実行されている SAP のサービス アカウントがネットワーク共有に対する書き込み権限。 以下に例を示します。  
  
  ```  
  SELECT * into file '\\share\output.txt' from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
   前の例では、SAP のサービス アカウントに名前「共有」を使用したネットワーク共有に対する書き込み権限があります。  
  
- SELECT ステートメントを使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SELECT クエリで引数の値のパラメーターの名前をサポートしています。 ただし、パラメーター名に関して規則に従うことを確認します。  
  
  -   SELECT のクエリで、"\@"記号はパラメーターの名前を付ける必要があります。  
  
  -   "\@"シンボルは、英字 (A ~ Z または a ~ z) の後になければなりません。  
  
  -   パラメーター名は文字の英数字を含めることができます (A ~ Z、a ~ z、または 0 ~ 9) と特殊文字。 パラメーター名に含めることができる唯一の特殊な文字はアンダー スコア「_」と「#」のハッシュは。  
  
- ビューで SELECT クエリを実行すると、ベース テーブルの主キー列がビューに存在してもすることを確認します。 また、実際には、ビューの主キー列として列もマークする必要があります。  
  
   主キー列がビューに存在しない場合は、ビューの SELECT クエリが、例外が発生します。  
  
- LRAW 型のフィールドを選択するテーブルで SELECT クエリを実行すると、対応する PREC フィールドを選択することを確認します。 また、PREC フィールドは、SELECT 句で LRAW フィールドの前にすぐに表示する必要があります。  
  
   テーブル内のすべての LRAW フィールドには、LRAW フィールドにデータの長さを格納する対応する PREC フィールドがあります。 PREC フィールドことがなく、SELECT 句で LRAW フィールドだけを指定すると、不適切なデータが抽出される可能性があります。  
  
- SAP システムでは、文字の比較は大文字小文字を区別します。 そのため、次の 2 つのクエリでは、異なる結果を返す可能性があります。  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'D%'  
  ```  
  
   And  
  
  ```  
  SELECT * FROM KNA1 WHERE LAND1 LIKE 'd%'  
  ```  
  
   Select クエリのフレーム化時に適切な場合を使用することを確認します。 また、SAP システムでは、一部の列が小文字または大文字の文字を含めることができます。 SAP GUI を使用して、テーブル内の列が小文字または大文字の文字を格納するかどうかを確認することができます。 SAP GUI の使用方法の詳細については、[を決定するかどうかを列ストア小文字または大文字の値](../../adapters-and-accelerators/adapter-sap/determining-whether-a-column-stores-lowercase-or-uppercase-values.md)を参照してください。  
  
- WHERE 条件はいくつかのデータ値をフィールド値の比較に対してのみサポートと*いない*とその他のテーブルのフィールド値。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]サポートしている 1 つのテーブル SELECT クエリ、テーブルのフィールド クエリの結合条件では、同じをサポートするために、結合条件を使用する必要があります。  
  
- 結合条件では、テーブル名を含める必要があります。  
  
   次に適切な SELECT ステートメント  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   次に、正しくない SELECT ステートメント  
  
  ```  
  select A.x, B.y from A inner join B on m = n  
  ```  
  
- 結合条件で結合条件で左テーブルは、条件の左側にあるべきし、結合条件の右側にある右側のテーブルの結合条件を指定する必要があります。  
  
   結合条件を指定する正しい方法を次に示します。  
  
  ```  
  select A.x, B.y from A inner join B on A.m = B.n  
  ```  
  
   結合条件を指定するを誤った方法を次に示します。  
  
  ```  
  select A.x, B.y from A inner join B on B.n = A.m  
  ```  
  
- SELECT ステートメントには、JOIN 句の「等しい」の条件のみ含めることができます。 以下に例を示します。  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
- SELECT ステートメントは、SAP システムから文字列型の列を取得できません。  
  
- SELECT ステートメントでは、1 つの結合のみを含める必要があります。 以下に例を示します。  
  
  ```  
  select * from spfli inner join sflight on spfli.carrid = sflight.carrid  
  ```  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
