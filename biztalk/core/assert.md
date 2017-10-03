---
title: "アサート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine], .NET objects
- Assert function [Business Rules Engine], TypedXMLDocument
- Assert function [Business Rules Engine]
- Assert function [Business Rules Engine], examples
- Assert function [Business Rules Engine], TypedData table
- Assert function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e9989214-3c10-4691-9c38-f6fe64e511ed
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2de66aab5cde0a9515f41713d3390632180fbff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assert"></a>Filter
*アサーション*プロセスをビジネス ルール エンジンの作業メモリにオブジェクトのインスタンスを追加することです。 エンジンは、一致、競合解決、アクションの各フェーズを使用し、その種類のインスタンスに対して記述された条件とアクションに基づいて各インスタンスを処理します。  
  
 以下のトピックを使用してに起因する動作を説明する、 **Assert**異なるファクトの種類の関数。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 各オブジェクトは、別々のインスタンスとして作業メモリにアサートされます。 つまり、インスタンスはオブジェクトの種類を参照する各述語によって分析されます (IF Object.Property = 1 など)。 ルール条件の結果によっては、その種類を参照するルール アクションからも使用できます。  
  
 次の例を考えてみましょう。  
  
 **ルール 1**  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 **規則 2**  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 1 の値を持つ A のインスタンスのみを持つルール 1 で、**ステータス**プロパティが更新されました。 ルール 2、ただし、条件の評価が場合**true**はのすべてのインスタンスがある状態が更新されました。 実際には、B の複数のインスタンスがある場合、A のインスタンスはたびに更新する条件の評価が**true** B のインスタンス。  
  
 ルール内から .NET オブジェクトをアサートするには、組み込みを追加することができます**Assert**ルールのアクションとして機能します。 ルール エンジンは、 **CreateObject**関数が、ビジネス ルール作成ツールで別の関数として表示されません。 この関数を呼び出すには、作成するオブジェクトのコンストラクター メソッドをファクト エクスプローラーの .NET クラス ビューからアクション ペインにドラッグします。 ビジネス ルール作成ツールは、コンス トラクター メソッドにし、変換、 **CreateObject**ルールの定義で呼び出します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 ときに、 **TypedXmlDocument**がアサートすると、子を作成するビジネス ルール エンジン**TypedXmlDocument**ルールで定義されたセレクターに基づいてインスタンス。  
  
 セレクターとフィールドは両方とも XPath 式です。 セレクターは、XML ドキュメントのノードを分離するための方法として、フィールドは、セレクター内の特定の項目を識別するものとしてとらえることができます。 各セレクター内のすべてのフィールドは、エンジンによって 1 つのオブジェクトとしてまとめられます。 下のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー、ビジネス ルール作成ツールが自動的に入力、 **XPath セレクター** 、すべてのノード プロパティおよび**XPath フィールド**に子ノードが含まれていない任意のノードのプロパティです。 独自の XPath 式を入力する代わりに、 **XPath セレクター**と**XPath フィールド**必要な場合です。  
  
 セレクターが XML ドキュメントの複数の部分と一致すると、この種類の複数のオブジェクトとルール エンジンの作業メモリとの間でアサートまたは取り消しが行われます。 たとえば、次の XML があるとします。  
  
```  
<root>  
   <order customer="Joe">  
      <item name="router" quantity="10" cost="550" />  
      <item name="switch" quantity="3" cost="300" />  
   </order>  
   <order customer="Jane">  
      <item name="switch" quantity="1" cost="300" />  
      <item name="cable" quantity="23" cost="9.99" />  
   </order>  
</root>  
```  
  
 セレクター /root/order (または //order) を使用すると、2 つのオブジェクトが作業メモリに追加されます。  
  
 1\)  
  
```  
<order customer="Joe">  
   <item name="router" quantity="10" cost="550" />  
   <item name="switch" quantity="3" cost="300" />  
</order>  
```  
  
 2\)  
  
