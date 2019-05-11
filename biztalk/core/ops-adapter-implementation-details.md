---
title: Ops アダプター実装の詳細 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, Ops adapters
- Ops adapters, batching
- Ops adapters, creating ports
- Ops adapters, implementing
- Ops adapters, transaction handling
- process management solution tutorial, Ops adapters
ms.assetid: dbca31ca-c3d8-4a25-9356-ef4bbab671e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e890b7413726993dd28aa21dec0f13e92f90f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323428"
---
# <a name="ops-adapter-implementation-details"></a><span data-ttu-id="8e712-102">Ops アダプター実装の詳細</span><span class="sxs-lookup"><span data-stu-id="8e712-102">Ops Adapter Implementation Details</span></span>
<span data-ttu-id="8e712-103">アダプターを変更する場合は、Ops アダプタの次の側面を理解する役に立つ場合がありますまたはプログラムによって構成します。</span><span class="sxs-lookup"><span data-stu-id="8e712-103">You may find it useful to understand the following aspects of the Ops adapter when modifying the adapter or configuring it programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e712-104">Ops アダプタは、アダプター フレームワークを使用して構築されています。</span><span class="sxs-lookup"><span data-stu-id="8e712-104">The Ops Adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="8e712-105">アダプタ フレームワークを構築する方法については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e712-105">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="batch-processing"></a><span data-ttu-id="8e712-106">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="8e712-106">Batch Processing</span></span>  
 <span data-ttu-id="8e712-107">ように各メッセージを個別に処理し、一度に 1 つだけの順序でロールバック操作が完了したら、アダプターは一度に 1 つのメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="8e712-107">The adapter processes one message at a time so that each message is processed separately, and rollback operations are done on only one order at a time.</span></span> <span data-ttu-id="8e712-108">アダプターは、一度に 1 つのメッセージを処理するが、バッチ サイズが 1 つのバッチ処理を使用してそうです。</span><span class="sxs-lookup"><span data-stu-id="8e712-108">Although the adapter processes one message at a time, it does so using batching with a batch size of one.</span></span> <span data-ttu-id="8e712-109">これにより、アダプターはメッセージをバッチ処理を変更しやすくします。</span><span class="sxs-lookup"><span data-stu-id="8e712-109">This makes it easier to modify the adapter to handle messages in batches.</span></span>  
  
## <a name="transaction-handling"></a><span data-ttu-id="8e712-110">トランザクションの処理</span><span class="sxs-lookup"><span data-stu-id="8e712-110">Transaction Handling</span></span>  
 <span data-ttu-id="8e712-111">アダプターは、Microsoft によって提供されるトランザクション機能を使用して[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] **System.Transactions**機能します。</span><span class="sxs-lookup"><span data-stu-id="8e712-111">The adapter uses the transaction facilities provided by the Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]**System.Transactions** facilities.</span></span> <span data-ttu-id="8e712-112">新しいアダプターを作成**CommittableTransaction**でこれを使用して、 **TransactionScope**します。</span><span class="sxs-lookup"><span data-stu-id="8e712-112">The adapter creates a new **CommittableTransaction** and uses it with a **TransactionScope**.</span></span> <span data-ttu-id="8e712-113">アダプターが、**初期化**と**Execute**このトランザクションのコンテキスト内のメソッド。</span><span class="sxs-lookup"><span data-stu-id="8e712-113">The adapter calls the **Initialize** and **Execute** methods within the context of this transaction.</span></span> <span data-ttu-id="8e712-114">呼び出されたアセンブリ内のコードを使用して、トランザクションに参加できる**Transaction.Current**トランザクション コンテキストを取得する静的メソッド。</span><span class="sxs-lookup"><span data-stu-id="8e712-114">Code in the called assembly can participate in the transaction by using **Transaction.Current** static method to get the transaction context.</span></span> <span data-ttu-id="8e712-115">サンプル エラー ハンドラを行わないのは、この機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="8e712-115">The sample error handler does not make use of this facility.</span></span> <span data-ttu-id="8e712-116">詳細については**System.Transactions**、.NET Framework クラス ライブラリのバージョンで"System.Transactions Namespace"を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e712-116">For more information about **System.Transactions**, see "System.Transactions Namespace" in the .NET Framework Class Library version.</span></span>  
  
