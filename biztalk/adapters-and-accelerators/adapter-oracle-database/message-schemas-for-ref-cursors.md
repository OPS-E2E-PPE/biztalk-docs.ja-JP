---
title: メッセージの REF CURSOR のスキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bddfde0b0897c7d8c21a20126d2fa1d2f0f8c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214762"
---
# <a name="message-schemas-for-ref-cursors"></a><span data-ttu-id="3ac98-102">REF CURSOR のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="3ac98-102">Message Schemas for REF CURSORS</span></span>
<span data-ttu-id="3ac98-103">REF CURSOR は、Oracle データベースに結果セットへのポインターを表す Oracle PL/SQL データ型です。</span><span class="sxs-lookup"><span data-stu-id="3ac98-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="3ac98-104">REF CURSOR 型は入力を有効にするデータのストリーミングを出力し、大量の PL/SQL コード ブロックとの間のデータを転送するために最適です。</span><span class="sxs-lookup"><span data-stu-id="3ac98-104">REF CURSOR types enable input and output streaming of data and are ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span> [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="3ac98-105">アウト PL/SQL プロシージャと関数でとして厳密に型指定され、弱い型指定の REF CURSOR パラメーターを渡すと IN OUT パラメーターのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-105"> provides support for passing strongly-typed and weakly-typed REF CURSOR parameters to PL/SQL procedures and functions as IN, OUT and IN OUT parameters.</span></span>  
  
 <span data-ttu-id="3ac98-106">Oracle データベースでは、REF CURSOR 型は厳密に型指定されたまたは、弱い型指定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ac98-106">In the Oracle database, a REF CURSOR type can be either strongly-typed or weakly-typed:</span></span>  
  
-   <span data-ttu-id="3ac98-107">厳密に型指定の REF CURSOR としての RETURN 句で宣言されて`TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`です。</span><span class="sxs-lookup"><span data-stu-id="3ac98-107">A strongly-typed REF CURSOR is declared with a RETURN clause as in `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`.</span></span> <span data-ttu-id="3ac98-108">厳密に型指定された REF カーソル変数では、その REF CURSOR 型が宣言されている型と一致するデータを含む結果セットを表すことができますのみです。</span><span class="sxs-lookup"><span data-stu-id="3ac98-108">A strongly-typed REF CURSOR variable can only represent a result set that contains data that matches the type with which its REF CURSOR type is declared.</span></span> <span data-ttu-id="3ac98-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]厳密に型指定された結果 REF カーソルの厳密に型指定されたセットを返します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a strongly-typed result set for a strongly-typed REF CURSOR.</span></span>  
  
-   <span data-ttu-id="3ac98-110">弱い型指定の REF CURSOR としての RETURN 句なしで宣言は`TYPE WeakCurType IS REF CURSOR;`します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-110">A weakly-typed REF CURSOR is declared without a RETURN clause as in `TYPE WeakCurType IS REF CURSOR;`.</span></span> <span data-ttu-id="3ac98-111">Oracle では、弱い型指定の REF CURSOR 変数の宣言に使用できる SYS_REFCURSOR と呼ばれる特別な REF カーソルの種類も提供します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-111">Oracle also provides a special REF CURSOR type called SYS_REFCURSOR that can be used to declare weakly-typed REF CURSOR variables.</span></span> <span data-ttu-id="3ac98-112">REF カーソル変数の弱い型指定には、あらゆる種類の行のデータを含む結果セットを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="3ac98-112">Weakly-typed REF CURSOR variables can represent a result set that contains any kind of row data.</span></span> <span data-ttu-id="3ac98-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]弱い型指定の REF CURSOR の汎用レコードの弱い型指定の結果セットを返します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a weakly-typed result set of generic records for a weakly-typed REF CURSOR.</span></span>  
  
