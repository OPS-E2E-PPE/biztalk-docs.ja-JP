---
title: "Ops アダプタの実装の詳細 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d68a55ce0f6eba835313075e8ab3753ec825db2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ops-adapter-implementation-details"></a><span data-ttu-id="deae2-102">Ops アダプタの実装の詳細</span><span class="sxs-lookup"><span data-stu-id="deae2-102">Ops Adapter Implementation Details</span></span>
<span data-ttu-id="deae2-103">次に示す Ops アダプタの特性を理解すると、アダプタを変更したりプログラムによって構成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="deae2-103">You may find it useful to understand the following aspects of the Ops adapter when modifying the adapter or configuring it programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="deae2-104">Ops アダプタはアダプタ フレームワークを使用して構築されています。</span><span class="sxs-lookup"><span data-stu-id="deae2-104">The Ops Adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="deae2-105">フレームワークでアダプタのビルドについては、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="deae2-105">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="batch-processing"></a><span data-ttu-id="deae2-106">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="deae2-106">Batch Processing</span></span>  
 <span data-ttu-id="deae2-107">このアダプタでは、それぞれのメッセージが別々に処理されるように、一度に 1 つのメッセージだけが処理されます。また、ロールバック操作も一度に 1 注文ずつ行われます。</span><span class="sxs-lookup"><span data-stu-id="deae2-107">The adapter processes one message at a time so that each message is processed separately, and rollback operations are done on only one order at a time.</span></span> <span data-ttu-id="deae2-108">このアダプタで一度に処理されるメッセージは 1 つだけですが、その場合には、バッチ サイズが 1 のバッチ処理が使用されています。</span><span class="sxs-lookup"><span data-stu-id="deae2-108">Although the adapter processes one message at a time, it does so using batching with a batch size of one.</span></span> <span data-ttu-id="deae2-109">これにより、メッセージをバッチ処理する場合にアダプタを変更する作業が容易になります。</span><span class="sxs-lookup"><span data-stu-id="deae2-109">This makes it easier to modify the adapter to handle messages in batches.</span></span>  
  
## <a name="transaction-handling"></a><span data-ttu-id="deae2-110">トランザクションの処理</span><span class="sxs-lookup"><span data-stu-id="deae2-110">Transaction Handling</span></span>  
 <span data-ttu-id="deae2-111">アダプターは、Microsoft によって提供されるトランザクション機能を使用して[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**機能します。</span><span class="sxs-lookup"><span data-stu-id="deae2-111">The adapter uses the transaction facilities provided by the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]**System.Transactions** facilities.</span></span> <span data-ttu-id="deae2-112">新しいアダプターを作成**CommittableTransaction**でそれを使用して、 **TransactionScope**です。</span><span class="sxs-lookup"><span data-stu-id="deae2-112">The adapter creates a new **CommittableTransaction** and uses it with a **TransactionScope**.</span></span> <span data-ttu-id="deae2-113">アダプターが、**初期化**と**Execute**このトランザクションのコンテキスト内のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="deae2-113">The adapter calls the **Initialize** and **Execute** methods within the context of this transaction.</span></span> <span data-ttu-id="deae2-114">呼び出されたアセンブリ内のコードを使用して、トランザクションに参加できる**Transaction.Current**トランザクション コンテキストを取得する静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="deae2-114">Code in the called assembly can participate in the transaction by using **Transaction.Current** static method to get the transaction context.</span></span> <span data-ttu-id="deae2-115">サンプル エラー ハンドラでは、この機能を使用していません。</span><span class="sxs-lookup"><span data-stu-id="deae2-115">The sample error handler does not make use of this facility.</span></span> <span data-ttu-id="deae2-116">詳細については**System.Transactions**、.NET Framework クラス ライブラリのバージョンで「System.Transactions Namespace」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deae2-116">For more information about **System.Transactions**, see "System.Transactions Namespace" in the .NET Framework Class Library version.</span></span>  
  
