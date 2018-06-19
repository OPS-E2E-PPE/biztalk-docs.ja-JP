---
title: WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8105b4b6f8eb77d68471faf9b702419f6a1f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225762"
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="20e78-102">WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="20e78-102">Configure dispatcher-initiated or adapter-initiated transactions with the WCF LOB Adapter SDK</span></span>
## <a name="inbound-transactions"></a><span data-ttu-id="20e78-103">受信トランザクション</span><span class="sxs-lookup"><span data-stu-id="20e78-103">Inbound Transactions</span></span>  
 <span data-ttu-id="20e78-104">受信操作でトランザクションを実装する 2 つの方法がある: ディスパッチャーによって開始されるか、アダプターが開始します。</span><span class="sxs-lookup"><span data-stu-id="20e78-104">There are two methods of implementing transactions with inbound operations: dispatcher-initiated or adapter-initiated.</span></span> <span data-ttu-id="20e78-105">アダプターの要件をディクテーションするメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e78-105">The requirements of the adapter dictate which method should be used.</span></span> <span data-ttu-id="20e78-106">値、`SupportsTransactedInbound`プロパティは、アダプターで実装するトランザクションの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="20e78-106">The value of the `SupportsTransactedInbound` property indicates which type of transaction your adapter will implement.</span></span>  
  
 <span data-ttu-id="20e78-107">次の表と比較してディスパッチャーによって開始されたアダプターで開始されたトランザクション。</span><span class="sxs-lookup"><span data-stu-id="20e78-107">The following table compares dispatcher-initiated with adapter-initiated transactions.</span></span>  
  
|<span data-ttu-id="20e78-108">SupportsTransactedInbound</span><span class="sxs-lookup"><span data-stu-id="20e78-108">SupportsTransactedInbound</span></span>|<span data-ttu-id="20e78-109">トランザクションの動作</span><span class="sxs-lookup"><span data-stu-id="20e78-109">Transactional Behavior</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="20e78-110">True (ディスパッチャーによって開始される)</span><span class="sxs-lookup"><span data-stu-id="20e78-110">True (dispatcher-initiated)</span></span>|<span data-ttu-id="20e78-111">-TryReceive は、トランザクションのコンテキスト内で常に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="20e78-111">-   TryReceive will always be called within the context of a transaction.</span></span><br /><span data-ttu-id="20e78-112">にサービスの実装にメッセージが返された後、トランザクションはコミットされます。</span><span class="sxs-lookup"><span data-stu-id="20e78-112">-   The transaction will be committed after the message is returned to the service implementation.</span></span><br /><span data-ttu-id="20e78-113">は、新しいトランザクションが作成されます IInputChannel.Receive 呼び出しごとにします。</span><span class="sxs-lookup"><span data-stu-id="20e78-113">-   A new transaction will be created for each IInputChannel.Receive call.</span></span> <span data-ttu-id="20e78-114">受信トランザクションを複数にまたがるよう、サービス ホストおよびアダプター開発者ではなくに依存します。</span><span class="sxs-lookup"><span data-stu-id="20e78-114">Spanning a transaction across multiple receives is dependent on the service host and not the adapter developer.</span></span> <span data-ttu-id="20e78-115">**注:** ホストが受け入れる必要がある場合は、ホストは、WCF ディスパッチャー (サービスのホスト) が使用されていないと、チャネル レベルのプログラミングを使用する代わりには、 **TransactedReceiveEnabled** WCF バインドのプロパティと、すべてで行う必要がありますトランザクション内で IInputChannel.Receive への呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="20e78-115">**Note:**  If the host is not using the WCF dispatcher (service host) and is instead using channel level programming, the host should honor the **TransactedReceiveEnabled** property of the WCF binding, and should make all calls to IInputChannel.Receive within a transaction.</span></span> <span data-ttu-id="20e78-116">**注:** 場合は、アダプターは、ディスパッチャーによって開始されたトランザクションを使用し、Biztalk Server で使用されます、設定、`SupportedInboundChannels`プロパティを`SupportedInboundChannels.IInputChannel`アダプターがのみ一方向チャネルをサポートしていることを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="20e78-116">**Note:**  If the adapter uses dispatcher-initiated transactions, and is used with Biztalk Server, set the `SupportedInboundChannels` property to `SupportedInboundChannels.IInputChannel` to indicate that the adapter only supports one-way channels.</span></span> <span data-ttu-id="20e78-117">これが設定されていない場合、BizTalk Server は双方向チャネルを使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="20e78-117">If this is not set, BizTalk Server will attempt to use two-way channels.</span></span>|  
|<span data-ttu-id="20e78-118">False (アダプターによって開始される)</span><span class="sxs-lookup"><span data-stu-id="20e78-118">False (adapter-initiated)</span></span>|<span data-ttu-id="20e78-119">-アダプター開発者は、アダプター内のトランザクション ロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e78-119">-   The adapter developer must implement transaction logic within the adapter.</span></span><br /><span data-ttu-id="20e78-120">-アダプターで開始されたトランザクションは、双方向のメッセージング (応答チャネル) モデルでのみ操作できます。</span><span class="sxs-lookup"><span data-stu-id="20e78-120">-   Adapter-initiated transactions can only work with a two-way messaging (Reply Channel) model.</span></span><br /><span data-ttu-id="20e78-121">-1 つのトランザクションは、依存クローンは、ディスパッチャーがメッセージごとに作成されますので、複数のメッセージをまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="20e78-121">-   One transaction can span multiple messages, since dependent clones will be created for each message by the dispatcher.</span></span>|  
  
