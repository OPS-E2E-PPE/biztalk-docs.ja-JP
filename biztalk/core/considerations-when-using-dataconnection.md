---
title: DataConnection を使用する場合の考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf932f4082e36ed6704f848d38691326be5af66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354637"
---
# <a name="considerations-when-using-dataconnection"></a>DataConnection を使用する場合の考慮事項
ビジネス ルール エンジンで DataConnection を使用する場合は、次を検討してください。  
  
## <a name="use-primary-keys"></a>主キーを使用します。  
 主キーがある場合は、2 つの行が等しいかどうかは、オブジェクトの比較ではなく、行、同じプライマリ キーであるかどうかによって決まります。 行が確定され同じである場合は、1 つだけのコピーがメモリに保持され、他の解放されます。 これにより、少ないメモリ消費量。  
  
 ときに、 **DataConnection**がアサートされてルール エンジンに最初に、エンジンは、常にそのスキーマから主キーの情報の検索を試みます。 主キーが存在する場合の主キー情報が、取得され、以降のすべての評価で使用されます。  
  
> [!NOTE]
>  主キーは、データベースに対する変更が必要な場合は必須です。  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a>可能な限り DataConnection に実行中のトランザクションを提供します。  
 トランザクションなしの各クエリにし、更新、 **DataConnection**ルール評価のさまざまな部分での結果を開始しますが、独自のクエリが異なると、ローカル トランザクションは別に返す可能性があります。 ユーザーは、基になるデータベース テーブルの変更がある場合、一貫性のない動作にすることがあります。  
  
 使用できますが、 **DataConnection**テーブルが時間の経過と共に変更しない場合は、トランザクションを提供する、なしをお勧めトランザクションを使用する場合でも、 **DataConnection**ことのみです読み取り操作に使用されます。  
  
 ただし、トランザクションは、データを更新するときに常に使用する必要があります。  
  
## <a name="number-of-queries-may-grow-linearly"></a>クエリの数が増大する可能性があります。  
 クエリ、 **DataConnection**に対して実行されるクエリの数、参加している他のオブジェクトでパラメーター化される、 **DataConnection**結合オブジェクトの数に直接対応しています到達、 **DataConnection**します。 そのため、結合オブジェクトの数に到達した場合、 **DataConnection**オブジェクト増大に対するクエリの数、 **DataConnection**も拡張されます。 現時点では、クエリの数を削減するための最適化ではありません。  
  
 この例では、ルールを示します。  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 表す、 **ObjectBinding**、dc、 **DataConnection**、x および y は A の属性を表すと DC と。  
  
 テストに合格する A のすべてのインスタンス (x = 7) を使用して生成されるクエリは、 **DataConnection**します。 多くの一致するインスタンスがある場合、同じ数のクエリの結果します。  
  
## <a name="use-or-conditions-with-caution"></a>注意して使用 OR 条件  
 ルールが論理積のみで使用する場合 (**AND**) 条件、テスト、およびクエリ実行される、できるだけ早い段階に渡されるオブジェクトのインスタンスが低下するようにします。 その結果、それに続くに対するクエリの数**DataConnection**比例して制限されます。 分離の場合 (**または**) 条件と**DataConnection**ルール評価は最後のクエリにプッシュされるすべての条件で一緒に使用します。 1 つ以上の場合**DataConnection**ルール、最後の 1 つの すべてのクエリ ステートメントは実質的に点を除いて、すべてのクエリで使用されます。  
  
 一般に、勧め OR 条件を持つすべてのルールを 2 つ以上の個別のルールに分割するため、OR 条件の使用よりアトミックなルールの定義と比較してパフォーマンスが低下します。 これはか Dataconnection を使用するかどうかに当てはまります。  
  
 1 つの規則ではなく、論理積条件だけで構成される個別のルールの使用を検討することがありますも**または**条件。 **または**条件、結合オブジェクトのすべてのインスタンスの乗算の速度でクエリの数が増加します。 次の例を参照してください。  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 この例では A を表します、 **ObjectBinding**;Dc を**DataConnection**x、y、および A の属性を表す z と DC とします。 コマンドを実行する 100 個のクエリがある場合は 100 のインスタンスを持つ、x は 1、2 ~ 100 のオブジェクトの 100 で、2 番目のオブジェクトに最初のオブジェクトに、 **DataConnection**します。  
  
 2 つのルールに分割して前のルールを書き直すことをお勧めします。  
  
 **ルール 1**  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 **Rule 2**  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a>SQL は一部の述語と関数をサポートしていません  
 一部の述語と、ルール エンジンでサポートされる関数は、SQL でサポートされていません。 これらのサポートされていない述語と関数をルールの条件で使用する場合は、クエリに組み込むことはできません。 次の用語は、SQL クエリとして最適化できません。  
  
-   一部のエンジン組み込み関数があるありませんと同じ SQL クエリで。 これらは**Power**、 **FindFirst**、および**FindAll**します。 使用して、 **DataConnection**列を 1 つ以上の引数として、クエリの一部として最適化できません; たとえば、Power (2, dc です。列 1)。  
  
-   組み込みの述語 Match を使用する、 **DataConnection**列として、正規表現の引数 (最初の引数)。 たとえば、次のように一致 (「abc *」、dc1 します。列 2) が有効ですが、一致 (dc1 します。Column1、dc1 します。列 2) を変換することはできません。  
  
-   持つユーザー関数を使用して、 **DataConnection**としてそのパラメーターの 1 つの列。 たとえば、c1 です。M (dc です。ユーザー関数は、データベース サーバーで実行できませんが、ビジネス ルール エンジンによって実行される必要がありますので、Column1) を最適化することはできません。  
  
-   集合演算を表すユーザー関数、 **DataConnection**。 たとえば、dc です。Column1(5) します。  
  
-   使用する関数、 **ObjectReference**を**DataConnection**。 例: ObjecRef(dc) します。  
  
-   1 つ以上の関数の引数が変換可能な場合、関数呼び出しが乱す; になりますたとえば、追加 (c1 します。M (dc です。列 1)、5)。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)