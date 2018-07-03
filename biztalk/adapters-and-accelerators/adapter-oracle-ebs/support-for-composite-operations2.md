---
title: 複合 Operations2 のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 724d5bc41686abc3928716a0e08801107df25055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979387"
---
# <a name="support-for-composite-operations"></a><span data-ttu-id="18726-102">複合操作のサポート</span><span class="sxs-lookup"><span data-stu-id="18726-102">Support for Composite Operations</span></span>
<span data-ttu-id="18726-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、任意の順序と、次の操作の任意の数を含めることができる複合操作を実行するクライアントはアダプター。</span><span class="sxs-lookup"><span data-stu-id="18726-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="18726-104">選択、挿入、更新、および、インターフェイス テーブルとデータベース テーブルでの操作を削除します。</span><span class="sxs-lookup"><span data-stu-id="18726-104">Select, Insert, Update, and Delete operations on an interface table and database table.</span></span>  
  
- <span data-ttu-id="18726-105">インターフェイス ビューとデータベース ビューを操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="18726-105">Select operation on an interface view and database view.</span></span>  
  
- <span data-ttu-id="18726-106">ストアド プロシージャ、関数、およびアダプターでの操作として表示されるパッケージ内のプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="18726-106">Stored procedures, functions, and procedures within packages that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="18726-107">複合操作の操作は、テーブルと同じデータベースまたは別のデータベース内のビューにターゲットします。</span><span class="sxs-lookup"><span data-stu-id="18726-107">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="18726-108">ただし、データを共有または複合操作のさまざまな操作で再利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="18726-108">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="18726-109">たとえば、複合操作で Select 操作の結果セットは使えません入力パラメーターとしてストアド プロシージャの。</span><span class="sxs-lookup"><span data-stu-id="18726-109">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
  <span data-ttu-id="18726-110">複合操作の各操作を実行するには、個別の接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="18726-110">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="18726-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]複合操作での操作の数は ODP.NET 接続プールからできるだけ多くの接続を消費し、取得、操作を実行するときに、接続を解放します。</span><span class="sxs-lookup"><span data-stu-id="18726-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="18726-112">ただし、複合操作内の操作では、結果セットを返しますの場合は、接続は、メッセージが消費した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="18726-112">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="18726-113">複合操作の実行中にタイムアウトの問題が発生した場合、可能性があります接続の数が、複合操作に関連する操作の数より少ない。</span><span class="sxs-lookup"><span data-stu-id="18726-113">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
> 
> - <span data-ttu-id="18726-114">OUT、BFILE、BLOB、CLOB、NCLOB、および REF CURSOR を含むストアド プロシージャまたは IN OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="18726-114">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
>   -   <span data-ttu-id="18726-115">操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="18726-115">Select operation.</span></span>  
> 
>   <span data-ttu-id="18726-116">この問題を解決するには、複合操作では、このような操作の数を"n"がある場合は、値が指定を確認する必要があります、 **MinPoolSize** "n+1"プロパティをバインドは以上です。</span><span class="sxs-lookup"><span data-stu-id="18726-116">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="18726-117">詳細については、 **MinPoolSize**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="18726-117">For more information about the **MinPoolSize** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="18726-118">詳細については。</span><span class="sxs-lookup"><span data-stu-id="18726-118">For information about:</span></span>  
  
- <span data-ttu-id="18726-119">複合操作を実行する方法[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を使用して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server を使用して Oracle データベースでの複合操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="18726-119">How to perform composite operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see  [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="18726-120">複合操作のスキーマのメッセージを参照してください[複合操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)します。</span><span class="sxs-lookup"><span data-stu-id="18726-120">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18726-121">複合操作でのアプリケーションのコンテキストを設定することも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18726-121">You can also set the applications context for composite operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="18726-122">インターフェイス テーブル、またはインターフェイス ビューの複合操作の操作を実行する場合は、複合操作のアプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18726-122">It is mandatory to set the applications context for the composite operations if any of the operations in a composite operation is performed on an interface table or interface view.</span></span> <span data-ttu-id="18726-123">アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="18726-123">For information about applications context, and how to set it, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18726-124">参照</span><span class="sxs-lookup"><span data-stu-id="18726-124">See Also</span></span>  
 [<span data-ttu-id="18726-125">Oracle E-business Suite アダプターによってサポートされる操作</span><span class="sxs-lookup"><span data-stu-id="18726-125">What operations are supported by the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)