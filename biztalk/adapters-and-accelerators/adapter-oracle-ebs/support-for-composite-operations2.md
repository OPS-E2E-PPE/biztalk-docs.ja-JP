---
title: "複合 Operations2 のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5766adec70c1a1fe7eaabe4ffaf07499e33d210c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-composite-operations"></a><span data-ttu-id="c0ff2-102">複合操作のサポート</span><span class="sxs-lookup"><span data-stu-id="c0ff2-102">Support for Composite Operations</span></span>
<span data-ttu-id="c0ff2-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが、次の操作、および任意の順序で任意の数を含めることができる複合操作を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
-   <span data-ttu-id="c0ff2-104">選択、挿入、更新、およびインターフェイス テーブルおよびデータベースのテーブルに対する操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-104">Select, Insert, Update, and Delete operations on an interface table and database table.</span></span>  
  
-   <span data-ttu-id="c0ff2-105">インターフェイス ビューとデータベース ビューに操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-105">Select operation on an interface view and database view.</span></span>  
  
-   <span data-ttu-id="c0ff2-106">ストアド プロシージャ、関数、およびアダプターでの操作として表示されたパッケージ内のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-106">Stored procedures, functions, and procedures within packages that are surfaced as operations in the adapter.</span></span>  
  
 <span data-ttu-id="c0ff2-107">複合操作内の操作対象に、同じデータベースまたは別のデータベースのテーブルおよびビューできます。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-107">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="c0ff2-108">ただし、データを共有または複合操作のさまざまな操作間で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-108">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="c0ff2-109">たとえば、操作では、複合、選択操作の結果セットは使えませんの入力パラメーターとしてストアド プロシージャの。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-109">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
 <span data-ttu-id="c0ff2-110">複合操作内の各操作は、別々 の接続を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-110">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="c0ff2-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作では、複合、操作の数として ODP.NET 接続プールからの複数の接続を使用し、操作が実行されると、接続を解放します。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="c0ff2-112">ただし、複合操作の操作は、結果セットを返す場合、は、接続は、メッセージが処理した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-112">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0ff2-113">複合操作を実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が関係する複合操作の操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-113">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="c0ff2-114">BFILE、BLOB、CLOB、NCLOB、および REF CURSOR とアウトを含むストアド プロシージャまたは IN OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-114">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="c0ff2-115">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-115">Select operation.</span></span>  
>   
>  <span data-ttu-id="c0ff2-116">この問題を解決するには、ある複合操作では、このような操作の"n"の数がある場合は、指定した値を確認する必要があります、 **MinPoolSize** "n+1"プロパティのバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-116">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="c0ff2-117">詳細については、 **MinPoolSize**バインディング プロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-117">For more information about the **MinPoolSize** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="c0ff2-118">詳細については。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-118">For information about:</span></span>  
  
-   <span data-ttu-id="c0ff2-119">複合操作を実行する方法[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-119">How to perform composite operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see  [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="c0ff2-120">メッセージ複合操作のスキーマを参照してください[複合操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-120">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ff2-121">複合の操作でアプリケーションのコンテキストを設定することも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-121">You can also set the applications context for composite operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="c0ff2-122">必須ではインターフェイス テーブルまたはインターフェイス ビューでの複合操作で操作を実行する場合は、複合操作のアプリケーション コンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-122">It is mandatory to set the applications context for the composite operations if any of the operations in a composite operation is performed on an interface table or interface view.</span></span> <span data-ttu-id="c0ff2-123">アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-123">For information about applications context, and how to set it, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ff2-124">参照</span><span class="sxs-lookup"><span data-stu-id="c0ff2-124">See Also</span></span>  
 [<span data-ttu-id="c0ff2-125">どのような操作、Oracle E-business Suite アダプターによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c0ff2-125">What operations are supported by the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)