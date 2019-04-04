---
title: SAP でプロバイダーによって使用されるカスタム Rfc |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b359fc893b8616fd4fb7339e9efbc42d7d3e13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992723"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a><span data-ttu-id="0968a-102">SAP でプロバイダーによって使用されるカスタム Rfc</span><span class="sxs-lookup"><span data-stu-id="0968a-102">Custom RFCs Used by the Provider in SAP</span></span>
<span data-ttu-id="0968a-103">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムの操作を実行するために内部的に使用する次のカスタム Rfc を提供します。</span><span class="sxs-lookup"><span data-stu-id="0968a-103">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] provides the following custom RFCs that it internally uses to perform operations on the SAP system.</span></span>  
  
- <span data-ttu-id="0968a-104">**Z_EXTRACT_DATA_OO RFC**します。</span><span class="sxs-lookup"><span data-stu-id="0968a-104">**Z_EXTRACT_DATA_OO RFC**.</span></span> <span data-ttu-id="0968a-105">データの抽出、RFC Z_EXTRACT_DATA_OO は、テーブルからデータを抽出、SAP R/3 システム ビューまたはデータ、および返すか、SQL Server テーブルの同期的にデータを変換します、またはフラット ファイルへのデータをダンプをします。</span><span class="sxs-lookup"><span data-stu-id="0968a-105">The data extraction RFC, Z_EXTRACT_DATA_OO, extracts data from tables or views in the SAP R/3 system, converts the data, and either returns the data synchronously in a SQL Server table or dumps data to a flat file.</span></span> <span data-ttu-id="0968a-106">WHERE 句で SELECT 操作を実行する、Z_EXTRACT_DATA_OO が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0968a-106">The Z_EXTRACT_DATA_OO is used to perform SELECT operation with WHERE clauses.</span></span> <span data-ttu-id="0968a-107">この RFC のパフォーマンスは、SAP システムのハードウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="0968a-107">The performance of this RFC is dependent on your SAP system hardware.</span></span>  
  
   <span data-ttu-id="0968a-108">Z_EXTRACT_DATA_OO RFC の .NET と SAP のデータ型をマップする方法については、[Data Type Mapping for カスタム Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0968a-108">For information on how the .NET and SAP data types are mapped for Z_EXTRACT_DATA_OO RFC, see [Data Type Mapping for Custom RFCs](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md).</span></span>  
  
- <span data-ttu-id="0968a-109">**Z_EXECUTE_SAP_QUERY RFC**します。</span><span class="sxs-lookup"><span data-stu-id="0968a-109">**Z_EXECUTE_SAP_QUERY RFC**.</span></span> <span data-ttu-id="0968a-110">この RFC を使って、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] SAP システムで既に定義されているクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0968a-110">This RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute queries that are already defined in the SAP system.</span></span> <span data-ttu-id="0968a-111">この RFC では、内部的には、SAP の RFC RSAQ_REMOTE_QUERY_CALL を実行します。</span><span class="sxs-lookup"><span data-stu-id="0968a-111">This RFC internally executes the SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="0968a-112">SAP クエリは、テーブル、列、入力パラメーター、結果セットの並べ替え順序を選択して、SAP GUI を使用してグラフィカルに作成されるクエリです。使用して、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ADO.NET クライアントからこのような SAP クエリを実行するようになりました。</span><span class="sxs-lookup"><span data-stu-id="0968a-112">SAP queries are queries that are graphically created using the SAP GUI by selecting the tables, columns, input parameters, sort order of the result set, etc. Using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] you can now execute such SAP queries from an ADO.NET client.</span></span>  
  
   <span data-ttu-id="0968a-113">EXECQUERY 操作によって返されるすべての値では、文字列型です。</span><span class="sxs-lookup"><span data-stu-id="0968a-113">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a><span data-ttu-id="0968a-114">Z_EXTRACT_DATA_OO RFC に関する制限事項</span><span class="sxs-lookup"><span data-stu-id="0968a-114">Limitations Related to the Z_EXTRACT_DATA_OO RFC</span></span>  
  
-   <span data-ttu-id="0968a-115">Z_EXTRACT_DATA_OO RFC では、次の条件を満たすテーブルからデータの読み取りがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0968a-115">The Z_EXTRACT_DATA_OO RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="0968a-116">テーブルの TabClass は TRANSP、クラスター、またはプールです。</span><span class="sxs-lookup"><span data-stu-id="0968a-116">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="0968a-117">TabClass はビューと ViewClass が D または P.</span><span class="sxs-lookup"><span data-stu-id="0968a-117">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
-   <span data-ttu-id="0968a-118">Z_EXTRACT_DATA_OO HR クラスター テーブル、たとえば PCL1 PCL2、PCL3、PCL4 PCL5 をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="0968a-118">Z_EXTRACT_DATA_OO does not support HR cluster tables, for example PCL1, PCL2, PCL3, PCL4, PCL5.</span></span>  
  
