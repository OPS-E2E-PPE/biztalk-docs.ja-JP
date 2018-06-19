---
title: ExecuteNonQuery、ExecuteReader、および ExecuteScalar を SQL アダプターを使用して操作を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f68f4378a4d89d2a997f5a78a524e4f6bfca2c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222274"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a><span data-ttu-id="2edfa-102">ExecuteNonQuery、ExecuteReader、および ExecuteScalar を SQL アダプターを使用して操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-102">Run ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations using the SQL adapter</span></span>
<span data-ttu-id="2edfa-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ルート レベルで、次の操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the following operations at the root level:</span></span>  
  
-   <span data-ttu-id="2edfa-104">**ExecuteNonQuery**: この操作を使用するすべての結果が返されるセットしたくない場合は、SQL Server で任意の SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements in SQL Server if you do not want any result set to be returned.</span></span> <span data-ttu-id="2edfa-105">この操作を使用するデータベース オブジェクトを作成または更新、挿入を実行することによって、データベース内のデータを変更したり、ステートメントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2edfa-105">You can use this operation to create database objects or change data in a database by executing UPDATE, INSERT, or DELETE statements.</span></span> <span data-ttu-id="2edfa-106">この操作の戻り値が Int32 データ型、および。</span><span class="sxs-lookup"><span data-stu-id="2edfa-106">The return value of this operation is of Int32 data type, and:</span></span>  
  
    -   <span data-ttu-id="2edfa-107">UPDATE、INSERT、および DELETE ステートメントでは、戻り値は、SQL ステートメントによって影響を受ける行の数です。</span><span class="sxs-lookup"><span data-stu-id="2edfa-107">For the UPDATE, INSERT, and DELETE statements, the return value is the number of rows affected by the SQL statement.</span></span>  
  
    -   <span data-ttu-id="2edfa-108">その他のすべての種類のステートメントでは、戻り値は **-1**です。</span><span class="sxs-lookup"><span data-stu-id="2edfa-108">For all other types of statements, the return value is **-1**.</span></span>  
  
-   <span data-ttu-id="2edfa-109">**ExecuteReader**: この操作を使用する場合、結果セットに返されるデータセットの配列として、任意の場合は、SQL Server で任意の SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-109">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements in SQL Server if you want the result set to be returned, if any, as an array of DataSet.</span></span> <span data-ttu-id="2edfa-110">データセットについてで「データセット クラス」を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)です。</span><span class="sxs-lookup"><span data-stu-id="2edfa-110">For information about DataSet, see “DataSet Class” at [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).</span></span>  
  
-   <span data-ttu-id="2edfa-111">**ExecuteScalar**: この操作を 1 つの値を返す SQL Server での任意の SQL ステートメントの実行に使用します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-111">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements in SQL Server to return a single value.</span></span> <span data-ttu-id="2edfa-112">この操作は、SQL ステートメントによって返される結果セットの最初の行の最初の列でのみ、値を返します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-112">This operation returns the value only in the first column of the first row in the result set returned by the SQL statement.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2edfa-113">ExecuteReader に対する ExecuteScalar の利点を ExecuteScalar 操作の応答メッセージのペイロードが非常に小さくなってと比較するが ExecuteReader 操作によって返される 1 つ。</span><span class="sxs-lookup"><span data-stu-id="2edfa-113">The advantage of ExecuteScalar over ExecuteReader is that the response message payload of the ExecuteScalar operation is much smaller compared to the one returned by the ExecuteReader operation.</span></span> <span data-ttu-id="2edfa-114">したがって、返される値を 1 つだけを必要とする場合は、ExecuteReader ではなく ExecuteScalar を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2edfa-114">Therefore, if you require only one value to be returned, you should use ExecuteScalar instead of ExecuteReader.</span></span>  
  
 <span data-ttu-id="2edfa-115">ExecuteNonQuery、ExecuteReader または ExecuteScalar 操作を使用すると、複数の SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="2edfa-115">You can use the ExecuteNonQuery, ExecuteReader or ExecuteScalar operation to execute multiple SQL statements.</span></span>  
  
 <span data-ttu-id="2edfa-116">使用してこれらの操作の実行の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ExecuteReader、ExecuteScalar、または BizTalk Server を使用して、ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)です。</span><span class="sxs-lookup"><span data-stu-id="2edfa-116">For more information about performing these operations using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edfa-117">参照</span><span class="sxs-lookup"><span data-stu-id="2edfa-117">See Also</span></span>  
 <span data-ttu-id="2edfa-118">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="2edfa-118">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>