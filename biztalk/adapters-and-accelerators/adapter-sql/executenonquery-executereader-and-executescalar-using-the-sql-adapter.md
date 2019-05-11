---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作の SQL アダプターを使用しての実行 |Microsoft Docs
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
ms.openlocfilehash: 0e4a32828be8fbaaa65263c24aa98ff1cfd957ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369537"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a><span data-ttu-id="85719-102">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作の SQL アダプターを使用してを実行します。</span><span class="sxs-lookup"><span data-stu-id="85719-102">Run ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations using the SQL adapter</span></span>
<span data-ttu-id="85719-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]ルート レベルでは、次の操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="85719-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the following operations at the root level:</span></span>  
  
- <span data-ttu-id="85719-104">**ExecuteNonQuery**:この操作を使用して、すべての結果が返されるセットしたくない場合は、SQL Server で任意の SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="85719-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements in SQL Server if you do not want any result set to be returned.</span></span> <span data-ttu-id="85719-105">この操作を使用して、データベース オブジェクトを作成または更新、挿入を実行することによってデータベース内のデータを変更またはステートメントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="85719-105">You can use this operation to create database objects or change data in a database by executing UPDATE, INSERT, or DELETE statements.</span></span> <span data-ttu-id="85719-106">この操作の戻り値が Int32 データ型、および。</span><span class="sxs-lookup"><span data-stu-id="85719-106">The return value of this operation is of Int32 data type, and:</span></span>  
  
  -   <span data-ttu-id="85719-107">UPDATE、INSERT、および DELETE ステートメントでは、戻り値は、SQL ステートメントによって影響を受ける行の数です。</span><span class="sxs-lookup"><span data-stu-id="85719-107">For the UPDATE, INSERT, and DELETE statements, the return value is the number of rows affected by the SQL statement.</span></span>  
  
  -   <span data-ttu-id="85719-108">その他のすべての種類のステートメントでは、戻り値は **-1**します。</span><span class="sxs-lookup"><span data-stu-id="85719-108">For all other types of statements, the return value is **-1**.</span></span>  
  
- <span data-ttu-id="85719-109">**ExecuteReader**:この操作を使用して、結果データセットの配列として存在する場合に返されるセットの場合は、SQL Server で任意の SQL ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="85719-109">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements in SQL Server if you want the result set to be returned, if any, as an array of DataSet.</span></span> <span data-ttu-id="85719-110">データセットの詳細についてを参照してください「DataSet クラス」 [ http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)します。</span><span class="sxs-lookup"><span data-stu-id="85719-110">For information about DataSet, see “DataSet Class” at [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).</span></span>  
  
- <span data-ttu-id="85719-111">**ExecuteScalar**:SQL server を 1 つの値を返す任意の SQL ステートメントを実行するのにには、この操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="85719-111">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements in SQL Server to return a single value.</span></span> <span data-ttu-id="85719-112">この操作は、SQL ステートメントによって返される結果セットの最初の行の最初の列でのみ、値を返します。</span><span class="sxs-lookup"><span data-stu-id="85719-112">This operation returns the value only in the first column of the first row in the result set returned by the SQL statement.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="85719-113">ExecuteReader 経由で ExecuteScalar の利点は、ExecuteScalar 操作の応答メッセージのペイロードが ExecuteReader 操作によって返されるものと比較されますかなり短くなります。</span><span class="sxs-lookup"><span data-stu-id="85719-113">The advantage of ExecuteScalar over ExecuteReader is that the response message payload of the ExecuteScalar operation is much smaller compared to the one returned by the ExecuteReader operation.</span></span> <span data-ttu-id="85719-114">したがって、返される値の 1 つだけを必要とする場合は、ExecuteReader ではなく ExecuteScalar を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85719-114">Therefore, if you require only one value to be returned, you should use ExecuteScalar instead of ExecuteReader.</span></span>  
  
  <span data-ttu-id="85719-115">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作を使用して、複数の SQL ステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="85719-115">You can use the ExecuteNonQuery, ExecuteReader or ExecuteScalar operation to execute multiple SQL statements.</span></span>  
  
  <span data-ttu-id="85719-116">使用してこれらの操作の実行の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[ExecuteReader、executescalar、ExecuteNonQuery 操作を使用して BizTalk Server によって](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)します。</span><span class="sxs-lookup"><span data-stu-id="85719-116">For more information about performing these operations using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85719-117">参照</span><span class="sxs-lookup"><span data-stu-id="85719-117">See Also</span></span>  
 <span data-ttu-id="85719-118">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="85719-118">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>