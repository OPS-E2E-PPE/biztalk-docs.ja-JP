---
title: ビジネス ルール エンジンでのデータ アクセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, data access
- Business Rules Engine, helper classes
- data, data access
ms.assetid: 38da32af-1e0d-43fb-b946-fb49a11f1681
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c685f0af9bb1750e2507c41d51e11774ae457ce0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390033"
---
# <a name="data-access-in-the-business-rule-engine"></a>ビジネス ルール エンジンでのデータ アクセス
ルール エンジンは、.NET オブジェクトだけをネイティブにサポートします。 データベースからデータを処理するためにする ADO.NET オブジェクトを直接使用できますが、エンジンのルールからデータをデータベースの使用を簡略化するいくつかのヘルパー クラスを提供します。 ルール エンジンは、次の 3 つのデータベースに関連する型を公開することで、サポートを拡張します。**TypedDataRow**、 **TypedDataTable**、および**DataConnection**します。 このセクションでは、これらのヘルパー クラスをについて説明します、種類ごとを使用するタイミングに関する推奨事項およびそれらを使用する場合にパフォーマンスへの影響について説明します。  
  
 ヘルパー クラスは次のとおりです。  
  
-   **TypedDataRow します。** ADO.NET への参照を使用して構築された**DataRow**インスタンス。 **TypedDataRow**ルールに最適なは、その 1 つまたは少数の特定のテーブルから行のデータだけを処理します。  
  
-   **TypedDataTable.** コレクションでは文字どおり**TypedDataRow**オブジェクト。 データベース テーブルの各行としてラップされる、 **TypedDataRow**ルール エンジンによって作業メモリにアサートされたとします。  
  
     A **TypedDataTable**メモリで ADO.NET を必要と**DataTable**、パフォーマンスのオーバーヘッドの場合は、この特定できる**DataTable**非常に多く行にはが含まれています。 少数のデータベース テーブルの行が関連して、ルールを呼び出す前にこれらの行を決定する場合、 **DataTable**、それ以外の場合を使用して、 **TypedDataRow**します。前提は、多数のデータ テーブル内の行が規則に関連することです。  
  
-   **DataConnection します。** データベース接続を通じてアクセスするデータベース内のテーブルを表します。 間の差**DataConnection**と**TypedDataTable**だけでなく、データセット名とテーブル名、つまり**DataConnection**使用可能なデータベースが必要です接続し、必要に応じてデータベースのトランザクション コンテキスト。  
  
     一部またはすべての述語をルールで使用される、 **DataConnection**データベース接続に対するクエリの制約の一部になります。 クエリの制約を満たす行だけがデータベースから取得し、エンジンによって使用します。 このメカニズムは、パフォーマンスが向上し、非常に大きなを保持しているよりもメモリを消費**DataTable**メモリにします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [DataConnection を使用する際の注意事項](../core/considerations-when-using-dataconnection.md)  
  
-   [DataConnection と TypedDataTable の使用](../core/using-dataconnection-and-typeddatatable.md)