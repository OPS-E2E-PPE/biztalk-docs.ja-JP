---
title: Null および DBNull を処理する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255042"
---
# <a name="how-to-handle-null-and-dbnull"></a>Null および DBNull を処理する方法
このトピックでは、さまざまな型に関連する Null 値が処理されるときの予期される動作、および特定のフィールドまたはメンバーについて Null または存在の有無をチェックするためのオプションについて説明します。  
  
## <a name="xml"></a>XML  
 次の説明は XML に関係します。  
  
-   ドキュメントから XML 値が Null として返されることはありません。 これは空の文字列または "存在しない" エラーのいずれかです。 空の文字列の場合は、特定の型 (たとえばルール作成時に整数型として指定されたフィールド) の変換でエラーが発生する場合があります。  
  
-   ビジネス ルール作成ツールで許可するフィールドを null に設定したりするためのフィールドの種類を設定していない**オブジェクト**です。  
  
-   オブジェクト モデルを使用型を設定できます**オブジェクト**です。 この場合、返される値は、XPath の評価結果の種類- **float**、**ブール**、または**文字列**XPath 式に応じて、します。  
  
## <a name="net-classes"></a>.NET クラス  
 次の説明は .NET クラスに関係します。  
  
-   戻り値の型がない場合、null と比較することはできません、**オブジェクト**型です。  
  
-   値の型以外のパラメーターには Null をパラメーターとして渡せますが、メンバーの実装によっては実行時エラーが発生する場合があります。  
  
-   派生した型のフィールドを設定することができます**オブジェクト**を null にします。  
  
## <a name="data-connection"></a>データ接続  
 次の説明はデータ接続に関係します。  
  
-   Null には、データベース テーブルの列を比較するには、テーブル、列の null を許可すると、列の型が**テキスト**、 **ntext**、および**イメージ**です。  
  
    > [!NOTE]
    >  ビジネス ルール作成ツールでは、型の列を使用することができます**テキスト**と**ntext**条件にします。 ただし、そのポリシーを実行すると、"IS NULL または LIKE 演算子を使用している場合を除き、テキスト、ntext、および画像のデータ型の比較や並べ替えはできません" というエラー メッセージが表示されます。  
  
-   データベース テーブルの列に対してテーブルで Null が許可されている場合は、その列を Null に設定できます。  
  
-   ビジネス ルール作成ツールへのバインドで、メンバーの種類を自動的に設定**オブジェクト**比較またはに設定した場合、値型の場合は null です。 リセットするか、引数を置換する場合、元の型に変更します。  
  
-   文字列型の場合に型を変更**オブジェクト**かどうかを null に設定が状態のままを文字列として null と比較する場合。  
  
-   比較またはに設定することはできません**DBNull.Value** 、ビジネス ルール作成ツールから、列の型には変化しないため**オブジェクト**です。  
  
-   エンジンでは、比較の際に DBNull 値が Null に変換され、データベースに挿入する際に Null が DBNull 値に変換されます。  
  
-   テストでは Null 値が無視されます (SQL Server の動作)。 たとえば、"IF db.column > 5 THEN" というルールがある場合は、db.column に値がある行のみがテストされ、Null を含んでいる行はスキップされます。  
  
## <a name="typeddatatable-and-typeddatarow"></a>TypedDataTable および TypedDataRow  
 次の説明は TypedDataTable および TypedDataRow に関係します。  
  
-   ビジネス ルール作成ツールの変更、フィールドの種類を**オブジェクト**と同じ方法で**DataConnection**s。  
  
-   Null と比較する場合を除いて、Null 値があるとテストは失敗します。 たとえば、アサートされた行に Null 値が含まれている場合は、ルール "IF db.column > 5 THEN" でエラーが発生します。  
  
     条件は同時に評価されるため、"IF db.column != NULL AND db.column > 5 THEN  " のようなテストも失敗するので注意してください。これは、すべての行で両方のテストが評価される可能性があるからです。  
  
## <a name="checking-for-null-or-existence"></a>Null または存在の有無のチェック  
 ビジネス ルールを作成するときには、通常、フィールドの値を比較する前にそのフィールドの存在を確認します。 ただし、フィールドが Null かまたは存在しない場合に値を比較すると、エラーが発生します。 たとえば、次のルールがあるとします。  
  
 IF Product/Quantity Exists AND Product/Quantity > 1  
  
 Product/Quantity が存在しない場合は、ルールでエラーがスローされます。 この問題を回避する 1 つの方法として、要素の値が存在する場合にその値を返し、存在しない場合は別のものを返すヘルパー メソッドに親ノードを渡します。 次のルールを見てください。  
  
 **ルール 1**  
  
 IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)  
  
 **規則 2**  
  
 IF Helper.Value == X THEN...  
  
 もう 1 つの解決方法として考えられるのは、次のようなルールを作成することです。  
  
 IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)  
  
 この例では、CheckQuantityAndDoSomething 関数がパラメーター値をチェックし、条件が満たされていれば処理を実行します。  
  
> [!NOTE]
>  XPath を変更する代わりに、**フィールド**が、エラーをキャッチする XML ファクトのプロパティが方法をお勧めします。