## <a name="in-ref-cursor-parameters"></a><span data-ttu-id="3ac98-114">REF CURSOR パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ac98-114">IN REF CURSOR Parameters</span></span>  
 <span data-ttu-id="3ac98-115">REF CURSOR でサーバーを作成、Oracle、ODP.NET API がないため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]クライアント プログラムを作成し、REF CURSOR 変数の管理の機能を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ac98-115">There is no ODP.NET API to create a REF CURSOR on the Oracle server, so the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cannot provide the capability for a client program to create and maintain REF CURSOR variables.</span></span>  
  
 <span data-ttu-id="3ac98-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ただし、REF CURSOR を返す PL/SQL コードのブロックを指定することによっての REF CURSOR パラメーターを関数やストアド プロシージャに渡すクライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ac98-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does, however, enable a client to pass IN REF CURSOR parameters to functions or stored procedures by specifying a block of PL/SQL code that returns a REF CURSOR.</span></span> <span data-ttu-id="3ac98-117">アダプターでは、このコードを使用して作成し、Oracle サーバーで REF カーソル変数を開く関数を呼び出す、または IN パラメーターとしてこの変数を使用してストアド プロシージャを格納します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-117">The adapter uses this code to create and OPEN a REF CURSOR variable on the Oracle server; it then calls the function or stored procedure using this variable as the IN parameter.</span></span>  
  
 <span data-ttu-id="3ac98-118">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] PL/SQL コード ブロックを含む文字列としての REF CURSOR パラメーターを表します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-118">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CURSOR parameters as strings that contain the PL/SQL code block.</span></span> <span data-ttu-id="3ac98-119">このブロック内で REF カーソルの位置は疑問符 (?) で指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-119">Within this block, the location of the REF CURSOR is specified with a question mark (?).</span></span> <span data-ttu-id="3ac98-120">PL/SQL のコード ブロックは、SQL クエリを含んだ開いて FOR ステートメントを含めることができます。関数またはプロシージャの呼び出しを含めることができますかで OUT パラメーターで開かれた REF カーソルが返されます。</span><span class="sxs-lookup"><span data-stu-id="3ac98-120">The PL/SQL code block can contain an OPEN-FOR statement that contains a SQL query; or it can contain a function or procedure call in which an opened REF CURSOR is returned in an OUT parameter.</span></span>  
  
 <span data-ttu-id="3ac98-121">ストアド プロシージャまたは REF カーソルをオープンする関数を呼び出すことによってで REF カーソルを指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-121">The following shows how to specify an IN REF CURSOR by calling a stored procedure or function to open the REF CURSOR.</span></span>  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 <span data-ttu-id="3ac98-122">REF カーソルをオープンする SELECT クエリを使用しての REF CURSOR を指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-122">The following shows how to specify an IN REF CURSOR by using a SELECT query to open the REF CURSOR.</span></span>  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a><span data-ttu-id="3ac98-123">REF CURSOR パラメーターを</span><span class="sxs-lookup"><span data-stu-id="3ac98-123">OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="3ac98-124">REF CURSOR 出力パラメーターに、いずれかとして厳密に型指定や、弱い型指定の結果セットが返されます。</span><span class="sxs-lookup"><span data-stu-id="3ac98-124">OUT REF CURSOR parameters are returned as either strongly-typed or weakly-typed result sets.</span></span> <span data-ttu-id="3ac98-125">返される結果の型は、Oracle サーバーでストアド プロシージャまたは関数定義で厳密に型指定されたか、弱い型指定の REF CURSOR として REF CURSOR パラメーターが宣言されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ac98-125">The type of the result set returned depends on whether the REF CURSOR parameter is declared as a strongly-typed or weakly-typed REF CURSOR in the stored procedure or function definition on the Oracle server.</span></span> <span data-ttu-id="3ac98-126">REF CURSOR パラメーターの厳密に型指定された、厳密に型指定された結果セットが返され、弱い型指定の REF CURSOR パラメーターの厳密に型指定された結果セットが返されます (たとえば、パラメーター型で宣言されて、SYS_REFCURSOR)。</span><span class="sxs-lookup"><span data-stu-id="3ac98-126">A strongly-typed result set is returned for strongly-typed REF CURSOR parameters and a weakly-typed result set is returned for weakly-typed REF CURSOR parameters (for example, parameters declared with a SYS_REFCURSOR type).</span></span>  
  
 <span data-ttu-id="3ac98-127">REF CURSOR 出力パラメーターの厳密に型指定された XML を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-127">The following shows the XML for a strongly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 <span data-ttu-id="3ac98-128">弱い型指定の REF CURSOR 出力パラメーターの XML を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-128">The following shows the XML for a weakly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a><span data-ttu-id="3ac98-129">REF CURSOR パラメーターを</span><span class="sxs-lookup"><span data-stu-id="3ac98-129">IN OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="3ac98-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の REF CURSOR パラメーターをモデル化文字列パラメーターと複合型としての REF CURSOR 出力パラメーターとしてサポートできない 1 つの型の REF CURSOR を IN パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3ac98-130">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] models IN REF CURSOR parameters as strings and OUT REF CURSOR parameters as complex types, it cannot support a single type for an IN OUT REF CURSOR parameter.</span></span> <span data-ttu-id="3ac98-131">このため、REF CURSOR を IN パラメーターとして扱います 2 つの異なるパラメーター: 要求メッセージと応答メッセージの OUT パラメーターに IN パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3ac98-131">For this reason, it treats IN OUT REF CURSOR parameters as two different parameters: an IN parameter in the request message and an OUT parameter in the response message.</span></span>  
  
 <span data-ttu-id="3ac98-132">サービス モデルのプログラミングで名前の競合を避けるために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] [PARAM_NAME] をという名前の指定されたパラメーター、2 つのパラメーターが作成されるため、要求メッセージで IN パラメーターに文字列"_IN"を追加します。</span><span class="sxs-lookup"><span data-stu-id="3ac98-132">To avoid a name conflict in service model programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] appends the string "_IN" to the IN parameter in the request message so that for a given parameter named [PARAM_NAME], two parameters are created:</span></span>  
  
