---
title: Siebel アダプターの SiebelParameter クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SiebelParameter
- Data Provider for Siebel, SiebelParameter
- SiebelParameter, supported properties and methods
ms.assetid: 1dcb72c7-a470-4609-8aba-a5c8ad5f3ac9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27df4b207b23cd04f7d29a2a18ec4ab032836e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222490"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a><span data-ttu-id="82124-102">Siebel アダプターの SiebelParameter クラス</span><span class="sxs-lookup"><span data-stu-id="82124-102">SiebelParameter class in the Siebel adapter</span></span>
<span data-ttu-id="82124-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbParameter`実装を特定のコマンドのパラメーターを指定する ADO.NET クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="82124-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbParameter` implementation to enable an ADO.NET client to specify parameters for a particular command.</span></span> <span data-ttu-id="82124-104">インスタンスを使用して、`System.Data.Common.DbCommand`のクラス、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、クライアント プログラムがのインスタンスを取得できます、`System.Data.Common.DbParameter`クラスです。</span><span class="sxs-lookup"><span data-stu-id="82124-104">Using an instance of the `System.Data.Common.DbCommand` class of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], a client program can obtain an instance of the `System.Data.Common.DbParameter` class.</span></span>  
  
```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  
  
 <span data-ttu-id="82124-105">また、次のアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82124-105">Alternatively, the following approach can be used:</span></span>  
  
```  
  
//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  
  
 <span data-ttu-id="82124-106">`SiebelParameter`クラスから継承`DbParameter`です。</span><span class="sxs-lookup"><span data-stu-id="82124-106">The `SiebelParameter` class inherits from `DbParameter`.</span></span>  <span data-ttu-id="82124-107">名前空間内に存在する`Microsoft.Data.SiebelClient`です。</span><span class="sxs-lookup"><span data-stu-id="82124-107">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  
  
## <a name="supported-properties"></a><span data-ttu-id="82124-108">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="82124-108">Supported Properties</span></span>  
 <span data-ttu-id="82124-109">`SiebelParameter`クラスは、次をサポート`DbParameter`*パブリック*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="82124-109">The `SiebelParameter` class supports the following `DbParameter`*public* properties:</span></span>  
  
|<span data-ttu-id="82124-110">名前</span><span class="sxs-lookup"><span data-stu-id="82124-110">Name</span></span>|<span data-ttu-id="82124-111">取得/設定</span><span class="sxs-lookup"><span data-stu-id="82124-111">Get/Set</span></span>|<span data-ttu-id="82124-112">Description</span><span class="sxs-lookup"><span data-stu-id="82124-112">Description</span></span>|  
|----------|--------------|-----------------|  
|<span data-ttu-id="82124-113">**DbType**</span><span class="sxs-lookup"><span data-stu-id="82124-113">**DbType**</span></span>|<span data-ttu-id="82124-114">Get および Set</span><span class="sxs-lookup"><span data-stu-id="82124-114">Get and Set</span></span>|<span data-ttu-id="82124-115">パラメーターのデータ型。</span><span class="sxs-lookup"><span data-stu-id="82124-115">Data type of the parameter.</span></span> <span data-ttu-id="82124-116">参照してください[Siebel の基本的なデータ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="82124-116">See [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>|  
|<span data-ttu-id="82124-117">**方向**</span><span class="sxs-lookup"><span data-stu-id="82124-117">**Direction**</span></span>|<span data-ttu-id="82124-118">Get および Set</span><span class="sxs-lookup"><span data-stu-id="82124-118">Get and Set</span></span>|<span data-ttu-id="82124-119">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="82124-119">The following values are supported:</span></span><br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput`|  
|<span data-ttu-id="82124-120">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="82124-120">**IsNullable**</span></span>|<span data-ttu-id="82124-121">Get および Set</span><span class="sxs-lookup"><span data-stu-id="82124-121">Get and Set</span></span>|<span data-ttu-id="82124-122">プロパティはサポートされていませんし、呼び出された場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="82124-122">The property is not supported, and will throw an exception if called.</span></span>|  
|<span data-ttu-id="82124-123">**パラメーター名**</span><span class="sxs-lookup"><span data-stu-id="82124-123">**ParameterName**</span></span>|<span data-ttu-id="82124-124">Get および Set</span><span class="sxs-lookup"><span data-stu-id="82124-124">Get and Set</span></span>|<span data-ttu-id="82124-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]パラメーター名を指定する ADO.NET クライアントのこのプロパティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="82124-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports this property for an ADO.NET client to specify the parameter name.</span></span>|  
|<span data-ttu-id="82124-126">**値**</span><span class="sxs-lookup"><span data-stu-id="82124-126">**Value**</span></span>|<span data-ttu-id="82124-127">Get および Set</span><span class="sxs-lookup"><span data-stu-id="82124-127">Get and Set</span></span>|<span data-ttu-id="82124-128">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]文字列としてのパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="82124-128">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] represents parameter values as strings.</span></span>|  
  
