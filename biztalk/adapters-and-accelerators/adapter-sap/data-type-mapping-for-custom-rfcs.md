---
title: データ型マッピング カスタム Rfc の |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-custom-rfcs"></a><span data-ttu-id="35d2c-102">カスタム Rfc のデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="35d2c-102">Data Type Mapping for Custom RFCs</span></span>
<span data-ttu-id="35d2c-103">次の表は、SAP データ型との Z_EXTRACT_DATA_OO RFC .NET データ型にマップする方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="35d2c-103">The following table provides information about SAP data types and how they are mapped to .NET data types for the Z_EXTRACT_DATA_OO RFC.</span></span> <span data-ttu-id="35d2c-104">このカスタム RFC を使って、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="35d2c-104">This custom RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35d2c-105">によって使用される、Z_EXECUTE_SAP_QUERY の[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]EXECQUERY コマンドを実行するには、すべての SAP データ型が .NET 文字列型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="35d2c-105">For the Z_EXECUTE_SAP_QUERY, which is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute the EXECQUERY command, all SAP data types are converted to .NET string types.</span></span>  
  
|<span data-ttu-id="35d2c-106">SAP データ型</span><span class="sxs-lookup"><span data-stu-id="35d2c-106">SAP Data Type</span></span>|<span data-ttu-id="35d2c-107">.NET データ型</span><span class="sxs-lookup"><span data-stu-id="35d2c-107">.NET Data Type</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="35d2c-108">ACCP</span><span class="sxs-lookup"><span data-stu-id="35d2c-108">ACCP</span></span>|<span data-ttu-id="35d2c-109">-Int32</span><span class="sxs-lookup"><span data-stu-id="35d2c-109">-   Int32</span></span><br /><span data-ttu-id="35d2c-110">、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。</span><span class="sxs-lookup"><span data-stu-id="35d2c-110">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="35d2c-111">CHAR</span><span class="sxs-lookup"><span data-stu-id="35d2c-111">CHAR</span></span>|<span data-ttu-id="35d2c-112">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-112">String</span></span>|  
|<span data-ttu-id="35d2c-113">CLNT</span><span class="sxs-lookup"><span data-stu-id="35d2c-113">CLNT</span></span>|<span data-ttu-id="35d2c-114">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-114">String</span></span>|  
|<span data-ttu-id="35d2c-115">CUKY</span><span class="sxs-lookup"><span data-stu-id="35d2c-115">CUKY</span></span>|<span data-ttu-id="35d2c-116">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-116">String</span></span>|  
|<span data-ttu-id="35d2c-117">現在</span><span class="sxs-lookup"><span data-stu-id="35d2c-117">CURR</span></span>|<span data-ttu-id="35d2c-118">Decimal、または有効桁数 28 以下</span><span class="sxs-lookup"><span data-stu-id="35d2c-118">Decimal, if precision less than or equal to 28</span></span><br /><br /> <span data-ttu-id="35d2c-119">文字列の場合は、有効桁数 28 桁を超える</span><span class="sxs-lookup"><span data-stu-id="35d2c-119">String, if precision greater than 28</span></span>|  
|<span data-ttu-id="35d2c-120">DATS</span><span class="sxs-lookup"><span data-stu-id="35d2c-120">DATS</span></span>|<span data-ttu-id="35d2c-121">-DateTime</span><span class="sxs-lookup"><span data-stu-id="35d2c-121">-   DateTime</span></span><br /><span data-ttu-id="35d2c-122">、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。</span><span class="sxs-lookup"><span data-stu-id="35d2c-122">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="35d2c-123">DEC</span><span class="sxs-lookup"><span data-stu-id="35d2c-123">DEC</span></span>|<span data-ttu-id="35d2c-124">Decimal</span><span class="sxs-lookup"><span data-stu-id="35d2c-124">Decimal</span></span>|  
|<span data-ttu-id="35d2c-125">FLTP</span><span class="sxs-lookup"><span data-stu-id="35d2c-125">FLTP</span></span>|<span data-ttu-id="35d2c-126">Double</span><span class="sxs-lookup"><span data-stu-id="35d2c-126">Double</span></span>|  
|<span data-ttu-id="35d2c-127">INT1</span><span class="sxs-lookup"><span data-stu-id="35d2c-127">INT1</span></span>|<span data-ttu-id="35d2c-128">Byte</span><span class="sxs-lookup"><span data-stu-id="35d2c-128">Byte</span></span>|  
|<span data-ttu-id="35d2c-129">INT2</span><span class="sxs-lookup"><span data-stu-id="35d2c-129">INT2</span></span>|<span data-ttu-id="35d2c-130">Int16</span><span class="sxs-lookup"><span data-stu-id="35d2c-130">Int16</span></span>|  
|<span data-ttu-id="35d2c-131">INT4</span><span class="sxs-lookup"><span data-stu-id="35d2c-131">INT4</span></span>|<span data-ttu-id="35d2c-132">Int32</span><span class="sxs-lookup"><span data-stu-id="35d2c-132">Int32</span></span>|  
|<span data-ttu-id="35d2c-133">LANG</span><span class="sxs-lookup"><span data-stu-id="35d2c-133">LANG</span></span>|<span data-ttu-id="35d2c-134">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-134">String</span></span>|  
|<span data-ttu-id="35d2c-135">NUMC</span><span class="sxs-lookup"><span data-stu-id="35d2c-135">NUMC</span></span>|<span data-ttu-id="35d2c-136">、フィールドの場合 Int32、9 の長さ以下</span><span class="sxs-lookup"><span data-stu-id="35d2c-136">-   Int32, if field length less than or equal to 9</span></span><br /><span data-ttu-id="35d2c-137">、フィールドの場合 Int64、長さ 9 よりも大きい 19 以下</span><span class="sxs-lookup"><span data-stu-id="35d2c-137">-   Int64, if field length greater than 9 and less than or equal to 19</span></span><br /><span data-ttu-id="35d2c-138">文字列、19 より大きい場合</span><span class="sxs-lookup"><span data-stu-id="35d2c-138">-   String, if greater than 19</span></span><br /><span data-ttu-id="35d2c-139">、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。</span><span class="sxs-lookup"><span data-stu-id="35d2c-139">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="35d2c-140">PREC</span><span class="sxs-lookup"><span data-stu-id="35d2c-140">PREC</span></span>|<span data-ttu-id="35d2c-141">Int16</span><span class="sxs-lookup"><span data-stu-id="35d2c-141">Int16</span></span>|  
|<span data-ttu-id="35d2c-142">QUAN</span><span class="sxs-lookup"><span data-stu-id="35d2c-142">QUAN</span></span>|<span data-ttu-id="35d2c-143">Decimal</span><span class="sxs-lookup"><span data-stu-id="35d2c-143">Decimal</span></span>|  
|<span data-ttu-id="35d2c-144">RAW</span><span class="sxs-lookup"><span data-stu-id="35d2c-144">RAW</span></span>|<span data-ttu-id="35d2c-145">Byte[]</span><span class="sxs-lookup"><span data-stu-id="35d2c-145">Byte []</span></span>|  
|<span data-ttu-id="35d2c-146">RSTR</span><span class="sxs-lookup"><span data-stu-id="35d2c-146">RSTR</span></span>|<span data-ttu-id="35d2c-147">Byte[]</span><span class="sxs-lookup"><span data-stu-id="35d2c-147">Byte []</span></span>|  
|<span data-ttu-id="35d2c-148">SSTR</span><span class="sxs-lookup"><span data-stu-id="35d2c-148">SSTR</span></span>|<span data-ttu-id="35d2c-149">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-149">String</span></span>|  
|<span data-ttu-id="35d2c-150">STRG</span><span class="sxs-lookup"><span data-stu-id="35d2c-150">STRG</span></span>|<span data-ttu-id="35d2c-151">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-151">String</span></span>|  
|<span data-ttu-id="35d2c-152">TIMS</span><span class="sxs-lookup"><span data-stu-id="35d2c-152">TIMS</span></span>|<span data-ttu-id="35d2c-153">-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="35d2c-153">-   TimeSpan</span></span><br /><span data-ttu-id="35d2c-154">、場合は文字列、 **disabledatavalidation**オプションは、SELECT ステートメントまたは EXEC ステートメントで設定します。</span><span class="sxs-lookup"><span data-stu-id="35d2c-154">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="35d2c-155">単位</span><span class="sxs-lookup"><span data-stu-id="35d2c-155">UNIT</span></span>|<span data-ttu-id="35d2c-156">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-156">String</span></span>|  
|<span data-ttu-id="35d2c-157">LCHR</span><span class="sxs-lookup"><span data-stu-id="35d2c-157">LCHR</span></span>|<span data-ttu-id="35d2c-158">文字列</span><span class="sxs-lookup"><span data-stu-id="35d2c-158">String</span></span>|  
|<span data-ttu-id="35d2c-159">LRAW</span><span class="sxs-lookup"><span data-stu-id="35d2c-159">LRAW</span></span>|<span data-ttu-id="35d2c-160">Byte[]</span><span class="sxs-lookup"><span data-stu-id="35d2c-160">Byte []</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35d2c-161">参照</span><span class="sxs-lookup"><span data-stu-id="35d2c-161">See Also</span></span>  
 [<span data-ttu-id="35d2c-162">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="35d2c-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)