-   <span data-ttu-id="0968a-119">Z_EXTRACT_DATA_OO で抽出できる行の数は、SAP サーバーにハードウェア リソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="0968a-119">The number of rows that can be extracted by Z_EXTRACT_DATA_OO depends on the hardware resources on the SAP server.</span></span>  
  
-   <span data-ttu-id="0968a-120">抽出されたすべてのデータは、主キーの順序で返されます。</span><span class="sxs-lookup"><span data-stu-id="0968a-120">All extracted data is returned in order of the primary keys.</span></span>  
  
-   <span data-ttu-id="0968a-121">テーブルまたはビューの文字列、SSTRING および RAWSTRING の可変長データ型を含むはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0968a-121">Tables or views containing the variable-length data types STRING, SSTRING and RAWSTRING are not supported.</span></span> <span data-ttu-id="0968a-122">テーブルまたはビューのこれらのデータ型を含むを抽出することはできません。</span><span class="sxs-lookup"><span data-stu-id="0968a-122">Tables or views containing these data types cannot be extracted.</span></span>  
  
-   <span data-ttu-id="0968a-123">Z_EXTRACT_DATA_OO 変換終了が割り当てられているすべてのフィールドで変換が終了を実行します。</span><span class="sxs-lookup"><span data-stu-id="0968a-123">Z_EXTRACT_DATA_OO runs conversion exits on all fields that have conversion exits assigned to them.</span></span> <span data-ttu-id="0968a-124">SELECT ステートメントの WHERE 句では、結果の変換後の値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="0968a-124">The resulting converted values must be entered in the WHERE clause of a SELECT statement.</span></span> <span data-ttu-id="0968a-125">変換後の値も返されます。</span><span class="sxs-lookup"><span data-stu-id="0968a-125">Converted values are also returned.</span></span> <span data-ttu-id="0968a-126">Z_EXTRACT_DATA_OO によって返される結果と SAP データ ブラウザー (SE16) で返される結果の間の不整合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0968a-126">This might cause inconsistencies between the results returned by Z_EXTRACT_DATA_OO and the results returned in the SAP data browser (SE16).</span></span>  
  
-   <span data-ttu-id="0968a-127">選択したテーブルには、ABAP (たとえば、接続) で予約された名前のフィールド名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="0968a-127">Selected tables cannot contain field names that are reserved names in ABAP (for example, CONNECTION).</span></span>  
  
-   <span data-ttu-id="0968a-128">SAP R/3 バージョン 4.6 C 型の整数フィールドの値で、クエリ プロセッサでの制限により INT4 は WHERE 句での-999999999 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0968a-128">Due to a limitation in the query processor in SAP R/3 version 4.6C, values for integer fields of type INT4 must be greater than or equal to -999999999 in the WHERE clause.</span></span> <span data-ttu-id="0968a-129">-999999999 よりも小さい INT4 値を持つ行は、値を含むフィールドが選択されているかどうかに関係なくは抽出されません。</span><span class="sxs-lookup"><span data-stu-id="0968a-129">Rows with INT4 values less than -999999999 will not be extracted regardless of whether the field containing the value is selected.</span></span>  
  
-   <span data-ttu-id="0968a-130">すべてのデータ値の型で SAP システムのバージョン 4.7 以上; で実行すると、WHERE 句は 256 文字に制限されています制限は、バージョン 4.6 c での 70 文字です。</span><span class="sxs-lookup"><span data-stu-id="0968a-130">Values for all data types in a WHERE clause are limited to 256 characters when executing on SAP system version 4.7 or greater; the limit is 70 characters in version 4.6c.</span></span> <span data-ttu-id="0968a-131">生のデータ型の値をこれらの制限は 128 ~ 35 文字をそれぞれ半分は。</span><span class="sxs-lookup"><span data-stu-id="0968a-131">For RAW data type values, these limits are halved to 128 and 35 characters, respectively.</span></span> <span data-ttu-id="0968a-132">制限はありません RAW と LCHR のデータ型の長さで、結果として返されるときにします。</span><span class="sxs-lookup"><span data-stu-id="0968a-132">There is no limit on RAW and LCHR data type length when they are returned as a result.</span></span>  
  
-   <span data-ttu-id="0968a-133">SAP R/3 バージョン 4.6 C では、フィールド、where 句は 70 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="0968a-133">In SAP R/3 version 4.6C, fields in the WHERE clause are limited to 70 characters.</span></span>  
  
-   <span data-ttu-id="0968a-134">SAP R/3 バージョン 4.6 C では、すべてのテーブルを持つ出力の長さが 70 文字を超える主キー フィールドを抽出できません。</span><span class="sxs-lookup"><span data-stu-id="0968a-134">In SAP R/3 version 4.6C, any table with a primary key field that has an output length greater than 70 characters cannot be extracted.</span></span>  
  
