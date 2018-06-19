---
title: ストアド プロシージャ、関数、および PL-SQL Api のメッセージ スキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d707f10-470d-4390-bb5b-0301c326f375
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029c48c1e6066d09d43da51b2bb1f6786a516f54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963152"
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="52bce-102">ストアド プロシージャ、関数、および PL/SQL Api のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="52bce-102">Message Schemas for Stored Procedures, Functions, and PL/SQL APIs</span></span>
<span data-ttu-id="52bce-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]サーフェス基になる Oracle データベースの操作としてストアド プロシージャ、関数、および PL/SQL Api (ストアド プロシージャ、およびパッケージ内の関数)。</span><span class="sxs-lookup"><span data-stu-id="52bce-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces the underlying Oracle database stored procedures, functions, and PL/SQL APIs (stored procedures and functions within a package) as operations.</span></span> <span data-ttu-id="52bce-104">このセクションでは、メッセージの構造とストアド プロシージャ、関数、および PL/SQL Api の呼び出しに使用する操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="52bce-104">This section describes the message structure and actions used to invoke stored procedures, functions, and PL/SQL APIs.</span></span>  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="52bce-105">ストアド プロシージャ、関数、および PL/SQL Api のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="52bce-105">Message Structure of Stored Procedures, Functions, and PL/SQL APIs</span></span>  
 <span data-ttu-id="52bce-106">関数の操作が表示され、ストアド プロシージャが、要求-応答メッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="52bce-106">The operations surfaced for functions and stored procedures follow a request-response message exchange pattern.</span></span> <span data-ttu-id="52bce-107">次の表は、これらの要求と応答メッセージの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="52bce-107">The following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52bce-108">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bce-108">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="52bce-109">操作</span><span class="sxs-lookup"><span data-stu-id="52bce-109">Operation</span></span>|<span data-ttu-id="52bce-110">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="52bce-110">XML Message</span></span>|<span data-ttu-id="52bce-111">Description</span><span class="sxs-lookup"><span data-stu-id="52bce-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="52bce-112">ストアド プロシージャ要求</span><span class="sxs-lookup"><span data-stu-id="52bce-112">Stored Procedure Request</span></span>|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="52bce-113">メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="52bce-113">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="52bce-114">ストアド プロシージャの応答</span><span class="sxs-lookup"><span data-stu-id="52bce-114">Stored Procedure Response</span></span>|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="52bce-115">メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="52bce-115">Supports Oracle OUT and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="52bce-116">関数の要求</span><span class="sxs-lookup"><span data-stu-id="52bce-116">Function Request</span></span>|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|<span data-ttu-id="52bce-117">メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="52bce-117">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="52bce-118">関数の応答</span><span class="sxs-lookup"><span data-stu-id="52bce-118">Function Response</span></span>|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|<span data-ttu-id="52bce-119">メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="52bce-119">Supports Oracle OUT and IN OUT parameters in the message body</span></span><br /><br /> <span data-ttu-id="52bce-120">関数の戻り値が返されます、 \<[FN_NAME] 結果\>要素。</span><span class="sxs-lookup"><span data-stu-id="52bce-120">The function return value is returned in the \<[FN_NAME]Result\> element.</span></span> <span data-ttu-id="52bce-121">これは、応答メッセージの最初の要素です。</span><span class="sxs-lookup"><span data-stu-id="52bce-121">This is the first element in the response message.</span></span> <span data-ttu-id="52bce-122">すべてのパラメーターの前になります。</span><span class="sxs-lookup"><span data-stu-id="52bce-122">It comes before any parameters.</span></span>|  
