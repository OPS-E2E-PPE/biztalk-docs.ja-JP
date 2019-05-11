---
title: Oracle データベースで複合操作の実行 |Microsoft Docs
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
ms.openlocfilehash: 9a9728f456e6f3cf3ad95a392a5fdc45d6cf9265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376119"
---
# <a name="run-composite-operations-in-oracle-database"></a><span data-ttu-id="ec3df-102">Oracle データベースで複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-102">Run Composite Operations in Oracle Database</span></span>
<span data-ttu-id="ec3df-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]により、任意の順序と、次の操作の任意の数を含めることができる複合操作を実行するクライアントはアダプター。</span><span class="sxs-lookup"><span data-stu-id="ec3df-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="ec3df-104">選択、挿入、更新、およびテーブルとビューで操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-104">Select, Insert, Update, and Delete operations on tables and views.</span></span>  
  
- <span data-ttu-id="ec3df-105">ストアド プロシージャ、関数、およびプロシージャまたはアダプターでの操作として表示されるパッケージ内の関数。</span><span class="sxs-lookup"><span data-stu-id="ec3df-105">Stored procedures, functions, and procedures or functions within packages that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="ec3df-106">複合操作の操作は、テーブルと同じデータベースまたは別のデータベース内のビューにターゲットします。</span><span class="sxs-lookup"><span data-stu-id="ec3df-106">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="ec3df-107">ただし、データを共有または複合操作のさまざまな操作で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec3df-107">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="ec3df-108">たとえば、複合操作で Select 操作の結果セットは使えません入力パラメーターとしてストアド プロシージャの。</span><span class="sxs-lookup"><span data-stu-id="ec3df-108">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
  <span data-ttu-id="ec3df-109">複合操作の各操作を実行するには、個別の接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-109">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="ec3df-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]複合操作での操作の数は ODP.NET 接続プールからできるだけ多くの接続を消費し、取得、操作を実行するときに、接続を解放します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="ec3df-111">ただし、複合操作内の操作では、結果セットを返しますの場合は、接続は、メッセージが消費した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="ec3df-111">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ec3df-112">複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="ec3df-112">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
> 
> - <span data-ttu-id="ec3df-113">OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ec3df-113">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
>   -   <span data-ttu-id="ec3df-114">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-114">Select operation.</span></span>  
> 
>   <span data-ttu-id="ec3df-115">この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="ec3df-115">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="ec3df-116">詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-116">For more information about the **MinPoolSize** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="ec3df-117">詳細については。</span><span class="sxs-lookup"><span data-stu-id="ec3df-117">For information about:</span></span>  
  
- <span data-ttu-id="ec3df-118">複合操作を実行する方法[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server での Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-118">How to perform composite operations in [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on Oracle Database by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="ec3df-119">複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec3df-119">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3df-120">参照</span><span class="sxs-lookup"><span data-stu-id="ec3df-120">See Also</span></span>  
 <span data-ttu-id="ec3df-121">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="ec3df-121">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>