---
title: "DataConnection と TypedDataTable を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b5a0a490023d77676cc5d156ad5126ad5d7d6c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-dataconnection-and-typeddatatable"></a>DataConnection と TypedDataTable の使用
使用して、多くのシナリオで**DataConnection**パフォーマンスを向上させると、使用するよりも少ないメモリを消費する**TypedDataTable**です。 ただし、 **TypedDataTable**で必要になる場合によってを使用して上の特定の制限のため**DataConnection**です。 場合によっては他を使用して**TypedDataTable**を使用するよりも優れたパフォーマンスが生じる**DataConnection**です。 このトピックでは、正しいアプローチを選択するために考慮する必要がある条件と要因について説明します。  
  
## <a name="when-to-use-typeddatatable-instead-of-dataconnection"></a>DataConnection より TypedDataTable が適している場合  
 次の場合は、DataConnection ではなく TypedDataTable を使用します。  
  
-   データを変更する必要があるが、テーブルに主キーがない場合。 使用してデータを変更する**DataConnection**、主キーが必要です。 そのための主キーがない場合、 **TypedDataTable**唯一の方法です。  
  
    > [!NOTE]
    >  ルール エンジンのメモリ内の値の更新のみ、 **TypedDataTable**です。 変更が永続的になるかどうかは呼び出し元によって異なります。  
  
-   選択度が高い場合。つまり、ルール条件として指定されたテストに大半のテーブル行が合格する場合。 この場合、 **DataConnection**メリットは提供されませんを実行できるよりも悪い**TypedDataTable**です。  
  
-   テーブルのサイズが小さい場合。通常これには、行数が 500 未満のテーブルが該当します。 ただし、この値は、ルール図形およびルール エンジンで使用可能なメモリによって異なる場合があります。  
  
-   ルール連鎖の動作がルール セットで予想されている場合。 呼び出す、**更新**で機能、 **DataConnection**はサポートされていません呼び出すことが**DataConnection.Update**ヘルパー メソッドを使用して、ルールにします。 ルール連鎖が必要な場合、 **TypedDataTable**方が適しています。  
  
-   テーブルの 1 つまたは複数の列に、ルールに不要なデータが大量に格納されている場合。 その例としては、イメージ (大量のデータ)、名前、日付などが列に格納される、イメージ データベースが挙げられます。 イメージが不要な場合は、ルールに必要な列だけを選択した方が効果的です。 たとえば、"SELECT Name, Date from TABLE"のようなクエリを発行できますを使用するよりも効率的**DataConnection**です。  
  
-   使用して多数のルールは、データベースの同じ行の更新が必要する場合、 **TypedDataTable**行はすべての規則の間で共有と同じ場合は、条件 (Table.Column = = 5)、条件の評価を最適化することができます。 **DataConnection**、使用するルールごとに生成されるクエリは一般に、 **DataConnection**です。 行は再使用されますが (テーブルに主キーがある場合)、同じデータを毎回取得する複数のクエリが生成されることがあります。  
  
## <a name="when-to-use-dataconnection-instead-of-typeddatatable"></a>TypedDataTable より DataConnection が適している場合  
 次の場合は、TypedDataTable ではなく DataConnection を使用します。  
  
-   テーブルには、行の数が多いが含まれていますが、選択度が低い — だけで、ルールの条件を満たす行の少ないです。  
  
-   サイズの大きなデータベース テーブルが 1 つしかなく、ルールで使用されるその他のオブジェクトには、少数のインスタンスしか含まれていない場合。 最悪の場合は、データベースに対して実行されるクエリの数が、ルールで使用されるその他すべてのインスタンスの結果と等しくなります。  
  
-   ルールが論理積条件だけで構成され、データベース テーブル以外のオブジェクトがこれらのルールで使用される場合。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)