## <a name="handling-data-other-than-error-reports"></a><span data-ttu-id="deae2-117">エラー報告以外のデータの処理</span><span class="sxs-lookup"><span data-stu-id="deae2-117">Handling Data Other Than Error Reports</span></span>  
 <span data-ttu-id="deae2-118">ソリューション内で、このアダプタは新しいエラー報告機能を使用してエラー報告メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="deae2-118">In the solution, the adapter handles error report messages from the new error reporting feature.</span></span> <span data-ttu-id="deae2-119">ただし、ため、 **Execute**メソッドは、唯一の引数としてバイト配列を受け取りに渡される内容を明示的に制限がある、 **Execute**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="deae2-119">However, because the **Execute** method takes a byte array as its only argument, there is nothing that specifically limits what can be passed to the **Execute** method.</span></span>  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a><span data-ttu-id="deae2-120">プログラムによりポートを作成した場合のアダプタの使用</span><span class="sxs-lookup"><span data-stu-id="deae2-120">Using the Adapter When Creating Ports Programmatically</span></span>  
 <span data-ttu-id="deae2-121">コードからポートを作成する場合に、このアダプタを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="deae2-121">You can specify the adapter when creating ports from code.</span></span> <span data-ttu-id="deae2-122">次の表は、カスタム プロパティ名とそれらに対応する表示名を示します。</span><span class="sxs-lookup"><span data-stu-id="deae2-122">The following table shows the custom property names and how they correspond to the display names.</span></span>  
  
|<span data-ttu-id="deae2-123">送信カスタム プロパティ名</span><span class="sxs-lookup"><span data-stu-id="deae2-123">Send Custom Property Name</span></span>|<span data-ttu-id="deae2-124">表示名</span><span class="sxs-lookup"><span data-stu-id="deae2-124">Display Name</span></span>|  
|-------------------------------|------------------|  
|<span data-ttu-id="deae2-125">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="deae2-125">**DotNetAssemblyStrongName**</span></span>|<span data-ttu-id="deae2-126">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="deae2-126">**DotNetAssemblyStrongName**</span></span>|  
|<span data-ttu-id="deae2-127">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="deae2-127">**DotNetClassName**</span></span>|<span data-ttu-id="deae2-128">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="deae2-128">**DotNetClassName**</span></span>|  
|<span data-ttu-id="deae2-129">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="deae2-129">**InitializationData**</span></span>|<span data-ttu-id="deae2-130">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="deae2-130">**InitializationData**</span></span>|  
|<span data-ttu-id="deae2-131">**TransportLocationUri**</span><span class="sxs-lookup"><span data-stu-id="deae2-131">**TransportLocationUri**</span></span>|<span data-ttu-id="deae2-132">該当なし。</span><span class="sxs-lookup"><span data-stu-id="deae2-132">Not applicable.</span></span>|  
  
 <span data-ttu-id="deae2-133">すべてのプロパティは文字列値です。</span><span class="sxs-lookup"><span data-stu-id="deae2-133">All of the properties are string values.</span></span> <span data-ttu-id="deae2-134">TransportLocationUri プロパティの値は、アセンブリ名とクラス名から構築されます。</span><span class="sxs-lookup"><span data-stu-id="deae2-134">You construct the value of the TransportLocationUri property from the assembly name and the class name.</span></span> <span data-ttu-id="deae2-135">URI の値は OPS://\<DotNetAssemblyStrongName >/\<DotNetClassName > プレース ホルダーは、対応するカスタム プロパティの値を置き換えです。</span><span class="sxs-lookup"><span data-stu-id="deae2-135">The URI has the value OPS://\<DotNetAssemblyStrongName>/\<DotNetClassName> where the placeholders are replaced by the values of the corresponding custom property.</span></span>  
  
 <span data-ttu-id="deae2-136">コードからポートを作成する方法の詳細については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="deae2-136">For information about creating ports from code, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deae2-137">参照</span><span class="sxs-lookup"><span data-stu-id="deae2-137">See Also</span></span>  
 [<span data-ttu-id="deae2-138">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="deae2-138">The Ops Adapter</span></span>](../core/the-ops-adapter.md)