---
title: "DataConnection を使用する際の考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Business Rules Engine, DataConnection tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], DataConnection
ms.assetid: 1b4c8aa5-053f-43d7-9f5f-050383405fed
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f99110daafa74cb16b6cc5b98e1382049bbb158
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="considerations-when-using-dataconnection"></a>DataConnection を使用する際の注意事項
ビジネス ルール エンジンで DataConnection を使用する際の注意事項を、次に示します。  
  
## <a name="use-primary-keys"></a>主キーを使用する  
 主キーが存在する場合、2 つの行が等しいかどうかは、オブジェクトの比較ではなく同じ主キーを使用するかどうかで決まります。 行が同一であると判断された場合、1 つのコピーだけがメモリに保持され、もう一方は解放されます。 これによって、メモリの消費が少なくなります。  
  
 ときに、 **DataConnection**がアサートされ、ルール エンジンに最初に、エンジンは常にそのスキーマから主キーの情報を検索ましょう。 主キーが存在する場合、主キーの情報が取得され、後続のすべての評価で使用されます。  
  
> [!NOTE]
>  データベースに変更を加える場合、主キーが必要です。  
  
## <a name="provide-a-running-transaction-to-the-dataconnection-whenever-possible"></a>可能な場合は DataConnection に実行中のトランザクションを提供する  
 トランザクションなし各クエリおよび更新、 **DataConnection**開始され、独自のローカル トランザクション、および複数の異なるクエリを別に返す場合がありますがルールの評価のさまざまな部分になります。 基になるデータベース テーブルが修正されると、矛盾した動作が発生する場合があります。  
  
 使用できますが、 **DataConnection**せず、テーブルが時間の経過と共に変化しない場合に、トランザクションを提供することをお勧めトランザクションを使用する場合でも、 **DataConnection**中のみ読み取り操作に使用されます。  
  
 ただし、データを更新する場合は、必ずトランザクションを使用してください。  
  
## <a name="number-of-queries-may-grow-linearly"></a>クエリの数が増大する可能性がある  
 クエリ、 **DataConnection**に対して実行されるクエリの数、参加している他のオブジェクトでパラメーター化される、 **DataConnection**する結合オブジェクトの数に直接対応しています達する、 **DataConnection**です。 したがって、結合の数のオブジェクトに到達する場合、 **DataConnection**比例して、に対するクエリの数に増大するオブジェクト、 **DataConnection**直線的にも拡張されます。 現在、クエリの数を減らす最適化は行われません。  
  
 この例を次のルールで示します。  
  
```  
IF A.x = 7 AND DC.y = A.y  
THEN  
```  
  
 表す、 **ObjectBinding**、DC を表します、 **DataConnection**、x および y は A の属性と DC とします。  
  
 テストに合格する A のすべてのインスタンス (x = 7) を使用して生成されるクエリ、 **DataConnection**です。 一致するインスタンスが多くある場合は、同じ数のクエリが生成されます。  
  
## <a name="use-or-conditions-with-caution"></a>慎重に OR 条件を使用する  
 ルールが論理積のみで使用する場合 (**AND**) 条件、テストおよびクエリ実行される、できるだけ早い段階で渡されるオブジェクトのインスタンスが低下するようにします。 その結果、その後、に対するクエリの数**DataConnection**比例して少なくなります。 選言場合 (**または**) 条件と**DataConnection**ルールの評価は最後のクエリにプッシュするすべての条件で同時に使用されます。 1 つ以上の場合**DataConnection**は一般に、最後の 1 つが、すべてのクエリ ステートメントになる効果的に点を除いて、すべてのクエリで使用します。  
  
 一般的に、OR 条件を持つルールは複数の別ルールに分割することをお勧めします。OR 条件を使用すると、よりアトミックなルールを定義した場合に比べて、パフォーマンスが低下するためです。 このことは、DataConnection を使用するどうかに関係なく当てはまります。  
  
 1 つの規則ではなく論理積条件だけで構成される個別のルールの使用を検討する可能性がありますも**または**条件。 **または**条件、結合するすべてのオブジェクトのインスタンスの乗算の速度でクエリの数が増加します。 次の例を参照してください。  
  
```  
IF (A.x ==7 OR A.x == 8) AND DC.y == A.y  
THEN DC.z = 10  
```  
  
 この例では A を表します、 **ObjectBinding**です。DC を表す、 **DataConnection**x、y、および z は A の属性を表すと DC とします。 100 個のクエリがに対して実行する必要があり場合は、100 インスタンスは、x は最初のオブジェクトでは、100、100 オブジェクトに、2 番目のオブジェクトの 2 では 1、 **DataConnection**です。  
  
 前のルールを書き換えて 2 つのルールに分割することをお勧めします。  
  
 **ルール 1**  
  
```  
IF A.x =7 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
 **規則 2**  
  
```  
IF A.x = 8 AND DC.y = A.y  
THEN DC.z = 10  
```  
  
## <a name="sql-does-not-support-some-predicates-and-functions"></a>SQL は一部の述語と関数をサポートしない  
 ルール エンジンがサポートしている一部の述語と関数は、SQL に対応していません。 対応していないこれらの述語と関数をルールの条件で使用すると、クエリに組み込むことができません。 次の条件は、SQL クエリとして最適化できません。  
  
-   一部のエンジン組み込み関数に相当する機能は、SQL クエリにありません。 これらは**Power**、 **FindFirst**、および**FindAll**です。 使用して、 **DataConnection**列を 1 つ以上の引数として、クエリの一部として最適化できません; たとえば、Power (2, dc です。列 1)。  
  
-   組み込みの述語 Match を使用する、 **DataConnection**列として、正規表現の引数 (最初の引数)。 たとえば、Match("abc*", dc1.Column2) は有効ですが、Match(dc1.Column1, dc1.Column2) は解釈できません。  
  
-   持つユーザー関数を使用して、 **DataConnection**列として、パラメーターのいずれか。 たとえば、ユーザー関数はデータベース サーバー上で実行できないため (ビジネス ルール エンジンで実行する必要がある)、c1.M(dc.Column1) は最適化できません。  
  
-   設定操作を表すユーザー関数、 **DataConnection**。 たとえば、dc です。Column1(5) です。  
  
-   使用する関数、 **ObjectReference**を**DataConnection**ObjecRef(dc) などです。  
  
-   解釈できない引数がある場合、関数の呼び出し自体が解釈できなくなります (Add(c1.M(dc.Column1), 5) など)。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)