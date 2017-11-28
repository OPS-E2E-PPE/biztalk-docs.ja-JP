---
title: "Siebel の EXEC ステートメントの構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EXEC statement, syntax for
- Data Provider for Siebel, EXEC statement
ms.assetid: c5534102-bf37-4b39-83ab-e09483744c4d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d18481b206b1be7e0062762c1844305fc36e10f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="syntax-for-an-exec-statement-in-siebel"></a><span data-ttu-id="00b4c-102">Siebel の EXEC ステートメントの構文</span><span class="sxs-lookup"><span data-stu-id="00b4c-102">Syntax for an EXEC Statement in Siebel</span></span>
<span data-ttu-id="00b4c-103">使用して、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、ADO.NET クライアントも EXEC 操作に対して行える、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00b4c-103">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], ADO.NET clients can also perform an EXEC operation on the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="00b4c-104">EXEC ステートメントの構文です。</span><span class="sxs-lookup"><span data-stu-id="00b4c-104">The syntax for the EXEC statement is:</span></span>  
  
```  
EXEC  
<Business Service name>.<Business Service method>  
\<value 1..n>,  
@parameter 1..n [OUTPUT],  
@parameter 1..n = <value>  
  
```  
  
 <span data-ttu-id="00b4c-105">上記の構文で`\<value 1..n>`無名のパラメーターのセットを表します。</span><span class="sxs-lookup"><span data-stu-id="00b4c-105">In the preceding syntax, `\<value 1..n>` represents a set of unnamed parameters.</span></span> <span data-ttu-id="00b4c-106">これらは、ハード コーディングされた値です。</span><span class="sxs-lookup"><span data-stu-id="00b4c-106">These are hard-coded values.</span></span> <span data-ttu-id="00b4c-107">これらは、通常、パラメーターで表します。</span><span class="sxs-lookup"><span data-stu-id="00b4c-107">They usually represent IN parameters.</span></span>  <span data-ttu-id="00b4c-108">それらを表す場合も INOUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="00b4c-108">They can also represent INOUT parameters.</span></span> <span data-ttu-id="00b4c-109">ただし、INOUT パラメーターのハードコード値を使用する場合そのパラメーターに関連付けられている出力値を取得できません EXEC ステートメントの実行後。</span><span class="sxs-lookup"><span data-stu-id="00b4c-109">However, if a hard-coded value is used for an INOUT parameter, the output value associated with that parameter cannot be retrieved after the EXEC statement is executed.</span></span>  
  
 <span data-ttu-id="00b4c-110">`@parameter 1..n`構文は、IN、INOUT は、名前付きパラメーターのパラメーターまたは OUT パラメーター セットを表します。</span><span class="sxs-lookup"><span data-stu-id="00b4c-110">The `@parameter 1..n` syntax represents a set of named parameters, which can be IN, INOUT, or OUT parameters.</span></span> <span data-ttu-id="00b4c-111">出力パラメーターの後に、**出力**キーワード。</span><span class="sxs-lookup"><span data-stu-id="00b4c-111">The output parameters must be followed by the **OUTPUT** keyword.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00b4c-112">**出力**パラメーター OUT および INOUT パラメーターではなくはキーワードを使用する必要がありますはのみです。</span><span class="sxs-lookup"><span data-stu-id="00b4c-112">The **OUTPUT** keyword must only be used with OUT parameters and not with INOUT parameters.</span></span>  
  
 <span data-ttu-id="00b4c-113">パラメーターの値を行内を指定するには、使用、`@parameter 1..n = <value>`構文です。</span><span class="sxs-lookup"><span data-stu-id="00b4c-113">To specify parameter values inline, use the `@parameter 1..n = <value>` syntax.</span></span>  
  
 <span data-ttu-id="00b4c-114">すべてのパラメーターは、コンマで区切られたにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b4c-114">All parameters must be comma-separated.</span></span>  
  
 <span data-ttu-id="00b4c-115">EXEC ステートメントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="00b4c-115">The following are examples of EXEC statements:</span></span>  
  
```  
EXEC ExtractDataService.Echo @In, @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo 'InputValue', @InOut, @Out OUTPUT  
  
EXEC ExtractDataService.Echo @InOut, @Out OUTPUT, @In='InputValue'  
  
EXEC ExtractDataService.Echo 'InputValue', @Out OUTPUT, @InOut='InputValue'  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="00b4c-116">パラメーター名 (など`@In`前の例で)、Siebel ビジネス サービス メソッドに対応する引数の名前に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00b4c-116">Every parameter name (like `@In` in the preceding example) must match the corresponding argument name in the Siebel Business Service method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b4c-117">参照</span><span class="sxs-lookup"><span data-stu-id="00b4c-117">See Also</span></span>  
 [<span data-ttu-id="00b4c-118">Siebel eBusiness Applications の .NET Framework データ プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="00b4c-118">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)