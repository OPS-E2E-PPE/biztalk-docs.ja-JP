---
title: "関数と、WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a6256491100939937113ac6f140adc031da0941
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="d0ba2-102">関数と、WCF サービス モデルを使用して Oracle データベースでプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d0ba2-102">Invoke Functions and Procedures in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="d0ba2-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]プロシージャ、関数、およびパッケージの操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces procedures, functions, and packages as operations.</span></span> <span data-ttu-id="d0ba2-104">WCF サービス モデルでは、これらの操作は、WCF クライアントのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-104">In the WCF service model these operations are represented as methods on a WCF client.</span></span> <span data-ttu-id="d0ba2-105">WCF サービス モデルと[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d0ba2-105">The WCF service model and the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:</span></span>  
  
-   <span data-ttu-id="d0ba2-106">**関数がサポートされて**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-106">**Support functions**.</span></span> <span data-ttu-id="d0ba2-107">Oracle 関数の戻り値は、WCF クライアント メソッドの戻り値として確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-107">The RETURN value of the Oracle function is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="d0ba2-108">Oracle パラメーターは、WCF クライアント メソッドに (適切な方向と定義されている以下) のパラメーターとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-108">Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="d0ba2-109">**プロシージャがサポート**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-109">**Support procedures**.</span></span> <span data-ttu-id="d0ba2-110">最初の出力、Oracle プロシージャのパラメーターは、WCF クライアント メソッドの戻り値として確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-110">The first OUT parameter of the Oracle procedure is surfaced as the return value of the WCF client method.</span></span> <span data-ttu-id="d0ba2-111">その他のすべての Oracle パラメーターは、WCF クライアント メソッドに (適切な方向と定義されている以下) のパラメーターとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-111">All other Oracle parameters are surfaced as parameters (with the appropriate direction as defined below) to the WCF client method.</span></span>  
  
-   <span data-ttu-id="d0ba2-112">**Oracle パッケージをサポート**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-112">**Support Oracle packages**.</span></span> <span data-ttu-id="d0ba2-113">パッケージの名前は、操作の名前とそのパラメーターの型の名前空間が修飾されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-113">The name of the operation and the namespace of its parameter types are qualified by the package name.</span></span>  
  
-   <span data-ttu-id="d0ba2-114">**サポートには、関数およびプロシージャがオーバー ロードされた**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-114">**Support overloaded functions and procedures**.</span></span>  
  
-   <span data-ttu-id="d0ba2-115">**サポート IN、OUT とプロシージャおよび関数の両方の基本の Oracle データ型のパラメーターを IN**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-115">**Support IN, OUT and IN OUT parameters for basic Oracle data types for both procedures and functions**.</span></span> <span data-ttu-id="d0ba2-116">OUT パラメーターとして表示された**アウト**WCF クライアント メソッドのパラメーターとで OUT パラメーターとして表示された**ref**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-116">OUT parameters are surfaced as **out** parameters on the WCF client method and IN OUT parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="d0ba2-117">**サポート IN、OUT、および IN OUT プロシージャと関数、関数の戻り値の REF CURSOR パラメーター**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-117">**Support IN, OUT, and IN OUT REF CURSOR parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="d0ba2-118">詳細については、次を参照してください。[を実行する操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-118">For more information, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="d0ba2-119">**サポートは、OUT、IN OUT レコード プロシージャや関数のパラメーターの型し関数の戻り値**です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-119">**Support IN, OUT, and IN OUT RECORD type parameters for procedures and functions, as well as function RETURN values**.</span></span> <span data-ttu-id="d0ba2-120">詳細については、次を参照してください。[を実行する操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-120">For more information, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="d0ba2-121">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="d0ba2-121">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="d0ba2-122">このトピックの使用、/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT の例では、プロシージャがオーバー ロードされます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-122">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT overloaded procedure.</span></span> <span data-ttu-id="d0ba2-123">この手順では、アカウント ID またはアカウント名のいずれかに基づいて、SCOTT/アカウント テーブルからレコードを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-123">This procedure reads a record from the SCOTT/ACCOUNT table based on either an account ID or an account name.</span></span> <span data-ttu-id="d0ba2-124">この手順と表を生成するスクリプトは、SDK サンプルの値が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-124">A script to generate this procedure and table is supplied with the SDK samples.</span></span> <span data-ttu-id="d0ba2-125">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-125">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="d0ba2-126">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="d0ba2-126">The WCF Client Class</span></span>  
 <span data-ttu-id="d0ba2-127">次の表は、WCF クライアントと手順については、生成されたメソッドの名前が機能し、パッケージであり、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスします。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-127">The following table shows the name of the WCF client and the method generated for procedures, functions and packages that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces.</span></span> <span data-ttu-id="d0ba2-128">関数またはプロシージャをオーバー ロードする場合を除き、1 つの WCF クライアントを使用して、すべてのスキーマのすべてのスキーマでプロシージャまたは関数のすべての機能およびパッケージ内のプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-128">Unless a function or procedure is overloaded, a single WCF client is used to invoke all of the functions in a schema, all of the procedures in a schema, or all of the functions and procedures in a package.</span></span>  
  
