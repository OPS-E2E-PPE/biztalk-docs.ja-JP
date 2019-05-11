---
title: Continuation を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0cf558ec136cf25bece9c899cad13e1c9d75f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340100"
---
# <a name="how-to-create-a-continuation"></a><span data-ttu-id="7186b-102">Continuation を作成する方法</span><span class="sxs-lookup"><span data-stu-id="7186b-102">How to Create a Continuation</span></span>
<span data-ttu-id="7186b-103">接続されたアクティビティを構築することによって関連する 1 つまたは複数のオーケストレーションでビジネス イベントを示すために、継続を作成します。</span><span class="sxs-lookup"><span data-stu-id="7186b-103">You create continuations to indicate which business events in one or more orchestrations are related by constructing connected activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7186b-104">追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="7186b-104">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="7186b-105">具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7186b-105">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="7186b-106">各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="7186b-106">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span>  <span data-ttu-id="7186b-107">ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7186b-107">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7186b-108">メッセージを処理しないオーケストレーションでは、continuation を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7186b-108">You can create continuations with orchestrations that do not process messages.</span></span> <span data-ttu-id="7186b-109">BAM Api を使用して、処理を継続してオーケストレーション間の実行呼び出しでパラメーターを渡すことによってメッセージの処理はオーケストレーションを同じ機能を取得できます。</span><span class="sxs-lookup"><span data-stu-id="7186b-109">You can obtain the same functionality as you can for orchestrations that do process messages by passing parameters in execution calls between orchestrations and by using BAM APIs to process the continuation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7186b-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="7186b-110">Prerequisites</span></span>  
 <span data-ttu-id="7186b-111">この手順を実行するには、必要がありますが展開した BAM アクティビティ定義とオーケストレーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="7186b-111">To perform this procedure, you must have deployed BAM activity definitions and orchestrations that you will connect to.</span></span>  
  
### <a name="to-create-a-continuation"></a><span data-ttu-id="7186b-112">Continuation を作成するには</span><span class="sxs-lookup"><span data-stu-id="7186b-112">To create a continuation</span></span>  
  
1.  <span data-ttu-id="7186b-113">既存の追跡プロファイルを開くか、追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7186b-113">Open an existing tracking profile or create a tracking profile.</span></span> <span data-ttu-id="7186b-114">追跡プロファイルを作成する方法の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。</span><span class="sxs-lookup"><span data-stu-id="7186b-114">For information about creating a tracking profile, see [How to Create a Tracking Profile](../core/how-to-create-a-tracking-profile.md).</span></span>  
  
2.  <span data-ttu-id="7186b-115">識別、*継続トークン、* 両方のアクティビティに使用できる一意の情報の一部であります。</span><span class="sxs-lookup"><span data-stu-id="7186b-115">Identify a *continuation token,* which is a piece of unique information that is available to both activities.</span></span> <span data-ttu-id="7186b-116">たとえば場合、 **CreditHistory**アクティビティがから送信されたメッセージによってアクティブ化、 **LoanProcess**内のアクティビティ、 **EquityLoan**オーケストレーションの SSN フィールド、メッセージは、両方の活動に共通するために継続トークンとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="7186b-116">For example, if a **CreditHistory** activity is activated by a message sent from a **LoanProcess** activity within an **EquityLoan**orchestration, the SSN field of the message can be used as a continuation token because it is common to both activities.</span></span>  
  
3.  <span data-ttu-id="7186b-117">アクティビティを右クリックし、**新しい Continuation** continuation (CreditHistory) を作成します。</span><span class="sxs-lookup"><span data-stu-id="7186b-117">Right-click the activity and then select **New Continuation** to create a continuation (CreditHistory).</span></span> <span data-ttu-id="7186b-118">作成した continuation のノードの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="7186b-118">Name the continuation node you just created.</span></span>  
  
4.  <span data-ttu-id="7186b-119">オーケストレーション スケジュール ビューからは、SSN (ここでは送信アクション) などの手順 2. で選択した継続トークンを選択し、手順 3 で作成した continuation のノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="7186b-119">From the Orchestration Schedule View, select the continuation token you chose in step 2, such as SSN (in this case from the Send action) and drop it into the continuation node you created in step 3.</span></span>  
  
5.  <span data-ttu-id="7186b-120">アクティビティを右クリックして**新しい ContinuationID** Continuation ID ノードを作成します。</span><span class="sxs-lookup"><span data-stu-id="7186b-120">Right-click the activity and select **New ContinuationID** to create a Continuation ID node.</span></span> <span data-ttu-id="7186b-121">手順 3. で指定した名前を使用して名前し、(この例では、受信アクションの SSN) では、対応するデータ項目を含むノードにドロップします。</span><span class="sxs-lookup"><span data-stu-id="7186b-121">Name it using the name you chose in step 3, and drop it in the node that contains the corresponding data item (in this case, SSN from the Receive action).</span></span>  
  
6.  <span data-ttu-id="7186b-122">**ファイル** メニューのをクリックして**名前を付けて保存**追跡プロファイルを BizTalk 管理データベースに .btt ファイルとして保存して、既存の .btt ファイルが上書きされないようにします。</span><span class="sxs-lookup"><span data-stu-id="7186b-122">On the **File**menu, click **Save As**to save the tracking profile as a .btt file to the BizTalk Management database and to avoid overwriting any existing .btt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7186b-123">参照</span><span class="sxs-lookup"><span data-stu-id="7186b-123">See Also</span></span>  
 <span data-ttu-id="7186b-124">[Continuation ノードと ContinuationID ノード](../core/continuation-and-continuationid-nodes.md) </span><span class="sxs-lookup"><span data-stu-id="7186b-124">[Continuation and ContinuationID Nodes](../core/continuation-and-continuationid-nodes.md) </span></span>  
 [<span data-ttu-id="7186b-125">追跡プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7186b-125">Creating Tracking Profiles</span></span>](../core/creating-tracking-profiles.md)