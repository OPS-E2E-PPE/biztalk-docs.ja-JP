---
title: "SQL アダプタを使用して SQL Server でテーブル値関数を実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fb8c81c-9384-4eba-b0a0-baed1782245b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69877f214a2a4b700de22ec043094510707114d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="execute-table-valued-functions-in-sql-server-using-the-sql-adapter"></a><span data-ttu-id="97b3f-102">SQL アダプタを使用して SQL Server でテーブル値関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="97b3f-102">Execute Table-Valued Functions in SQL Server using the SQL adapter</span></span>
<span data-ttu-id="97b3f-103">SQL Server で Transact SQL と CLR テーブル値関数での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="97b3f-103">The Transact-SQL and CLR table valued functions in SQL Server are surfaced as operations in [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="97b3f-104">内の操作名、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]値関数で SQL Server テーブルの名前と同じであります。</span><span class="sxs-lookup"><span data-stu-id="97b3f-104">The operation name in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is the same as the name of the table valued function in SQL Server.</span></span>  
  
 <span data-ttu-id="97b3f-105">テーブル値関数のすべてのパラメーターは、対応する操作で公開されます。</span><span class="sxs-lookup"><span data-stu-id="97b3f-105">All the parameters in the table valued function are exposed in the corresponding operation.</span></span> <span data-ttu-id="97b3f-106">テーブル値関数の場合、入力パラメーターが指定されていない場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]内部的に DEFAULT キーワードを使用して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="97b3f-106">If you do not specify an input parameter for a table valued function, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] internally invokes the function using the DEFAULT keyword.</span></span> <span data-ttu-id="97b3f-107">これは、関数を定義する際に指定した既定値を使用して、テーブル値関数を実行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="97b3f-107">This implies that the table valued function is executed using the default value specified while defining the function.</span></span>  
  
 <span data-ttu-id="97b3f-108">詳細については。</span><span class="sxs-lookup"><span data-stu-id="97b3f-108">For more information about:</span></span>  
  
-   <span data-ttu-id="97b3f-109">使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] BizTalk Server を SQL Server でのテーブル値関数を呼び出すと、次を参照してください。 [Invoking Table-Valued 関数を使用して BizTalk Server で、SQL Server で](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="97b3f-109">Using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with BizTalk Server to invoke table valued functions in SQL Server, see [Invoking Table-Valued Functions in SQL Server by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="97b3f-110">メッセージの構造とテーブル値関数用の SOAP アクションを参照してください[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)です。</span><span class="sxs-lookup"><span data-stu-id="97b3f-110">Message structure and SOAP actions for table valued functions, see [Message Schemas for Procedures and Functions](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b3f-111">参照</span><span class="sxs-lookup"><span data-stu-id="97b3f-111">See Also</span></span>  
 <span data-ttu-id="97b3f-112">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="97b3f-112">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>