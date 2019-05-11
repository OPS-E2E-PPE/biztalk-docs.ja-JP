---
title: DataConnection と TypedDataTable の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], DataConnection
- RetractByType function [Business Rules Engine], DataConnection
- Assert function [Business Rules Engine], TypedData table
- Business Rules Engine, DataConnection tips
- TypedData table
- Business Rules Engine, TypedData table tips
- Assert function [Business Rules Engine], DataConnection
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], DataConnection
ms.assetid: e825803e-6626-4ddd-a77e-75a3ba2b74a4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9decd3a849aa21e0e769e006c8dfe29ca5b7315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401612"
---
# <a name="using-dataconnection-and-typeddatatable"></a>DataConnection と TypedDataTable の使用
使用して、多くのシナリオで**DataConnection**パフォーマンスが優れており、使用するよりも少ないメモリを消費**TypedDataTable**します。 ただし、 **TypedDataTable**の使用に関する制限があるため、場合によっては必要があります**DataConnection**します。 その他の場合を使用して**TypedDataTable**を使用してより優れたパフォーマンスを生じる**DataConnection**します。 このトピックでは、条件と適切なアプローチを選択するために考慮すべき要因について説明します。  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a>DataConnection ではなく TypedDataTable を使用する場合  
 次のインスタンスで、DataConnection ではなく TypedDataTable を使用します。  
  
-   データの変更ができるようにする必要がありますが、テーブルには、主キーにありません。 使用してデータを変更する**DataConnection**、主キーが必要です。 そのため、主キーがない場合**TypedDataTable**は唯一の方法です。  
  
    > [!NOTE]
    >  ルール エンジンのメモリ内の値を更新のみを**TypedDataTable**します。 これらの変更を永続的なを呼び出し元の責任です。  
  
-   選択度は、大きなテーブル内の行の割合がルールの条件として指定されたテストに合格するは、高です。 この場合、 **DataConnection**メリットを提供しない可能性がありますよりも悪い**TypedDataTable**します。  
  
-   テーブルは通常、小規模、500 未満の行を含むテーブル。 この番号が大きくまたは小さく、ルール図形およびルール エンジンで使用できるメモリによってありますに注意してください。  
  
-   ルール連鎖の動作が規則セットが必要です。 呼び出す、 **Update**に対して関数を**DataConnection**はサポートされていません呼び出すことができますが、 **DataConnection.Update**ヘルパー メソッドを使用してルール。 ルール連鎖が必要なときに**TypedDataTable**をお勧めします。  
  
-   テーブルの 1 つまたは複数の列は、非常に大量のデータは、ルールで必要としないを保持します。 例は、列に格納されるイメージ (大量のデータ)、名前、日付、およびなど、イメージ データベースです。 イメージが必要ない場合は、ルールで必要な列のみを選択する方がよい場合があります。 たとえば、"SELECT Name, Date from TABLE"などのクエリを発行できますを使用してよりも効率的**DataConnection**します。  
  
-   使用して多数のルールまたはデータベースの同じ行の更新を場合、 **TypedDataTable**行がすべてのルールの間で共有条件が同じである場合、(Table.Column 5 = =)、条件の評価を最適化することができます。 **DataConnection**、一般を使用する各ルールには、クエリが生成、 **DataConnection**します。 (テーブルに主キーがある場合)、行が再利用が毎回同じデータを取得する複数のクエリを生成できませんでした。  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a>TypedDataTable ではなく DataConnection を使用する場合  
 次のインスタンスで、TypedDataTable ではなく DataConnection を使用します。  
  
-   テーブルには、行の数が多いが含まれていますが、選択度が低い-ルールの条件を満たす行のごく一部のみです。  
  
-   1 つのデータベースのテーブルが大きいです。ルールで使用されるその他のすべてのオブジェクトでは、少数のインスタンスがあります。 最悪の場合、データベースに対して実行されるクエリの数は、ルールで使用されるその他のすべてのインスタンスの積に等しくなります。  
  
-   論理積条件だけルールを構成し、データベース テーブル以外のオブジェクトは、これらのルールで使用します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)