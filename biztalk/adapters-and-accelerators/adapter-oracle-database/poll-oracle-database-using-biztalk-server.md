---
title: BizTalk Server を使用して Oracle データベースをポーリング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c3aef30-956d-4585-b2de-7eebb919fab5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2578d00518a9f1632e690e84db04426575619109
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214178"
---
# <a name="poll-oracle-database-using-biztalk-server"></a><span data-ttu-id="1623e-102">BizTalk Server を使用して Oracle データベースをポーリング</span><span class="sxs-lookup"><span data-stu-id="1623e-102">Poll Oracle Database using BizTalk Server</span></span>
<span data-ttu-id="1623e-103">構成することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからのポーリングに基づいたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="1623e-103">You can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="1623e-104">アダプターは、Oracle データベースをポーリングする 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1623e-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
-   <span data-ttu-id="1623e-105">**SELECT ステートメントを使用して**です。</span><span class="sxs-lookup"><span data-stu-id="1623e-105">**Using SELECT statements**.</span></span> <span data-ttu-id="1623e-106">テーブルと、Oracle データベースでビューをポーリングする単純な SELECT ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1623e-106">You can specify a simple SELECT statement to poll the tables and views in the Oracle database.</span></span> <span data-ttu-id="1623e-107">アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="1623e-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
-   <span data-ttu-id="1623e-108">**ストアド プロシージャ、関数、プロシージャ、またはパッケージ内で関数を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="1623e-108">**Using stored procedures, functions, or procedures or functions within a package**.</span></span> <span data-ttu-id="1623e-109">ストアド プロシージャ、関数、またはプロシージャまたは Oracle データベースをポーリングするパッケージ内で関数を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1623e-109">You can specify a stored procedure, function, or procedure or function within a package to poll the Oracle database.</span></span> <span data-ttu-id="1623e-110">アダプターは、指定した間隔で要求メッセージを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="1623e-110">The adapter executes the request message at specified intervals and returns the result to the adapter clients.</span></span>  
  
 <span data-ttu-id="1623e-111">2 つのアプローチの主な違いは、方法アダプター クライアントが、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1623e-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="1623e-112">単純な SELECT ステートメントでは、ポーリング ステートメントの最初の方法に関するその他の方法については、ポーリング ステートメント、ストアド プロシージャ、関数、またはプロシージャまたはパッケージ内で関数を実行する要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="1623e-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the other approach is a request message that executes the stored procedure, function, or procedure or function within a package.</span></span> <span data-ttu-id="1623e-113">アダプターのクライアントで、いずれかの方法では、ポーリング ステートメントを指定して、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="1623e-113">Adapter clients specify the polling statement, for either approach, in the **PollingStatement** binding property.</span></span> <span data-ttu-id="1623e-114">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="1623e-114">For more information about the binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
 <span data-ttu-id="1623e-115">このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャ、関数、またはプロシージャを使用してをポーリングする方法について説明またはパッケージ内で機能します。</span><span class="sxs-lookup"><span data-stu-id="1623e-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure, function, or procedure or function within a package.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1623e-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1623e-116">In This Section</span></span>  
  
-   [<span data-ttu-id="1623e-117">SELECT ステートメントを使用してポーリング Oracle データベース</span><span class="sxs-lookup"><span data-stu-id="1623e-117">Poll Oracle Database using the SELECT statement</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-database-using-the-select-statement.md)  
  
-   [<span data-ttu-id="1623e-118">ストアド プロシージャ、関数、またはパッケージ化されたプロシージャおよび関数を使用して Oracle データベースをポーリング</span><span class="sxs-lookup"><span data-stu-id="1623e-118">Poll Oracle Database Using Stored Procedures, Functions, or Packaged Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-oracle-database/poll-oracle-db-using-stored-procedures-functions-or-packaged-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="1623e-119">参照</span><span class="sxs-lookup"><span data-stu-id="1623e-119">See Also</span></span>  
[<span data-ttu-id="1623e-120">Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="1623e-120">Develop BizTalk applications using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)