-   <span data-ttu-id="3ac98-133">[PARAM_NAME] _IN は、ストアド プロシージャまたは関数の要求メッセージ内で REF カーソル パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3ac98-133">[PARAM_NAME]_IN is an IN REF CURSOR parameter in the stored procedure or function request message.</span></span> <span data-ttu-id="3ac98-134">REF CURSOR を返す PL/SQL ステートメント (select クエリまたはストアド プロシージャまたは関数の呼び出し) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ac98-134">It contains a PL/SQL statement (either a select query or a stored procedure or function call) that returns a REF CURSOR.</span></span>  
  
-   <span data-ttu-id="3ac98-135">[PARAM_NAME] は、ストアド プロシージャまたは関数の応答メッセージの REF CURSOR 出力パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3ac98-135">[PARAM_NAME] is an OUT REF CURSOR parameter in the stored procedure or function response message.</span></span> <span data-ttu-id="3ac98-136">厳密に型指定や、弱い型指定の結果セットとして除外 REF カーソルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ac98-136">It contains the OUT REF CURSOR as a strongly-typed or weakly-typed result set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ac98-137">アダプターは、プロシージャまたは関数 [PARAM_NAME] _IN と [PARAM_NAME] という名前で OUT REF CURSOR パラメーターをという名前のパラメーターを含むをサポートできません。</span><span class="sxs-lookup"><span data-stu-id="3ac98-137">The adapter cannot support a procedure or function that contains an IN parameter named [PARAM_NAME]_IN and an IN OUT REF CURSOR parameter named [PARAM_NAME].</span></span> <span data-ttu-id="3ac98-138">これは、アダプターには、REF CURSOR パラメーターに入力を表す [PARAM_NAME] _IN をという名前のパラメーターが必要ですが、要求メッセージの両方のパラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ac98-138">This is because the adapter expects a parameter named [PARAM_NAME]_IN to represent the input to the REF CURSOR parameter, and you cannot specify both parameters in the request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac98-139">参照</span><span class="sxs-lookup"><span data-stu-id="3ac98-139">See Also</span></span>  
 [<span data-ttu-id="3ac98-140">メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="3ac98-140">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)