|<span data-ttu-id="52bce-123">PL/SQL API 要求</span><span class="sxs-lookup"><span data-stu-id="52bce-123">PL/SQL API Request</span></span>|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="52bce-124">関数またはストアド プロシージャと同じ</span><span class="sxs-lookup"><span data-stu-id="52bce-124">Same as Function or Stored Procedure</span></span>|  
|<span data-ttu-id="52bce-125">パッケージ化されたプロシージャまたは関数の応答</span><span class="sxs-lookup"><span data-stu-id="52bce-125">Packaged Procedure or Function Response</span></span>|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="52bce-126">関数またはストアド プロシージャと同じ</span><span class="sxs-lookup"><span data-stu-id="52bce-126">Same as Function or Stored Procedure</span></span>|  
  
 <span data-ttu-id="52bce-127">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="52bce-127">Entity descriptions:</span></span>  
  
 <span data-ttu-id="52bce-128">[バージョン] http://schemas.microsoft.com/OracleEBS/2008/05 を = です。</span><span class="sxs-lookup"><span data-stu-id="52bce-128">[VERSION] = http://schemas.microsoft.com/OracleEBS/2008/05.</span></span>  
  
 <span data-ttu-id="52bce-129">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="52bce-129">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="52bce-130">[SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。</span><span class="sxs-lookup"><span data-stu-id="52bce-130">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  
  
 <span data-ttu-id="52bce-131">[FN_NAME] 実行する関数を =たとえば、FN_GETID です。</span><span class="sxs-lookup"><span data-stu-id="52bce-131">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  
  
 <span data-ttu-id="52bce-132">[PRM1_NAME] = Oracle パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="52bce-132">[PRM1_NAME] = The name of the Oracle parameter.</span></span> <span data-ttu-id="52bce-133">メッセージごとにサポートされているパラメーターの方向について [説明] 列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bce-133">See the Description column for supported parameter directions for each message.</span></span>  
  
 <span data-ttu-id="52bce-134">[PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52bce-134">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  
  
 <span data-ttu-id="52bce-135">Oracle データベースでは、ストアド プロシージャと関数のオーバー ロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="52bce-135">The Oracle database supports overloading for stored procedures and functions.</span></span> <span data-ttu-id="52bce-136">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]オーバー ロードされた各成果物のターゲット名前空間にオーバー ロード文字列を付加してこの機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="52bce-136">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports this capability by appending an overload string to the target namespace for each overloaded artifact.</span></span> <span data-ttu-id="52bce-137">この文字列の値は"overload1"最初のオーバー ロード"overload2"の 2 番目のオーバー ロードです。</span><span class="sxs-lookup"><span data-stu-id="52bce-137">The value of this string is "overload1" for the first overload, "overload2" for the second overload, and so on.</span></span> <span data-ttu-id="52bce-138">次の例は、2 つのオーバー ロードされたストアド プロシージャのメッセージ構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="52bce-138">The following example shows the message structure for two overloaded stored procedures.</span></span>  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a><span data-ttu-id="52bce-139">ストアド プロシージャ、関数、および PL/SQL Api のメッセージの動作</span><span class="sxs-lookup"><span data-stu-id="52bce-139">Message Actions of Stored Procedures, Functions, and PL/SQL APIs</span></span>  
 <span data-ttu-id="52bce-140">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ストアド プロシージャ、関数、および PL/SQL API 操作の次のメッセージ アクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="52bce-140">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses the following message actions for stored procedure, function, and PL/SQL API operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52bce-141">表の後に、エンティティの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52bce-141">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="52bce-142">メッセージ</span><span class="sxs-lookup"><span data-stu-id="52bce-142">Message</span></span>|<span data-ttu-id="52bce-143">操作</span><span class="sxs-lookup"><span data-stu-id="52bce-143">Action</span></span>|<span data-ttu-id="52bce-144">例</span><span class="sxs-lookup"><span data-stu-id="52bce-144">Example</span></span>|  
|-------------|------------|-------------|  
|<span data-ttu-id="52bce-145">ストアド プロシージャ要求</span><span class="sxs-lookup"><span data-stu-id="52bce-145">Stored Procedure Request</span></span>|<span data-ttu-id="52bce-146">プロシージャ/[スキーマ]/[SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="52bce-146">Procedures/[SCHEMA]/[SP_NAME]</span></span>|<span data-ttu-id="52bce-147">プロシージャ/SCOTT/SP_INSERT</span><span class="sxs-lookup"><span data-stu-id="52bce-147">Procedures/SCOTT/SP_INSERT</span></span>|  
|<span data-ttu-id="52bce-148">ストアド プロシージャの応答</span><span class="sxs-lookup"><span data-stu-id="52bce-148">Stored Procedure Response</span></span>|<span data-ttu-id="52bce-149">プロシージャ/[スキーマ]/[SP_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-149">Procedures/[SCHEMA]/[SP_NAME]/response</span></span>|<span data-ttu-id="52bce-150">プロシージャ、SCOTT、SP_INSERT/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-150">Procedures/SCOTT/SP_INSERT/response</span></span>|  
|<span data-ttu-id="52bce-151">関数の要求</span><span class="sxs-lookup"><span data-stu-id="52bce-151">Function Request</span></span>|<span data-ttu-id="52bce-152">機能/[スキーマ]/[FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="52bce-152">Functions/[SCHEMA]/[FN_NAME]</span></span>|<span data-ttu-id="52bce-153">FN_GETID SCOTT/関数/</span><span class="sxs-lookup"><span data-stu-id="52bce-153">Functions/SCOTT/FN_GETID</span></span>|  
|<span data-ttu-id="52bce-154">関数の応答</span><span class="sxs-lookup"><span data-stu-id="52bce-154">Function Response</span></span>|<span data-ttu-id="52bce-155">機能/[スキーマ]/[FN_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-155">Functions/[SCHEMA]/[FN_NAME]/response</span></span>|<span data-ttu-id="52bce-156">関数、SCOTT、FN_GETID/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-156">Functions/SCOTT/FN_GETID/response</span></span>|  
|<span data-ttu-id="52bce-157">PL/SQL API 要求</span><span class="sxs-lookup"><span data-stu-id="52bce-157">PL/SQL API Request</span></span>|<span data-ttu-id="52bce-158">[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="52bce-158">[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]</span></span>|<span data-ttu-id="52bce-159">SCOTT/パッケージ/顧客/SP_INSERT</span><span class="sxs-lookup"><span data-stu-id="52bce-159">SCOTT/Package/CUSTOMER/SP_INSERT</span></span>|  
|<span data-ttu-id="52bce-160">ストアド プロシージャの応答をパッケージ化</span><span class="sxs-lookup"><span data-stu-id="52bce-160">Packaged Stored Procedure Response</span></span>|<span data-ttu-id="52bce-161">[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-161">[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response</span></span>|<span data-ttu-id="52bce-162">SCOTT/パッケージ/顧客/SP_INSERT/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-162">SCOTT/Package/CUSTOMER/SP_INSERT/response</span></span>|  
|<span data-ttu-id="52bce-163">パッケージ化された関数の要求</span><span class="sxs-lookup"><span data-stu-id="52bce-163">Packaged Function Request</span></span>|<span data-ttu-id="52bce-164">[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="52bce-164">[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]</span></span>|<span data-ttu-id="52bce-165">SCOTT/パッケージ/顧客/FN_GETID</span><span class="sxs-lookup"><span data-stu-id="52bce-165">SCOTT/Package/CUSTOMER/FN_GETID</span></span>|  
|<span data-ttu-id="52bce-166">パッケージ化された関数の応答</span><span class="sxs-lookup"><span data-stu-id="52bce-166">Packaged Function Response</span></span>|<span data-ttu-id="52bce-167">[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-167">[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response</span></span>|<span data-ttu-id="52bce-168">SCOTT/パッケージ/顧客/FN_GETID/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-168">SCOTT/Package/CUSTOMER/FN_GETID/response</span></span>|  
|<span data-ttu-id="52bce-169">ストアド プロシージャのオーバー ロードされた要求</span><span class="sxs-lookup"><span data-stu-id="52bce-169">Overloaded Stored Procedure Request</span></span>|<span data-ttu-id="52bce-170">[スキーマ]/Procedure/[SP_NAME]/[オーバー ロードする]</span><span class="sxs-lookup"><span data-stu-id="52bce-170">[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]</span></span>|<span data-ttu-id="52bce-171">SCOTT、プロシージャ、SP_INSERT/overload1</span><span class="sxs-lookup"><span data-stu-id="52bce-171">SCOTT/Procedure/SP_INSERT/overload1</span></span>|  
|<span data-ttu-id="52bce-172">ストアド プロシージャの応答をオーバー ロード</span><span class="sxs-lookup"><span data-stu-id="52bce-172">Overloaded Stored Procedure Response</span></span>|<span data-ttu-id="52bce-173">[スキーマ]/Procedure/[SP_NAME]/[オーバー ロード]/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-173">[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response</span></span>|<span data-ttu-id="52bce-174">SCOTT/プロシージャ/SP_INSERT/overload1/応答</span><span class="sxs-lookup"><span data-stu-id="52bce-174">SCOTT/Procedure/SP_INSERT/overload1/response</span></span>|  
  
 <span data-ttu-id="52bce-175">エンティティの説明</span><span class="sxs-lookup"><span data-stu-id="52bce-175">Entity descriptions:</span></span>  
  
 <span data-ttu-id="52bce-176">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="52bce-176">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="52bce-177">[SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。</span><span class="sxs-lookup"><span data-stu-id="52bce-177">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  
  
 <span data-ttu-id="52bce-178">[FN_NAME] 実行する関数を =たとえば、FN_GETID です。</span><span class="sxs-lookup"><span data-stu-id="52bce-178">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  
  
 <span data-ttu-id="52bce-179">[PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。</span><span class="sxs-lookup"><span data-stu-id="52bce-179">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  
  
 <span data-ttu-id="52bce-180">[オーバー ロード]、オーバー ロードのパラメーターを = です。</span><span class="sxs-lookup"><span data-stu-id="52bce-180">[OVERLOAD] = The Overload parameter.</span></span> <span data-ttu-id="52bce-181">使用可能な値は overload1、overload2、およびなどです。</span><span class="sxs-lookup"><span data-stu-id="52bce-181">The possible values are overload1, overload2, and so on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bce-182">参照</span><span class="sxs-lookup"><span data-stu-id="52bce-182">See Also</span></span>  
 [<span data-ttu-id="52bce-183">BizTalk Adapter for Oracle E-Business Suite 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="52bce-183">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)