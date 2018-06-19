---
title: 'ソリューションのインストルメント化: API の使用方法の詳細な手順 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e027ab-1927-4905-8970-8061ac55d591
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73c59ab28c228c779fd9e6e84d836b87415d6386
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258234"
---
# <a name="instrumenting-a-solution-step-by-step-api-usage"></a><span data-ttu-id="0253d-102">ソリューションのインストルメント化: API の使用方法の詳細な手順</span><span class="sxs-lookup"><span data-stu-id="0253d-102">Instrumenting a Solution: Step-by-Step API Usage</span></span>
<span data-ttu-id="0253d-103">このトピックでは、主要な BAM API クラスを使用してアプリケーションをインストルメント化する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="0253d-103">This topic describes how to instrument an application using the key BAM API class.</span></span> <span data-ttu-id="0253d-104">以下のコードは、定数と、アプリケーションのインストルメント化に必要な最小限のコードを使用して、サンプル コードを単純化したものです。</span><span class="sxs-lookup"><span data-stu-id="0253d-104">In the following code snippets we have simplified the sample code by using constants and by using the minimum code necessary to instrument an application.</span></span>  
  
 <span data-ttu-id="0253d-105">次のコード スニペットでは、 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) オブジェクト、具体的には、 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)を新規に作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0253d-105">The following code snippet demonstrates how you create a new [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object, specifically a [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx).</span></span> <span data-ttu-id="0253d-106">このコードでは、最初のパラメーターで BAM プライマリ インポート データベースのデータ ストアへの接続文字列を指定し、2 番目のパラメーターでイベントがデータ ストアに書き込まれる頻度を指定しています。</span><span class="sxs-lookup"><span data-stu-id="0253d-106">In this snippet, the first parameter specifies the connection string to the data store of the BAM Primary Import database and the second parameter specifies the frequency with which the events are written to the data store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0253d-107">BAM では、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データ ストアへの接続のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0253d-107">BAM supports connections only to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] data stores.</span></span> <span data-ttu-id="0253d-108">このサンプルの接続文字列は、接続を確立するために必要な最低限の接続文字列を表しています。</span><span class="sxs-lookup"><span data-stu-id="0253d-108">The sample connection string represents the minimal connection string required to establish a connection.</span></span> <span data-ttu-id="0253d-109">構成によっては、接続文字列で追加のパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-109">Your configuration may require additional parameters to be specified in the connection string.</span></span>  
  
 <span data-ttu-id="0253d-110">*FlushThreshold* の値を 0 にすると、イベントが自動的に書き込まれなくなります。この場合、イベントを書き込むには Flush メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-110">A *FlushThreshold* value of 0 specifies that events are not automatically written and that you must call the Flush method to write the events.</span></span> <span data-ttu-id="0253d-111">この値を 1 にすると、イベントは発生するたびに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0253d-111">A value of one causes each event to be written when it occurs.</span></span> <span data-ttu-id="0253d-112">1 より大きい値にすると、発生したイベントの数が指定した値になるとイベントが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0253d-112">Values of greater than one specify that events are written when a batch of the specified accumulation has occurred.</span></span> <span data-ttu-id="0253d-113">この設定は、パフォーマンスの向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0253d-113">Using a value of greater than one can be useful to enhance performance.</span></span>  
  
