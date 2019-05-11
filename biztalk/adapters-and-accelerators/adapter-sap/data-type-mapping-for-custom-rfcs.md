---
title: カスタム Rfc のデータ型マッピング |Microsoft Docs
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
ms.openlocfilehash: 0d6934847a5c5a9482a9c4f1dc8026c50aec6295
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373551"
---
# <a name="data-type-mapping-for-custom-rfcs"></a><span data-ttu-id="1a8b4-102">カスタム Rfc のデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="1a8b4-102">Data Type Mapping for Custom RFCs</span></span>
<span data-ttu-id="1a8b4-103">次の表は、SAP のデータ型および Z_EXTRACT_DATA_OO RFC の .NET データ型にマップする方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-103">The following table provides information about SAP data types and how they are mapped to .NET data types for the Z_EXTRACT_DATA_OO RFC.</span></span> <span data-ttu-id="1a8b4-104">このカスタム RFC を使って、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-104">This custom RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a8b4-105">によって使用されるため、Z_EXECUTE_SAP_QUERY、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] EXECQUERY コマンドを実行するすべての SAP のデータ型は .NET の文字列型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-105">For the Z_EXECUTE_SAP_QUERY, which is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute the EXECQUERY command, all SAP data types are converted to .NET string types.</span></span>  
  
