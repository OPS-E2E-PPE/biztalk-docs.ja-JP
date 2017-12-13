---
title: "SQLEXECUTE 操作のメッセージ スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7efc6a59e9dd4c163388803763a7b90a13b31
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a><span data-ttu-id="74430-102">SQLEXECUTE 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="74430-102">Message Schemas for the SQLEXECUTE Operation</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="74430-103">LOB システムに存在成果物のための厳密に型指定されたメタデータを表示し、これらの成果物の標準的な操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="74430-103"> surfaces strongly-typed metadata for artifacts present in the LOB system and exposes standard operations on these artifacts.</span></span> <span data-ttu-id="74430-104">ただし、アプリケーションがアプリケーションにビジネス ロジックによって駆動される任意の SQL ステートメントの実行を必要がありますのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="74430-104">However, there are scenarios where an application might require the execution of an arbitrary SQL statement that is driven by the business logic in the application.</span></span> <span data-ttu-id="74430-105">たとえばをする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74430-105">For example, you may want to:</span></span>  
  
-   <span data-ttu-id="74430-106">表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle シーケンスの NEXTVAL を取得します。</span><span class="sxs-lookup"><span data-stu-id="74430-106">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
-   <span data-ttu-id="74430-107">データ定義言語の操作です。たとえば、テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="74430-107">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
-   <span data-ttu-id="74430-108">デザイン時に存在しませんでした、データベースの成果物の操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="74430-108">Perform operations on a database artifact that was not present at design-time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
-   <span data-ttu-id="74430-109">によって表示される演算よりもテーブルでより複雑な DML 操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; の例は、結合句を含むクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="74430-109">Perform more complex DML operations on tables than the operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example perform a query that includes a JOIN clause.</span></span>  
  
 <span data-ttu-id="74430-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスのようなシナリオをサポートするために、SQLEXECUTE 操作と呼ばれる特別な操作です。</span><span class="sxs-lookup"><span data-stu-id="74430-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces a special operation called the SQLEXECUTE operation to support such scenarios.</span></span> <span data-ttu-id="74430-111">この操作を使用するの任意の SQL ステートメントを指定することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで実行します。</span><span class="sxs-lookup"><span data-stu-id="74430-111">By using this operation, you can specify an arbitrary SQL statement for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to execute on the Oracle database.</span></span> <span data-ttu-id="74430-112">SQL ステートメントに渡す入力パラメーターの複数のブロックを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="74430-112">You can also specify multiple blocks of input parameters to the SQL statement.</span></span> <span data-ttu-id="74430-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーターのセットごとに、SQL ステートメントを実行し、汎用的な (弱い型指定) のレコード セットとして出力を返します。</span><span class="sxs-lookup"><span data-stu-id="74430-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes the SQL statement once for each set of parameters and returns any output as a generic (weakly-typed) record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74430-114">IN を渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージに IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="74430-114">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="74430-115">Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作返さない外の値と、クライアントに IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="74430-115">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="74430-116">設定するように、専用の操作を呼び出すことによってプロシージャ、関数、またはパッケージを起動する場合は、Microsoft にお勧めする、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物用に公開します。</span><span class="sxs-lookup"><span data-stu-id="74430-116">If you want to invoke procedures, functions, or packages, Microsoft recommends that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="74430-117">次の XML は、SQLEXECUTE 操作の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="74430-117">The following XML shows the structure of the SQLEXECUTE operation:</span></span>  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="74430-118">[ステートメント] = SQL ステートメントを実行します。たとえば、"選択 * emp から WHERE empno =: emp_no"です。</span><span class="sxs-lookup"><span data-stu-id="74430-118">[STATEMENT] = The SQL statement to execute; for example, "SELECT * from emp WHERE empno=:emp_no".</span></span>  
  
 <span data-ttu-id="74430-119">[PARAM_SPEC] で、SQL ステートメントとそのデータ型は IN パラメーターの一覧を =たとえば、"emp_no 数"です。</span><span class="sxs-lookup"><span data-stu-id="74430-119">[PARAM_SPEC] = The list of the IN parameters in the SQL statement and their data types; for example, "emp_no NUMBER".</span></span>  
  
 <span data-ttu-id="74430-120">[PARAM_VAL_1] の最初のパラメーターの値を = です。</span><span class="sxs-lookup"><span data-stu-id="74430-120">[PARAM_VAL_1] = The value of the first parameter.</span></span>  
  
 <span data-ttu-id="74430-121">各\<PARAMETERDATA\>セクションには、完全なセットが含まれています。\<パラメーター\>内のスキーマに一致する要素、 \<PARAMETERSCHEMA\>セクションです。</span><span class="sxs-lookup"><span data-stu-id="74430-121">Each \<PARAMETERDATA\> section contains a complete set of \<PARAMETER\> elements that match the schema in the \<PARAMETERSCHEMA\> section.</span></span> <span data-ttu-id="74430-122">\<PARAMETERSET\>複数を含めることができる\<PARAMETERDATA\>セクションです。</span><span class="sxs-lookup"><span data-stu-id="74430-122">The \<PARAMETERSET\> can contain multiple \<PARAMETERDATA\> sections.</span></span> <span data-ttu-id="74430-123">これは、大文字と小文字、SQL ステートメントが各パラメーター セットに対して 1 回の複数回実行されます。</span><span class="sxs-lookup"><span data-stu-id="74430-123">If this is the case, the SQL statement is executed multiple times, once against each parameter set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74430-124">参照</span><span class="sxs-lookup"><span data-stu-id="74430-124">See Also</span></span>  
 [<span data-ttu-id="74430-125">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="74430-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)