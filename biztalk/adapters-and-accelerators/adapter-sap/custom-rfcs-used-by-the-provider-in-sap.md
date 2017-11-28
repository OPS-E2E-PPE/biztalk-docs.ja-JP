---
title: "SAP のプロバイダーによって使用されるカスタム Rfc |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55473dbcfeebecc504906d569c129989b054211
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a><span data-ttu-id="75576-102">SAP のプロバイダーによって使用されるカスタム Rfc</span><span class="sxs-lookup"><span data-stu-id="75576-102">Custom RFCs Used by the Provider in SAP</span></span>
<span data-ttu-id="75576-103">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムでの操作を実行する内部で使用されているカスタム Rfc を提供します。</span><span class="sxs-lookup"><span data-stu-id="75576-103">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] provides the following custom RFCs that it internally uses to perform operations on the SAP system.</span></span>  
  
-   <span data-ttu-id="75576-104">**Z_EXTRACT_DATA_OO RFC**です。</span><span class="sxs-lookup"><span data-stu-id="75576-104">**Z_EXTRACT_DATA_OO RFC**.</span></span> <span data-ttu-id="75576-105">データの抽出、RFC Z_EXTRACT_DATA_OO、テーブルからデータを抽出 SAP R/3 システム ビュー、データ、およびを返すか、SQL Server テーブルで同期的にデータを変換します。 またはフラット ファイルへのデータをダンプします。</span><span class="sxs-lookup"><span data-stu-id="75576-105">The data extraction RFC, Z_EXTRACT_DATA_OO, extracts data from tables or views in the SAP R/3 system, converts the data, and either returns the data synchronously in a SQL Server table or dumps data to a flat file.</span></span> <span data-ttu-id="75576-106">Z_EXTRACT_DATA_OO を使用して、WHERE 句で SELECT 操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="75576-106">The Z_EXTRACT_DATA_OO is used to perform SELECT operation with WHERE clauses.</span></span> <span data-ttu-id="75576-107">この RFC のパフォーマンスは SAP システムのハードウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="75576-107">The performance of this RFC is dependent on your SAP system hardware.</span></span>  
  
     <span data-ttu-id="75576-108">Z_EXTRACT_DATA_OO RFC 用 .NET と SAP のデータ型をマップする方法については、次を参照してください。[カスタム Rfc のデータ型マッピング](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)です。</span><span class="sxs-lookup"><span data-stu-id="75576-108">For information on how the .NET and SAP data types are mapped for Z_EXTRACT_DATA_OO RFC, see [Data Type Mapping for Custom RFCs](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md).</span></span>  
  
-   <span data-ttu-id="75576-109">**Z_EXECUTE_SAP_QUERY RFC**です。</span><span class="sxs-lookup"><span data-stu-id="75576-109">**Z_EXECUTE_SAP_QUERY RFC**.</span></span> <span data-ttu-id="75576-110">この RFC を使って、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムで既に定義されているクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="75576-110">This RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute queries that are already defined in the SAP system.</span></span> <span data-ttu-id="75576-111">この RFC では、SAP RFC、RSAQ_REMOTE_QUERY_CALL 内部的に実行します。</span><span class="sxs-lookup"><span data-stu-id="75576-111">This RFC internally executes the SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="75576-112">SAP クエリは、テーブル、列、入力パラメーター、結果セットの並べ替え順序を選択して、SAP GUI を使用してグラフィカルに作成されるクエリです。使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET クライアントからこのような SAP クエリを実行するようになりました。</span><span class="sxs-lookup"><span data-stu-id="75576-112">SAP queries are queries that are graphically created using the SAP GUI by selecting the tables, columns, input parameters, sort order of the result set, etc. Using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] you can now execute such SAP queries from an ADO.NET client.</span></span>  
  
     <span data-ttu-id="75576-113">EXECQUERY 操作によって返されるすべての値では、文字列型です。</span><span class="sxs-lookup"><span data-stu-id="75576-113">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a><span data-ttu-id="75576-114">Z_EXTRACT_DATA_OO RFC に関連する制限事項</span><span class="sxs-lookup"><span data-stu-id="75576-114">Limitations Related to the Z_EXTRACT_DATA_OO RFC</span></span>  
  
-   <span data-ttu-id="75576-115">次の条件を満たすテーブルからデータを読み取る Z_EXTRACT_DATA_OO RFC をサポートします。</span><span class="sxs-lookup"><span data-stu-id="75576-115">The Z_EXTRACT_DATA_OO RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="75576-116">テーブルの TabClass は TRANSP、クラスター、またはプールです。</span><span class="sxs-lookup"><span data-stu-id="75576-116">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="75576-117">TabClass ビューは、ViewClass D または P. のいずれか</span><span class="sxs-lookup"><span data-stu-id="75576-117">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
-   <span data-ttu-id="75576-118">Z_EXTRACT_DATA_OO は HR クラスター テーブル、たとえば PCL1 PCL2、PCL3、PCL4 PCL5 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="75576-118">Z_EXTRACT_DATA_OO does not support HR cluster tables, for example PCL1, PCL2, PCL3, PCL4, PCL5.</span></span>  
  
