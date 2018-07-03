---
title: SQL アダプターを使用して SQL Server でのテーブル値関数の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fb8c81c-9384-4eba-b0a0-baed1782245b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dab49fa57a3132a75fd937f1d89333577d28c420
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007235"
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a><span data-ttu-id="570e8-102">SQL アダプターを使用して SQL Server でのテーブル値関数の実行します。</span><span class="sxs-lookup"><span data-stu-id="570e8-102">Execute Table-Valued Functions in SQL Server using the SQL adapter</span></span>
<span data-ttu-id="570e8-103">SQL Server で Transact SQL と CLR テーブル値関数での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="570e8-103">The Transact-SQL and CLR table valued functions in SQL Server are surfaced as operations in [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="570e8-104">内の操作名、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]値関数で SQL Server テーブルの名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="570e8-104">The operation name in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is the same as the name of the table valued function in SQL Server.</span></span>  
  
 <span data-ttu-id="570e8-105">テーブル値関数のすべてのパラメーターは、対応する操作で公開されます。</span><span class="sxs-lookup"><span data-stu-id="570e8-105">All the parameters in the table valued function are exposed in the corresponding operation.</span></span> <span data-ttu-id="570e8-106">テーブル値関数の場合、入力パラメーターを指定しない場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]内部的に DEFAULT キーワードを使用して、関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="570e8-106">If you do not specify an input parameter for a table valued function, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] internally invokes the function using the DEFAULT keyword.</span></span> <span data-ttu-id="570e8-107">これは、関数を定義するときに指定された既定値を使用して、テーブル値関数を実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="570e8-107">This implies that the table valued function is executed using the default value specified while defining the function.</span></span>  
  
 <span data-ttu-id="570e8-108">詳細については。</span><span class="sxs-lookup"><span data-stu-id="570e8-108">For more information about:</span></span>  
  
- <span data-ttu-id="570e8-109">使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server でのテーブル値関数を呼び出すための BizTalk Server で、次を参照してください。 [Invoking Table-Valued 関数を使用して BizTalk Server によって SQL Server で](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="570e8-109">Using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with BizTalk Server to invoke table valued functions in SQL Server, see [Invoking Table-Valued Functions in SQL Server by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="570e8-110">メッセージの構造とテーブル値関数用の SOAP アクションを参照してください[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="570e8-110">Message structure and SOAP actions for table valued functions, see [Message Schemas for Procedures and Functions](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="570e8-111">参照</span><span class="sxs-lookup"><span data-stu-id="570e8-111">See Also</span></span>  
 <span data-ttu-id="570e8-112">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="570e8-112">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>