###  <a name="BKMK_Datatypes"></a><span data-ttu-id="82124-129">サポートされるデータ型</span><span class="sxs-lookup"><span data-stu-id="82124-129">Supported Data Types</span></span>  
 <span data-ttu-id="82124-130">次の表は、単純な Siebel フィールドの種類を[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82124-130">The following table summarizes the simple Siebel field types that [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports.</span></span> <span data-ttu-id="82124-131">カバレッジの詳細を参照してください。 [Siebel の基本データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="82124-131">For more detailed coverage, see [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>  
  
|<span data-ttu-id="82124-132">Siebel のフィールドの種類</span><span class="sxs-lookup"><span data-stu-id="82124-132">Siebel Field Type</span></span>|<span data-ttu-id="82124-133">.NET 型</span><span class="sxs-lookup"><span data-stu-id="82124-133">.NET Type</span></span>|<span data-ttu-id="82124-134">XML スキーマの型</span><span class="sxs-lookup"><span data-stu-id="82124-134">XML Schema Type</span></span>|  
|-----------------------|---------------|---------------------|  
|<span data-ttu-id="82124-135">DTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="82124-135">DTYPE_BOOL</span></span>|<span data-ttu-id="82124-136">ブール値</span><span class="sxs-lookup"><span data-stu-id="82124-136">Boolean</span></span>|<span data-ttu-id="82124-137">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="82124-137">xsd:boolean</span></span>|  
|<span data-ttu-id="82124-138">DTYPE_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="82124-138">DTYPE_CURRENCY</span></span>|<span data-ttu-id="82124-139">Decimal</span><span class="sxs-lookup"><span data-stu-id="82124-139">Decimal</span></span>|<span data-ttu-id="82124-140">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="82124-140">xsd:decimal</span></span>|  
|<span data-ttu-id="82124-141">DTYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="82124-141">DTYPE_DATE</span></span>|<span data-ttu-id="82124-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="82124-142">DateTime</span></span>|<span data-ttu-id="82124-143">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="82124-143">xsd:dateTime</span></span>|  
|<span data-ttu-id="82124-144">DTYPE_DATETIME</span><span class="sxs-lookup"><span data-stu-id="82124-144">DTYPE_DATETIME</span></span>|<span data-ttu-id="82124-145">DateTime</span><span class="sxs-lookup"><span data-stu-id="82124-145">DateTime</span></span>|<span data-ttu-id="82124-146">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="82124-146">xsd:dateTime</span></span>|  
|<span data-ttu-id="82124-147">DTYPE_ UTCDATETIME のフィールド</span><span class="sxs-lookup"><span data-stu-id="82124-147">DTYPE_ UTCDATETIME</span></span>|<span data-ttu-id="82124-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="82124-148">DateTime</span></span>|<span data-ttu-id="82124-149">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="82124-149">xsd:dateTime</span></span>|  
|<span data-ttu-id="82124-150">DTYPE_ID</span><span class="sxs-lookup"><span data-stu-id="82124-150">DTYPE_ID</span></span>|<span data-ttu-id="82124-151">文字列</span><span class="sxs-lookup"><span data-stu-id="82124-151">String</span></span>|<span data-ttu-id="82124-152">xsd:string</span><span class="sxs-lookup"><span data-stu-id="82124-152">xsd:string</span></span>|  
|<span data-ttu-id="82124-153">DTYPE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="82124-153">DTYPE_INTEGER</span></span>|<span data-ttu-id="82124-154">Integer</span><span class="sxs-lookup"><span data-stu-id="82124-154">Integer</span></span>|<span data-ttu-id="82124-155">xsd:int</span><span class="sxs-lookup"><span data-stu-id="82124-155">xsd:int</span></span>|  
|<span data-ttu-id="82124-156">DTYPE_NOTE</span><span class="sxs-lookup"><span data-stu-id="82124-156">DTYPE_NOTE</span></span>|<span data-ttu-id="82124-157">文字列</span><span class="sxs-lookup"><span data-stu-id="82124-157">String</span></span>|<span data-ttu-id="82124-158">xsd:string</span><span class="sxs-lookup"><span data-stu-id="82124-158">xsd:string</span></span>|  
|<span data-ttu-id="82124-159">DTYPE_NUMBER</span><span class="sxs-lookup"><span data-stu-id="82124-159">DTYPE_NUMBER</span></span>|<span data-ttu-id="82124-160">Decimal</span><span class="sxs-lookup"><span data-stu-id="82124-160">Decimal</span></span>|<span data-ttu-id="82124-161">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="82124-161">xsd:decimal</span></span>|  
|<span data-ttu-id="82124-162">DTYPE_PHONE</span><span class="sxs-lookup"><span data-stu-id="82124-162">DTYPE_PHONE</span></span>|<span data-ttu-id="82124-163">文字列</span><span class="sxs-lookup"><span data-stu-id="82124-163">String</span></span>|<span data-ttu-id="82124-164">xsd:string</span><span class="sxs-lookup"><span data-stu-id="82124-164">xsd:string</span></span>|  
|<span data-ttu-id="82124-165">DTYPE_TEXT</span><span class="sxs-lookup"><span data-stu-id="82124-165">DTYPE_TEXT</span></span>|<span data-ttu-id="82124-166">文字列</span><span class="sxs-lookup"><span data-stu-id="82124-166">String</span></span>|<span data-ttu-id="82124-167">xsd:string</span><span class="sxs-lookup"><span data-stu-id="82124-167">xsd:string</span></span>|  
|<span data-ttu-id="82124-168">DTYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="82124-168">DTYPE_TIME</span></span>|<span data-ttu-id="82124-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="82124-169">DateTime</span></span>|<span data-ttu-id="82124-170">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="82124-170">xsd:dateTime</span></span>|  
  
## <a name="supported-methods"></a><span data-ttu-id="82124-171">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="82124-171">Supported Methods</span></span>  
 <span data-ttu-id="82124-172">`SiebelParameter`クラスがで特別なメソッドをオーバーライドしていない`DbParameter`です。</span><span class="sxs-lookup"><span data-stu-id="82124-172">The `SiebelParameter` class does not override any special methods in `DbParameter`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82124-173">参照</span><span class="sxs-lookup"><span data-stu-id="82124-173">See Also</span></span>  
 [<span data-ttu-id="82124-174">Siebel アダプターと ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="82124-174">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)