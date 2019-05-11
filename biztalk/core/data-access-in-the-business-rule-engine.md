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
# <a name="data-access-in-the-business-rule-engine"></a><span data-ttu-id="4f7cf-102">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="4f7cf-102">Data Access in the Business Rule Engine</span></span>
<span data-ttu-id="4f7cf-103">ルール エンジンは、.NET オブジェクトだけをネイティブにサポートします。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-103">The rule engine supports only .NET objects natively.</span></span> <span data-ttu-id="4f7cf-104">データベースからデータを処理するためにする ADO.NET オブジェクトを直接使用できますが、エンジンのルールからデータをデータベースの使用を簡略化するいくつかのヘルパー クラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-104">To handle data from a database, you can use the ADO.NET objects directly, but the engine provides some helper classes to simplify the use of database data from rules.</span></span> <span data-ttu-id="4f7cf-105">ルール エンジンは、次の 3 つのデータベースに関連する型を公開することで、サポートを拡張します。**TypedDataRow**、 **TypedDataTable**、および**DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-105">The rule engine extends its support by exposing three database-related types: **TypedDataRow**, **TypedDataTable**, and **DataConnection**.</span></span> <span data-ttu-id="4f7cf-106">このセクションでは、これらのヘルパー クラスをについて説明します、種類ごとを使用するタイミングに関する推奨事項およびそれらを使用する場合にパフォーマンスへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-106">This section describes these helper classes, gives recommendations about when to use each type, and discusses some performance implications when using them.</span></span>  
  
 <span data-ttu-id="4f7cf-107">ヘルパー クラスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-107">The helper classes are as follows:</span></span>  
  
-   <span data-ttu-id="4f7cf-108">**TypedDataRow します。**</span><span class="sxs-lookup"><span data-stu-id="4f7cf-108">**TypedDataRow.**</span></span> <span data-ttu-id="4f7cf-109">ADO.NET への参照を使用して構築された**DataRow**インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-109">Constructed by using a reference to an ADO.NET **DataRow** instance.</span></span> <span data-ttu-id="4f7cf-110">**TypedDataRow**ルールに最適なは、その 1 つまたは少数の特定のテーブルから行のデータだけを処理します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-110">The **TypedDataRow** is an obvious choice for rules that only deal with data from one or a small number of rows from a particular table.</span></span>  
  
-   <span data-ttu-id="4f7cf-111">**TypedDataTable.**</span><span class="sxs-lookup"><span data-stu-id="4f7cf-111">**TypedDataTable.**</span></span> <span data-ttu-id="4f7cf-112">コレクションでは文字どおり**TypedDataRow**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-112">Literally a collection of **TypedDataRow** objects.</span></span> <span data-ttu-id="4f7cf-113">データベース テーブルの各行としてラップされる、 **TypedDataRow**ルール エンジンによって作業メモリにアサートされたとします。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-113">Each row in the database table will be wrapped as a **TypedDataRow** and asserted into the working memory by the rule engine.</span></span>  
  
     <span data-ttu-id="4f7cf-114">A **TypedDataTable**メモリで ADO.NET を必要と**DataTable**、パフォーマンスのオーバーヘッドの場合は、この特定できる**DataTable**非常に多く行にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-114">A **TypedDataTable** requires an in-memory ADO.NET **DataTable**, which can be a performance overhead if this particular **DataTable** contains a very large number of rows.</span></span> <span data-ttu-id="4f7cf-115">少数のデータベース テーブルの行が関連して、ルールを呼び出す前にこれらの行を決定する場合、 **DataTable**、それ以外の場合を使用して、 **TypedDataRow**します。前提は、多数のデータ テーブル内の行が規則に関連することです。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-115">If a small number of rows in the database table is relevant and you can determine these rows prior to calling the rules, use a **DataTable**, otherwise use **TypedDataRow**.The assumption is that a high number of rows in the DataTable are relevant to the rules.</span></span>  
  
-   <span data-ttu-id="4f7cf-116">**DataConnection します。**</span><span class="sxs-lookup"><span data-stu-id="4f7cf-116">**DataConnection.**</span></span> <span data-ttu-id="4f7cf-117">データベース接続を通じてアクセスするデータベース内のテーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-117">Represents a table in a database accessed through a database connection.</span></span> <span data-ttu-id="4f7cf-118">間の差**DataConnection**と**TypedDataTable**だけでなく、データセット名とテーブル名、つまり**DataConnection**使用可能なデータベースが必要です接続し、必要に応じてデータベースのトランザクション コンテキスト。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-118">The difference between **DataConnection** and **TypedDataTable** is that in addition to the dataset name and table name, **DataConnection** requires a usable database connection and optionally a database transaction context.</span></span>  
  
     <span data-ttu-id="4f7cf-119">一部またはすべての述語をルールで使用される、 **DataConnection**データベース接続に対するクエリの制約の一部になります。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-119">Some or all predicates used in rules with the **DataConnection** will become part of query constraints against the database connection.</span></span> <span data-ttu-id="4f7cf-120">クエリの制約を満たす行だけがデータベースから取得し、エンジンによって使用します。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-120">Only rows that satisfy the query constraints will be retrieved from the database and used by the engine.</span></span> <span data-ttu-id="4f7cf-121">このメカニズムは、パフォーマンスが向上し、非常に大きなを保持しているよりもメモリを消費**DataTable**メモリにします。</span><span class="sxs-lookup"><span data-stu-id="4f7cf-121">This mechanism provides better performance and consumes less memory than holding a very large **DataTable** in memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f7cf-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4f7cf-122">In This Section</span></span>  
  
-   [<span data-ttu-id="4f7cf-123">DataConnection を使用する際の注意事項</span><span class="sxs-lookup"><span data-stu-id="4f7cf-123">Considerations When Using DataConnection</span></span>](../core/considerations-when-using-dataconnection.md)  
  
-   [<span data-ttu-id="4f7cf-124">DataConnection と TypedDataTable の使用</span><span class="sxs-lookup"><span data-stu-id="4f7cf-124">Using DataConnection and TypedDataTable</span></span>](../core/using-dataconnection-and-typeddatatable.md)