## <a name="handling-data-other-than-error-reports"></a><span data-ttu-id="8e712-117">エラー報告以外のデータの処理</span><span class="sxs-lookup"><span data-stu-id="8e712-117">Handling Data Other Than Error Reports</span></span>  
 <span data-ttu-id="8e712-118">ソリューションでは、アダプターは、新しいエラー報告機能からエラー レポート メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="8e712-118">In the solution, the adapter handles error report messages from the new error reporting feature.</span></span> <span data-ttu-id="8e712-119">ただし、ため、 **Execute**メソッドは、唯一の引数としてバイト配列を受け取りを明示的に制限に渡されるものを使用する必要がある、 **Execute**メソッド。</span><span class="sxs-lookup"><span data-stu-id="8e712-119">However, because the **Execute** method takes a byte array as its only argument, there is nothing that specifically limits what can be passed to the **Execute** method.</span></span>  
  
## <a name="using-the-adapter-when-creating-ports-programmatically"></a><span data-ttu-id="8e712-120">ポートをプログラムで作成するときに、アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e712-120">Using the Adapter When Creating Ports Programmatically</span></span>  
 <span data-ttu-id="8e712-121">コードからポートを作成するときに、アダプターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8e712-121">You can specify the adapter when creating ports from code.</span></span> <span data-ttu-id="8e712-122">次の表は、カスタム プロパティ名と表示名に対応する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8e712-122">The following table shows the custom property names and how they correspond to the display names.</span></span>  
  
|<span data-ttu-id="8e712-123">カスタム プロパティの名前を送信します。</span><span class="sxs-lookup"><span data-stu-id="8e712-123">Send Custom Property Name</span></span>|<span data-ttu-id="8e712-124">表示名</span><span class="sxs-lookup"><span data-stu-id="8e712-124">Display Name</span></span>|  
|-------------------------------|------------------|  
|<span data-ttu-id="8e712-125">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="8e712-125">**DotNetAssemblyStrongName**</span></span>|<span data-ttu-id="8e712-126">**DotNetAssemblyStrongName**</span><span class="sxs-lookup"><span data-stu-id="8e712-126">**DotNetAssemblyStrongName**</span></span>|  
|<span data-ttu-id="8e712-127">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="8e712-127">**DotNetClassName**</span></span>|<span data-ttu-id="8e712-128">**DotNetClassName**</span><span class="sxs-lookup"><span data-stu-id="8e712-128">**DotNetClassName**</span></span>|  
|<span data-ttu-id="8e712-129">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="8e712-129">**InitializationData**</span></span>|<span data-ttu-id="8e712-130">**InitializationData**</span><span class="sxs-lookup"><span data-stu-id="8e712-130">**InitializationData**</span></span>|  
|<span data-ttu-id="8e712-131">**TransportLocationUri**</span><span class="sxs-lookup"><span data-stu-id="8e712-131">**TransportLocationUri**</span></span>|<span data-ttu-id="8e712-132">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8e712-132">Not applicable.</span></span>|  
  
 <span data-ttu-id="8e712-133">すべてのプロパティは、文字列値です。</span><span class="sxs-lookup"><span data-stu-id="8e712-133">All of the properties are string values.</span></span> <span data-ttu-id="8e712-134">アセンブリ名とクラス名から TransportLocationUri プロパティの値を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e712-134">You construct the value of the TransportLocationUri property from the assembly name and the class name.</span></span> <span data-ttu-id="8e712-135">URI が、値は OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\>プレース ホルダーは対応するカスタム プロパティの値を置き換えです。</span><span class="sxs-lookup"><span data-stu-id="8e712-135">The URI has the value OPS://\<DotNetAssemblyStrongName\>/\<DotNetClassName\> where the placeholders are replaced by the values of the corresponding custom property.</span></span>  
  
 <span data-ttu-id="8e712-136">コードからポートを作成する方法については、次を参照してください。[コードから MSMQ 受信場所の作成と送信ポートを方法](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e712-136">For information about creating ports from code, see [How to Create MSMQ Receive Locations and Send Ports from Code](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e712-137">参照</span><span class="sxs-lookup"><span data-stu-id="8e712-137">See Also</span></span>  
 [<span data-ttu-id="8e712-138">Ops アダプター</span><span class="sxs-lookup"><span data-stu-id="8e712-138">The Ops Adapter</span></span>](../core/the-ops-adapter.md)