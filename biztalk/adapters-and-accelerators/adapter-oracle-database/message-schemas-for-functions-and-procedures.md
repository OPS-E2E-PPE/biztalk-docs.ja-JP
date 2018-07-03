---
title: メッセージ関数およびプロシージャのスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a821de5ac4a05165f33fa7035880d239bd6892b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008579"
---
# <a name="message-schemas-for-functions-and-procedures"></a><span data-ttu-id="d62d6-102">関数およびプロシージャのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d62d6-102">Message Schemas for Functions and Procedures</span></span>
<span data-ttu-id="d62d6-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェス Oracle データベースの関数およびストアド プロシージャの操作として。</span><span class="sxs-lookup"><span data-stu-id="d62d6-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces Oracle database functions and stored procedures as operations.</span></span> <span data-ttu-id="d62d6-104">このセクションでは、メッセージの構造と関数およびプロシージャの呼び出しに使用するアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d62d6-104">This section describes the message structure and actions used to invoke functions and procedures.</span></span>  

## <a name="message-structure-of-functions-and-procedures"></a><span data-ttu-id="d62d6-105">関数およびプロシージャのメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="d62d6-105">Message Structure of Functions and Procedures</span></span>  
 <span data-ttu-id="d62d6-106">関数の操作が表示され、ストアド プロシージャが、要求-応答のメッセージ交換パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="d62d6-106">The operations surfaced for functions and stored procedures follow a request-response message exchange pattern.</span></span> <span data-ttu-id="d62d6-107">次の表では、これらの要求と応答メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="d62d6-107">The following table shows the structure of these request and response messages.</span></span>  

|<span data-ttu-id="d62d6-108">演算</span><span class="sxs-lookup"><span data-stu-id="d62d6-108">Operation</span></span>|<span data-ttu-id="d62d6-109">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="d62d6-109">XML Message</span></span>|<span data-ttu-id="d62d6-110">説明</span><span class="sxs-lookup"><span data-stu-id="d62d6-110">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="d62d6-111">ストアド プロシージャの要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-111">Stored Procedure Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="d62d6-112">メッセージの本文に Oracle IN および OUT IN パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="d62d6-112">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="d62d6-113">ストアド プロシージャの応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-113">Stored Procedure Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="d62d6-114">メッセージの本文に Oracle OUT、IN OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="d62d6-114">Supports Oracle OUT and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="d62d6-115">関数の要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-115">Function Request</span></span>|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|<span data-ttu-id="d62d6-116">メッセージの本文に Oracle IN および OUT IN パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="d62d6-116">Supports Oracle IN and IN OUT parameters in the message body</span></span>|  
|<span data-ttu-id="d62d6-117">関数の応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-117">Function Response</span></span>|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|<span data-ttu-id="d62d6-118">メッセージの本文に Oracle OUT、IN OUT パラメーターをサポートしています</span><span class="sxs-lookup"><span data-stu-id="d62d6-118">Supports Oracle OUT and IN OUT parameters in the message body</span></span><br /><br /> <span data-ttu-id="d62d6-119">関数の戻り値が返される、 \<[FN_NAME] 結果\>要素。</span><span class="sxs-lookup"><span data-stu-id="d62d6-119">- The function return value is returned in the \<[FN_NAME]Result\> element.</span></span> <span data-ttu-id="d62d6-120">これは、応答メッセージの最初の要素です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-120">This is the first element in the response message.</span></span> <span data-ttu-id="d62d6-121">すべてのパラメーターの前に来ます。</span><span class="sxs-lookup"><span data-stu-id="d62d6-121">It comes before any parameters.</span></span>|  
|<span data-ttu-id="d62d6-122">パッケージ化されたプロシージャまたは関数の要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-122">Packaged Procedure or Function Request</span></span>|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|<span data-ttu-id="d62d6-123">関数またはストアド プロシージャと同じ</span><span class="sxs-lookup"><span data-stu-id="d62d6-123">Same as Function or Stored Procedure</span></span>|  
|<span data-ttu-id="d62d6-124">パッケージ化されたプロシージャまたは関数の応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-124">Packaged Procedure or Function Response</span></span>|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|<span data-ttu-id="d62d6-125">関数またはストアド プロシージャと同じ</span><span class="sxs-lookup"><span data-stu-id="d62d6-125">Same as Function or Stored Procedure</span></span>|  

 <span data-ttu-id="d62d6-126">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-126">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="d62d6-127">[SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-127">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="d62d6-128">[FN_NAME] を実行する関数を =たとえば、FN_GETID です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-128">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="d62d6-129">[PRM1_NAME] = Oracle パラメーターの名前。</span><span class="sxs-lookup"><span data-stu-id="d62d6-129">[PRM1_NAME] = The name of the Oracle parameter.</span></span> <span data-ttu-id="d62d6-130">メッセージごとにサポートされているパラメーターの方向の [説明] 列を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d62d6-130">See the Description column for supported parameter directions for each message.</span></span>  

 <span data-ttu-id="d62d6-131">[PACKAGE_NAME] = を対象となるプロシージャまたは関数を含むパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d62d6-131">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="d62d6-132">Oracle データベースでは、ストアド プロシージャおよび関数のオーバー ロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d62d6-132">The Oracle database supports overloading for stored procedures and functions.</span></span> <span data-ttu-id="d62d6-133">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]オーバー ロードされた各成果物のターゲット名前空間にはオーバー ロードの文字列を追加することによってこの機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d62d6-133">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports this capability by appending an overload string to the target namespace for each overloaded artifact.</span></span> <span data-ttu-id="d62d6-134">この文字列の値は、2 番目のオーバー ロードの最初のオーバー ロードで"overload2""overload1"が。</span><span class="sxs-lookup"><span data-stu-id="d62d6-134">The value of this string is "overload1" for the first overload, "overload2" for the second overload, and so on.</span></span> <span data-ttu-id="d62d6-135">次の例では、2 つのオーバー ロードされたストアド プロシージャのメッセージ構造を示します。</span><span class="sxs-lookup"><span data-stu-id="d62d6-135">The following example shows the message structure for two overloaded stored procedures.</span></span>  

