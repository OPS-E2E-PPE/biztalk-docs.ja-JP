---
title: Siebel アダプターの SiebelParameter クラス |Microsoft Docs
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
ms.openlocfilehash: 4945b7c2dfb72286682b8afa396f882648c88118
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370623"
---
# <a name="siebelparameter-class-in-the-siebel-adapter"></a><span data-ttu-id="3e802-102">Siebel アダプターの SiebelParameter クラス</span><span class="sxs-lookup"><span data-stu-id="3e802-102">SiebelParameter class in the Siebel adapter</span></span>
<span data-ttu-id="3e802-103">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]提供、`DbParameter`特定のコマンドのパラメーターを指定する、ADO.NET クライアントを有効にする実装。</span><span class="sxs-lookup"><span data-stu-id="3e802-103">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides a `DbParameter` implementation to enable an ADO.NET client to specify parameters for a particular command.</span></span> <span data-ttu-id="3e802-104">インスタンスを使用して、`System.Data.Common.DbCommand`のクラス、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、クライアント プログラムがのインスタンスを取得、`System.Data.Common.DbParameter`クラス。</span><span class="sxs-lookup"><span data-stu-id="3e802-104">Using an instance of the `System.Data.Common.DbCommand` class of the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], a client program can obtain an instance of the `System.Data.Common.DbParameter` class.</span></span>  

```  
//In this example, command is an instance of DbCommand  
DbParameter param = command.CreateParameter();  
```  

 <span data-ttu-id="3e802-105">または、次のアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e802-105">Alternatively, the following approach can be used:</span></span>  

```  

//Here command is an instance of SiebelCommand  
SiebelParameter param = (SiebelParameter) command.CreateParameter();                  
param.ParameterName = "@Time";  
```  

 <span data-ttu-id="3e802-106">`SiebelParameter`クラスから継承`DbParameter`します。</span><span class="sxs-lookup"><span data-stu-id="3e802-106">The `SiebelParameter` class inherits from `DbParameter`.</span></span>  <span data-ttu-id="3e802-107">名前空間内に存在する`Microsoft.Data.SiebelClient`します。</span><span class="sxs-lookup"><span data-stu-id="3e802-107">It exists in the namespace `Microsoft.Data.SiebelClient`.</span></span>  

## <a name="supported-properties"></a><span data-ttu-id="3e802-108">サポートされているプロパティ</span><span class="sxs-lookup"><span data-stu-id="3e802-108">Supported Properties</span></span>  
 <span data-ttu-id="3e802-109">`SiebelParameter`クラスは、次をサポート`DbParameter`*パブリック*プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3e802-109">The `SiebelParameter` class supports the following `DbParameter`*public* properties:</span></span>  


|       <span data-ttu-id="3e802-110">名前</span><span class="sxs-lookup"><span data-stu-id="3e802-110">Name</span></span>        |   <span data-ttu-id="3e802-111">Get/Set</span><span class="sxs-lookup"><span data-stu-id="3e802-111">Get/Set</span></span>   |                                                                                                            <span data-ttu-id="3e802-112">説明</span><span class="sxs-lookup"><span data-stu-id="3e802-112">Description</span></span>                                                                                                            |
|-------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="3e802-113">**DbType**</span><span class="sxs-lookup"><span data-stu-id="3e802-113">**DbType**</span></span>     | <span data-ttu-id="3e802-114">Get と Set</span><span class="sxs-lookup"><span data-stu-id="3e802-114">Get and Set</span></span> |                                               <span data-ttu-id="3e802-115">パラメーターのデータ型。</span><span class="sxs-lookup"><span data-stu-id="3e802-115">Data type of the parameter.</span></span> <span data-ttu-id="3e802-116">参照してください[基本的な Siebel データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e802-116">See [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>                                               |
|   <span data-ttu-id="3e802-117">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="3e802-117">**Direction**</span></span>   | <span data-ttu-id="3e802-118">Get と Set</span><span class="sxs-lookup"><span data-stu-id="3e802-118">Get and Set</span></span> | <span data-ttu-id="3e802-119">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3e802-119">The following values are supported:</span></span><br /><br /> -                     `ParameterDirection.Input`<br /><br /> -                     `ParameterDirection.Output`<br /><br /> -                     `ParameterDirection.InputOutput` |
|  <span data-ttu-id="3e802-120">**IsNullable**</span><span class="sxs-lookup"><span data-stu-id="3e802-120">**IsNullable**</span></span>   | <span data-ttu-id="3e802-121">Get と Set</span><span class="sxs-lookup"><span data-stu-id="3e802-121">Get and Set</span></span> |                                                                               <span data-ttu-id="3e802-122">プロパティはサポートされていません、呼び出された場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="3e802-122">The property is not supported, and will throw an exception if called.</span></span>                                                                               |
| <span data-ttu-id="3e802-123">**ParameterName**</span><span class="sxs-lookup"><span data-stu-id="3e802-123">**ParameterName**</span></span> | <span data-ttu-id="3e802-124">Get と Set</span><span class="sxs-lookup"><span data-stu-id="3e802-124">Get and Set</span></span> |                                  <span data-ttu-id="3e802-125">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] ADO.NET クライアント パラメーター名を指定するには、このプロパティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e802-125">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports this property for an ADO.NET client to specify the parameter name.</span></span>                                  |
|     <span data-ttu-id="3e802-126">**[値]**</span><span class="sxs-lookup"><span data-stu-id="3e802-126">**Value**</span></span>     | <span data-ttu-id="3e802-127">Get と Set</span><span class="sxs-lookup"><span data-stu-id="3e802-127">Get and Set</span></span> |                                                    <span data-ttu-id="3e802-128">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]文字列としてパラメーター値を表します。</span><span class="sxs-lookup"><span data-stu-id="3e802-128">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] represents parameter values as strings.</span></span>                                                    |

