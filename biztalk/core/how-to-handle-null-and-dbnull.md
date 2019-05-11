---
title: Null および DBNull を処理する方法 |Microsoft Docs
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
ms.openlocfilehash: ea5635e289ce1d510e7e2701c79eeb3c9543b54e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385010"
---
# <a name="how-to-handle-null-and-dbnull"></a>Null および DBNull を処理する方法
このトピックでは、さまざまな種類に関連付けられている null 値を処理するときに予期される動作について説明し、null または特定のフィールドまたはメンバーの存在をチェックするためのオプションについて説明します。  
  
## <a name="xml"></a>XML  
 次の XML に適用されます。  
  
-   XML 値は、null としてのドキュメントからは返されません。 空の文字列または「存在しません」エラーのいずれかになります。 空の文字列がある場合に、エラーが発生する、特定の種類の変換などのルールを作成するときに、整数型として指定されたフィールド。  
  
-   ビジネス ルール作成ツールでは許可するフィールドを null に設定したりするためのフィールドの型を設定しない**オブジェクト**します。  
  
-   オブジェクト モデルを使用種類を設定することができます**オブジェクト**します。 この場合、返される値は、XPath の評価結果の種類: **float**、**ブール**、または**文字列**XPath 式に応じて、します。  
  
## <a name="net-classes"></a>.NET クラス  
 次の .NET クラスに適用されます。  
  
-   戻り値の型でない場合は、null と比較することはできません、**オブジェクト**型。  
  
-   Null 値の型ではないパラメーターをパラメーターとして渡すことができますが、メンバーの実装によって、ランタイム エラーが発生する可能性があります。  
  
-   派生した型のフィールドを設定する**オブジェクト**を null にします。  
  
## <a name="data-connection"></a>データ接続  
 次のデータ接続に適用されます。  
  
-   Null にデータベース テーブルの列を比較するには、テーブル列の null 値を使用して、列の型でない場合**テキスト**、 **ntext**、および**イメージ**します。  
  
    > [!NOTE]
    >  ビジネス ルール作成ツールでは、型の列を使用できます。**テキスト**と**ntext**、条件にします。 ただし、ポリシーを実行するときに、「text、ntext、および image データ型と比較することはできませんまたは以外の場合、IS NULL を使用して、並べ替え、または LIKE 演算子」と表示、エラー メッセージが表示されます。  
  
-   データベース テーブルの列は、テーブル列の null 値を許可する場合を null に設定できます。  
  
-   ビジネス ルール作成ツールが自動的にメンバーの種類を設定するバインディングで**オブジェクト**比較またはに設定する場合は、値型の場合は null 以外、リセットまたは引数を置換する場合、元の型に変更します。  
  
-   文字列型の場合に型を変更**オブジェクト**かどうか、null に設定が、null と比較した場合、文字列として残ります。  
  
-   比較またはに設定することはできません**DBNull.Value** 、ビジネス ルール作成ツールから、列の型には変更されないため、**オブジェクト**します。  
  
-   エンジンは、null を比較する際に DBNull 値を変換し、null をデータベースへの挿入の際に DBNull 値に変換されます。  
  
-   テストでは、(これは SQL Server の動作です)、null 値を無視します。 例では、ルールがある場合、"場合 db.column > 5 THEN。"、db.column に値を持つ行のみがテストされます-null 行はスキップされます。  
  
## <a name="typeddatatable-and-typeddatarow"></a>TypedDataTable および TypedDataRow  
 次は TypedDataTable および TypedDataRow に適用されます。  
  
-   ビジネス ルール作成ツールの変更、フィールドの種類を**オブジェクト**と同じ方法で**DataConnection**秒。  
  
-   Null を比較する場合を除き、null 値は、テストは失敗します。 などがありますエラー ルール"IF db.column > 5 THEN"アサートされた行の値が null の場合、します。  
  
     並列での条件が評価されるため、テストのように注意してください。"IF db.column! = NULL AND db.column > 5 THEN"は、両方のテストは 1 行ごとに評価される可能性があるためです。  
  
## <a name="checking-for-null-or-existence"></a>Null または存在の有無の確認  
 ビジネス ルールを記述する場合は、自然にその値を比較する前に、フィールドの存在を確認します。 ただし、フィールドが null か、存在しない場合、値と比較するエラーが発生します。 次のルールがあると仮定します。  
  
 Product/quantity AND Product/quantity が存在する場合 > 1  
  
 Product/quantity が存在しない場合、ルールでエラーがスローされます。 この問題を回避する方法の 1 つは、要素の値が存在する場合、またはそうでない場合は、別のものを返すヘルパー メソッドに親ノードを渡します。 次の規則を参照してください。  
  
 **ルール 1**  
  
 IF EXISTS(Product/Quantity) し ASSERT(CREATEOBJECT(typeof(Helper)、Product/quantity)  
  
 **Rule 2**  
  
 IF Helper.Value X = = し.  
  
 別の解決策では、次のようなルールを作成します。  
  
 Product/quantity が存在し CheckQuantityAndDoSomething(Product/Quantity) を場合  
  
 前の例では、CheckQuantityAndDoSomething 関数は、パラメーターの値がチェックされ、条件が満たされた場合に実行します。  
  
> [!NOTE]
>  XPath を変更する代わりに、**フィールド**プロパティがすべてのエラーをキャッチする XML ファクトが推奨されるアプローチです。