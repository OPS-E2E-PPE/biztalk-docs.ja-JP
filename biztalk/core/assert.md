---
title: アサート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3fcf26ae039999b4d4593f94ab4b8f375cd03a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528620"
---
# <a name="assert"></a>Filter
*アサーション*は、ビジネス ルール エンジンの作業メモリにオブジェクトのインスタンスを追加するプロセスです。 エンジンは、条件と一致-競合解決-アクション フェーズを使用して、インスタンスの型に対して記述されたアクションに従って各インスタンスを処理します。  
  
 次のトピックでは、動作を使用した、 **Assert**関数のさまざまなファクトの種類。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 各オブジェクトは、別個のインスタンスとして作業メモリにアサートされます。 つまり、インスタンスが、オブジェクトの型を参照する各述語によって分析される (たとえば、IF Object.Property = 1)。 ルールの条件の結果に依存して、型を参照するルール アクションで使用できるもされます。  
  
 次の例を考えてみましょう。  
  
 **ルール 1**  
  
```  
IF A.Value = 1  
THEN A.Status = "good"  
```  
  
 **Rule 2**  
  
```  
IF B.Value = 1  
THEN A.Status = "good"  
```  
  
 ルール 1 では、1 の値が A のインスタンスのみがその**状態**プロパティが更新されました。 ルール 2、ただし、条件の評価が場合**true**はのすべてのインスタンスがある、状態を更新します。 実際には、B の複数のインスタンスがある場合、A のインスタンスはたびに更新する条件の評価が**true** B のインスタンス。  
  
 ルール内から .NET オブジェクトをアサートするには、組み込みを追加することができます**Assert**ルールのアクションとして機能します。 ルール エンジンは、 **CreateObject**関数がビジネス ルール作成ツールで個別の関数としては表示されません。 その呼び出しは、操作ウィンドウに、ファクト エクスプ ローラーの .NET クラス ビューから作成するオブジェクトのコンス トラクター メソッドをドラッグして構築されています。 ビジネス ルール作成ツールには、コンス トラクターのメソッドに変換されます、 **CreateObject**ルール定義で呼び出します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 ときに、 **TypedXmlDocument**アサートすると、ビジネス ルール エンジンは、子を作成します。 **TypedXmlDocument**ルールで定義されたセレクターに基づいてインスタンス。  
  
 セレクターとフィールドは、両方の XPath 式です。 セレクターは、XML ドキュメント、および、セレクター内の特定の項目を識別するフィールドのノードを分離する方法として考えることができます。 1 つのセレクター内のすべてのフィールドは、エンジンによって、オブジェクトとしてまとめられます。 下のノードを選択すると、 **XML スキーマ** タブで、ファクト エクスプ ローラー、ビジネス ルール作成ツールが自動的に入力、 **XPath セレクター** 、すべてのノードのプロパティと**XPath フィールド**に子ノードが含まれていない任意のノードのプロパティ。 独自の XPath 式を入力する代わりに、 **XPath セレクター**と**XPath フィールド**必要な場合。  
  
 セレクターには、XML ドキュメントの複数の部分が一致すると、この種類の複数のオブジェクトがアサートまたはルール エンジンの作業メモリから取り消されます。 次の XML があると仮定します。  
  
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
  
 セレクター/ルート順序を使用する場合 (または/注文/)、2 つのオブジェクトが作業メモリに追加されます。  
  
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
  
 各セレクター内では、個々 のフィールドを Xpath によって呼びます。  
  
 セレクター/root/order/item を使用するかどうか (または (//order/item または//item)、4 つのオブジェクトがルール エンジン作業メモリ、Joe の 2 つの項目と Jane の 2 つの項目に追加されます。  
  
```  
<root>  
   <order customer="Joe">  
  
   </order>  
   <order customer="Jane">  
  
   </order>  
</root>  
```  
  
 各オブジェクトは、3 つのフィールドにアクセス-@name、 @quantity、および@costします。 オブジェクトは元のドキュメントへの参照では、親フィールドを参照できます (たとえば、"../@customer")。  
  
 同じドキュメント内の複数のセレクターを使用することができます。 これにより、(場合など、1 つのセクションでは、順序と、別のセクションには、出荷先住所が含まれています)、ドキュメントのさまざまな部分を表示することができます。 ただし、それを作成した、XPath 文字列によって作成されるオブジェクトが定義されていることに留意してください。 一意の結果、同じノードに解決される場合でも、別の XPath 式を使用して**TypedXmlDocument**します。  
  
 ルール エンジンは、参照型のオブジェクトおよびネイティブに基本的な .NET スカラー型をサポートします。 XML ドキュメントは、基本的に、テキストがフィールドの値は、ルールの作成時に指定された型に基づき、任意の型指定可能性があります。 また、フィールドは XPath 式であるために、ケース セットの最初の項目が値として使用されている、ノード セットを返す、可能性があります。  
  
 背後では、ルール エンジンでサポートされている型のいずれかにテキスト フィールドの値を変換できる、 **XmlConvert**関数。 これは、ビジネス ルール作成ツールの種類を設定を指定することができます。 変換が不可能な場合は、例外がスローされます。 種類**bool**と**二重**それぞれの型、文字列、またはオブジェクトとしてのみ取得できます。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 ときに、 **TypedDataTable**がアサートされると、すべて**Datarow**に含まれている、 **DataTable**としてエンジンにアサートが自動的に**TypedDataRows**. テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価される**TypedDataRows**、およびに対してではなく、 **TypedDataTable**します。  
  
 たとえば、"Customers"テーブルに対して構築された、次の規則があるとします。  
  
```  
IF Northwind.Customers.CustomerID = 001  
THEN Northwind.Customers.ContactTitle = "Purchasing Manager"  
```  
  
> [!NOTE]
>  使用する必要があります、データベース テーブルに対してルールを構築する**データ テーブル/データ行**データベース バインドの種類として。  
  
 次をアサートするとします**DataTable** 3 **Datarow**エンジンに (として、 **TypedDataTable**)。  
  
|CustomerID|[部署]|  
|----------------|------------------|  
|001|クラークを指定します。|  
|002|クラークを指定します。|  
|003|クラークを指定します。|  
  
 3 つのエンジンが挿入**TypedDataRows**:001、002、003  
  
 各**TypedDataRow**ルールに対して個別に評価します。 最初の**TypedDataRow**ルールの条件と 2 つの失敗を満たしています。 結果は次のようです。  
  
|CustomerID|[部署]|  
|----------------|------------------|  
|001|購買担当マネージャー|  
|002|クラークを指定します。|  
|003|クラークを指定します。|  
  
> [!NOTE]
>  TypedDataRows も、エンジンにアサート直接ことができます。 これらには、前述のと同じ方法で処理されます。  
  
 **DataSetName.DataTableName**一意識別子と見なされます。 そのため、2 番目の場合**TypedDataTable**がアサートされた同じ**データセット**名と**DataTable**名、1 つ目の後継となります**TypedDataTable**. すべて**TypedDataRow**s が最初に関連付けられている**TypedDataTable**は取り消され、2 番目**TypedDataTable**がアサートされます。  
  
## <a name="dataconnection"></a>DataConnection  
 同様、 **TypedDataTable**、結果、返されたに対してルールが作成、ビジネス ルール作成ツールでルールの引数としてテーブルまたは列をドラッグ**TypedDataRow**ではなく、 **DataConnection**自体。  
  
 たとえば、次の規則が作成されると**DataConnection**アサートされる、 **SqlConnection** Northwind.Customers に。  
  
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
  
 データベースの 1 つだけの行が 1 つだけ、この条件を満たしているので**TypedDataRow**が作成され、さらに処理エンジンにアサートします。  
  
## <a name="summary-of-asserted-entities-and-instance-types"></a>アサートされるエンティティとインスタンスの型の概要  
 次の表は、それらを識別するためにそれらのインスタンスのそれぞれに適用される型と同様に、アサートされた各エンティティのエンジンで作成された結果として得られるインスタンスの数を示す、さまざまな種類の assert の動作をまとめたものです。  
  
|Entity|アサートされるインスタンスの数|インスタンスの種類|  
|------------|----------------------------------|-------------------|  
|.NET オブジェクト|1 (オブジェクト自体)|完全修飾 .NET クラス|  
|TypedXmlDocument|1 ~ n 個の TypedXmlDocument (s):作成されるセレクター バインドとドキュメントのコンテンツに基づく|DocumentType.Selector|  
|TypedDataTable|1 ~ n 個の TypedDataRow (s):<br /><br /> DataTable 内の各 DataRow のいずれか|DataSetName.DataTableName|  
|TypedDataRow|1 (アサートされる TypedDataRow)|DataSetName.DataTableName|  
|DataConnection|1 ~ N (DataConnection の照会によって返される各 typeddatarow につき 1 つ)|DataSetName.DataTableName|  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)