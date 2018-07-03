---
title: SQLEXECUTE 操作のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f753d2dcbd5782f456b099174e0369e37cca2e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981483"
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a><span data-ttu-id="b6b2d-102">SQLEXECUTE 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="b6b2d-102">Message Schemas for the SQLEXECUTE Operation</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="b6b2d-103"> LOB システムに存在する成果物の厳密に型指定されたメタデータを表示し、これらの成果物の標準的な操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-103"> surfaces strongly-typed metadata for artifacts present in the LOB system and exposes standard operations on these artifacts.</span></span> <span data-ttu-id="b6b2d-104">ただし、アプリケーションが、アプリケーションでビジネス ロジックによって駆動される任意の SQL ステートメントの実行を必要がありますのシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-104">However, there are scenarios where an application might require the execution of an arbitrary SQL statement that is driven by the business logic in the application.</span></span> <span data-ttu-id="b6b2d-105">たとえば、しをたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-105">For example, you may want to:</span></span>  
  
- <span data-ttu-id="b6b2d-106">表示されませんがデータベースのアイテムに対して操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 たとえば、CURVAL または Oracle のシーケンスの NEXTVAL を取得します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-106">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
- <span data-ttu-id="b6b2d-107">データ定義言語の操作を実行します。たとえば、テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-107">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
- <span data-ttu-id="b6b2d-108">デザイン時になかったデータベース成果物に対して操作を実行します。たとえば、ビジネス ロジックによって作成される一時テーブル内のレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-108">Perform operations on a database artifact that was not present at design-time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
- <span data-ttu-id="b6b2d-109">によって表示される演算よりもテーブルでより複雑な DML 操作を実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; の例は、JOIN 句を含むクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-109">Perform more complex DML operations on tables than the operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example perform a query that includes a JOIN clause.</span></span>  
  
  <span data-ttu-id="b6b2d-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスのようなシナリオをサポートするために、SQLEXECUTE 操作と呼ばれる特別な操作です。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces a special operation called the SQLEXECUTE operation to support such scenarios.</span></span> <span data-ttu-id="b6b2d-111">このオペレーションを使用しての任意の SQL ステートメントを指定することができます、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで実行します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-111">By using this operation, you can specify an arbitrary SQL statement for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to execute on the Oracle database.</span></span> <span data-ttu-id="b6b2d-112">SQL ステートメントへの入力パラメーターの複数のブロックを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-112">You can also specify multiple blocks of input parameters to the SQL statement.</span></span> <span data-ttu-id="b6b2d-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーターのセットごとに、SQL ステートメントを実行し、汎用的な (弱い型指定) のレコード セットとして出力を返します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes the SQL statement once for each set of parameters and returns any output as a generic (weakly-typed) record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6b2d-114">渡すことができ、プロシージャ、関数、および SQLEXECUTE 操作内のパッケージには、IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-114">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="b6b2d-115">Oracle データベースで指定されたパラメーターで呼び出された成果物が実行されます。ただし、SQLEXECUTE 操作がタイムアウトの値を返されませんとクライアントの OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-115">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="b6b2d-116">専用の操作を呼び出して実行をプロシージャ、関数、またはパッケージを呼び出す場合は、Microsoft にお勧めする[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これら Oracle の成果物を公開します。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-116">If you want to invoke procedures, functions, or packages, Microsoft recommends that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="b6b2d-117">次の XML は、SQLEXECUTE 操作の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-117">The following XML shows the structure of the SQLEXECUTE operation:</span></span>  
  
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
  
 <span data-ttu-id="b6b2d-118">[ステートメント]; を実行する SQL ステートメントを =たとえば、"選択 \* emp から WHERE empno =: emp_no"。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-118">[STATEMENT] = The SQL statement to execute; for example, "SELECT \* from emp WHERE empno=:emp_no".</span></span>  
  
 <span data-ttu-id="b6b2d-119">[PARAM_SPEC] SQL ステートメントとそのデータ型は IN パラメーターの一覧を =たとえば、"emp_no 数"です。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-119">[PARAM_SPEC] = The list of the IN parameters in the SQL statement and their data types; for example, "emp_no NUMBER".</span></span>  
  
 <span data-ttu-id="b6b2d-120">[PARAM_VAL_1] = 最初のパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-120">[PARAM_VAL_1] = The value of the first parameter.</span></span>  
  
 <span data-ttu-id="b6b2d-121">各\<PARAMETERDATA\>セクションには、完全なセットが含まれています。\<パラメーター\>内のスキーマに一致する要素、 \<PARAMETERSCHEMA\>セクション。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-121">Each \<PARAMETERDATA\> section contains a complete set of \<PARAMETER\> elements that match the schema in the \<PARAMETERSCHEMA\> section.</span></span> <span data-ttu-id="b6b2d-122">\<PARAMETERSET\>複数含めることができます\<PARAMETERDATA\>セクション。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-122">The \<PARAMETERSET\> can contain multiple \<PARAMETERDATA\> sections.</span></span> <span data-ttu-id="b6b2d-123">大文字と小文字の場合は、SQL ステートメントは各パラメーターのセットに対して 1 回の繰り返しで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b6b2d-123">If this is the case, the SQL statement is executed multiple times, once against each parameter set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b2d-124">参照</span><span class="sxs-lookup"><span data-stu-id="b6b2d-124">See Also</span></span>  
 [<span data-ttu-id="b6b2d-125">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="b6b2d-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)