-   <span data-ttu-id="75576-119">Z_EXTRACT_DATA_OO で抽出できる行の数は、SAP サーバー上のハードウェア リソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="75576-119">The number of rows that can be extracted by Z_EXTRACT_DATA_OO depends on the hardware resources on the SAP server.</span></span>  
  
-   <span data-ttu-id="75576-120">主キーの順序では、すべての抽出データが返されます。</span><span class="sxs-lookup"><span data-stu-id="75576-120">All extracted data is returned in order of the primary keys.</span></span>  
  
-   <span data-ttu-id="75576-121">テーブルまたはビューを含む文字列、SSTRING および RAWSTRING の可変長データ型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75576-121">Tables or views containing the variable-length data types STRING, SSTRING and RAWSTRING are not supported.</span></span> <span data-ttu-id="75576-122">テーブルまたはビューのこれらのデータ型を含むを抽出することはできません。</span><span class="sxs-lookup"><span data-stu-id="75576-122">Tables or views containing these data types cannot be extracted.</span></span>  
  
-   <span data-ttu-id="75576-123">Z_EXTRACT_DATA_OO は変換終了します。 割り当てられているすべてのフィールドに変換が終了を実行します。</span><span class="sxs-lookup"><span data-stu-id="75576-123">Z_EXTRACT_DATA_OO runs conversion exits on all fields that have conversion exits assigned to them.</span></span> <span data-ttu-id="75576-124">SELECT ステートメントの WHERE 句では、結果の変換後の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="75576-124">The resulting converted values must be entered in the WHERE clause of a SELECT statement.</span></span> <span data-ttu-id="75576-125">変換された値も返されます。</span><span class="sxs-lookup"><span data-stu-id="75576-125">Converted values are also returned.</span></span> <span data-ttu-id="75576-126">Z_EXTRACT_DATA_OO によって返される結果と SAP データ ブラウザー (SE16) で返される結果との矛盾する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75576-126">This might cause inconsistencies between the results returned by Z_EXTRACT_DATA_OO and the results returned in the SAP data browser (SE16).</span></span>  
  
-   <span data-ttu-id="75576-127">選択したテーブルには、ABAP (たとえば、接続) で予約済みの名前は、フィールド名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="75576-127">Selected tables cannot contain field names that are reserved names in ABAP (for example, CONNECTION).</span></span>  
  
-   <span data-ttu-id="75576-128">SAP R/3 バージョン 4.6 C 型の整数フィールドの値では、クエリ プロセッサに制限のため INT4 は、WHERE 句での-999999999 以上でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="75576-128">Due to a limitation in the query processor in SAP R/3 version 4.6C, values for integer fields of type INT4 must be greater than or equal to -999999999 in the WHERE clause.</span></span> <span data-ttu-id="75576-129">-999999999 よりも小さい INT4 値を持つ行は、値を含むフィールドが選択されているかどうかに関係なくは抽出されません。</span><span class="sxs-lookup"><span data-stu-id="75576-129">Rows with INT4 values less than -999999999 will not be extracted regardless of whether the field containing the value is selected.</span></span>  
  
-   <span data-ttu-id="75576-130">SAP システムのバージョン 4.7 以上; で実行されている場合は、WHERE 句が 256 文字に制限されます内のすべてのデータの値の型します。制限は、バージョン 4.6 c で 70 文字です。</span><span class="sxs-lookup"><span data-stu-id="75576-130">Values for all data types in a WHERE clause are limited to 256 characters when executing on SAP system version 4.7 or greater; the limit is 70 characters in version 4.6c.</span></span> <span data-ttu-id="75576-131">生のデータ型の値のこれらの制限が半分に 128 ~ 35 文字をそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="75576-131">For RAW data type values, these limits are halved to 128 and 35 characters, respectively.</span></span> <span data-ttu-id="75576-132">なしに制限は RAW モードおよび LCHR のデータ型の長さ、結果として返されるときにします。</span><span class="sxs-lookup"><span data-stu-id="75576-132">There is no limit on RAW and LCHR data type length when they are returned as a result.</span></span>  
  
-   <span data-ttu-id="75576-133">SAP R/3 バージョン 4.6 C WHERE 句でのフィールドでは、句は、70 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="75576-133">In SAP R/3 version 4.6C, fields in the WHERE clause are limited to 70 characters.</span></span>  
  