-   <span data-ttu-id="0968a-135">SAP r/3 システム、バージョン 4.6 c、テーブルと可変長データ型を含むビューで (`VARC`) テーブルし、Z_EXTRACT_DATA_OO 関数の呼び出しを使用してデータ ソースからこれらのデータ型を抽出することはできませんを含むビューはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0968a-135">In SAP R/3, version 4.6c, tables and views that contain variable length data types (`VARC`) are not supported, and tables and views containing these data types cannot be extracted from the data source using the Z_EXTRACT_DATA_OO function call.</span></span>  
  
-   <span data-ttu-id="0968a-136">ファイルのモードで Z_EXTRACT_DATA_OO 関数の呼び出しを確認しないかどうかを変換先ファイルが既に開かれて、自体または別のアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="0968a-136">In file mode, the Z_EXTRACT_DATA_OO function call does not check whether a destination file is already opened, either by itself or by another application.</span></span> <span data-ttu-id="0968a-137">そのため、関数できますを正しく記述しない開くファイルを同時に同じファイルにデータの追加中。</span><span class="sxs-lookup"><span data-stu-id="0968a-137">Therefore, the function can incorrectly write to an open file while simultaneously appending data to the same file.</span></span> <span data-ttu-id="0968a-138">エラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="0968a-138">No error is raised.</span></span>  
  
-   <span data-ttu-id="0968a-139">ファイルのモードで Z_EXTRACT_DATA_OO 関数の呼び出しは、既存のファイルを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="0968a-139">In file mode, the Z_EXTRACT_DATA_OO function call can overwrite existing files.</span></span> <span data-ttu-id="0968a-140">S_DATASET を使用してファイル システム アクセス Z_EXTRACT_DATA_OO を使用する SAP ユーザーが制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0968a-140">Ensure that SAP users who use Z_EXTRACT_DATA_OO have restricted file-system access by way of S_DATASET.</span></span>  
  
## <a name="security-considerations-with-the-custom-rfc"></a><span data-ttu-id="0968a-141">カスタム RFC のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0968a-141">Security Considerations with the Custom RFC</span></span>  
  
-   <span data-ttu-id="0968a-142">`Security Issue`: はそれらのファイルを保護するためサポートしていない場合は、フラット ファイルに書き込まれたデータを公開する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0968a-142">`Security Issue`: There is potential to expose data that is written to flat files if you do not help protect those files.</span></span>  
  
     <span data-ttu-id="0968a-143">`Best practice`: フラット ファイル モードで Z_EXTRACT_DATA_OO 関数の呼び出しによってデータが書き込まれるファイル共有のセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="0968a-143">`Best practice`: Improve the security of the file share to which any data is written by the Z_EXTRACT_DATA_OO function call in flat file mode.</span></span>  
  
-   <span data-ttu-id="0968a-144">`Security Issue`: ファイル モードで Z_EXTRACT_DATA_OO 関数の呼び出しを使用してに書き込まれる任意の共有上のファイルを上書きする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0968a-144">`Security Issue`: There is the potential to overwrite files on any share that is written to using the Z_EXTRACT_DATA_OO function call in file mode.</span></span> <span data-ttu-id="0968a-145">これは、SAP のドメイン アカウントがアクセスを持っている任意の共有上の任意のファイルに発生します。</span><span class="sxs-lookup"><span data-stu-id="0968a-145">This can occur to any file on any share to which the SAP domain account has access.</span></span>  
  
     <span data-ttu-id="0968a-146">`Best practice`: SAP のドメイン アカウントがアクセスを持っているすべての共有の保護に努めてください。</span><span class="sxs-lookup"><span data-stu-id="0968a-146">`Best practice`: Strive to protect all shares to which the SAP domain account has access.</span></span>  
  
-   <span data-ttu-id="0968a-147">`Security Issue`: ユーザーには、ターゲットが別の物理マシン上の場合、SAP アプリケーション サーバーからそのターゲット ファイル共有に転送中にデータを検査する (または「スニッフィング」) に機能があります。</span><span class="sxs-lookup"><span data-stu-id="0968a-147">`Security Issue`: Users have the ability to inspect (or "sniff") data during transmission from an SAP application server to its target file share, in cases when the target is on a different physical machine.</span></span>  
  
     <span data-ttu-id="0968a-148">`Best practice`: 通信を SAP サーバーとターゲット間でセキュリティを強化するため、IPsec または別の適切なメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0968a-148">`Best practice`: Use IPsec or another appropriate method to help make communication more secure between the SAP server and its targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0968a-149">参照</span><span class="sxs-lookup"><span data-stu-id="0968a-149">See Also</span></span>  
 [<span data-ttu-id="0968a-150">.NET Framework Data Provider for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="0968a-150">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)