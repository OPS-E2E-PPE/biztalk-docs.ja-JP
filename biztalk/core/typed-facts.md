---
title: 型指定されたファクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine library
- Business Rule Composer, typed facts
- ITypedFact interface
- DataConnection class
- facts, typed
- TypedDataTable class
- TypedDataRow class
- TypedXmlDocument class
ms.assetid: 8207bfd5-ebd2-45ac-8992-795acdf3ba4c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6041a64fcc4b3496c319a25a2ce758ed7f52a71
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="typed-facts"></a>型指定されたファクト
*型指定されたファクト* クラスを実装するには、 **ITypedFact** インターフェイス: **TypedXmlDocument**, 、**DataConnection**, 、**TypedDataTable**, 、および **TypedDataRow**します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 **TypedXmlDocument** クラスは、ビジネス ルール フレームワークで XML ドキュメントの種類を表します。 2 つの XPath 式を作成するルールの引数として、XML ドキュメントのノードを使用する場合: セレクターとフィールド バインドします。  
  
 ノードに子ノードがあるない場合、 *セレクター バインド* (XmlDocument バインド) がノードの親ノードを作成し、 *フィールドのバインド* ノード自体を (XmlDocumentMember バインドとも呼ばれます) を作成します。 このフィールド バインドはセレクター バインドと相対的な関係にあります。 ノードに子ノードがある場合は、そのノードにセレクター バインドが作成され、フィールド バインドは作成されません。  
  
 次のスキーマがあると仮定します。  
  
 ![ファクト エクスプ ローラーに表示されたサンプル スキーマ](../core/media/xmldocumentbrowser.gif "xmldocumentbrowser")  
Case.xsd  
  
 Income ノードが選択されている場合は、このノードに子ノードがないため、セレクター バインドのみが作成されます。 既定の XPath 式、 **XPath セレクター** プロパティ ペインのプロパティが含まれています。  
  
```  
/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']/*[local-name()='Income' and namespace-uri()='']  
```  
  
 一方、Name ノードが選択されている場合は、セレクター バインドとフィールド バインドが作成されます。 バインド情報は次のようになります。  
  
|プロパティ|値|  
|--------------|-----------|  
|**XPath フィールド**|*[local-name()='Name' and namespace-uri()='']|  
|**XPath セレクター**|/*[local-name()='Root' and namespace-uri()='http://LoansProcessor.Case']|  
  
 ノードをルールの引数にドラッグする前に、XML ノードに対する既定の XPath 式を変更することもできます。これにより、新しいバインド情報がポリシーに含められます。 ただし、XPath 式に加えた編集はすべて、スキーマを再読み込みするときにビジネス ルール作成ツールで再入力する必要があります。  
  
 XML ノードのボキャブラリ定義が作成される際、バインドの XPath 式には、前に説明したルールに基づいた同様の既定値が設定されますが、これはボキャブラリ定義ウィザードで編集できます。 式に加えた変更はボキャブラリ定義に含められ、その定義から作成されたルールの引数すべてに反映されます。  
  
## <a name="dataconnection"></a>DataConnection  
 **DataConnection** .NET クラスに追加された、 **RuleEngine** ライブラリです。 .NET が含まれている **SqlConnection** インスタンスおよび **データセット** 名。 **データセット** 名では、一意の識別子を作成することができます、 **SqlConnection** され、結果の型を定義する際に使用されます。  
  
 **DataConnection** クラスには、パフォーマンスを最適化するには、ビジネス ルール エンジンが用意されています。 エンジンの非常に大規模なデータベース テーブルにアサートするのではなく (**TypedDataTable** クラス) 多数のデータベース行が含まれている可能性があります (**TypedDataRow** クラス) は、ポリシーに関連するでは、軽量をアサートする **DataConnection**します。 ルールの述語やアクションとクエリに基づく SELECT クエリを動的に作成し、エンジンは、ポリシーを評価するとき、 **DataConnection** の実行時。 たとえば、次のようなルールがあるとします。  
  
```  
IF NorthWind.Products.UnitPrice >= 0   
THEN <do something>  
```  
  
 次の SQL クエリは、ルールで生成されます。  
  
```  
Select * From [Product] Where [UnitPrice] >= 0  
```  
  
 クエリの結果がデータ行としてエンジンにアサートされます。  
  
> [!NOTE]
>  使用、 **OleDbConnection** で、 **DataConnection** は現在サポートされていません。  
  
 ルール条件またはアクションで使用するデータベースのテーブルまたは列を選択するときに、いずれかを使用してオブジェクトにバインドできます **DataConnection** または **TypedDataTable** から データ接続 または データベースのテーブルの行/"を選択して、 **データベース バインドの種類**ドロップダウン ボックスの プロパティ ウィンドウで、 **データベース** ファクト エクスプ ローラーのタブをクリックします。  
  
> [!NOTE]
>  既定では DataConnection バインドが使用されます。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 ADO.NET をアサートする **DataTable** 、エンジンにオブジェクトが他の .NET オブジェクトと同様に扱われます。 ほとんどの場合は代わりにするルール エンジン クラスをアサート **TypedDataTable**します。  
  
 **TypedDataTable** ADO.NET を含んでいるラッパー クラスは、 **DataTable**します。 コンス トラクターを受け取り、 **DataTable**します。 テーブルまたはテーブルの列がルールの引数として使用される、個人に対して式が評価されます **TypedDataRow** ラッパーでなく、 **TypedDataTable**します。  
  
## <a name="typeddatarow"></a>TypedDataRow  
 これは、ADO の型指定されたファクト ラッパー **DataRow** オブジェクトです。 ビジネス ルール作成ツールでルールの引数にテーブルまたは列をドラッグする結果、返されたに対してルールが作成、 **TypedDataRow** ラッパーです。  
  
## <a name="see-also"></a>参照  
 [ファクト](../core/facts.md)