### <a name="dispatcher-initiated-transactions"></a><span data-ttu-id="20e78-122">ディスパッチャーで開始されたトランザクション</span><span class="sxs-lookup"><span data-stu-id="20e78-122">Dispatcher-initiated Transactions</span></span>  
 <span data-ttu-id="20e78-123">SupportsTransactedInbound に設定すると**true**、WCF ディスパッチャーは、自動的にトランザクションを作成の呼び出し時に、 **TryReceive**アダプターのメソッドのトランザクションをコミットし、後、サービス実装では、メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="20e78-123">When SupportsTransactedInbound is set to **true**, the WCF dispatcher will then automatically create a transaction when calling the **TryReceive** method of the adapter, and will commit the transaction after the message is returned to the service implementation.</span></span> <span data-ttu-id="20e78-124">設定する以外、アダプター内の任意の特定のトランザクション コード実装しないため、`SupportsTransactedInbound`プロパティを**true**です。</span><span class="sxs-lookup"><span data-stu-id="20e78-124">This does not require any specific transactional code implementation within the adapter other than setting the `SupportsTransactedInbound` property to **true**.</span></span> <span data-ttu-id="20e78-125">ただし、これは、WCF ディスパッチャーを使用するサービス ホスト内でホストされるアダプターに依存、チャネル レベルのプログラミングを使用している場合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="20e78-125">However, this is dependent on the adapter being hosted within a service host that uses the WCF dispatcher, and will not occur if you are using channel level programming.</span></span> <span data-ttu-id="20e78-126">ホストが受け入れる必要があるチャネル レベルのプログラミングを使用する場合、`TransactedReceiveEnabled`プロパティの WCF バインドと、トランザクション内で受信するすべての呼び出しを作成します。</span><span class="sxs-lookup"><span data-stu-id="20e78-126">When using channel level programming, the host should honor the `TransactedReceiveEnabled` property of the WCF binding and make all calls to Receive within a transaction.</span></span>  
  
 <span data-ttu-id="20e78-127">トランザクションを作成し、チャネル レベルのプログラミングを使用してアダプターを呼び出すクライアントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e78-127">The following demonstrates a client creating a transaction, and then calling the adapter using channel level programming.</span></span>  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a><span data-ttu-id="20e78-128">アダプターで開始されたトランザクション</span><span class="sxs-lookup"><span data-stu-id="20e78-128">Adapter-initiated Transactions</span></span>  
 <span data-ttu-id="20e78-129">ときに、`SupportsTransactedInbound`プロパティに設定されている**false**、新しいトランザクションを作成することで、アダプター コード内でトランザクションのサポートを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20e78-129">When hte `SupportsTransactedInbound` property is set to **false**, transaction support must be implemented within the adapter code by creating a new transaction.</span></span> <span data-ttu-id="20e78-130">メッセージを返す前に**TryReceive**、トランザクションは、呼び出すことによって、メッセージに添付する必要があります、**設定**のメソッド、 **TransactionMessageProperty**クラスです。</span><span class="sxs-lookup"><span data-stu-id="20e78-130">Before returning a message from **TryReceive**, the transaction must be attached to the message by calling the **Set** method of the **TransactionMessageProperty** class.</span></span> <span data-ttu-id="20e78-131">この実装では、アダプター コード内の明示的なトランザクションのサポートを必要とし、アダプターのトランザクションの動作をより細かく制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="20e78-131">This implementation requires explicit transaction support in the adapter code, and provides greater control over the transactional behavior of the adapter.</span></span>  
  
 <span data-ttu-id="20e78-132">依存のトランザクションを作成して、クライアントに返される前に、メッセージに添付するこれを次に示します。</span><span class="sxs-lookup"><span data-stu-id="20e78-132">The following demonstrates creating a dependent transaction, and attaching this to the message before it is returned to the client.</span></span>  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a><span data-ttu-id="20e78-133">参照</span><span class="sxs-lookup"><span data-stu-id="20e78-133">See Also</span></span>  
 [<span data-ttu-id="20e78-134">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="20e78-134">Development Activities</span></span>](../../esb-toolkit/development-activities.md)