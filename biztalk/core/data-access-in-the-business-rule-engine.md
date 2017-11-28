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
# <a name="data-access-in-the-business-rule-engine"></a><span data-ttu-id="1599c-102">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="1599c-102">Data Access in the Business Rule Engine</span></span>
<span data-ttu-id="1599c-103">ルール エンジンは、.NET オブジェクトだけをネイティブにサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1599c-103">The rule engine supports only .NET objects natively.</span></span> <span data-ttu-id="1599c-104">データベースのデータを扱う場合、直接 ADO.NET オブジェクトを使用できます。ただし、このエンジンにはヘルパー クラスが提供されているので、データベースのデータをルールから簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1599c-104">To handle data from a database, you can use the ADO.NET objects directly, but the engine provides some helper classes to simplify the use of database data from rules.</span></span> <span data-ttu-id="1599c-105">ルール エンジンは、次の 3 つのデータベースに関連する型を公開することでのサポートを拡張します。 **TypedDataRow**、 **TypedDataTable**、および**DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="1599c-105">The rule engine extends its support by exposing three database-related types: **TypedDataRow**, **TypedDataTable**, and **DataConnection**.</span></span> <span data-ttu-id="1599c-106">このセクションでは、これらのヘルパー クラス、それぞれの型を使用するタイミングに関する推奨事項、およびそれぞれの型を使用する際のパフォーマンスへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="1599c-106">This section describes these helper classes, gives recommendations about when to use each type, and discusses some performance implications when using them.</span></span>  
  
 <span data-ttu-id="1599c-107">用意されているヘルパー クラスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1599c-107">The helper classes are as follows:</span></span>  
  
-   <span data-ttu-id="1599c-108">**TypedDataRow です。**</span><span class="sxs-lookup"><span data-stu-id="1599c-108">**TypedDataRow.**</span></span> <span data-ttu-id="1599c-109">ADO.NET への参照を使用して構築**DataRow**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1599c-109">Constructed by using a reference to an ADO.NET **DataRow** instance.</span></span> <span data-ttu-id="1599c-110">**TypedDataRow**はルールに最適な 1 つまたは少数の特定のテーブルから行のデータをそのだけを処理します。</span><span class="sxs-lookup"><span data-stu-id="1599c-110">The **TypedDataRow** is an obvious choice for rules that only deal with data from one or a small number of rows from a particular table.</span></span>  
  
-   <span data-ttu-id="1599c-111">**TypedDataTable です。**</span><span class="sxs-lookup"><span data-stu-id="1599c-111">**TypedDataTable.**</span></span> <span data-ttu-id="1599c-112">コレクションでは文字どおり**TypedDataRow**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1599c-112">Literally a collection of **TypedDataRow** objects.</span></span> <span data-ttu-id="1599c-113">データベース テーブルの各行としてラップする、 **TypedDataRow**され、ルール エンジンによって作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="1599c-113">Each row in the database table will be wrapped as a **TypedDataRow** and asserted into the working memory by the rule engine.</span></span>  
  
     <span data-ttu-id="1599c-114">A **TypedDataTable**インメモリ ADO.NET が必要です**DataTable**、パフォーマンスのオーバーヘッドの場合は、この特定できる**DataTable**非常に大量行にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1599c-114">A **TypedDataTable** requires an in-memory ADO.NET **DataTable**, which can be a performance overhead if this particular **DataTable** contains a very large number of rows.</span></span> <span data-ttu-id="1599c-115">少数のデータベース テーブルの行が関連するルールを使用してを呼び出す前にこれらの行を判断した場合、 **DataTable**、それ以外の場合を使用して**TypedDataRow**です。前提は、多数の DataTable 内の行がルールに関連することです。</span><span class="sxs-lookup"><span data-stu-id="1599c-115">If a small number of rows in the database table is relevant and you can determine these rows prior to calling the rules, use a **DataTable**, otherwise use **TypedDataRow**.The assumption is that a high number of rows in the DataTable are relevant to the rules.</span></span>  
  
-   <span data-ttu-id="1599c-116">**DataConnection です。**</span><span class="sxs-lookup"><span data-stu-id="1599c-116">**DataConnection.**</span></span> <span data-ttu-id="1599c-117">: データベース接続を通じてアクセスするデータベースのテーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="1599c-117">Represents a table in a database accessed through a database connection.</span></span> <span data-ttu-id="1599c-118">違い**DataConnection**と**TypedDataTable**に加えて、データセット名とテーブル名は**DataConnection**使用可能なデータベースが必要です接続し、必要に応じて、データベースのトランザクション コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="1599c-118">The difference between **DataConnection** and **TypedDataTable** is that in addition to the dataset name and table name, **DataConnection** requires a usable database connection and optionally a database transaction context.</span></span>  
  
     <span data-ttu-id="1599c-119">一部またはすべての述語をルールで使用される、 **DataConnection**データベース接続に対するクエリの制約の一部になります。</span><span class="sxs-lookup"><span data-stu-id="1599c-119">Some or all predicates used in rules with the **DataConnection** will become part of query constraints against the database connection.</span></span> <span data-ttu-id="1599c-120">クエリの制約を満たす行だけがデータベースから取得され、エンジンで使用されます。</span><span class="sxs-lookup"><span data-stu-id="1599c-120">Only rows that satisfy the query constraints will be retrieved from the database and used by the engine.</span></span> <span data-ttu-id="1599c-121">このメカニズムは、パフォーマンスを向上させると、非常に大きなを保持しているよりも少ないメモリを消費**DataTable**メモリにします。</span><span class="sxs-lookup"><span data-stu-id="1599c-121">This mechanism provides better performance and consumes less memory than holding a very large **DataTable** in memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1599c-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1599c-122">In This Section</span></span>  
  
-   [<span data-ttu-id="1599c-123">DataConnection を使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1599c-123">Considerations When Using DataConnection</span></span>](../core/considerations-when-using-dataconnection.md)  
  
-   [<span data-ttu-id="1599c-124">DataConnection と TypedDataTable の使用</span><span class="sxs-lookup"><span data-stu-id="1599c-124">Using DataConnection and TypedDataTable</span></span>](../core/using-dataconnection-and-typeddatatable.md)