---
title: WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションの構成 |Microsoft Docs
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
ms.openlocfilehash: 98ad767d0da4816e1d0c0658db898ebec282ffa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363609"
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="059a3-102">WCF LOB Adapter SDK のディスパッチャーによって開始されたか、アダプターによって開始されたトランザクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="059a3-102">Configure dispatcher-initiated or adapter-initiated transactions with the WCF LOB Adapter SDK</span></span>
## <a name="inbound-transactions"></a><span data-ttu-id="059a3-103">トランザクションを受信します。</span><span class="sxs-lookup"><span data-stu-id="059a3-103">Inbound Transactions</span></span>  
 <span data-ttu-id="059a3-104">受信操作でトランザクションを実装する 2 つの方法がある: ディスパッチャー開始またはアダプターが開始します。</span><span class="sxs-lookup"><span data-stu-id="059a3-104">There are two methods of implementing transactions with inbound operations: dispatcher-initiated or adapter-initiated.</span></span> <span data-ttu-id="059a3-105">アダプターの要件をディクテーションするメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a3-105">The requirements of the adapter dictate which method should be used.</span></span> <span data-ttu-id="059a3-106">値、`SupportsTransactedInbound`プロパティは、アダプターで実装するトランザクションの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="059a3-106">The value of the `SupportsTransactedInbound` property indicates which type of transaction your adapter will implement.</span></span>  
  
 <span data-ttu-id="059a3-107">次の表は、ディスパッチャー開始を比較とアダプター開始トランザクションとします。</span><span class="sxs-lookup"><span data-stu-id="059a3-107">The following table compares dispatcher-initiated with adapter-initiated transactions.</span></span>  
  
|<span data-ttu-id="059a3-108">SupportsTransactedInbound</span><span class="sxs-lookup"><span data-stu-id="059a3-108">SupportsTransactedInbound</span></span>|<span data-ttu-id="059a3-109">トランザクションの動作</span><span class="sxs-lookup"><span data-stu-id="059a3-109">Transactional Behavior</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="059a3-110">True (ディスパッチャー開始)</span><span class="sxs-lookup"><span data-stu-id="059a3-110">True (dispatcher-initiated)</span></span>|<span data-ttu-id="059a3-111">-TryReceive は、常にトランザクションのコンテキスト内で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="059a3-111">-   TryReceive will always be called within the context of a transaction.</span></span><br /><span data-ttu-id="059a3-112">にサービスの実装にメッセージが返された後、トランザクションはコミットされます。</span><span class="sxs-lookup"><span data-stu-id="059a3-112">-   The transaction will be committed after the message is returned to the service implementation.</span></span><br /><span data-ttu-id="059a3-113">-新しいトランザクションが作成されます IInputChannel.Receive 呼び出しごとにします。</span><span class="sxs-lookup"><span data-stu-id="059a3-113">-   A new transaction will be created for each IInputChannel.Receive call.</span></span> <span data-ttu-id="059a3-114">受信トランザクションを複数にまたがるはサービス ホストとアダプターは開発者向けに依存します。</span><span class="sxs-lookup"><span data-stu-id="059a3-114">Spanning a transaction across multiple receives is dependent on the service host and not the adapter developer.</span></span> <span data-ttu-id="059a3-115">**注:** ホストが受け入れる必要がある場合は、ホストは、WCF ディスパッチャー (サービスのホスト) を使用していないと、チャネル レベルのプログラミングを使用して、代わりに、 **TransactedReceiveEnabled** WCF のバインドのプロパティと、すべての呼び出しを行う必要がありますトランザクション内で IInputChannel.Receive します。</span><span class="sxs-lookup"><span data-stu-id="059a3-115">**Note:**  If the host is not using the WCF dispatcher (service host) and is instead using channel level programming, the host should honor the **TransactedReceiveEnabled** property of the WCF binding, and should make all calls to IInputChannel.Receive within a transaction.</span></span> <span data-ttu-id="059a3-116">**注:** アダプターがディスパッチャーによって開始されたトランザクションを使用、Biztalk Server と共に使用される場合は、設定、`SupportedInboundChannels`プロパティを`SupportedInboundChannels.IInputChannel`をアダプターがのみ一方向チャネルをサポートしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="059a3-116">**Note:**  If the adapter uses dispatcher-initiated transactions, and is used with Biztalk Server, set the `SupportedInboundChannels` property to `SupportedInboundChannels.IInputChannel` to indicate that the adapter only supports one-way channels.</span></span> <span data-ttu-id="059a3-117">これが設定されていない場合は、BizTalk Server は双方向チャネルを使用しようとします。</span><span class="sxs-lookup"><span data-stu-id="059a3-117">If this is not set, BizTalk Server will attempt to use two-way channels.</span></span>|  
|<span data-ttu-id="059a3-118">False (アダプターが開始した)</span><span class="sxs-lookup"><span data-stu-id="059a3-118">False (adapter-initiated)</span></span>|<span data-ttu-id="059a3-119">アダプター開発者は、アダプター内でのトランザクション ロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a3-119">-   The adapter developer must implement transaction logic within the adapter.</span></span><br /><span data-ttu-id="059a3-120">-アダプター開始トランザクションは、双方向メッセージング (応答チャネル) モデルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="059a3-120">-   Adapter-initiated transactions can only work with a two-way messaging (Reply Channel) model.</span></span><br /><span data-ttu-id="059a3-121">-1 つのトランザクションは、ディスパッチャーによって各メッセージに依存する複製が作成されますので、複数のメッセージをまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="059a3-121">-   One transaction can span multiple messages, since dependent clones will be created for each message by the dispatcher.</span></span>|  
  