-   <span data-ttu-id="75576-134">SAP R/3 バージョン 4.6 C では、すべてのテーブルを持つ出力の長さが 70 文字を超える主キー フィールドを抽出できません。</span><span class="sxs-lookup"><span data-stu-id="75576-134">In SAP R/3 version 4.6C, any table with a primary key field that has an output length greater than 70 characters cannot be extracted.</span></span>  
  
-   <span data-ttu-id="75576-135">SAP R/3 バージョン 4.6 c、テーブルと可変長データ型を含むビュー (`VARC`) はサポートされていませんし、テーブルし、ビューを含む Z_EXTRACT_DATA_OO 関数呼び出しを使用してデータ ソースからこれらのデータ型を抽出することはできません。</span><span class="sxs-lookup"><span data-stu-id="75576-135">In SAP R/3, version 4.6c, tables and views that contain variable length data types (`VARC`) are not supported, and tables and views containing these data types cannot be extracted from the data source using the Z_EXTRACT_DATA_OO function call.</span></span>  
  
-   <span data-ttu-id="75576-136">ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しをチェックしないかどうか、コピー先ファイルは既に開かれて、単独または他のアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="75576-136">In file mode, the Z_EXTRACT_DATA_OO function call does not check whether a destination file is already opened, either by itself or by another application.</span></span> <span data-ttu-id="75576-137">そのため、関数は、正しく記述できましていない開いているファイルへ同時に同じファイルにデータの追加中。</span><span class="sxs-lookup"><span data-stu-id="75576-137">Therefore, the function can incorrectly write to an open file while simultaneously appending data to the same file.</span></span> <span data-ttu-id="75576-138">エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="75576-138">No error is raised.</span></span>  
  
-   <span data-ttu-id="75576-139">ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しは、既存のファイルを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="75576-139">In file mode, the Z_EXTRACT_DATA_OO function call can overwrite existing files.</span></span> <span data-ttu-id="75576-140">Z_EXTRACT_DATA_OO を使用する SAP ユーザーが S_DATASET を使用してファイル システムへのアクセスを制限することを確認します。</span><span class="sxs-lookup"><span data-stu-id="75576-140">Ensure that SAP users who use Z_EXTRACT_DATA_OO have restricted file-system access by way of S_DATASET.</span></span>  
  
## <a name="security-considerations-with-the-custom-rfc"></a><span data-ttu-id="75576-141">カスタムの RFC にセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="75576-141">Security Considerations with the Custom RFC</span></span>  
  
-   <span data-ttu-id="75576-142">`Security Issue`: はそれらのファイルを保護する役立たない場合、フラット ファイルに書き込まれたデータを公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="75576-142">`Security Issue`: There is potential to expose data that is written to flat files if you do not help protect those files.</span></span>  
  
     <span data-ttu-id="75576-143">`Best practice`: フラット ファイル モードで Z_EXTRACT_DATA_OO 関数呼び出しによってデータが書き込まれるファイル共有のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="75576-143">`Best practice`: Improve the security of the file share to which any data is written by the Z_EXTRACT_DATA_OO function call in flat file mode.</span></span>  
  
-   <span data-ttu-id="75576-144">`Security Issue`: 可能性がある Z_EXTRACT_DATA_OO 関数呼び出しを使用してファイル モードで書き込むことができる任意の共有にファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="75576-144">`Security Issue`: There is the potential to overwrite files on any share that is written to using the Z_EXTRACT_DATA_OO function call in file mode.</span></span> <span data-ttu-id="75576-145">これは、SAP のドメイン アカウントがアクセスしている任意の共有上の任意のファイルに発生することができます。</span><span class="sxs-lookup"><span data-stu-id="75576-145">This can occur to any file on any share to which the SAP domain account has access.</span></span>  
  
     <span data-ttu-id="75576-146">`Best practice`: SAP ドメイン アカウントがアクセスしているすべての共有の保護に努めています。</span><span class="sxs-lookup"><span data-stu-id="75576-146">`Best practice`: Strive to protect all shares to which the SAP domain account has access.</span></span>  
  
-   <span data-ttu-id="75576-147">`Security Issue`: ユーザーでは、状況で、ターゲットが異なる物理コンピューターには、SAP アプリケーション サーバーから、対象のファイル共有への転送中にデータを検査 (または「傍受」) に機能があります。</span><span class="sxs-lookup"><span data-stu-id="75576-147">`Security Issue`: Users have the ability to inspect (or "sniff") data during transmission from an SAP application server to its target file share, in cases when the target is on a different physical machine.</span></span>  
  
     <span data-ttu-id="75576-148">`Best practice`: SAP サーバーとターゲットの間でより安全な通信を行うため、IPsec または別の適切なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="75576-148">`Best practice`: Use IPsec or another appropriate method to help make communication more secure between the SAP server and its targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75576-149">参照</span><span class="sxs-lookup"><span data-stu-id="75576-149">See Also</span></span>  
 [<span data-ttu-id="75576-150">.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="75576-150">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)