---
title: Siebel の EXEC ステートメントの構文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094161f866b12f656dd42e3eddbaba7c56a6ff01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370487"
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a><span data-ttu-id="aff30-102">Siebel の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="aff30-102">Syntax for an EXEC Statement in Siebel</span></span>
<span data-ttu-id="aff30-103">使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントは、EXEC 操作を実行もできる、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aff30-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can also perform an EXEC operation on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="aff30-104">EXEC ステートメントの構文です。</span><span class="sxs-lookup"><span data-stu-id="aff30-104">The syntax for the EXEC statement is:</span></span>  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 <span data-ttu-id="aff30-105">上記の構文で`\<value 1..n\>`無名のパラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="aff30-105">In the preceding syntax, `\<value 1..n\>` represents a set of unnamed parameters.</span></span> <span data-ttu-id="aff30-106">これらは、ハード コーディングされた値です。</span><span class="sxs-lookup"><span data-stu-id="aff30-106">These are hard-coded values.</span></span> <span data-ttu-id="aff30-107">通常、パラメーターを表します。</span><span class="sxs-lookup"><span data-stu-id="aff30-107">They usually represent IN parameters.</span></span>  <span data-ttu-id="aff30-108">INOUT パラメーターを表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="aff30-108">They can also represent INOUT parameters.</span></span> <span data-ttu-id="aff30-109">ただし、INOUT パラメーターのハードコード値を使用する場合、パラメーターに関連付けられている出力値を取得できません EXEC ステートメントの実行後。</span><span class="sxs-lookup"><span data-stu-id="aff30-109">However, if a hard-coded value is used for an INOUT parameter, the output value associated with that parameter cannot be retrieved after the EXEC statement is executed.</span></span>  
  
 <span data-ttu-id="aff30-110">`@parameter 1..n`構文は、IN、INOUT、可能性がある名前付きパラメーターのパラメーターまたは OUT パラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="aff30-110">The `@parameter 1..n` syntax represents a set of named parameters, which can be IN, INOUT, or OUT parameters.</span></span> <span data-ttu-id="aff30-111">出力パラメーターの後に、**出力**キーワード。</span><span class="sxs-lookup"><span data-stu-id="aff30-111">The output parameters must be followed by the **OUTPUT** keyword.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff30-112">**出力**パラメーター OUT および INOUT パラメーターではなくはキーワードを使用する必要がありますはのみです。</span><span class="sxs-lookup"><span data-stu-id="aff30-112">The **OUTPUT** keyword must only be used with OUT parameters and not with INOUT parameters.</span></span>  
  
 <span data-ttu-id="aff30-113">パラメーター値をインラインを指定するには、使用、`@parameter 1..n = <value>`構文。</span><span class="sxs-lookup"><span data-stu-id="aff30-113">To specify parameter values inline, use the `@parameter 1..n = <value>` syntax.</span></span>  
  
 <span data-ttu-id="aff30-114">すべてのパラメーターは、コンマ区切りにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff30-114">All parameters must be comma-separated.</span></span>  
  
 <span data-ttu-id="aff30-115">EXEC ステートメントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aff30-115">The following are examples of EXEC statements:</span></span>  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="aff30-116">すべてのパラメーター名 (など`@In`前の例)、Siebel ビジネス サービス メソッドに対応する引数名に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff30-116">Every parameter name (like `@In` in the preceding example) must match the corresponding argument name in the Siebel Business Service method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff30-117">参照</span><span class="sxs-lookup"><span data-stu-id="aff30-117">See Also</span></span>  
 [<span data-ttu-id="aff30-118">.NET Framework Data Provider for Siebel eBusiness Applications を使用する</span><span class="sxs-lookup"><span data-stu-id="aff30-118">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)