### <a name="dispatcher-initiated-transactions"></a><span data-ttu-id="059a3-122">ディスパッチャー開始トランザクション</span><span class="sxs-lookup"><span data-stu-id="059a3-122">Dispatcher-initiated Transactions</span></span>  
 <span data-ttu-id="059a3-123">SupportsTransactedInbound に設定すると**true**、WCF ディスパッチャーは、自動的にトランザクションを作成を呼び出すときに、 **TryReceive**アダプターのメソッドのトランザクションをコミットし、後のメッセージには、サービスの実装が返されます。</span><span class="sxs-lookup"><span data-stu-id="059a3-123">When SupportsTransactedInbound is set to **true**, the WCF dispatcher will then automatically create a transaction when calling the **TryReceive** method of the adapter, and will commit the transaction after the message is returned to the service implementation.</span></span> <span data-ttu-id="059a3-124">アダプターの設定以外の任意の特定のトランザクション コード実装する必要はありません、`SupportsTransactedInbound`プロパティを**true**します。</span><span class="sxs-lookup"><span data-stu-id="059a3-124">This does not require any specific transactional code implementation within the adapter other than setting the `SupportsTransactedInbound` property to **true**.</span></span> <span data-ttu-id="059a3-125">ただし、これは、WCF ディスパッチャーを使用するサービス ホスト内でホストされるアダプターに依存し、チャネル レベルのプログラミングを使用している場合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="059a3-125">However, this is dependent on the adapter being hosted within a service host that uses the WCF dispatcher, and will not occur if you are using channel level programming.</span></span> <span data-ttu-id="059a3-126">チャネル レベルのプログラミングを使用する場合、ホストが受け入れる必要がある、`TransactedReceiveEnabled`プロパティの WCF バインドと、トランザクション内で受信する呼び出しはすべて作成します。</span><span class="sxs-lookup"><span data-stu-id="059a3-126">When using channel level programming, the host should honor the `TransactedReceiveEnabled` property of the WCF binding and make all calls to Receive within a transaction.</span></span>  
  
 <span data-ttu-id="059a3-127">トランザクションを作成し、チャネル レベルのプログラミングを使用して、アダプターを呼び出すクライアントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="059a3-127">The following demonstrates a client creating a transaction, and then calling the adapter using channel level programming.</span></span>  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a><span data-ttu-id="059a3-128">アダプターによって開始されたトランザクション</span><span class="sxs-lookup"><span data-stu-id="059a3-128">Adapter-initiated Transactions</span></span>  
 <span data-ttu-id="059a3-129">ときに、`SupportsTransactedInbound`プロパティに設定されて**false**、新しいトランザクションを作成してアダプター コード内でトランザクションのサポートを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a3-129">When hte `SupportsTransactedInbound` property is set to **false**, transaction support must be implemented within the adapter code by creating a new transaction.</span></span> <span data-ttu-id="059a3-130">メッセージを返す前に**TryReceive**、トランザクションは、呼び出すことによって、メッセージに添付する必要があります、**設定**のメソッド、 **TransactionMessageProperty**クラス。</span><span class="sxs-lookup"><span data-stu-id="059a3-130">Before returning a message from **TryReceive**, the transaction must be attached to the message by calling the **Set** method of the **TransactionMessageProperty** class.</span></span> <span data-ttu-id="059a3-131">この実装は、アダプター コード内の明示的なトランザクションのサポートが必要ですし、アダプターのトランザクションの動作をより細かく制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="059a3-131">This implementation requires explicit transaction support in the adapter code, and provides greater control over the transactional behavior of the adapter.</span></span>  
  
 <span data-ttu-id="059a3-132">依存トランザクションを作成し、クライアントに返される前に、メッセージに添付するこれを次に示します。</span><span class="sxs-lookup"><span data-stu-id="059a3-132">The following demonstrates creating a dependent transaction, and attaching this to the message before it is returned to the client.</span></span>  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a><span data-ttu-id="059a3-133">参照</span><span class="sxs-lookup"><span data-stu-id="059a3-133">See Also</span></span>  
 [<span data-ttu-id="059a3-134">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="059a3-134">Development Activities</span></span>](../../esb-toolkit/development-activities.md)