|<span data-ttu-id="d0ba2-129">Oracle の成果物</span><span class="sxs-lookup"><span data-stu-id="d0ba2-129">Oracle Artifact</span></span>|<span data-ttu-id="d0ba2-130">WCF クライアントの操作名</span><span class="sxs-lookup"><span data-stu-id="d0ba2-130">WCF Client Operation Name</span></span>|<span data-ttu-id="d0ba2-131">例</span><span class="sxs-lookup"><span data-stu-id="d0ba2-131">Example</span></span>|  
|---------------------|-------------------------------|-------------|  
|<span data-ttu-id="d0ba2-132">手順</span><span class="sxs-lookup"><span data-stu-id="d0ba2-132">Procedure</span></span>|<span data-ttu-id="d0ba2-133">[スキーマ]ProcedureClient です。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-133">[SCHEMA]ProcedureClient.[PROC_NAME]</span></span>|<span data-ttu-id="d0ba2-134">SCOTTProcedureClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-134">SCOTTProcedureClient.MYPROC</span></span>|  
|<span data-ttu-id="d0ba2-135">関数</span><span class="sxs-lookup"><span data-stu-id="d0ba2-135">Function</span></span>|<span data-ttu-id="d0ba2-136">[スキーマ]FunctionClient です。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-136">[SCHEMA]FunctionClient.[FUNC_NAME]</span></span>|<span data-ttu-id="d0ba2-137">SCOTTProcedureClient.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-137">SCOTTProcedureClient.MYFUNC</span></span>|  
|<span data-ttu-id="d0ba2-138">パッケージ (プロシージャまたは関数)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-138">Package (procedure or function)</span></span>|<span data-ttu-id="d0ba2-139">[スキーマ]パッケージ [PACKAGE_NAME] のクライアントです。[PROC_NAME または FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-139">[SCHEMA]Package[PACKAGE_NAME]Client.[PROC_NAME or FUNC_NAME]</span></span>|<span data-ttu-id="d0ba2-140">SCOTTPackageMYPACKAGEClient.MYPROC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-140">SCOTTPackageMYPACKAGEClient.MYPROC</span></span>|  
  
 <span data-ttu-id="d0ba2-141">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-141">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="d0ba2-142">[PROC_NAME];、Oracle のプロシージャの名前を =たとえば、MYPROC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-142">[PROC_NAME] = The name of an Oracle procedure; for example, MYPROC.</span></span>  
  
 <span data-ttu-id="d0ba2-143">[FUNC_NAME]、Oracle 関数の名前を =たとえば、MYFUNC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-143">[FUNC_NAME] = The name of an Oracle function; for example, MYFUNC.</span></span>  
  
 <span data-ttu-id="d0ba2-144">[PACKAGE_NAME] = Oracle パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-144">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="d0ba2-145">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]パラメーターを入力および Oracle のレコードの行のデータ (またはフィールド) を含む複雑な XML 型としての REF CURSOR パラメーターによって返される結果セットだけでなく、値を返す Oracle レコードを表します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-145">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents Oracle RECORD type parameters and return values as well as the result sets returned by REF CURSOR parameters as complex XML types that contain the row data (or fields) of an Oracle record.</span></span> <span data-ttu-id="d0ba2-146">.NET クラスとして表されるこれらの XML 型の各モデルでは、WCF サービス、クラスのプロパティは、レコード型または REF カーソルの結果セットのフィールドを表します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-146">In the WCF service model, each of these XML types is represented as a .NET class; the properties of the class represent the fields of the RECORD type or REF CURSOR result set.</span></span> <span data-ttu-id="d0ba2-147">Oracle のレコードの種類は、厳密に型指定された .NET クラスとして常に表されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-147">Oracle RECORD types are always represented as strongly-typed .NET classes.</span></span> <span data-ttu-id="d0ba2-148">ただし、REF CURSOR の結果セットは、自体 REF カーソルが宣言されていると厳密に型指定または厳密に型指定されたかどうかに基づいて厳密に型指定されたか、弱い型指定のレコードとして表現できます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-148">A REF CURSOR result set, however, can be represented as either strongly-typed or weakly-typed records based on whether the REF CURSOR itself is declared as strongly-typed or weakly-typed.</span></span> <span data-ttu-id="d0ba2-149">表す REF CURSOR またはレコード型のパラメーター (または戻り値) は、プロシージャ、関数、またはパッケージに基づく一意の名前空間で生成されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-149">The classes that represent REF CURSOR or RECORD type parameters (or return values) are generated in a unique namespace based on the procedure, function, or package.</span></span> <span data-ttu-id="d0ba2-150">次の表は、これらの名前空間を示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-150">The following table shows these namespaces.</span></span>  
  
