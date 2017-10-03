---
title: "ビジネス ルール エンジンでのデータ アクセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, data access
- Business Rules Engine, helper classes
- data, data access
ms.assetid: 38da32af-1e0d-43fb-b946-fb49a11f1681
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58de70c2befd13f4995ebd073ebd70a2e7d84ea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-access-in-the-business-rule-engine"></a>ビジネス ルール エンジンでのデータ アクセス
ルール エンジンは、.NET オブジェクトだけをネイティブにサポートしています。 データベースのデータを扱う場合、直接 ADO.NET オブジェクトを使用できます。ただし、このエンジンにはヘルパー クラスが提供されているので、データベースのデータをルールから簡単に使用できます。 ルール エンジンは、次の 3 つのデータベースに関連する型を公開することでのサポートを拡張します。 **TypedDataRow**、 **TypedDataTable**、および**DataConnection**です。 このセクションでは、これらのヘルパー クラス、それぞれの型を使用するタイミングに関する推奨事項、およびそれぞれの型を使用する際のパフォーマンスへの影響について説明します。  
  
 用意されているヘルパー クラスは次のとおりです。  
  
-   **TypedDataRow です。** ADO.NET への参照を使用して構築**DataRow**インスタンス。 **TypedDataRow**はルールに最適な 1 つまたは少数の特定のテーブルから行のデータをそのだけを処理します。  
  
-   **TypedDataTable です。** コレクションでは文字どおり**TypedDataRow**オブジェクト。 データベース テーブルの各行としてラップする、 **TypedDataRow**され、ルール エンジンによって作業メモリにアサートします。  
  
     A **TypedDataTable**インメモリ ADO.NET が必要です**DataTable**、パフォーマンスのオーバーヘッドの場合は、この特定できる**DataTable**非常に大量行にはが含まれています。 少数のデータベース テーブルの行が関連するルールを使用してを呼び出す前にこれらの行を判断した場合、 **DataTable**、それ以外の場合を使用して**TypedDataRow**です。前提は、多数の DataTable 内の行がルールに関連することです。  
  
-   **DataConnection です。** : データベース接続を通じてアクセスするデータベースのテーブルを表します。 違い**DataConnection**と**TypedDataTable**に加えて、データセット名とテーブル名は**DataConnection**使用可能なデータベースが必要です接続し、必要に応じて、データベースのトランザクション コンテキスト。  
  
     一部またはすべての述語をルールで使用される、 **DataConnection**データベース接続に対するクエリの制約の一部になります。 クエリの制約を満たす行だけがデータベースから取得され、エンジンで使用されます。 このメカニズムは、パフォーマンスを向上させると、非常に大きなを保持しているよりも少ないメモリを消費**DataTable**メモリにします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [DataConnection を使用する際の考慮事項](../core/considerations-when-using-dataconnection.md)  
  
-   [DataConnection と TypedDataTable の使用](../core/using-dataconnection-and-typeddatatable.md)