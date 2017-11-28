---
title: "Oracle データベースで SQLEXECUTE 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac8d5c8284e1f273d4b9aef17e79e25636dc581
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sqlexecute-operation-in-oracle-database"></a><span data-ttu-id="41985-102">Oracle データベースで SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="41985-102">SQLEXECUTE Operation in Oracle Database</span></span>
<span data-ttu-id="41985-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle のデータベース成果物の操作の標準セットを表示します。</span><span class="sxs-lookup"><span data-stu-id="41985-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="41985-104">これらの操作を使用すると、Oracle 関数またはプロシージャの呼び出しなどの操作または基本的な SQL データ操作言語 (DML) 操作でテーブルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="41985-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="41985-105">ただし、シナリオが考えられます、ビジネス ロジックによって操作を実行する必要があること、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]発生しません。</span><span class="sxs-lookup"><span data-stu-id="41985-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="41985-106">たとえばをする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41985-106">For example, you may want to:</span></span>  
  
-   <span data-ttu-id="41985-107">表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle シーケンスの NEXTVAL を取得します。</span><span class="sxs-lookup"><span data-stu-id="41985-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
-   <span data-ttu-id="41985-108">操作データ定義言語です。たとえば、テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="41985-108">Perform data definition language operations; for example, create a table.</span></span>  
  
-   <span data-ttu-id="41985-109">デザイン時に存在しませんでした、データベースの成果物の操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="41985-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
-   <span data-ttu-id="41985-110">操作よりもテーブルでより複雑な DML 操作を実行する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス; たとえば、クエリを実行して、含む JOIN 句です。</span><span class="sxs-lookup"><span data-stu-id="41985-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
 <span data-ttu-id="41985-111">これらのシナリオでは、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="41985-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="41985-112">SQLEXECUTE 操作がルート ノード (/) の下に表示される、**カテゴリを選択**ペインで、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]と[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="41985-112">The SQLEXECUTE operation is surfaced under the root node (/) in the **Select a category** pane in the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
 <span data-ttu-id="41985-113">SQLEXECUTE 操作を使用すると、Oracle データベースでパラメーター化された SQL ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="41985-113">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="41985-114">SQLEXECUTE 操作には、セットごとに、同じ SQL ステートメントを実行できるようにするパラメーター セットで構成される入力パラメーター ブロックがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41985-114">The SQLEXECUTE operation supports an input parameter block consisting of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="41985-115">SQLEXECUTE 操作は、レコード セットの汎用的な SQL ステートメントの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="41985-115">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41985-116">IN を渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージに IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="41985-116">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="41985-117">Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作返さない外の値と、クライアントに IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="41985-117">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="41985-118">プロシージャ、関数、またはパッケージを起動する場合をお勧めすることによって、専用の操作を呼び出すことを[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物用に公開します。</span><span class="sxs-lookup"><span data-stu-id="41985-118">If you want to invoke procedures, functions, or packages, we recommend that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="41985-119">詳細については。</span><span class="sxs-lookup"><span data-stu-id="41985-119">For more information about:</span></span>  
  
-   <span data-ttu-id="41985-120">使用して、SQLEXECUTE 操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[SQLEXECUTE 操作を使用して BizTalk Server によって実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="41985-120">Performing a SQLEXECUTE operation by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run SQLEXECUTE Operation by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="41985-121">SQLEXECUTE 操作を実行して、モデルを使用して、WCF サービスを参照してください[SQLEXECUTE 操作を WCF サービス モデルを使用して実行](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="41985-121">Performing a SQLEXECUTE operation by using the WCF service model, see [Run SQLEXECUTE Operation by Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="41985-122">WCF チャネル モデルを使用して、SQLEXECUTE 操作を実行するを参照してください[WCF チャネル モデルを使用して SQLEXECUTE 操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="41985-122">Performing the SQLEXECUTE operation by using the WCF channel model, see [Run SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
-   <span data-ttu-id="41985-123">メッセージの構造と SQLEXECUTE 操作を実行するための SOAP アクションを参照してください[SQLEXECUTE 操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)です。</span><span class="sxs-lookup"><span data-stu-id="41985-123">Message structure and SOAP actions for performing a SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41985-124">参照</span><span class="sxs-lookup"><span data-stu-id="41985-124">See Also</span></span>  
 <span data-ttu-id="41985-125">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="41985-125">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>