|<span data-ttu-id="d0ba2-151">Oracle の成果物</span><span class="sxs-lookup"><span data-stu-id="d0ba2-151">Oracle Artifact</span></span>|<span data-ttu-id="d0ba2-152">名前空間</span><span class="sxs-lookup"><span data-stu-id="d0ba2-152">Namespace</span></span>|<span data-ttu-id="d0ba2-153">例</span><span class="sxs-lookup"><span data-stu-id="d0ba2-153">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="d0ba2-154">手順</span><span class="sxs-lookup"><span data-stu-id="d0ba2-154">Procedure</span></span>|<span data-ttu-id="d0ba2-155">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-155">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-156">[スキーマ] です。プロシージャです。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-156">[SCHEMA].Procedure.[PROC_NAME]</span></span>|<span data-ttu-id="d0ba2-157">microsoft.lobservices.oracledb._2007._03.SCOTT です。Procedure.MYPROC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-157">microsoft.lobservices.oracledb._2007._03.SCOTT.Procedure.MYPROC</span></span>|  
|<span data-ttu-id="d0ba2-158">関数</span><span class="sxs-lookup"><span data-stu-id="d0ba2-158">Function</span></span>|<span data-ttu-id="d0ba2-159">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-159">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-160">[スキーマ] です。関数。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-160">[SCHEMA].Function.[FUNC_NAME]</span></span>|<span data-ttu-id="d0ba2-161">microsoft.lobservices.oracledb._2007._03.SCOTT です。Function.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-161">microsoft.lobservices.oracledb._2007._03.SCOTT.Function.MYFUNC</span></span>|  
|<span data-ttu-id="d0ba2-162">パッケージ (プロシージャ)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-162">Package (Procedure)</span></span>|<span data-ttu-id="d0ba2-163">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-163">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-164">[スキーマ] です。パッケージです。[PACKAGE_NAME] です。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-164">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME]</span></span>|<span data-ttu-id="d0ba2-165">microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYPROC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-165">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC</span></span>|  
|<span data-ttu-id="d0ba2-166">パッケージ (Function)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-166">Package (Function)</span></span>|<span data-ttu-id="d0ba2-167">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-167">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-168">[スキーマ] です。パッケージです。[PACKAGE_NAME] です。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-168">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME]</span></span>|<span data-ttu-id="d0ba2-169">microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-169">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC</span></span>|  
|<span data-ttu-id="d0ba2-170">汎用レコードに設定 (弱い型指定)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-170">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="d0ba2-171">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-171">[BASE_NS]</span></span>|<span data-ttu-id="d0ba2-172">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="d0ba2-172">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="d0ba2-173">[BASE_NS] = ベース アダプターの名前空間です。microsoft.lobservices.oracledb._2007._03 です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-173">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="d0ba2-174">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-174">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="d0ba2-175">[PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-175">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="d0ba2-176">[FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-176">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="d0ba2-177">[PACKAGE_NAME] = Oracle パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-177">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="d0ba2-178">レコードのパラメーターをこれらの名前空間を使用する方法については、次を参照してください。[を実行する操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-178">For information about how these namespaces are used for RECORD parameters, see [Performing Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span> <span data-ttu-id="d0ba2-179">REF CURSOR パラメーターをこれらの名前空間を使用する方法については、次を参照してください。[を実行する操作を使用して REF CURSOR、WCF サービス モデルを使用して Oracle データベースで](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-179">For information about how these namespaces are used for REF CURSOR parameters, see [Performing Operations Using REF CURSORS in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="d0ba2-180">一般に、Oracle パラメーターと戻り値でマップされたとおり、WCF クライアント メソッド。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-180">In general, the Oracle parameters and return values are mapped as follows in the WCF client method:</span></span>  
  
-   <span data-ttu-id="d0ba2-181">Oracle IN パラメーターは、.NET (入力) パラメーターにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-181">Oracle IN parameters are mapped to .NET (input) parameters.</span></span>  
  
-   <span data-ttu-id="d0ba2-182">.NET に oracle OUT パラメーターを割り当てる**アウト**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-182">Oracle OUT parameters are mapped to .NET **out** parameters.</span></span>  
  
-   <span data-ttu-id="d0ba2-183">.NET に oracle IN OUT パラメーターを割り当てる**ref**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-183">Oracle IN OUT parameters are mapped to .NET **ref** parameters.</span></span>  
  
-   <span data-ttu-id="d0ba2-184">関数の戻り値は、メソッドの戻り値にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-184">Function RETURN values are mapped to the method return value.</span></span>  
  
 <span data-ttu-id="d0ba2-185">ただし、2 つの重要な例外があります。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-185">However, two important exceptions exist:</span></span>  
  
-   <span data-ttu-id="d0ba2-186">REF CURSOR を oracle IN パラメーターが入力文字列と、出力に分割されます (**アウト**) セットを記録します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-186">Oracle IN OUT REF CURSOR parameters are split into an input string and an output (**out**) record set.</span></span> <span data-ttu-id="d0ba2-187">これは、ため、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN REF CUSROR パラメーターを表すこれら、文字列、複合型 (レコード セット) としての REF CURSOR 出力パラメーターとして 1 つのパラメーターに組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-187">This is because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CUSROR parameters as strings and OUT REF CURSOR parameters as complex types (record sets), these cannot be combined into a single parameter.</span></span>  
  
-   <span data-ttu-id="d0ba2-188">最初の出力パラメーター、Oracle のプロシージャでは、WCF クライアント メソッドの戻り値にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-188">The first OUT parameter in an Oracle procedure is mapped to the return value of the WCF client method.</span></span> <span data-ttu-id="d0ba2-189">これは、標準の WCF 動作です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-189">This is standard WCF behavior.</span></span>  
  
 <span data-ttu-id="d0ba2-190">次の例では、単純な Oracle プロシージャ (SCOTT スキーマに読み込まれる) の一部とそれを呼び出すために生成される WCF クライアント メソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-190">The following example shows part of a simple Oracle procedure (loaded in the SCOTT schema) and the signature of the WCF client method that is generated to invoke it.</span></span> <span data-ttu-id="d0ba2-191">Oracle プロシージャには、3 個の IN パラメーター、3 つの OUT パラメーター、および 3 OUT パラメーターです。ただし、WCF クライアントのメソッドは、最初の出力パラメーターのパラメーターをマップできません。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-191">The Oracle procedure has three IN parameters, three IN OUT parameters, and three OUT parameters; however, the WCF client method does not map a parameter for the first OUT parameter.</span></span> <span data-ttu-id="d0ba2-192">代わりにメソッドの戻り値にマップされます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-192">Instead it is mapped to the method return value.</span></span>  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a><span data-ttu-id="d0ba2-193">オーバー ロードされたプロシージャ、関数、およびパッケージのサポート</span><span class="sxs-lookup"><span data-stu-id="d0ba2-193">Support for Overloaded Procedures, Functions and Packages</span></span>  
 <span data-ttu-id="d0ba2-194">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポートしていますが、ノード ID と名前空間をオーバー ロードされた各成果物を表示する一意の文字列を追加することによってプロシージャ、関数、およびパッケージをオーバー ロードされました。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-194">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports overloaded procedures, functions, and packages by appending a unique string to the node ID and the namespace that it surfaces for each overloaded artifact.</span></span> <span data-ttu-id="d0ba2-195">この文字列は、次のオーバー ロードの最初のオーバー ロード"overload2"の"overload1"がします。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-195">This string is "overload1" for the first overload, "overload2" for the next overload, and so on.</span></span>  
  
 <span data-ttu-id="d0ba2-196">WCF サービス モデルの各オーバー ロードされたプロシージャまたは関数は、一意の WCF クライアントで表されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-196">In the WCF service model each overloaded procedure or function is represented by a unique WCF client.</span></span> <span data-ttu-id="d0ba2-197">これとは異なるスキーマでプロシージャのすべてのスキーマ内の関数のすべてのオーバー ロードされた非ケースまたはのプロシージャと、パッケージ内の関数はすべて、同じ WCF クライアントによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-197">This is different from the non-overloaded case in which all of the functions in a SCHEMA, all of the procedures in a SCHEMA, or all of the procedures and functions in a PACKAGE are invoked by the same WCF client.</span></span> <span data-ttu-id="d0ba2-198">次の表は、名、およびメソッドのオーバー ロードされたプロシージャ、関数、およびパッケージの生成、WCF クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-198">The following table shows the WCF client name and method generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="d0ba2-199">Oracle の成果物</span><span class="sxs-lookup"><span data-stu-id="d0ba2-199">Oracle Artifact</span></span>|<span data-ttu-id="d0ba2-200">WCF クライアント名</span><span class="sxs-lookup"><span data-stu-id="d0ba2-200">WCF Client Name</span></span>|<span data-ttu-id="d0ba2-201">例</span><span class="sxs-lookup"><span data-stu-id="d0ba2-201">Example</span></span>|  
|---------------------|---------------------|-------------|  
|<span data-ttu-id="d0ba2-202">オーバー ロードされたパッケージ (プロシージャ)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-202">Overloaded Package (Procedure)</span></span>|<span data-ttu-id="d0ba2-203">[スキーマ]パッケージの [PACKAGE_NAME] [PROC_NAME] [OVERLOAD_ID] のクライアントです。[PROC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-203">[SCHEMA]Package[PACKAGE_NAME][PROC_NAME] ][OVERLOAD_ID]Client.[PROC_NAME]</span></span>|<span data-ttu-id="d0ba2-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-204">SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC</span></span>|  
|<span data-ttu-id="d0ba2-205">オーバー ロードされたパッケージ (Function)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-205">Overloaded Package (Function)</span></span>|<span data-ttu-id="d0ba2-206">[スキーマ]パッケージの [PACKAGE_NAME] [FUNC_NAME] [OVERLOAD_ID] のクライアントです。[FUNC_NAME]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-206">[SCHEMA]Package[PACKAGE_NAME][FUNC_NAME] ][OVERLOAD_ID]Client.[FUNC_NAME]</span></span>|<span data-ttu-id="d0ba2-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span><span class="sxs-lookup"><span data-stu-id="d0ba2-207">SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC</span></span>|  
  
 <span data-ttu-id="d0ba2-208">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-208">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="d0ba2-209">[PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-209">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="d0ba2-210">[FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-210">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="d0ba2-211">[PACKAGE_NAME] = Oracle パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-211">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="d0ba2-212">[OVERLOAD_ID]; オーバー ロードされた成果物を識別する一意の文字列を ="overload1"、"overload2"、およびなどです。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-212">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span>  
  
 <span data-ttu-id="d0ba2-213">次の表は、オーバー ロードされたプロシージャ、関数、およびパッケージの生成された名前空間を示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-213">The following table shows the namespace generated for overloaded procedures, functions, and packages.</span></span>  
  
|<span data-ttu-id="d0ba2-214">Oracle の成果物</span><span class="sxs-lookup"><span data-stu-id="d0ba2-214">Oracle Artifact</span></span>|<span data-ttu-id="d0ba2-215">名前空間</span><span class="sxs-lookup"><span data-stu-id="d0ba2-215">Namespace</span></span>|<span data-ttu-id="d0ba2-216">例</span><span class="sxs-lookup"><span data-stu-id="d0ba2-216">Example</span></span>|  
|---------------------|---------------|-------------|  
|<span data-ttu-id="d0ba2-217">パッケージ (プロシージャ)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-217">Package (Procedure)</span></span>|<span data-ttu-id="d0ba2-218">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-218">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-219">[スキーマ] です。パッケージです。[PACKAGE_NAME] です。[PROC_NAME][OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-219">[SCHEMA].Package.[PACKAGE_NAME].[PROC_NAME] [OVERLOAD_ID]</span></span>|<span data-ttu-id="d0ba2-220">microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYPROC.overload1</span><span class="sxs-lookup"><span data-stu-id="d0ba2-220">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYPROC.overload1</span></span>|  
|<span data-ttu-id="d0ba2-221">パッケージ (Function)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-221">Package (Function)</span></span>|<span data-ttu-id="d0ba2-222">[BASE_NS] です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-222">[BASE_NS].</span></span> <span data-ttu-id="d0ba2-223">[スキーマ] です。パッケージです。[PACKAGE_NAME] です。[FUNC_NAME] です。[OVERLOAD_ID]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-223">[SCHEMA].Package.[PACKAGE_NAME].[FUNC_NAME].[OVERLOAD_ID]</span></span>|<span data-ttu-id="d0ba2-224">microsoft.lobservices.oracledb._2007._03.SCOTT です。Package.MYPACKAGE.MYFUNC.overload1</span><span class="sxs-lookup"><span data-stu-id="d0ba2-224">microsoft.lobservices.oracledb._2007._03.SCOTT.Package.MYPACKAGE.MYFUNC.overload1</span></span>|  
|<span data-ttu-id="d0ba2-225">汎用レコードに設定 (弱い型指定)</span><span class="sxs-lookup"><span data-stu-id="d0ba2-225">Generic Record Set (weakly-typed)</span></span>|<span data-ttu-id="d0ba2-226">[BASE_NS]</span><span class="sxs-lookup"><span data-stu-id="d0ba2-226">[BASE_NS]</span></span>|<span data-ttu-id="d0ba2-227">microsoft.lobservices.oracledb._2007._03</span><span class="sxs-lookup"><span data-stu-id="d0ba2-227">microsoft.lobservices.oracledb._2007._03</span></span>|  
  
 <span data-ttu-id="d0ba2-228">[BASE_NS] = ベース アダプターの名前空間です。microsoft.lobservices.oracledb._2007._03 です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-228">[BASE_NS] = The base adapter namespace; microsoft.lobservices.oracledb._2007._03.</span></span>  
  
 <span data-ttu-id="d0ba2-229">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-229">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="d0ba2-230">[PROC_NAME];、Oracle のプロシージャの名前を =例を示します。MYPROC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-230">[PROC_NAME] = The name of an Oracle procedure; for example; MYPROC.</span></span>  
  
 <span data-ttu-id="d0ba2-231">[FUNC_NAME]、Oracle 関数の名前を =たとえば MYFUNC です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-231">[FUNC_NAME] = The name of an Oracle function; for example MYFUNC.</span></span>  
  
 <span data-ttu-id="d0ba2-232">[PACKAGE_NAME] = Oracle パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-232">[PACKAGE_NAME] = The name of an Oracle package.</span></span>  
  
 <span data-ttu-id="d0ba2-233">[OVERLOAD_ID]; オーバー ロードされた成果物を識別する一意の文字列を ="overload1"、"overload2"、およびなどです。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-233">[OVERLOAD_ID] = The unique string that identifies the overloaded artifact; "overload1", "overload2", and so on.</span></span> <span data-ttu-id="d0ba2-234">文字列内の数値は、Oracle データベースで保持されている成果物のオーバー ロードの ID です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-234">The numeric value in the string is the overload ID for the artifact maintained by the Oracle database.</span></span>  
  
 <span data-ttu-id="d0ba2-235">次の例では、WCF クライアントと ACCOUNT_PKG パッケージ内のオーバー ロードされた GET_ACCOUNT プロシージャについて生成されたメソッドのシグネチャを示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-235">The following example shows the WCF clients and the method signatures generated for the overloaded GET_ACCOUNT procedure in the ACCOUNT_PKG package.</span></span> <span data-ttu-id="d0ba2-236">(Oracle の宣言が含まれます) です。この例では、各オーバー ロードの一意の WCF クライアントを生成する方法と、クライアントごとに生成されたメソッドが一意の名前空間のレコード セットを返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-236">(The Oracle declarations are included.) This example shows how a unique WCF client is generated for each overload and how the method generated for each client returns a record set in a unique namespace.</span></span>  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a><span data-ttu-id="d0ba2-237">呼び出し元関数およびプロシージャ</span><span class="sxs-lookup"><span data-stu-id="d0ba2-237">Invoking Functions and Procedures</span></span>  
 <span data-ttu-id="d0ba2-238">WCF クライアントを使用して、関数またはプロシージャを呼び出すには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-238">To invoke a function or a procedure by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="d0ba2-239">対象とする関数、プロシージャ、またはパッケージの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-239">Generate a WCF client class for the target function, procedure, or package.</span></span> <span data-ttu-id="d0ba2-240">このクラスは、ターゲットの成果物に呼び出すことができる操作のメソッドを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-240">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0ba2-241">[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、オーバー ロードされた関数およびプロシージャに表示されます、**利用可能なカテゴリと操作**[name].1、.2、.3 の [名前] の [名前] ボックスに、[NAME] はオーバー ロードされた成果物と数値の値の名前を指定Oracle データベースでオーバー ロードの ID です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-241">In the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], overloaded functions and procedures appear in the **Available categories and operations** box as [NAME].1, [NAME].2, [NAME].3, and so on, where [NAME] is the name of the overloaded artifact and the numeric value is the overload ID on the Oracle database.</span></span>  
  
2.  <span data-ttu-id="d0ba2-242">WCF クライアント クラスのインスタンスを作成し、関数またはプロシージャを呼び出すには、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-242">Create an instance of the WCF client class and call its methods to invoke the function or procedure.</span></span>  
  
 <span data-ttu-id="d0ba2-243">詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-243">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="d0ba2-244">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-244">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0ba2-245">関数またはプロシージャ (およびパッケージ) の値を返しますまたは REF CURSOR およびレコードの型パラメーターを表すクラスは、関数またはプロシージャごとに一意の名前空間でも宣言されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-245">The classes that represent REF CURSOR and RECORD type parameters or return values in functions or procedures (and packages) are declared in a unique namespace for each function or procedure.</span></span> <span data-ttu-id="d0ba2-246">つまり、たとえば、WCF クライアントのメソッドごとに異なる 2 つの関数の戻り値として使用されているパッケージ REF カーソルの種類が一意の名前空間で宣言されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-246">This means, for example, that a PACKAGE REF CURSOR type that is used as a return value in two different functions will be declared in a unique namespace for each WCF client method.</span></span> <span data-ttu-id="d0ba2-247">これらの異なる値を返すか、WCF クライアントのいずれかを呼び出すときに変数を適切にキャストを保持するために別々 の変数を宣言する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-247">You must either declare separate variables to hold these different return values or appropriately cast the variable when you invoke one of the WCF client methods.</span></span>  
  
 <span data-ttu-id="d0ba2-248">次の例では、/SCOTT/ACCOUNT テーブルからアカウント レコードを取得するオーバー ロードされた/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT プロシージャを呼び出すことを示します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-248">The following example demonstrates calling the overloaded /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT procedure to get account records from the /SCOTT/ACCOUNT table.</span></span> <span data-ttu-id="d0ba2-249">まず、/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT プロシージャを呼び出すことによって、新しいレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-249">First a new record is created by calling the /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT procedure.</span></span> <span data-ttu-id="d0ba2-250">新しいレコードが読み込まれる GET_ACCOUNT のさまざまなオーバー ロードを呼び出すことによって、2 回バックアップします。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-250">Then the new record is read back twice by calling different overloads of GET_ACCOUNT.</span></span> <span data-ttu-id="d0ba2-251">この例では、3 つの WCF クライアント、CREATE_ACCOUNT プロシージャと 1 つ各 GET_ACCOUNT いずれのオーバー ロードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-251">This example uses three WCF clients, one for the CREATE_ACCOUNT procedure and one each for the GET_ACCOUNT overloads.</span></span> <span data-ttu-id="d0ba2-252">エイリアスは、GET_ACCOUNT の戻り値を使用する名前空間を区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-252">Aliases are used to distinguish between namespaces used for the return value of GET_ACCOUNT.</span></span> <span data-ttu-id="d0ba2-253">フル サンプルは、SDK サンプルで使用します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-253">A full sample is available in the SDK samples.</span></span> <span data-ttu-id="d0ba2-254">SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-254">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0ba2-255">参照</span><span class="sxs-lookup"><span data-stu-id="d0ba2-255">See Also</span></span>  
 [<span data-ttu-id="d0ba2-256">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="d0ba2-256">Develop Oracle Database Applications by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)