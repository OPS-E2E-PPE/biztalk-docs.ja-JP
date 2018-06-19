---
title: 関数と Oracle データベースでストアド プロシージャに対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSOR
- packaged functions and procedures
- operations, on functions and stored procedures
- stored procedure
- RECORD type
- overloaded functions and procedures
ms.assetid: 18072b58-65b2-4da5-9433-ea0da4e2d4f4
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78181aae7921cad3996e4bd408e604857a2bd15e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214954"
---
# <a name="operations-on-functions-and-stored-procedures-in-oracle-database"></a><span data-ttu-id="bd84e-102">関数と Oracle データベースでストアド プロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="bd84e-102">Operations on functions and stored procedures in Oracle Database</span></span>
<span data-ttu-id="bd84e-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]次のように Oracle 関数、プロシージャ、およびパッケージをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bd84e-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports Oracle functions, procedures, and packages in the following manner:</span></span>  
  
-   <span data-ttu-id="bd84e-104">**関数**操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-104">**Functions** are surfaced as operations.</span></span> <span data-ttu-id="bd84e-105">操作の名前は、Oracle 関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-105">The name of the operation is the name of the Oracle function.</span></span> <span data-ttu-id="bd84e-106">出し、および OUT パラメーターはサポートし、同様に、値を返します。</span><span class="sxs-lookup"><span data-stu-id="bd84e-106">IN, OUT, and IN OUT parameters are supported, as well as, RETURN values.</span></span>  
  
-   <span data-ttu-id="bd84e-107">**プロシージャ**操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-107">**Procedures** are surfaced as operations.</span></span> <span data-ttu-id="bd84e-108">操作の名前は、Oracle のプロシージャの名前です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-108">The name of the operation is the name of the Oracle procedure.</span></span> <span data-ttu-id="bd84e-109">出し、および OUT パラメーターはサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd84e-109">IN, OUT, and IN OUT parameters are supported.</span></span>  
  
-   <span data-ttu-id="bd84e-110">**関数およびプロシージャをパッケージ化**操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-110">**Packaged functions and procedures** are surfaced as operations.</span></span> <span data-ttu-id="bd84e-111">処理 (関数またはプロシージャ) の名前空間と名前は、Oracle パッケージの名前で修飾されます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-111">The name and namespace of the operation (function or procedure) is qualified by the name of the Oracle package.</span></span> <span data-ttu-id="bd84e-112">オーバー ロードは、(次の項目を参照してください) のパッケージでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-112">Overloads are supported in packages (see next bullet).</span></span>  
  
-   <span data-ttu-id="bd84e-113">**オーバー ロードされた関数とプロシージャ**パッケージでの操作として表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd84e-113">**Overloaded functions and procedures** in packages are surfaced as operations.</span></span> <span data-ttu-id="bd84e-114">それぞれのオーバー ロード関数またはプロシージャは、オーバー ロードを識別する名前に追加される文字列を確認します。</span><span class="sxs-lookup"><span data-stu-id="bd84e-114">Each overloaded function or procedure is surfaced with a string appended to its name that identifies the overload.</span></span> <span data-ttu-id="bd84e-115">この文字列は、"overload1"、"overload2"、"overload3"と順序などの一部です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-115">This string is part of the sequence "overload1", "overload2", "overload3", and so on.</span></span>  
  
-   <span data-ttu-id="bd84e-116">**REF CURSOR 型**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="bd84e-116">**REF CURSOR types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="bd84e-117">詳細については、次を参照してください。[関数および REF CURSOR パラメーターを持つプロシージャで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-117">For more information, see [Operations on Functions and Procedures with REF CURSOR Parameters](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md).</span></span>  
  
-   <span data-ttu-id="bd84e-118">**レコードの種類**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="bd84e-118">**RECORD types** are supported for IN, OUT, and IN OUT parameters for procedures and functions, as well as for function RETURN values.</span></span> <span data-ttu-id="bd84e-119">単純または複雑なの両方の (入れ子になった) レコードの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd84e-119">Both simple and complex (nested) RECORD types are supported.</span></span> [<span data-ttu-id="bd84e-120">関数およびレコードの種類のプロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="bd84e-120">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
 <span data-ttu-id="bd84e-121">詳細については。</span><span class="sxs-lookup"><span data-stu-id="bd84e-121">For more information about:</span></span>  
  
-   <span data-ttu-id="bd84e-122">使用して、Oracle のプロシージャまたは関数を呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[関数の呼び出しおよび BizTalk Server を使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)と[オーバー ロード関数の呼び出しとプロシージャを使用して Oracle データベースBizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-122">Invoking an Oracle procedure or function by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md) and [Invoke Overload Functions and Procedures in Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="bd84e-123">WCF サービス モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[関数の呼び出しと、WCF サービス モデルを使用して Oracle データベースでプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-123">Invoking an Oracle procedure or function by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="bd84e-124">WCF チャネル モデルを使用して、Oracle のプロシージャまたは関数の呼び出しを参照してください[WCF チャネル モデルを使用して Oracle データベース内の関数を呼び出す](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-124">Invoking an Oracle procedure or function by using the WCF channel model, see [Invoke a Function in Oracle Database using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
-   <span data-ttu-id="bd84e-125">メッセージの構造と Oracle プロシージャと関数の呼び出しは、「を使用する SOAP アクション[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd84e-125">Message structure and SOAP actions used to invoke Oracle procedures and functions, see [Message Schemas for Functions and Procedures](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd84e-126">参照</span><span class="sxs-lookup"><span data-stu-id="bd84e-126">See Also</span></span>  
 <span data-ttu-id="bd84e-127">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="bd84e-127">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>