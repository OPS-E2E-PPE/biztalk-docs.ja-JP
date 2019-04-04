---
title: 送信バッチの設定、受信トランザクションの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fbe40f8-7379-42be-b8a7-070ce8a7ce26
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44f89133cbfb7f5925f975a723b84c715180c7a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013803"
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a><span data-ttu-id="a41a9-102">受信トランザクション セットと送信パッチの関連付け</span><span class="sxs-lookup"><span data-stu-id="a41a9-102">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a41a9-103">では、バッチ処理オーケストレーションに送信された EDI トランザクション セットを、送信バッチに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-103">enables you to correlate an EDI transaction set submitted to the Batching Orchestration with an outgoing batch.</span></span> <span data-ttu-id="a41a9-104">これを行うには、バッチ処理オーケストレーションに送信されたトランザクション セットの状態レポートのエントリ (BTSInterchangeID) を、オーケストレーションの状態レポートのエントリ (ActivityID) に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-104">You do so by correlating a status reporting entry for the transaction set submitted to the Batching Orchestration (the BTSInterchangeID) to a status reporting entry for the orchestration (ActivityID).</span></span> <span data-ttu-id="a41a9-105">この関連付けは、BusinessMessageJournal BAM アクティビティのエントリを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="a41a9-105">This correlation is performed using entries in the BusinessMessageJournal BAM activity.</span></span> <span data-ttu-id="a41a9-106">これらのエントリは、バッチ処理オーケストレーションが、バッチ要素の受信時に作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-106">These entries are created by the Batching Orchestration when a batch element is received.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a41a9-107">では、アグリーメントで EDI の状態レポートとトランザクション セットの追跡が有効になっている場合にのみ、BusinessMessageJournal アクティビティにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-107">will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
 <span data-ttu-id="a41a9-108">以下のセクションでは、次の事項について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-108">The sections below describe the following:</span></span>  
  
- <span data-ttu-id="a41a9-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が追跡データを保存する方法</span><span class="sxs-lookup"><span data-stu-id="a41a9-109">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] saves tracking data</span></span>  
  
- <span data-ttu-id="a41a9-110">カスタム パイプライン コンポーネントを作成して関連付けを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a41a9-110">How you can create a custom pipeline component to enable correlation</span></span>  
  
- <span data-ttu-id="a41a9-111">受信トランザクション セットを送信バッチに関連付ける方法</span><span class="sxs-lookup"><span data-stu-id="a41a9-111">How you can correlate an incoming transaction set with an outgoing batch.</span></span>  
  
- <span data-ttu-id="a41a9-112">バッチに含まれるトランザクション セットの BTSInterchangeID がわかっている場合に、BusinessMessageJournal アクティビティに対してクエリを実行し、バッチの BTSInterchangeID を特定する方法</span><span class="sxs-lookup"><span data-stu-id="a41a9-112">How you can query the BusinessMessageJournal activity to determine the BTSInterchangeID of the batch if you know the BTSInterchangeID of the transaction set contained in the batch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a41a9-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="a41a9-113">Prerequisites</span></span>  
 <span data-ttu-id="a41a9-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a41a9-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="changes-to-the-activities"></a><span data-ttu-id="a41a9-115">アクティビティに対する変更</span><span class="sxs-lookup"><span data-stu-id="a41a9-115">Changes to the Activities</span></span>  
 <span data-ttu-id="a41a9-116">バッチ処理オーケストレーションは、BatchingActivity、TransactionSetActivity、および BusinessMessageJournal の各 BAM アクティビティにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-116">The Batching Orchestration makes entries in the BatchingActivity, TransactionSetActivity, and BusinessMessageJournal BAM activities.</span></span> <span data-ttu-id="a41a9-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を通じてトランザクション セットの処理を行う間に、これらのアクィビティ テーブルに対し、トランザクション セットとそれを含むバッチのエントリを次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-117">As a transaction set moves through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will make the following entries in these activity tables for the transaction set and the batch that includes it:</span></span>  
  