```  
// Specify the DES connection string.  
const string connBAMPIT =  
   "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
// Write the activity update data on every call.  
int flushThreshold = 1;  
// Create a DES instance  
EventStream es =   
   new DirectEventStream(connBAMPIT, flushThreshold);  
```  
  
 <span data-ttu-id="0253d-114">[Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) オブジェクトが作成されたら、アクティビティを開始して、収集されたマイルストーンとデータでアクティビティ テーブルを更新できます。</span><span class="sxs-lookup"><span data-stu-id="0253d-114">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/Microsoft.BizTalk.Bam.EventObservation.EventStream.aspx) object has been created, you can begin the activity and start updating the activity table with the collected milestones and data.</span></span> <span data-ttu-id="0253d-115">BAM アクティビティが展開されたときに、BAM プライマリ インポート データベースに 5 つのテーブルが作成されています。</span><span class="sxs-lookup"><span data-stu-id="0253d-115">When the BAM activity was deployed, five tables were created in the BAM Primary Import database.</span></span> <span data-ttu-id="0253d-116">開発プロセスの詳細については、次を参照してください。 [BAM 開発プロセスの概要](../core/overview-of-the-bam-development-process.md)です。</span><span class="sxs-lookup"><span data-stu-id="0253d-116">For more information about the development process, see [Overview of the BAM Development Process](../core/overview-of-the-bam-development-process.md).</span></span>  
  
 <span data-ttu-id="0253d-117">[Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドを呼び出すと、bam _ PurchaseOrder_Activity テーブルにレコードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="0253d-117">Calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method adds a record to the bam_ PurchaseOrder_Activity table.</span></span> <span data-ttu-id="0253d-118">最初のパラメーターには、更新されるアクティビティの名前が含まれています。2 番目のパラメーターには、そのアクティビティの現在のインスタンスの識別子が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0253d-118">The first parameter contains the name of the activity being updated and the second parameter contains an identifier for this instance of the activity.</span></span> <span data-ttu-id="0253d-119">識別子には任意の文字列を使用できますが、アクティビティのレコードセットで一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-119">The identifier can be any string, but it must be unique in the record set for the activity.</span></span>  
  
 <span data-ttu-id="0253d-120">この時点では、レコードにデータは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0253d-120">At this point the record does not contain any data.</span></span> <span data-ttu-id="0253d-121">[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドが、キャプチャされたイベント データでレコードを更新します。</span><span class="sxs-lookup"><span data-stu-id="0253d-121">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method updates the record with the captured event data.</span></span> <span data-ttu-id="0253d-122">ここでも、アクティビティと、そのアクティビティのインスタンスの識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="0253d-122">Once again you specify an activity and the activity instance identifier.</span></span> <span data-ttu-id="0253d-123">[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドには、アクティビティで定義したデータ項目とマイルストーンの名前と値の組を渡します。</span><span class="sxs-lookup"><span data-stu-id="0253d-123">You pass the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method name value pairs of data items and milestones you defined in the activity.</span></span> <span data-ttu-id="0253d-124">たとえば、この例のアクティビティではマイルストーン MS_Received が定義されています。</span><span class="sxs-lookup"><span data-stu-id="0253d-124">For example, our activity defined a milestone MS_Received.</span></span> <span data-ttu-id="0253d-125">アクティビティが展開されたときに、このマイルストーンのための列が bam_ PurchaseOrder_Activity テーブルに作成されています。</span><span class="sxs-lookup"><span data-stu-id="0253d-125">When the activity was deployed, a column in the bam_ PurchaseOrder_Activity table was created for the milestone.</span></span> <span data-ttu-id="0253d-126">[Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドの呼び出しで MS_Received と DateTime.UtcNow という名前と値の組を指定して、注文書の受信日でアクティビティを更新します。</span><span class="sxs-lookup"><span data-stu-id="0253d-126">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) method specifies the name value pair of MS_Received and DateTime.UtcNow to update the activity with received date for the purchase order.</span></span>  
  
```  
// When a purchase order is received, you call the  
// BeginActivity method in the receive application.  
// You can then capture the event data by calling   
// the UpdateActivity method.  
es.BeginActivity ("PurchaseOrder", "PO123");  
es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
```  
  
 <span data-ttu-id="0253d-127">このサンプルでは 2 番目のアクティビティに継続します。</span><span class="sxs-lookup"><span data-stu-id="0253d-127">In this sample we continue to a second activity.</span></span> <span data-ttu-id="0253d-128">Continuation の詳細については、次を参照してください。[アクティビティ Continuation](../core/activity-continuation.md)です。</span><span class="sxs-lookup"><span data-stu-id="0253d-128">For more information about continuations, see [Activity Continuation](../core/activity-continuation.md).</span></span>  
  
 <span data-ttu-id="0253d-129">他のインストルメント アプリケーションが PurchaseOrder アクティビティを更新できるようにするには、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="0253d-129">To enable other instrumented applications to update the PurchaseOrder activity, you include a call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method.</span></span> <span data-ttu-id="0253d-130">この呼び出しでは、他のアプリケーションが関与できるアクティビティ、追跡するアクティビティのインスタンスの識別子、および他のアプリケーションがアクティビティを更新するために使用する継続トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0253d-130">The call specifies the activity to which other applications can contribute, the identifier for the instance of the activity being tracked, and the continuation token that other applications will use to update the activity.</span></span> <span data-ttu-id="0253d-131">継続の状態を追跡するために、bam_ PurchaseOrder_continuations テーブルにレコードが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0253d-131">A record is written to the bam_ PurchaseOrder_continuations table to track the status of the continuation.</span></span> <span data-ttu-id="0253d-132">アクティビティが他のプロセスに継続される場合、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが一意の継続トークンで呼び出されるたびにレコードが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0253d-132">If the activity continues to other processes, a record is written for each call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method with a unique continuation token.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0253d-133">継続のシナリオでは、すべてのコード セグメントに [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドの呼び出しが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-133">Every code segment in a continuation scenario must have its own [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method call.</span></span> <span data-ttu-id="0253d-134">そうでないと、ぶら下がり/孤立状態のアクティビティ レコードが生じます。</span><span class="sxs-lookup"><span data-stu-id="0253d-134">Failing to do so will result in a dangling/orphaned activity record.</span></span>  
>   
>  <span data-ttu-id="0253d-135">ただし、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドがあるのは最初のセグメント (実際のアクティビティ ID を使用するセグメント) だけです。その他のセグメント (それぞれの一意のトークン ID を使用するセグメント) では [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="0253d-135">However, only the first segment (that uses the actual activity ID) has the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method; all the other segments (that use their own unique token ID) must not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span>  
  
 <span data-ttu-id="0253d-136">[Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが呼び出されると、他のコンポーネントが PurchaseOrder アクティビティを更新できるようになります。その際には、アクティビティ ID の代わりに継続トークンを指定して、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0253d-136">After the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, other components can update the purchase order activity using [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the continuation token instead of the activity ID.</span></span> <span data-ttu-id="0253d-137">他のコンポーネントでは、それぞれのタスクが完了したら、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) を継続トークンと共に呼び出して、イベントがこれ以上発生しないことを BAM インフラストラクチャに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-137">When the other components have completed their tasks, each of the components must call [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) with the continuation token to inform the BAM infrastructure that no more events are expected.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0253d-138">[Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) メソッドが呼び出された後に、アクティビティが継続されているプロセスで [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドが継続トークンと共に呼び出されないと、アクティビティが孤立する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-138">Once the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method is called, it is possible for an activity to become orphaned if the process in which the activity is continued never calls an [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method with the continuation token.</span></span>  
  
```  
// Continue the activity to the next process that has been  
// instrumented to handle the continuation.  
es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
```  
  
 <span data-ttu-id="0253d-139">最後に、アクティビティ名とアクティビティ識別子を指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドを呼び出して、アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="0253d-139">Finally, the activity is finalized by calling the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the activity name and the activity identifier.</span></span> <span data-ttu-id="0253d-140">終了されていない継続がなければ、アクティビティが bam_ PurchaseOrder _completed テーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="0253d-140">If there are no unfinished continuations, the activity is moved to the bam_ PurchaseOrder _completed table.</span></span> <span data-ttu-id="0253d-141">継続アクティビティを完了しないとアクティビティが孤立する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0253d-141">It is possible for activities to become orphaned if continuation activities fail to complete.</span></span>  
  
```  
// Activity from this segment (PO submission) is completed  
es.EndActivity("PurchaseOrder", “PO123”);  
```  
  
 <span data-ttu-id="0253d-142">アクティビティが別のプロセスに継続されると、アクティビティ テーブルを更新する際にアクティビティ名と継続トークン ( [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) メソッドの呼び出しで宣言される) を指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) を呼び出すようにアプリケーションがインストルメント化されます。</span><span class="sxs-lookup"><span data-stu-id="0253d-142">When the activity continues to separate process, the application is instrumented to update the activity table by calling [Microsoft.BizTalk.Bam.EventObservation.EventStream.UpdateActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.updateactivity.aspx) specifying the activity name and the continuation token declared in the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EnableContinuation](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.EnableContinuation.aspx) method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0253d-143">継続されたアクティビティを処理するプロセスでは、 [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドは呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="0253d-143">The process handling the continued activity does not call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method.</span></span> <span data-ttu-id="0253d-144">[Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) メソッドは、BAM プライマリ インポート データベースのテーブルを作成することによってアクティビティのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0253d-144">The [Microsoft.BizTalk.Bam.EventObservation.EventStream.BeginActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.beginactivity.aspx) method creates an instance of the activity by creating the tables in the BAM Primary Import database.</span></span> <span data-ttu-id="0253d-145">アクティビティの継続先プロセスでは、既に存在するアクティビティのインスタンスを更新します。</span><span class="sxs-lookup"><span data-stu-id="0253d-145">The process to which the activity is continued is updating the instance of the already existing activity.</span></span>  
  
```  
// update when the order is approved  
es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                    DateTime.UtcNow, "T_Product", "Widget");  
  
// update when the product is ready for shipment  
es.UpdateActivity ("PurchaseOrder", “AP123”,  
                   "MS_Ready", DateTime.UtcNow);  
```  
  
 <span data-ttu-id="0253d-146">このサンプルのワークフローの一部では、コードで参照が指定されています。この場合の参照は、関連アクティビティという特別な種類の参照です。</span><span class="sxs-lookup"><span data-stu-id="0253d-146">Part of the workflow for this sample the code specifies a reference, in this case a specific type of reference - a related activity.</span></span> <span data-ttu-id="0253d-147">関連アクティビティを指定すると、プライマリ アクティビティから、BAM ポータルでそのアクティビティを表示するユーザーにとって関心のある他のアクティビティに、リンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0253d-147">By specifying a related activity you create a link from your primary activity to other activities that are of interest to a user viewing the activity in the BAM portal.</span></span>  
  
 <span data-ttu-id="0253d-148">[Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) メソッドを呼び出すと、bam_ PurchaseOrder_ActiveRelationships にレコードが書き込まれて、アクティビティがリンクされます。</span><span class="sxs-lookup"><span data-stu-id="0253d-148">The call to the [Microsoft.BizTalk.Bam.EventObservation.EventStream.AddRelatedActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.addrelatedactivity.aspx) method writes a record to the bam_ PurchaseOrder_ActiveRelationships linking the activities.</span></span>  
  
```  
// These are shipped in two shipments.  
// Relates the current purchase order   
// instance to two shippings.  
// Note: only one direction  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS101”);  
es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                       "Shipping", “UPS102”);  
```  
  
 <span data-ttu-id="0253d-149">継続されたアクティビティを終了するには、終了する継続の継続トークンを指定して [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0253d-149">To end the continued activity you call the [Microsoft.BizTalk.Bam.EventObservation.EventStream.EndActivity](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.endactivity.aspx) method specifying the continuation token for the continuation that is ending.</span></span> <span data-ttu-id="0253d-150">終了されていない継続が他になければ、PurchaseOrder アクティビティが完了済みテーブルに移動されます。</span><span class="sxs-lookup"><span data-stu-id="0253d-150">If there are no other unfinished continuations, the purchase order activity is moved to the completed table.</span></span>  
  
```  
// Activity from this segment (ApprovalProcess) is completed  
es.EndActivity("PurchaseOrder", “AP123”);  
```  
  
## <a name="complete-code-sample"></a><span data-ttu-id="0253d-151">完全なコード例</span><span class="sxs-lookup"><span data-stu-id="0253d-151">Complete Code Sample</span></span>  
  
```  
//---------------------------------------------------------------------  
// File:BAMMinimalSample.cs  
//   
// Summary: Demonstrates how to instrument an application   
//using BAM APIs to track useful information.  
//  
// Sample: BAM Api Sample  
//  
//---------------------------------------------------------------------  
// This file is part of the Microsoft BizTalk Server SDK  
//  
// Copyright (c) Microsoft Corporation. All rights reserved.  
//  
// This source code is intended only as a supplement to Microsoft   
// BizTalk Server release and/or on-line documentation. See   
// these other materials for detailed information regarding Microsoft // code samples.  
//  
// THIS CODE AND INFORMATION ARE PROVIDED "AS IS" WITHOUT WARRANTY OF  
// ANY KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO // THE IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A   
// PARTICULAR PURPOSE.  
//---------------------------------------------------------------------  
// This sample requires that you add the     
// Microsoft.BizTalk.Bam.EventObservation.dll to the   
// references in the Visual Studio Solution.  
  
using System;  
using System.Text;  
using Microsoft.BizTalk.Bam.EventObservation;  
  
namespace EventStreamSample  
{  
  
    static void Main(string[] args)  
    {  
        //   
  // The following code would appear in a purchase order  
   // receipt application.  
        //  
  
        // Specify the DES connection string.  
        const string connBAMPIT =  
            "Integrated Security=SSPI;server=.;database=BAMPrimaryImport";  
  
        // Write the activity update data on every call.  
        int flushThreshold = 1;  
  
        // Create an instance of the DirectEventStream.  
        EventStream es =   
               new DirectEventStream(connBAMPIT, flushThreshold);  
  
        // When a purchase order is received, you call the  
       // BeginActivity method in the receive application.  
  // You can then capture the event data by calling   
        // the UpdateActivity method.  
        es.BeginActivity ("PurchaseOrder", "PO123");  
        es.UpdateActivity ("PurchaseOrder", "PO123",  
                    "MS_Received", DateTime.UtcNow,   
                    "T_Customer", "Joe");  
  
   // Continue the activity to the next process that has been  
   // instrumented to handle the continuation.  
        es.EnableContinuation("PurchaseOrder", “PO123”, “AP123”);  
  
        // Activity from this segment (PO submission) is completed  
        // end activity is synonymous to IsCompleted = 1  
        es.EndActivity("PurchaseOrder", “PO123”);  
  
        //  
        // The following code would typically appear in a separate   
        // application that monitors the approval process  
        // (ApprovalProcess.exe)  
        //  
  
        // update when the order is approved  
        es.UpdateActivity ("PurchaseOrder", “AP123”, "MS_Approved",  
                            DateTime.UtcNow, "T_Product", "Widget");  
  
        // update when the product is ready for shipment  
        es.UpdateActivity ("PurchaseOrder", “AP123”,  
                            "MS_Ready", DateTime.UtcNow);  
  
        // These are shipped in two shipments.  
        // Relates the current purchase order  
        // instance to two shippings.  
        // Note: only one direction  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS101”);  
        es.AddRelatedActivity ("PurchaseOrder", “AP123”,  
                                "Shipping", “UPS102”);  
  
        // Activity from this segment (ApprovalProcess) is completed  
        es.EndActivity("PurchaseOrder", “AP123”);  
  
        // In another Shipping application, two shipments with  
            ID’s UPS101 and UPS102 will be created.  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="0253d-152">参照</span><span class="sxs-lookup"><span data-stu-id="0253d-152">See Also</span></span>  
 [<span data-ttu-id="0253d-153">BAM アクティビティのイベント ストリームの実装</span><span class="sxs-lookup"><span data-stu-id="0253d-153">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)