|<span data-ttu-id="1a8b4-106">SAP のデータ型</span><span class="sxs-lookup"><span data-stu-id="1a8b4-106">SAP Data Type</span></span>|<span data-ttu-id="1a8b4-107">.NET データ型</span><span class="sxs-lookup"><span data-stu-id="1a8b4-107">.NET Data Type</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="1a8b4-108">ACCP</span><span class="sxs-lookup"><span data-stu-id="1a8b4-108">ACCP</span></span>|<span data-ttu-id="1a8b4-109">-Int32</span><span class="sxs-lookup"><span data-stu-id="1a8b4-109">-   Int32</span></span><br /><span data-ttu-id="1a8b4-110">、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-110">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="1a8b4-111">CHAR</span><span class="sxs-lookup"><span data-stu-id="1a8b4-111">CHAR</span></span>|<span data-ttu-id="1a8b4-112">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-112">String</span></span>|  
|<span data-ttu-id="1a8b4-113">CLNT</span><span class="sxs-lookup"><span data-stu-id="1a8b4-113">CLNT</span></span>|<span data-ttu-id="1a8b4-114">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-114">String</span></span>|  
|<span data-ttu-id="1a8b4-115">CUKY</span><span class="sxs-lookup"><span data-stu-id="1a8b4-115">CUKY</span></span>|<span data-ttu-id="1a8b4-116">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-116">String</span></span>|  
|<span data-ttu-id="1a8b4-117">CURR</span><span class="sxs-lookup"><span data-stu-id="1a8b4-117">CURR</span></span>|<span data-ttu-id="1a8b4-118">場合、28 に等しいかそれよりも有効桁数が 10 進数</span><span class="sxs-lookup"><span data-stu-id="1a8b4-118">Decimal, if precision less than or equal to 28</span></span><br /><br /> <span data-ttu-id="1a8b4-119">文字列の場合は、有効桁数が 28 より大きい</span><span class="sxs-lookup"><span data-stu-id="1a8b4-119">String, if precision greater than 28</span></span>|  
|<span data-ttu-id="1a8b4-120">DATS</span><span class="sxs-lookup"><span data-stu-id="1a8b4-120">DATS</span></span>|<span data-ttu-id="1a8b4-121">-DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8b4-121">-   DateTime</span></span><br /><span data-ttu-id="1a8b4-122">、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-122">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="1a8b4-123">12 月</span><span class="sxs-lookup"><span data-stu-id="1a8b4-123">DEC</span></span>|<span data-ttu-id="1a8b4-124">10 進数</span><span class="sxs-lookup"><span data-stu-id="1a8b4-124">Decimal</span></span>|  
|<span data-ttu-id="1a8b4-125">FLTP</span><span class="sxs-lookup"><span data-stu-id="1a8b4-125">FLTP</span></span>|<span data-ttu-id="1a8b4-126">Double</span><span class="sxs-lookup"><span data-stu-id="1a8b4-126">Double</span></span>|  
|<span data-ttu-id="1a8b4-127">INT1</span><span class="sxs-lookup"><span data-stu-id="1a8b4-127">INT1</span></span>|<span data-ttu-id="1a8b4-128">バイト</span><span class="sxs-lookup"><span data-stu-id="1a8b4-128">Byte</span></span>|  
|<span data-ttu-id="1a8b4-129">INT2</span><span class="sxs-lookup"><span data-stu-id="1a8b4-129">INT2</span></span>|<span data-ttu-id="1a8b4-130">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8b4-130">Int16</span></span>|  
|<span data-ttu-id="1a8b4-131">INT4</span><span class="sxs-lookup"><span data-stu-id="1a8b4-131">INT4</span></span>|<span data-ttu-id="1a8b4-132">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8b4-132">Int32</span></span>|  
|<span data-ttu-id="1a8b4-133">LANG</span><span class="sxs-lookup"><span data-stu-id="1a8b4-133">LANG</span></span>|<span data-ttu-id="1a8b4-134">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-134">String</span></span>|  
|<span data-ttu-id="1a8b4-135">NUMC</span><span class="sxs-lookup"><span data-stu-id="1a8b4-135">NUMC</span></span>|<span data-ttu-id="1a8b4-136">、フィールドの場合 Int32、9 の長さ以下</span><span class="sxs-lookup"><span data-stu-id="1a8b4-136">-   Int32, if field length less than or equal to 9</span></span><br /><span data-ttu-id="1a8b4-137">、フィールドの場合 Int64、長さが 9 よりも大きい 19 以下</span><span class="sxs-lookup"><span data-stu-id="1a8b4-137">-   Int64, if field length greater than 9 and less than or equal to 19</span></span><br /><span data-ttu-id="1a8b4-138">、19 より大きい場合は文字列、</span><span class="sxs-lookup"><span data-stu-id="1a8b4-138">-   String, if greater than 19</span></span><br /><span data-ttu-id="1a8b4-139">、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-139">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="1a8b4-140">PREC</span><span class="sxs-lookup"><span data-stu-id="1a8b4-140">PREC</span></span>|<span data-ttu-id="1a8b4-141">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8b4-141">Int16</span></span>|  
|<span data-ttu-id="1a8b4-142">QUAN</span><span class="sxs-lookup"><span data-stu-id="1a8b4-142">QUAN</span></span>|<span data-ttu-id="1a8b4-143">10 進数</span><span class="sxs-lookup"><span data-stu-id="1a8b4-143">Decimal</span></span>|  
|<span data-ttu-id="1a8b4-144">RAW</span><span class="sxs-lookup"><span data-stu-id="1a8b4-144">RAW</span></span>|<span data-ttu-id="1a8b4-145">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1a8b4-145">Byte []</span></span>|  
|<span data-ttu-id="1a8b4-146">RSTR</span><span class="sxs-lookup"><span data-stu-id="1a8b4-146">RSTR</span></span>|<span data-ttu-id="1a8b4-147">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1a8b4-147">Byte []</span></span>|  
|<span data-ttu-id="1a8b4-148">SSTR</span><span class="sxs-lookup"><span data-stu-id="1a8b4-148">SSTR</span></span>|<span data-ttu-id="1a8b4-149">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-149">String</span></span>|  
|<span data-ttu-id="1a8b4-150">STRG</span><span class="sxs-lookup"><span data-stu-id="1a8b4-150">STRG</span></span>|<span data-ttu-id="1a8b4-151">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-151">String</span></span>|  
|<span data-ttu-id="1a8b4-152">TIMS</span><span class="sxs-lookup"><span data-stu-id="1a8b4-152">TIMS</span></span>|<span data-ttu-id="1a8b4-153">間隔</span><span class="sxs-lookup"><span data-stu-id="1a8b4-153">-   TimeSpan</span></span><br /><span data-ttu-id="1a8b4-154">、場合は文字列、 **disabledatavalidation** SELECT または EXEC ステートメントでオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="1a8b4-154">-   String, if **disabledatavalidation** option is set in the SELECT or EXEC statement.</span></span>|  
|<span data-ttu-id="1a8b4-155">ユニット</span><span class="sxs-lookup"><span data-stu-id="1a8b4-155">UNIT</span></span>|<span data-ttu-id="1a8b4-156">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-156">String</span></span>|  
|<span data-ttu-id="1a8b4-157">LCHR</span><span class="sxs-lookup"><span data-stu-id="1a8b4-157">LCHR</span></span>|<span data-ttu-id="1a8b4-158">String</span><span class="sxs-lookup"><span data-stu-id="1a8b4-158">String</span></span>|  
|<span data-ttu-id="1a8b4-159">LRAW</span><span class="sxs-lookup"><span data-stu-id="1a8b4-159">LRAW</span></span>|<span data-ttu-id="1a8b4-160">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1a8b4-160">Byte []</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a8b4-161">参照</span><span class="sxs-lookup"><span data-stu-id="1a8b4-161">See Also</span></span>  
 [<span data-ttu-id="1a8b4-162">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="1a8b4-162">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)