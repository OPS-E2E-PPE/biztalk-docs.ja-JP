---
title: Oracle データベースで複合操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5595823fab4f25948e3d88db759ae525f62130
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215122"
---
# <a name="run-composite-operations-in-oracle-database"></a><span data-ttu-id="9d353-102">Oracle データベースでの複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d353-102">Run Composite Operations in Oracle Database</span></span>
<span data-ttu-id="9d353-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントが、次の操作、および任意の順序で任意の数を含めることができる複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d353-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
-   <span data-ttu-id="9d353-104">選択、挿入、更新、およびテーブルとビューでの Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="9d353-104">Select, Insert, Update, and Delete operations on tables and views.</span></span>  
  
-   <span data-ttu-id="9d353-105">ストアド プロシージャ、関数、およびプロシージャまたはアダプターでの操作として表示されたパッケージ内の関数。</span><span class="sxs-lookup"><span data-stu-id="9d353-105">Stored procedures, functions, and procedures or functions within packages that are surfaced as operations in the adapter.</span></span>  
  
 <span data-ttu-id="9d353-106">複合操作内の操作対象に、同じデータベースまたは別のデータベースのテーブルおよびビューできます。</span><span class="sxs-lookup"><span data-stu-id="9d353-106">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="9d353-107">ただし、データを共有または複合操作のさまざまな操作間で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9d353-107">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="9d353-108">たとえば、操作では、複合、選択操作の結果セットは使えませんの入力パラメーターとしてストアド プロシージャの。</span><span class="sxs-lookup"><span data-stu-id="9d353-108">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
 <span data-ttu-id="9d353-109">複合操作内の各操作は、別々 の接続を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="9d353-109">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="9d353-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作では、複合、操作の数として ODP.NET 接続プールからの複数の接続を使用し、操作が実行されると、接続を解放します。</span><span class="sxs-lookup"><span data-stu-id="9d353-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="9d353-111">ただし、複合操作の操作は、結果セットを返す場合、は、接続は、メッセージが処理した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="9d353-111">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9d353-112">複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="9d353-112">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="9d353-113">BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="9d353-113">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="9d353-114">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d353-114">Select operation.</span></span>  
>   
>  <span data-ttu-id="9d353-115">この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="9d353-115">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="9d353-116">詳細については、 **MinPoolSize**バインディング プロパティを参照してください[Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d353-116">For more information about the **MinPoolSize** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="9d353-117">詳細については。</span><span class="sxs-lookup"><span data-stu-id="9d353-117">For information about:</span></span>  
  
-   <span data-ttu-id="9d353-118">複合操作を実行する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server での Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d353-118">How to perform composite operations in [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on Oracle Database by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9d353-119">メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)です。</span><span class="sxs-lookup"><span data-stu-id="9d353-119">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d353-120">参照</span><span class="sxs-lookup"><span data-stu-id="9d353-120">See Also</span></span>  
 <span data-ttu-id="9d353-121">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="9d353-121">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>