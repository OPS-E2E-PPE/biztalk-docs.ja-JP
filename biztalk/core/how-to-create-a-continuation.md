---
title: "Continuation を作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e63983b290f0f4d7dff544cd2faea45f6cf46adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-continuation"></a><span data-ttu-id="a7c65-102">Continuation を作成する方法</span><span class="sxs-lookup"><span data-stu-id="a7c65-102">How to Create a Continuation</span></span>
<span data-ttu-id="a7c65-103">Continuation は、接続されたアクティビティを構築することによって、1 つ以上のオーケストレーション内のどのビジネス イベントが関連付けられているのかを示すために作成します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-103">You create continuations to indicate which business events in one or more orchestrations are related by constructing connected activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7c65-104">追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7c65-104">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="a7c65-105">具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7c65-105">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="a7c65-106">各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a7c65-106">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span>  <span data-ttu-id="a7c65-107">ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a7c65-107">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7c65-108">メッセージを処理しないオーケストレーションを使用して、Continuation を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a7c65-108">You can create continuations with orchestrations that do not process messages.</span></span> <span data-ttu-id="a7c65-109">メッセージを処理するオーケストレーションと同等の機能を実現するには、オーケストレーション間の実行呼び出しでパラメーターを渡し、Continuation の処理で BAM API を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-109">You can obtain the same functionality as you can for orchestrations that do process messages by passing parameters in execution calls between orchestrations and by using BAM APIs to process the continuation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7c65-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="a7c65-110">Prerequisites</span></span>  
 <span data-ttu-id="a7c65-111">ここで示す手順を実行するには、BAM アクティビティ定義および接続先のオーケストレーションを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7c65-111">To perform this procedure, you must have deployed BAM activity definitions and orchestrations that you will connect to.</span></span>  
  
### <a name="to-create-a-continuation"></a><span data-ttu-id="a7c65-112">Continuation を作成するには</span><span class="sxs-lookup"><span data-stu-id="a7c65-112">To create a continuation</span></span>  
  
1.  <span data-ttu-id="a7c65-113">既存の追跡プロファイルを開くか、追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-113">Open an existing tracking profile or create a tracking profile.</span></span> <span data-ttu-id="a7c65-114">追跡プロファイルを作成する方法の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)です。</span><span class="sxs-lookup"><span data-stu-id="a7c65-114">For information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="a7c65-115">識別、*継続トークン、*は両方のアクティビティに使用される固有の情報の一部であります。</span><span class="sxs-lookup"><span data-stu-id="a7c65-115">Identify a *continuation token,* which is a piece of unique information that is available to both activities.</span></span> <span data-ttu-id="a7c65-116">たとえば場合、 **CreditHistory**アクティビティがから送信されたメッセージによってアクティブ化、 **LoanProcess**内のアクティビティ、 **EquityLoan**オーケストレーションの SSN フィールド、メッセージは、両方のアクティビティに一般的になっているために、継続トークンとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7c65-116">For example, if a **CreditHistory** activity is activated by a message sent from a **LoanProcess** activity within an **EquityLoan**orchestration, the SSN field of the message can be used as a continuation token because it is common to both activities.</span></span>  
  
3.  <span data-ttu-id="a7c65-117">アクティビティを右クリックし **新しい Continuation** continuation (CreditHistory) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-117">Right-click the activity and then select **New Continuation** to create a continuation (CreditHistory).</span></span> <span data-ttu-id="a7c65-118">作成した Continuation のノードに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a7c65-118">Name the continuation node you just created.</span></span>  
  
4.  <span data-ttu-id="a7c65-119">オーケストレーション スケジュール ビューから、手順 2. で選択した継続トークン (この場合は送信アクションの SSN) を選択し、手順 3. で作成した Continuation のノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7c65-119">From the Orchestration Schedule View, select the continuation token you chose in step 2, such as SSN (in this case from the Send action) and drop it into the continuation node you created in step 3.</span></span>  
  
5.  <span data-ttu-id="a7c65-120">アクティビティを右クリックし [**新しい continuationid]** Continuation ID ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-120">Right-click the activity and select **New ContinuationID** to create a Continuation ID node.</span></span> <span data-ttu-id="a7c65-121">作成したノードに、手順 3. で指定した名前を付け、対応するデータ項目 (この場合は受信アクションの SSN) を含むノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="a7c65-121">Name it using the name you chose in step 3, and drop it in the node that contains the corresponding data item (in this case, SSN from the Receive action).</span></span>  
  
6.  <span data-ttu-id="a7c65-122">**ファイル** メニューのをクリックして**名前を付けて保存**追跡プロファイルを BizTalk 管理データベースに .btt ファイルとして保存し、既存の .btt ファイルが上書きされないようにします。</span><span class="sxs-lookup"><span data-stu-id="a7c65-122">On the **File**menu, click **Save As**to save the tracking profile as a .btt file to the BizTalk Management database and to avoid overwriting any existing .btt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c65-123">参照</span><span class="sxs-lookup"><span data-stu-id="a7c65-123">See Also</span></span>  
 <span data-ttu-id="a7c65-124">[Continuation ノードと ContinuationID ノード](../core/continuation-and-continuationid-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="a7c65-124">[Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md) </span></span>  
 [<span data-ttu-id="a7c65-125">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7c65-125">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)