```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  

Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  

## <a name="message-actions-of-functions-and-procedures"></a><span data-ttu-id="d62d6-136">関数およびプロシージャのメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="d62d6-136">Message Actions of Functions and Procedures</span></span>  
 <span data-ttu-id="d62d6-137">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ストアド プロシージャと関数の操作を次のメッセージ アクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d62d6-137">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the following message actions for stored procedure and function operations.</span></span>  


|               <span data-ttu-id="d62d6-138">メッセージ</span><span class="sxs-lookup"><span data-stu-id="d62d6-138">Message</span></span>                |                                              <span data-ttu-id="d62d6-139">操作</span><span class="sxs-lookup"><span data-stu-id="d62d6-139">Action</span></span>                                              |                                          <span data-ttu-id="d62d6-140">例</span><span class="sxs-lookup"><span data-stu-id="d62d6-140">Example</span></span>                                           |
|--------------------------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|       <span data-ttu-id="d62d6-141">ストアド プロシージャの要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-141">Stored Procedure Request</span></span>       |            <span data-ttu-id="d62d6-142">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Procedure/[SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="d62d6-142">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]</span></span>            |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT           |
|      <span data-ttu-id="d62d6-143">ストアド プロシージャの応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-143">Stored Procedure Response</span></span>       |       <span data-ttu-id="d62d6-144">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Procedure/[SP_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-144">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/response</span></span>        |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response      |
|           <span data-ttu-id="d62d6-145">関数の要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-145">Function Request</span></span>           |            <span data-ttu-id="d62d6-146">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Function/[FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="d62d6-146">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]</span></span>             |           http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID            |
|          <span data-ttu-id="d62d6-147">関数の応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-147">Function Response</span></span>           |        <span data-ttu-id="d62d6-148">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Function/[FN_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-148">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]/response</span></span>        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response       |
|  <span data-ttu-id="d62d6-149">ストアド プロシージャの要求をパッケージ化</span><span class="sxs-lookup"><span data-stu-id="d62d6-149">Packaged Stored Procedure Request</span></span>   |     <span data-ttu-id="d62d6-150">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]</span><span class="sxs-lookup"><span data-stu-id="d62d6-150">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]</span></span>      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT       |
|  <span data-ttu-id="d62d6-151">ストアド プロシージャの応答をパッケージ化</span><span class="sxs-lookup"><span data-stu-id="d62d6-151">Packaged Stored Procedure Response</span></span>  | <span data-ttu-id="d62d6-152">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-152">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response</span></span> |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response   |
|      <span data-ttu-id="d62d6-153">パッケージ化された関数の要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-153">Packaged Function Request</span></span>       |     <span data-ttu-id="d62d6-154">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]</span><span class="sxs-lookup"><span data-stu-id="d62d6-154">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]</span></span>      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID        |
|      <span data-ttu-id="d62d6-155">パッケージ化された関数の応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-155">Packaged Function Response</span></span>      | <span data-ttu-id="d62d6-156">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]/応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-156">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response</span></span> |   http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response   |
| <span data-ttu-id="d62d6-157">ストアド プロシージャのオーバー ロードされた要求</span><span class="sxs-lookup"><span data-stu-id="d62d6-157">Overloaded Stored Procedure Request</span></span>  |      <span data-ttu-id="d62d6-158">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Procedure/[SP_NAME]/[オーバー ロードする]</span><span class="sxs-lookup"><span data-stu-id="d62d6-158">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]</span></span>       |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1      |
| <span data-ttu-id="d62d6-159">応答のストアド プロシージャをオーバー ロード</span><span class="sxs-lookup"><span data-stu-id="d62d6-159">Overloaded Stored Procedure Response</span></span> |  <span data-ttu-id="d62d6-160">http://Microsoft.LobServices.OracleDB/2007/03/[スキーマ]/Procedure/[SP_NAME]/[オーバー ロード]/応答</span><span class="sxs-lookup"><span data-stu-id="d62d6-160">http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response</span></span>  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response |

 <span data-ttu-id="d62d6-161">[スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-161">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="d62d6-162">[SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-162">[SP_NAME] = The stored procedure to be executed; for example, SP_INSERT.</span></span>  

 <span data-ttu-id="d62d6-163">[FN_NAME] を実行する関数を =たとえば、FN_GETID です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-163">[FN_NAME] = The function to be executed; for example, FN_GETID.</span></span>  

 <span data-ttu-id="d62d6-164">[PACKAGE_NAME] = を対象となるプロシージャまたは関数を含むパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="d62d6-164">[PACKAGE_NAME] = The name of the package that contains the targeted procedure or function.</span></span>  

 <span data-ttu-id="d62d6-165">[オーバー ロード] = のオーバー ロードのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d62d6-165">[OVERLOAD] = The Overload parameter.</span></span> <span data-ttu-id="d62d6-166">使用可能な値は、overload1 や overload2、です。</span><span class="sxs-lookup"><span data-stu-id="d62d6-166">The possible values are overload1, overload2, and so on.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d62d6-167">参照</span><span class="sxs-lookup"><span data-stu-id="d62d6-167">See Also</span></span>  
 [<span data-ttu-id="d62d6-168">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="d62d6-168">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)