###  <a name="BKMK_Datatypes"></a> <span data-ttu-id="3e802-129">サポートされるデータ型</span><span class="sxs-lookup"><span data-stu-id="3e802-129">Supported Data Types</span></span>  
 <span data-ttu-id="3e802-130">次の表に、単純な Siebel フィールドの種類を[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3e802-130">The following table summarizes the simple Siebel field types that [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] supports.</span></span> <span data-ttu-id="3e802-131">カバレッジの詳細を参照してください。[基本的な Siebel データ型](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e802-131">For more detailed coverage, see [Basic Siebel Data Types](../../adapters-and-accelerators/adapter-siebel/basic-siebel-data-types.md).</span></span>  

|<span data-ttu-id="3e802-132">Siebel のフィールドの種類</span><span class="sxs-lookup"><span data-stu-id="3e802-132">Siebel Field Type</span></span>|<span data-ttu-id="3e802-133">.NET Type</span><span class="sxs-lookup"><span data-stu-id="3e802-133">.NET Type</span></span>|<span data-ttu-id="3e802-134">XML スキーマ型</span><span class="sxs-lookup"><span data-stu-id="3e802-134">XML Schema Type</span></span>|  
|-----------------------|---------------|---------------------|  
|<span data-ttu-id="3e802-135">DTYPE_BOOL</span><span class="sxs-lookup"><span data-stu-id="3e802-135">DTYPE_BOOL</span></span>|<span data-ttu-id="3e802-136">ブール値</span><span class="sxs-lookup"><span data-stu-id="3e802-136">Boolean</span></span>|<span data-ttu-id="3e802-137">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="3e802-137">xsd:boolean</span></span>|  
|<span data-ttu-id="3e802-138">DTYPE_CURRENCY</span><span class="sxs-lookup"><span data-stu-id="3e802-138">DTYPE_CURRENCY</span></span>|<span data-ttu-id="3e802-139">10 進数</span><span class="sxs-lookup"><span data-stu-id="3e802-139">Decimal</span></span>|<span data-ttu-id="3e802-140">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="3e802-140">xsd:decimal</span></span>|  
|<span data-ttu-id="3e802-141">DTYPE_DATE</span><span class="sxs-lookup"><span data-stu-id="3e802-141">DTYPE_DATE</span></span>|<span data-ttu-id="3e802-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-142">DateTime</span></span>|<span data-ttu-id="3e802-143">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-143">xsd:dateTime</span></span>|  
|<span data-ttu-id="3e802-144">DTYPE_DATETIME</span><span class="sxs-lookup"><span data-stu-id="3e802-144">DTYPE_DATETIME</span></span>|<span data-ttu-id="3e802-145">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-145">DateTime</span></span>|<span data-ttu-id="3e802-146">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-146">xsd:dateTime</span></span>|  
|<span data-ttu-id="3e802-147">DTYPE_ UTCDATETIME</span><span class="sxs-lookup"><span data-stu-id="3e802-147">DTYPE_ UTCDATETIME</span></span>|<span data-ttu-id="3e802-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-148">DateTime</span></span>|<span data-ttu-id="3e802-149">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-149">xsd:dateTime</span></span>|  
|<span data-ttu-id="3e802-150">DTYPE_ID</span><span class="sxs-lookup"><span data-stu-id="3e802-150">DTYPE_ID</span></span>|<span data-ttu-id="3e802-151">String</span><span class="sxs-lookup"><span data-stu-id="3e802-151">String</span></span>|<span data-ttu-id="3e802-152">xsd:string</span><span class="sxs-lookup"><span data-stu-id="3e802-152">xsd:string</span></span>|  
|<span data-ttu-id="3e802-153">DTYPE_INTEGER</span><span class="sxs-lookup"><span data-stu-id="3e802-153">DTYPE_INTEGER</span></span>|<span data-ttu-id="3e802-154">Integer</span><span class="sxs-lookup"><span data-stu-id="3e802-154">Integer</span></span>|<span data-ttu-id="3e802-155">xsd:int</span><span class="sxs-lookup"><span data-stu-id="3e802-155">xsd:int</span></span>|  
|<span data-ttu-id="3e802-156">DTYPE_NOTE</span><span class="sxs-lookup"><span data-stu-id="3e802-156">DTYPE_NOTE</span></span>|<span data-ttu-id="3e802-157">String</span><span class="sxs-lookup"><span data-stu-id="3e802-157">String</span></span>|<span data-ttu-id="3e802-158">xsd:string</span><span class="sxs-lookup"><span data-stu-id="3e802-158">xsd:string</span></span>|  
|<span data-ttu-id="3e802-159">DTYPE_NUMBER</span><span class="sxs-lookup"><span data-stu-id="3e802-159">DTYPE_NUMBER</span></span>|<span data-ttu-id="3e802-160">10 進数</span><span class="sxs-lookup"><span data-stu-id="3e802-160">Decimal</span></span>|<span data-ttu-id="3e802-161">xsd:decimal</span><span class="sxs-lookup"><span data-stu-id="3e802-161">xsd:decimal</span></span>|  
|<span data-ttu-id="3e802-162">DTYPE_PHONE</span><span class="sxs-lookup"><span data-stu-id="3e802-162">DTYPE_PHONE</span></span>|<span data-ttu-id="3e802-163">String</span><span class="sxs-lookup"><span data-stu-id="3e802-163">String</span></span>|<span data-ttu-id="3e802-164">xsd:string</span><span class="sxs-lookup"><span data-stu-id="3e802-164">xsd:string</span></span>|  
|<span data-ttu-id="3e802-165">DTYPE_TEXT</span><span class="sxs-lookup"><span data-stu-id="3e802-165">DTYPE_TEXT</span></span>|<span data-ttu-id="3e802-166">String</span><span class="sxs-lookup"><span data-stu-id="3e802-166">String</span></span>|<span data-ttu-id="3e802-167">xsd:string</span><span class="sxs-lookup"><span data-stu-id="3e802-167">xsd:string</span></span>|  
|<span data-ttu-id="3e802-168">DTYPE_TIME</span><span class="sxs-lookup"><span data-stu-id="3e802-168">DTYPE_TIME</span></span>|<span data-ttu-id="3e802-169">DateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-169">DateTime</span></span>|<span data-ttu-id="3e802-170">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="3e802-170">xsd:dateTime</span></span>|  

## <a name="supported-methods"></a><span data-ttu-id="3e802-171">サポートされているメソッド</span><span class="sxs-lookup"><span data-stu-id="3e802-171">Supported Methods</span></span>  
 <span data-ttu-id="3e802-172">`SiebelParameter`クラスが内の特殊なメソッドをオーバーライドしていない`DbParameter`します。</span><span class="sxs-lookup"><span data-stu-id="3e802-172">The `SiebelParameter` class does not override any special methods in `DbParameter`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3e802-173">参照</span><span class="sxs-lookup"><span data-stu-id="3e802-173">See Also</span></span>  
 [<span data-ttu-id="3e802-174">Siebel アダプターを使用した ADO.NET インターフェイスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="3e802-174">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)