1.  <span data-ttu-id="a41a9-118">EDI 逆アセンブラーは、受信 EDI インターチェンジの処理時に、InterchangeStatusActivity テーブルと TransactionSetActivity テーブルにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-118">When the EDI disassembler processes an incoming EDI interchange, it creates entries in the InterchangeStatusActivity and the TransactionSetActivity tables.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a41a9-119">BAM アクティビティの詳細については、[EDI AS2 メッセージの追跡するために BAM アクティビティ作成](../core/bam-activities-created-to-track-edi-as2-messages.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41a9-119">For more information about the BAM activities, see [BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md).</span></span>  
  
2.  <span data-ttu-id="a41a9-120">バッチ処理オーケストレーションは、インスタンスが作成されたときに、BatchingActivity にエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-120">When the Batching Orchestration is instantiated, the orchestration creates an entry in the BatchingActivity.</span></span> <span data-ttu-id="a41a9-121">BAM サブシステムは、ActivityID の値を作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-121">The BAM subsystem creates a value for the ActivityID.</span></span>  
  
3.  <span data-ttu-id="a41a9-122">バッチ処理オーケストレーションは、トランザクション セットの受信時に、TransactionSetActivity テーブルにそのトランザクション セットのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-122">After the batching orchestration has picked up the transaction set, it creates an entry for the transaction set in the TransactionSetActivity table.</span></span>  
  
4.  <span data-ttu-id="a41a9-123">オーケストレーションは、BusinessMessageJournal アクティビティにエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-123">The orchestration creates an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="a41a9-124">次に、このアクティビティの MessageTrackingID フィールドを、TransactionSetActivity テーブルに作成したエントリの ActivityID フィールドの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-124">It sets the MessageTrackingID field of this activity to the value of the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="a41a9-125">さらに、BTSInterchangeID フィールドをトランザクション セットの BTS.InterchangeID コンテキスト プロパティに、BTSMessageID フィールドをトランザクション セットの BTS.MessageID コンテキスト プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-125">It also sets the BTSInterchangeID field to the BTS.InterchangeID context property for the transaction set and the BTSMessageID field to the BTS.MessageID context property for the transaction set.</span></span>  
  
5.  <span data-ttu-id="a41a9-126">オーケストレーションは、BusinessMessageJournal アクティビティに 2 つ目のエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-126">The orchestration creates a second entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="a41a9-127">次に、MessageTrackingID フィールドを、TransactionSetActivity テーブルに作成したエントリの ActivityID フィールドに設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-127">It sets the MessageTrackingID field to the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="a41a9-128">さらに、BTSInterchangeID フィールドを、バッチの BTS.InterchangeID コンテキスト プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-128">It sets the BTSInterchangeID field to the BTS.InterchangeID context property for the batch.</span></span> <span data-ttu-id="a41a9-129">また、BTSMessageID は設定せずに、</span><span class="sxs-lookup"><span data-stu-id="a41a9-129">It does not set the BTSMessageID.</span></span> <span data-ttu-id="a41a9-130">ContainerActivityID を BatchingActivity の ActivityID の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-130">It sets the ContainerActivityID to the value of the ActivityID in the BatchingActivity.</span></span>  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a><span data-ttu-id="a41a9-131">カスタム パイプライン コンポーネントの作成による関連付けの準備</span><span class="sxs-lookup"><span data-stu-id="a41a9-131">Creating a Custom Pipeline Component for Enabling Correlation</span></span>  
 <span data-ttu-id="a41a9-132">受信トランザクション セットをそのトランザクションを含む、送信バッチの相関関係を設定する設定、カスタム パイプライン コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a41a9-132">To set up correlation of an incoming transaction set with an outgoing batch that contains that transaction set, you need to create a custom pipeline component.</span></span> <span data-ttu-id="a41a9-133">このパイプライン コンポーネントでの処理は、EDI 逆アセンブラーによる処理の後、EDIReceive パイプラインの BatchMarker コンポーネントで処理を行う前に行います。</span><span class="sxs-lookup"><span data-stu-id="a41a9-133">This pipeline component should come after the EDI Disassembler and before the BatchMarker component of the EDIReceive pipeline.</span></span> <span data-ttu-id="a41a9-134">このパイプライン コンポーネントでは、BusinessMessageJournal アクティビティにエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a41a9-134">This pipeline component needs to create an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="a41a9-135">このエントリでは、BTSInterchangeID フィールドを BTS.InterchangeID コンテキスト プロパティに、BTSMessageID フィールドを BTS.MessageID コンテキスト プロパティに設定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-135">In this entry, the BTSInterchangeID field should be set to the BTS.InterchangeID context property and the BTSMessageID field should be set to the BTS.MessageID context property.</span></span>  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a><span data-ttu-id="a41a9-136">バッチ内トランザクション セットの InterchangeID の検索</span><span class="sxs-lookup"><span data-stu-id="a41a9-136">Looking Up the InterchangeID for a Transaction Set in a Batch</span></span>  
 <span data-ttu-id="a41a9-137">受信したインターチェンジと、インターチェンジ内のトランザクション セットを含むバッチを関連付けるには、BatchingActivity テーブルと BusinessMessageJournal アクティビティのエントリを使用して、次に示す作業を行います。</span><span class="sxs-lookup"><span data-stu-id="a41a9-137">You correlate a received interchange, and the batch that contains the transaction set from the interchange, by using the entries in the BatchingActivity table and the BusinessMessageJournal activity, as described below.</span></span>  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a><span data-ttu-id="a41a9-138">受信トランザクション セットとそのトランザクション セットを含む送信バッチを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="a41a9-138">To correlate an incoming transaction set with an outgoing batch that contains that transaction set</span></span>  
  
1.  <span data-ttu-id="a41a9-139">BatchingActivity テーブルで、バッチの ActivityID の値を特定します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-139">Determine the value of ActivityID for the batch in the BatchingActivity table.</span></span>  
  
2.  <span data-ttu-id="a41a9-140">その ActivityID の値を、BusinessMessageJournal アクティビティ テーブルの ContainerActivityID フィールドで検索します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-140">Search for the ActivityID value in the ContainerActivityID field of the BusinessMessageJournal activity table.</span></span>  
  
3.  <span data-ttu-id="a41a9-141">ContainerActivityID で特定したレコード内で、バッチに関連付けられている MessageTrackingID フィールドの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-141">In the record identified by the ContainerActivityID, look up the value of the MessageTrackingID field, which is associated with the batch.</span></span>  
  
4.  <span data-ttu-id="a41a9-142">BusinessMessageJournal アクティビティ テーブルでバッチに関連付けられている MessageTrackingID フィールドの値を使用して、BusinessMessageJournal アクティビティ テーブル内で同じ MessageTrackingID フィールドの値を持つ他のレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-142">Using the value of the MessageTrackingID field associated with the batch in the BusinessMessageJournal activity table, search for the same value in the MessageTrackingID field of other records in the BusinessMessageJournal activity table.</span></span> <span data-ttu-id="a41a9-143">ここで見つかったレコードが、バッチ処理オーケストレーションによって記録された、バッチ内のトランザクションに関連付けられたレコードです。</span><span class="sxs-lookup"><span data-stu-id="a41a9-143">Any records found are associated with transaction sets in the batch, as recorded by the Batching Orchestration.</span></span>  
  
5.  <span data-ttu-id="a41a9-144">BusinessMessageJournal アクティビティ テーブルのトランザクション セットに関連付けられたレコードで、BTSInterchangeID フィールドの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="a41a9-144">In a record associated with a transaction set in the BusinessMessageJournal activity table, look up the value of the BTSInterchangeID field.</span></span>  
  
6.  <span data-ttu-id="a41a9-145">この BTSInterchangeID の値を使用して、カスタムのパイプライン コンポーネントによって BusinessMessageJournal アクティビティ テーブルに作成された、トランザクション セットのレコードを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-145">Using the value of the BTSInterchangeID, you can look up a record for the transaction set that was created in the BusinessMessageJournal activity table, as recorded by the custom pipeline component.</span></span> <span data-ttu-id="a41a9-146">また、TransactionSetActivity テーブルでも、トランザクション セットのレコードを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-146">You can also look up a record for the transaction set in the TransactionSetActivity table.</span></span>  
  
## <a name="querying-businessmessagejournal"></a><span data-ttu-id="a41a9-147">BusinessMessageJournal に対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="a41a9-147">Querying BusinessMessageJournal</span></span>  
 <span data-ttu-id="a41a9-148">トランザクション セットのレポートが有効になっており、受信したインターチェンジの BTSInterchangeID がわかっている場合は、次の SQL クエリを使用して、バッチ処理オーケストレーションに送信されたトランザクション セットを含むバッチの BTSInterchangeID を検索できます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-148">If transaction set reporting is enabled, and you know the BTSInterchangeID of the received interchange, you can use the following SQL Query to find out the BTSInterchangeID of the batch that contains the transaction set submitted to the Batching Orchestration.</span></span> <span data-ttu-id="a41a9-149">このコードを使用すると、バッチ内のメッセージを表示するカスタムのアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-149">With this code, you can create a custom application to gain visibility into the messages in a batch.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a41a9-150">では、アグリーメントで EDI の状態レポートとトランザクション セットの追跡が有効になっている場合にのみ、BusinessMessageJournal アクティビティにエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a41a9-150">will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a41a9-151">参照</span><span class="sxs-lookup"><span data-stu-id="a41a9-151">See Also</span></span>  
 <span data-ttu-id="a41a9-152">[EDI AS2 メッセージの追跡に作成された BAM アクティビティ](../core/bam-activities-created-to-track-edi-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a41a9-152">[BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md) </span></span>  
 [<span data-ttu-id="a41a9-153">EDI および AS2 状態レポートの有効化</span><span class="sxs-lookup"><span data-stu-id="a41a9-153">Enabling EDI and AS2 Status Reports</span></span>](../core/enabling-edi-and-as2-status-reports.md)