```  
<order customer="Jane">  
   <item name="switch" quantity="1" cost="300" />  
   <item name="cable" quantity="23" cost="9.99" />  
</order>  
```  
  
 各セレクター内で、個々のフィールドは XPath によって参照されます。  
  
 セレクター/root/order/item を使用するかどうか (または (//order/item または//item)、4 つのオブジェクトがルール エンジン作業メモリ、Joe の 2 つの項目と Jane の 2 つの項目に追加されます。  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 各オブジェクトは、3 つのフィールドにアクセス-@name、 @quantity、および@costです。 オブジェクトは、元のドキュメントへの参照であるために、親フィールドを参照できます (たとえば、"../@customer") です。  
  
 同じドキュメント内でも、複数のセレクターを使用することができます。 これにより、ドキュメントのさまざまな部分 (注文を示すセクションと発送先住所を示すセクションなど) を表示することが可能になります。 ただし、作成されるオブジェクトは作成元の XPath 文字列によって定義されることを覚えておく必要があります。 一意の結果、同じノードに解決される場合でも、別の XPath 式を使用して**TypedXmlDocument**です。  
  
 ルール エンジンは、基本的な .NET スカラー型をネイティブでサポートしているだけでなく、参照型のオブジェクトもサポートしています。 XML ドキュメントは基本的にテキストですが、ルールの作成時に指定された型に基づいており、フィールド値の型は任意です。 また、フィールドは XPath 式であるため、ノード セットを返す場合があります。この場合は、セット内の最初の項目が値として使用されます。  
  
 背後では、ルール エンジンは、によってサポートされている種類のいずれにもテキスト フィールドの値を変換できます、 **XmlConvert**関数。 これを指定するには、ビジネス ルール作成ツールで型を設定します。 変換が不可能な場合は、例外がスローされます。 種類**bool**と**二重**それぞれの型、文字列、またはオブジェクトとしてのみ取得できます。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 ときに、 **TypedDataTable**がアサートされ、すべて**Datarow**に含まれている、 **DataTable**としてエンジンにアサートが自動的に**TypedDataRows**. テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価されます**TypedDataRows**、およびに対してではなく、 **TypedDataTable**です。  
  
 たとえば、"Customers" テーブルに対して作成された次のルールがあるとします。  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  データベース テーブルに対して、ルールを作成するを使用する必要があります**データ テーブル/データ行**データベース バインドの種類として。  
  
 次をアサートすると仮定**DataTable**を 3 つ**Datarow**エンジンに (として、 **TypedDataTable**)。  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|Supply Clerk|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
 エンジンは 3 つを挿入します。 **TypedDataRows**: 001、002、003 です。  
  
 各**TypedDataRow**ルールに対して個別に評価されます。 最初の**TypedDataRow**ルールの条件と残りの 2 つの失敗を満たしています。 結果を次に示します。  
  
|CustomerID|ContactTitle|  
|----------------|------------------|  
|001|Purchasing Manager|  
|002|Supply Clerk|  
|003|Supply Clerk|  
  
> [!NOTE]
>  TypedDataRow はエンジンに直接アサートすることもできます。 その場合も前述の方法で処理されます。  
  
 **DataSetName.DataTableName**は一意の識別子であると見なされます。 したがって場合、2 番目**TypedDataTable**がアサートされた同じ**データセット**名と**DataTable**名、最初のによって置き換えられる**TypedDataTable**. すべて**TypedDataRow**に最初の関連付けられている**TypedDataTable**は取り消され、2 番目**TypedDataTable**がアサートします。  
  
## <a name="dataconnection"></a>DataConnection  
 同様、 **TypedDataTable**、ビジネス ルール作成ツールでルールの引数としてテーブルまたは列をドラッグする結果、返されたに対してルールが作成、 **TypedDataRow**そのものではなく、 **DataConnection**自体です。  
  
 たとえば、次の規則を作成して**DataConnection**を格納しているがアサートされる、 **SqlConnection** Northwind.Customers に。  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
 エンジンがで使用されるルールと評価される場合、 **TypedDataTable**  セクションで、動的に作成し、次のようなクエリ。  
  
```  
SELECT *  
FROM Northwind.Customers  
WHERE CustomerID = 1  
```  
  
 データベース内の行を 1 つだけがこの条件は、1 つだけを満たすため**TypedDataRow**が作成され、さらに処理エンジンにアサートします。  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a>アサートされるエンティティとインスタンスの種類の要約  
 次の表は、エンジンにアサートされたエンティティごとで作成された結果として得られるインスタンスの数を示す、さまざまな種類だけでなくそれらのインスタンスを識別するためのそれぞれに適用される型のアサートの動作をまとめたものです。  
  
|Entity|アサートされるインスタンスの数|インスタンスの種類|  
|------------|----------------------------------|-------------------|  
|.NET オブジェクト|1 (オブジェクト自体)|完全修飾 .NET クラス|  
|TypedXmlDocument|1 ～ N 個の TypedXmlDocument (作成されるセレクター バインドとドキュメントのコンテンツに基づく)|DocumentType.Selector|  
|TypedDataTable|1 ～ N 個の TypedDataRow<br /><br /> (DataTable の各 DataRow につき 1 個)|DataSetName.DataTableName|  
|TypedDataRow|1 (アサートされる TypedDataRow)|DataSetName.DataTableName|  
|DataConnection|1 ～N 個 (DataConnection の照会によって返される各 TypedDataRow につき 1 個)|DataSetName.DataTableName|  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)