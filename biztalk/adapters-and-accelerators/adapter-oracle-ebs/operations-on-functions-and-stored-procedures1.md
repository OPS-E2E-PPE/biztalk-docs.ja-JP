---
title: "関数およびストアド Procedures1 に対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfe5f705c8e432c920c8fae41a2b2f050c188047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-functions-and-stored-procedures"></a><span data-ttu-id="99848-102">関数およびストアド プロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="99848-102">Operations on Functions and Stored Procedures</span></span>
<span data-ttu-id="99848-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle 関数およびプロシージャをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="99848-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures.</span></span>

## <a name="functions-and-procedures"></a><span data-ttu-id="99848-104">関数およびプロシージャ</span><span class="sxs-lookup"><span data-stu-id="99848-104">Functions and procedures</span></span>

<span data-ttu-id="99848-105">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次のように Oracle 関数およびプロシージャをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="99848-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports Oracle functions and procedures in the following manner:</span></span>  
  
-   <span data-ttu-id="99848-106">**関数**操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="99848-106">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="99848-107">操作の名前は、Oracle 関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="99848-107">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="99848-108">出し、および OUT パラメーターはサポートし、同様に、値を返します。</span><span class="sxs-lookup"><span data-stu-id="99848-108">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="99848-109">関数で無効なパラメーターを渡す場合 (つまり、数値フィールドの文字列値、渡す、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 動作によって例外をスローする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99848-109">If you pass an invalid parameter in a function (that is, pass a string value for a numeric field), the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] might throw an exception depending on the ODP.NET behavior.</span></span> <span data-ttu-id="99848-110">これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET を使用して Oracle E-business Suite と通信します。</span><span class="sxs-lookup"><span data-stu-id="99848-110">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite.</span></span>  
  
-   <span data-ttu-id="99848-111">**プロシージャ**操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="99848-111">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="99848-112">操作の名前は、Oracle のプロシージャの名前です。</span><span class="sxs-lookup"><span data-stu-id="99848-112">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="99848-113">出し、および OUT パラメーターはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="99848-113">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="99848-114">挿入またはインターフェイスのテーブルまたはデータベース テーブルの数値フィールドに (たとえば、15.2) の 10 進値を更新する場合、プロシージャの一部として、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="99848-114">As part of a procedure, if you insert or update a decimal value (for example, 15.2) into a numeric field of an interface table or database table, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] will throw an exception.</span></span> <span data-ttu-id="99848-115">これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と通信するために ODP.NET、ODP.NET はサポートしていません数値フィールドの 10 進数の値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="99848-115">This is because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses ODP.NET to communicate with Oracle E-Business Suite, and ODP.NET does not support accepting decimal values for the numeric fields.</span></span>  
  
-   <span data-ttu-id="99848-116">**REF CURSOR 型**IN はサポートされてし、OUT パラメーター プロシージャおよび関数、および関数の戻り値。</span><span class="sxs-lookup"><span data-stu-id="99848-116">**REF CURSOR types** are supported for IN and OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="99848-117">詳細については、次を参照してください。[関数および REF CURSOR パラメーターを持つプロシージャで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)です。</span><span class="sxs-lookup"><span data-stu-id="99848-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
-   <span data-ttu-id="99848-118">**レコードの種類**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="99848-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="99848-119">単純または複雑なの両方の (入れ子になった) レコードの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="99848-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="99848-120">関数およびレコードの種類のプロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="99848-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  <span data-ttu-id="99848-121">関数およびストアド プロシージャでのアプリケーション コンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="99848-121">You can also set the application context for functions and stored procedures in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="99848-122">アプリケーションのコンテキストとそれを設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="99848-122">For information about application context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99848-123">参照</span><span class="sxs-lookup"><span data-stu-id="99848-123">See Also</span></span>  
 <span data-ttu-id="99848-124">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="99848-124">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>