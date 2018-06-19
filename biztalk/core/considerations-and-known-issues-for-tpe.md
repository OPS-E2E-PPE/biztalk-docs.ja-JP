---
title: 考慮事項と既知の問題 TPE |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, known issues
- planning, Tracking Profile Editor
- Tracking Profile Editor, planning
ms.assetid: e96d85e0-e9ae-434a-b54e-5950f4a2b9c6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d630b2cfa5cca1d7a441796ef8c555d02bb04910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234578"
---
# <a name="considerations-and-known-issues-for-tpe"></a><span data-ttu-id="9bf43-102">TPE の考慮事項と既知の問題</span><span class="sxs-lookup"><span data-stu-id="9bf43-102">Considerations and Known Issues for TPE</span></span>
<span data-ttu-id="9bf43-103">追跡プロファイルと TPE を操作する際に留意しなければならない点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-103">You should consider the following issues when you work with tracking profiles and the TPE.</span></span>  
  
## <a name="naming-folders-in-the-tpe"></a><span data-ttu-id="9bf43-104">TPE でのフォルダー名の付け方</span><span class="sxs-lookup"><span data-stu-id="9bf43-104">Naming Folders in the TPE</span></span>  
 <span data-ttu-id="9bf43-105">追跡プロファイル エディターでフォルダーに名前を付ける場合は、次の命名規則に従ってください。</span><span class="sxs-lookup"><span data-stu-id="9bf43-105">Note the following naming requirements when naming folders in Tracking Profile Editor:</span></span>  
  
-   <span data-ttu-id="9bf43-106">フォルダー名とデータ項目インスタンス値を合わせた長さは 128 文字を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-106">The length of the combination of folder name and data item instance values must not exceed 128 characters.</span></span>  
  
-   <span data-ttu-id="9bf43-107">Continuation および ContinuationID フォルダーの場合、フォルダーの名前付けは、2 つのオーケストレーションを相関付ける際に非常に重要になります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-107">For Continuation and ContinuationID folders, the naming of the folder is the key to correlating two orchestrations.</span></span> <span data-ttu-id="9bf43-108">たとえば、オーケストレーション A がオーケストレーション B の親である場合、オーケストレーション A には、オーケストレーション B 内の ContinuationID フォルダーに直接マップされる名前を持つ Continuation フォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9bf43-108">For example, if Orchestration A is the parent of Orchestration B, Orchestration A contains a continuation folder whose name maps directly to the ContinuationID folder in Orchestration B.</span></span>  
  
## <a name="developing-orchestrations-for-the-tpe"></a><span data-ttu-id="9bf43-109">TPE のオーケストレーションの開発</span><span class="sxs-lookup"><span data-stu-id="9bf43-109">Developing Orchestrations for the TPE</span></span>  
 <span data-ttu-id="9bf43-110">無効な図形で開始する、または終了するビジネス アクティビティにオーケストレーションをマップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-110">You cannot map an orchestration to a business activity if it starts or ends with an invalid shape.</span></span> <span data-ttu-id="9bf43-111">オーケストレーション エンジンでは、一部の図形を追跡できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-111">The Orchestration engine does not allow tracking for some shapes.</span></span> <span data-ttu-id="9bf43-112">これらは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-112">They are:</span></span>  
  
-   <span data-ttu-id="9bf43-113">メッセージの割り当て</span><span class="sxs-lookup"><span data-stu-id="9bf43-113">Message Assignment</span></span>  
  
-   <span data-ttu-id="9bf43-114">変換</span><span class="sxs-lookup"><span data-stu-id="9bf43-114">Transform</span></span>  
  
-   <span data-ttu-id="9bf43-115">グループ (タスク)</span><span class="sxs-lookup"><span data-stu-id="9bf43-115">Group (Task)</span></span>  
  
-   <span data-ttu-id="9bf43-116">[中断]</span><span class="sxs-lookup"><span data-stu-id="9bf43-116">Suspend</span></span>  
  
-   <span data-ttu-id="9bf43-117">ループ (While)</span><span class="sxs-lookup"><span data-stu-id="9bf43-117">Loop (While)</span></span>  
  
-   <span data-ttu-id="9bf43-118">分岐</span><span class="sxs-lookup"><span data-stu-id="9bf43-118">Branch</span></span>  
  
-   <span data-ttu-id="9bf43-119">終了</span><span class="sxs-lookup"><span data-stu-id="9bf43-119">Terminate</span></span>  
  
-   <span data-ttu-id="9bf43-120">スロー</span><span class="sxs-lookup"><span data-stu-id="9bf43-120">Throw</span></span>  
  
-   <span data-ttu-id="9bf43-121">キャッチ</span><span class="sxs-lookup"><span data-stu-id="9bf43-121">Catch</span></span>  
  
-   <span data-ttu-id="9bf43-122">While 図形</span><span class="sxs-lookup"><span data-stu-id="9bf43-122">While shape</span></span>  
  
 <span data-ttu-id="9bf43-123">追跡プロファイル エディターやその他の BAM ツールでビジネス アクティビティを利用できるように、ビジネス アクティビティへのマップを行う場合は、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="9bf43-123">Use the following guidelines when mapping to business activities so that the Tracking Profile Editor and other BAM tools can use them:</span></span>  
  
-   <span data-ttu-id="9bf43-124">グループ図形の場合は、トランザクション以外のスコープ図形を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-124">For the Group shape, use a non-transactional Scope shape.</span></span>  
  
-   <span data-ttu-id="9bf43-125">While 図形の場合は、トランザクション以外のスコープ図形内にラップします。</span><span class="sxs-lookup"><span data-stu-id="9bf43-125">For the While shape, wrap it in a non-transactional Scope shape.</span></span>  
  
-   <span data-ttu-id="9bf43-126">終了図形の場合、通常のシナリオでは終了図形の End イベントが発生しないので、回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-126">For the Terminate shapes, there is no workaround, because the end event of this shape never occurs in a normal scenario.</span></span>  
  
-   <span data-ttu-id="9bf43-127">ドラッグ アンド ドロップ操作が許可されていない図形を使用してスケジュールの開始または終了を行わないでください。</span><span class="sxs-lookup"><span data-stu-id="9bf43-127">Do not start or end schedules with any of the shapes for which drag-and-drop operations are not permitted.</span></span>  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a><span data-ttu-id="9bf43-128">実行中のプロセスを監視する追跡プロファイルの適用</span><span class="sxs-lookup"><span data-stu-id="9bf43-128">Applying Tracking Profiles that Monitor Running Processes</span></span>  
 <span data-ttu-id="9bf43-129">追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-129">Updating a tracking profile can impact activity instances in progress if the activity includes a BAM continuation.</span></span> <span data-ttu-id="9bf43-130">具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-130">Specifically, if the update to the tracking profile specifies a downstream interception of data for an activity item already recorded, it is possible that the original value will be overwritten.</span></span> <span data-ttu-id="9bf43-131">各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-131">In essence, any single event stream will not be affected by the application of tracking profile updates because each stream object is tied to the specific version of the profile which was in place at the time the activity/stream started.</span></span> <span data-ttu-id="9bf43-132">ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-132">However, because continuations are the means of correlating multiple event streams, streams not yet begun at the time of a profile update will pick up the changes in the update, thus introducing the possible data overwrite described.</span></span> <span data-ttu-id="9bf43-133">Continuation の詳細については、次を参照してください。[アクティビティ Continuation](../core/activity-continuation.md)と[Continuation を作成する方法](../core/how-to-create-a-continuation.md)です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-133">For more information about continuations, see [Activity Continuation](../core/activity-continuation.md) and [How to Create a Continuation](../core/how-to-create-a-continuation.md).</span></span>  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a><span data-ttu-id="9bf43-134">メッセージ プロパティを作成するときの起点となる送信図形や受信図形のないプロファイルの追跡</span><span class="sxs-lookup"><span data-stu-id="9bf43-134">Tracking Profiles Without a Send or Receive Shape from Which to Draw Message Properties</span></span>  
 <span data-ttu-id="9bf43-135">Continuation は、アクティビティ間で共通するコンテキスト プロパティまたはペイロード データを通じてアクティビティを追跡するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-135">Continuations track activities through context properties or payload data that are the same between activities.</span></span> <span data-ttu-id="9bf43-136">メッセージ ID、サービス ID、インスタンス ID などのプロパティの値は、アクティビティ間で変化します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-136">Properties such as Message ID, Service ID, and Instance ID change value between activities.</span></span>  
  
 <span data-ttu-id="9bf43-137">このようなシナリオを処理する追跡プロファイルは、次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-137">You can create tracking profiles to handle this scenario by using the following methods:</span></span>  
  
-   <span data-ttu-id="9bf43-138">動的バインドを通じてあるオーケストレーションから別のオーケストレーションにメッセージが送信される場合、グローバルな一意のペイロード データ値を Continuation に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-138">If an orchestration sends a message through a dynamic binding to another orchestration, then a globally unique payload data value can be used for the continuation.</span></span>  
  
-   <span data-ttu-id="9bf43-139">メッセージ内に一意のペイロード データが含まれていない場合は、メッセージのインターチェンジ ID を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-139">If there is no unique payload data in the message, then the interchange ID of the message can be used.</span></span> <span data-ttu-id="9bf43-140">インターチェンジ ID を使用するには、これを同じ受信図形上で追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-140">To use the interchange ID, you must track it on the same Receive shape.</span></span> <span data-ttu-id="9bf43-141">新しいメッセージを作成する場合はインターチェンジ ID が変更されるため、インターチェンジ ID を使用してメッセージを新規作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-141">You cannot use the interchange ID if you create a new message, as the interchange ID changes when the new message is created.</span></span> <span data-ttu-id="9bf43-142">受信図形または送信図形以外の図形からインターチェンジ ID を追跡すると、信頼性が低下します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-142">Tracking the interchange ID from any shape other than a Receive or Send shape is not reliable.</span></span>  
  
-   <span data-ttu-id="9bf43-143">また、パイプライン経由で受信されたものとまったく同じメッセージをオーケストレーション内で使用する限り、つまり、オーケストレーション ポートがパイプラインにバインドされており、受信図形とメッセージ ID がその場所から追跡される場合に限り、メッセージ ID を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-143">You can also use message ID as long as the exact same message that is received from the pipeline is used in the orchestration, that is, the orchestration port is bound to a pipeline and a Receive shape and the message ID are tracked from that location.</span></span> <span data-ttu-id="9bf43-144">異なる図形からメッセージ ID を追跡すると、そのメッセージ ID は無効となり、Continuation で使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-144">If you track the message ID from a different shape, then the message ID will be invalid for use in continuations.</span></span>  
  
-   <span data-ttu-id="9bf43-145">ユーザーがインスタンス ID を使用できますがオーケストレーションが別のオーケストレーションを呼び出したとメッセージが渡されないまたはオーケストレーションが別のオーケストレーションを呼び出した呼び出し先の構築では、受信、またはない送信図形ペイロード データ値を取得できる、</span><span class="sxs-lookup"><span data-stu-id="9bf43-145">If an orchestration calls another orchestration and no message is passed, or an orchestration calls another orchestration but the callee does not have any Construct, Receive, or Send shape where payload data values can be retrieved, the user can use the instance ID.</span></span> <span data-ttu-id="9bf43-146">呼び出されたオーケストレーションのインスタンス ID は変更されません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-146">The instance ID for the called orchestrations does not change.</span></span>  
  
-   <span data-ttu-id="9bf43-147">オーケストレーションが、直接呼び出しではなく実行呼び出しによって別のオーケストレーションを読み込む場合は、静的メッセージ プロパティを使用してアクティビティを追跡することはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-147">If the orchestration loads another orchestration through an execution call rather than calling it directly, then there is no way to use any static message properties to track the activity.</span></span> <span data-ttu-id="9bf43-148">つまり、Continuation を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-148">The user cannot enable a continuation.</span></span> <span data-ttu-id="9bf43-149">このようなオーケストレーション インスタンスで追跡を実行する唯一の方法は、追跡の実行対象となる一意のペイロード データを含んでいるパイプラインを経由してメッセージを渡すことです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-149">The only way to perform tracking in this instance is if a message is passed through the pipeline that contains unique payload data on which to perform the tracking.</span></span>  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a><span data-ttu-id="9bf43-150">パススルー パイプラインの場合、継続トークンとしてセッション ID を使用できない</span><span class="sxs-lookup"><span data-stu-id="9bf43-150">You Cannot Use a Session ID as a Continuation Token for Pass-Through Pipelines</span></span>  
 <span data-ttu-id="9bf43-151">追跡プロファイルでは、メッセージ ペイロードから項目を選択すると、追跡プロファイルはそのメッセージのスキーマにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-151">In a tracking profile, when you select items from a message payload, the tracking profile is bound to the schema of that message.</span></span> <span data-ttu-id="9bf43-152">パススルー パイプライン内では、スキーマ名の値が NULL 値となります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-152">In a pass-through pipeline, the schema name value is a null value.</span></span> <span data-ttu-id="9bf43-153">BAM が、ポート名別およびスキーマ名別に構成を読み込もうとした場合、セッション ID スキーマとの照合を行うことはできず、エンジンによるデータ追跡は行われません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-153">When BAM attempts to load the configuration by port name and schema name it cannot make the match to the session ID schema and no data is tracked by the engine.</span></span>  
  
 <span data-ttu-id="9bf43-154">パススルー パイプラインの場合、追跡プロファイルからすべてのペイロード追跡を削除できます。また、ペイロード データの追跡が必要であれば、XML パイプラインの使用も可能です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-154">For pass-through pipelines, you can either remove all payload tracking from the tracking profile or use XML pipelines if you do need to track the payload data.</span></span>  
  
## <a name="using-unique-port-names"></a><span data-ttu-id="9bf43-155">一意のポート名の使用</span><span class="sxs-lookup"><span data-stu-id="9bf43-155">Using Unique Port Names</span></span>  
 <span data-ttu-id="9bf43-156">双方向ポートを列挙する場合、TPE により、ポートは 2 つの論理ポート (送信ポートと受信ポート) として表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-156">When enumerating two-way ports, the TPE displays them as two logical ports, a send and a receive port.</span></span> <span data-ttu-id="9bf43-157">これらの各論理ポートは、同じ名前で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-157">Each of these logical ports is displayed with the same name.</span></span> <span data-ttu-id="9bf43-158">BizTalk Server では、一方向ポートと双方向ポートを同じ名前で作成できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-158">BizTalk Server allows you to create one-way and two-way ports with the same name.</span></span> <span data-ttu-id="9bf43-159">たとえば、"Port1" という名前の双方向ポートを作成してから、同じ名前の受信ポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-159">For example, you can create a two-way port named "Port1" and then create a receive port with the same name.</span></span> <span data-ttu-id="9bf43-160">この場合、TPE には受信ポートは一度だけ表示され、双方向は 2 回 (1 回は受信ポートとして、もう 1 回は送信ポートとして) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-160">In these cases the TPE displays the receive port once and the two-way port twice, once as a receive port and once as a send port.</span></span>  
  
 <span data-ttu-id="9bf43-161">TPE は、この場合、両方の受信ポートに追跡プロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-161">TPE will apply tracking profiles to both receive ports in this case.</span></span> <span data-ttu-id="9bf43-162">識別しやすいように、ポートには一意の名前を割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9bf43-162">We recommend that ports be given unique names to help identify them properly.</span></span>  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a><span data-ttu-id="9bf43-163">最初の図形が平行図形である TPE オーケストレーションの使用</span><span class="sxs-lookup"><span data-stu-id="9bf43-163">Using TPE Orchestrations with a Parallel Shape as the First Shape</span></span>  
 <span data-ttu-id="9bf43-164">分岐図形、平行図形、待ち受け図形が含まれたオーケストレーションを開始する場合、いずれかの分岐にアクティビティ ID をマップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-164">If you begin an orchestration with a Fork, Parallel, or Listen shape, you cannot map an activity ID on one of the branches.</span></span> <span data-ttu-id="9bf43-165">平行処理の場合は、分岐図形の上層にアクティビティ ID をマップできます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-165">In cases of parallel processing you can map the ActivityID above the Fork shape.</span></span> <span data-ttu-id="9bf43-166">また、BAM によってアクティビティ ID を生成し、オーケストレーションの最上層で平行図形の問題を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-166">You can also let BAM generate the activity ID to avoid the issue of a parallel shape at the top of the orchestration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9bf43-167">アクティビティを複数のパスにマップするだけでなく、分岐図形のいずれかのパスにアクティビティ ID をマップすると、アクティビティ ID がマップされていないパスに沿って処理が進められた場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-167">Mapping an activity to more than one path and also mapping the ActivityID to one path of the Fork shape causes an error when processing follows the path on which the ActivityID is not mapped.</span></span>  
  
## <a name="availability-of-message-properties-at-design-time"></a><span data-ttu-id="9bf43-168">デザイン時のメッセージ プロパティの可用性</span><span class="sxs-lookup"><span data-stu-id="9bf43-168">Availability of Message Properties at Design Time</span></span>  
 <span data-ttu-id="9bf43-169">追跡プロファイルを作成する際、一部のメッセージ プロパティを利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-169">When creating tracking profiles, not all message properties are available.</span></span> <span data-ttu-id="9bf43-170">たとえば、メッセージ プロパティのマップ元となる図形がオーケストレーションの最上部に位置している場合などです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-170">This is most likely to be encountered when the shape where the message properties are mapped from is at the top of an orchestration.</span></span> <span data-ttu-id="9bf43-171">このようなオーケストレーション インスタンスでは、メッセージ プロパティの値は NULL 値になります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-171">In these instances, the value of the message properties is null.</span></span>  
  
 <span data-ttu-id="9bf43-172">その例として、待ち受け図形がオーケストレーションの最初の図形である場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-172">An example of this is where the Listen shape is the first shape in an orchestration.</span></span> <span data-ttu-id="9bf43-173">この図形からメッセージのプロパティがマップされているだけで、次のプロパティ値がある場合: InstanceID、ServiceID、ServiceClassID です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-173">When message properties are mapped from this shape, only the following properties have values: InstanceID, ServiceID and ServiceClassID.</span></span> <span data-ttu-id="9bf43-174">ただし、MessageID はこの時点ではスコープ外となるので、NULL 値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-174">(MessageID is not in scope at this point and has a null value.)</span></span>  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a><span data-ttu-id="9bf43-175">ループ図形内部の図形をマップしてマイルストーンを報告することはできない</span><span class="sxs-lookup"><span data-stu-id="9bf43-175">You Cannot Map Shapes Inside a Loop Shape to Report a Milestone</span></span>  
 <span data-ttu-id="9bf43-176">TPE では、ループ図形内部にあるソースを、ループ図形外部の項目にマップされているアクティビティに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-176">The TPE blocks mapping sources contained from within a Loop shape to activities that are mapped to items that are outside of the loop.</span></span>  
  
 <span data-ttu-id="9bf43-177">ループ アクティビティとは、オーケストレーション内でループ処理される、つまり反復するアクションのことです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-177">Looping activities refers to actions that loop, or repeat, within an orchestration.</span></span> <span data-ttu-id="9bf43-178">オーケストレーション内でループ処理されるアクションからイベントをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-178">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="9bf43-179">この操作を行うには、アクティビティをもう 1 つ作成し、ループ内の新しいアクティビティ マイルストーンとデータのすべてをマップします。</span><span class="sxs-lookup"><span data-stu-id="9bf43-179">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="9bf43-180">ループ内でのデータ処理は、スケジュールされた実行ごとに 1 回以上行われるので、この操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-180">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span>  
  
 <span data-ttu-id="9bf43-181">たとえば、ループ内で処理される複数の品目の発注書を使っている場合のような質問「どの注文がある 100 ドルの品目の価格か」</span><span class="sxs-lookup"><span data-stu-id="9bf43-181">For example, if you have a purchase order with multiple line items that process in a loop, questions like “Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="9bf43-182">あいまいになります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-182">are ambiguous.</span></span> <span data-ttu-id="9bf43-183">質問を明確にすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-183">Unambiguous questions are:</span></span>  
  
 <span data-ttu-id="9bf43-184">価格が 100 ドルの品目があるのはどの注文書か</span><span class="sxs-lookup"><span data-stu-id="9bf43-184">Which purchase orders have line items with a price of $100?</span></span>  
  
 <span data-ttu-id="9bf43-185">合計/最低/最高 100 ドルの価格があるのはどの注文書か</span><span class="sxs-lookup"><span data-stu-id="9bf43-185">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
 <span data-ttu-id="9bf43-186">明確な質問を作成するには、注文書とは別のものとして品目を考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-186">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="9bf43-187">追跡プロファイル エディターでは、ルート アクティビティ (注文書など) はループの外側のすべてのアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-187">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="9bf43-188">子アクティビティ (品目など) はループ内のアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-188">The child activity (for example, a line item) maps to the actions inside the loop.</span></span>  
  
 <span data-ttu-id="9bf43-189">このような構造を操作するには、通常、反復ループを分解し、外部アクティビティに関連付けられている内部アクティビティに基づいて関連アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-189">The typical approach to working with these types of constructs is to decompose the repeating loop and to have a related activity based on the inner activity that is related to the outer activity.</span></span>  
  
 <span data-ttu-id="9bf43-190">ルート アクティビティの ActivityID としてペイロード項目を使用し、このペイロード項目を、ループ内部の一部のメッセージで利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-190">You need to use a payload item as the ActivityID for the root activity and have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="9bf43-191">子アクティビティの下に表示されるリレーションシップ ノードにアクティビティをマップし、ルート アクティビティとして名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-191">Map the activity to the relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a><span data-ttu-id="9bf43-192">複数のアプリケーションにまたがるプロファイルの追跡</span><span class="sxs-lookup"><span data-stu-id="9bf43-192">Tracking Profiles Spanning Multiple Applications</span></span>  
 <span data-ttu-id="9bf43-193">追跡プロファイルが複数のアプリケーションにまたがっている場合、追跡プロファイルは、ソリューション内のすべてのアプリケーションが展開された後に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-193">If a tracking profile spans multiple applications, the tracking profile must be deployed after all applications in the solution are deployed.</span></span> <span data-ttu-id="9bf43-194">追跡プロファイルが展開されている最後の項目ではない場合は、次のメッセージが表示されます"**マッピング ソースが見つかりません。**"の展開ウィザードが BTTDeploy.exe を呼び出すときに、します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-194">If the tracking profile is not the last item deployed, you will receive the following message, "**Mapping source not found.**", when the deployment wizard calls BTTDeploy.exe.</span></span>  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a><span data-ttu-id="9bf43-195">複数の BizTalk Server アイテムのドキュメント参照 URL または MessageID ノードへのマップ</span><span class="sxs-lookup"><span data-stu-id="9bf43-195">Mapping Multiple BizTalk Server Artifacts to a Document Reference URL or MessageID Nodes</span></span>  
 <span data-ttu-id="9bf43-196">TPE では、複数の BizTalk Server アイテムを同じドキュメント参照 URL ノードや MessageID ノードにドラッグ アンド ドロップできます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-196">The TPE allows you to drag and drop from multiple BizTalk Server artifacts onto the same document reference URL or MessageID node.</span></span>  
  
 <span data-ttu-id="9bf43-197">複数のソースが BAM アクティビティ内の同じ項目にマップされている場合、BAM 処理時に発生した最後のアイテムが追跡データに保持され、BAM ポータルで表示可能になります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-197">In cases where multiple sources are mapped to the same item in a BAM activity, the last artifact that was encountered during BAM processing is the one that persists in the tracking data and can be viewed in the BAM portal.</span></span>  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a><span data-ttu-id="9bf43-198">BizTalk ソリューション バージョンに合わせた BTT バージョンの更新</span><span class="sxs-lookup"><span data-stu-id="9bf43-198">Updating BTT Versions to Match BizTalk Solution Versions</span></span>  
 <span data-ttu-id="9bf43-199">BAM 開発者や管理者は、BTT ファイルを自動更新することにより、追跡プロファイルと BizTalk ソリューションのバージョン同期を維持できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-199">BAM developers and administrators can maintain version synchronization between tracking profiles and BizTalk solutions by automating the update to the BTT file.</span></span> <span data-ttu-id="9bf43-200">これを行うには、変更、**バージョン**属性、 **DataLevel** BTT ファイルの要素。</span><span class="sxs-lookup"><span data-stu-id="9bf43-200">To do this, modify the **Version** attribute in the **DataLevel** element of the BTT file.</span></span> <span data-ttu-id="9bf43-201">次の例では、TargetAssemblyName および SchemaName 属性を使用してバージョン情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-201">In the following sample element, you would modify the version information in the TargetAssemblyName and SchemaName attributes.</span></span>  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a><span data-ttu-id="9bf43-202">TPE で一部のオーケストレーション図形を追跡できない</span><span class="sxs-lookup"><span data-stu-id="9bf43-202">Some Orchestration Shapes Cannot be Tracked in the TPE</span></span>  
 <span data-ttu-id="9bf43-203">オーケストレーション エンジンは次の図形についてイベントを生成できないので、これらの図形を TPE で追跡またはマップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bf43-203">The orchestration ongine does not generate events for the following shapes and thus these shapes cannot be tracked or mapped in the TPE:</span></span>  
  
-   <span data-ttu-id="9bf43-204">タスク</span><span class="sxs-lookup"><span data-stu-id="9bf43-204">Task</span></span>  
  
-   <span data-ttu-id="9bf43-205">すべての分岐</span><span class="sxs-lookup"><span data-stu-id="9bf43-205">All Branches</span></span>  
  
-   <span data-ttu-id="9bf43-206">[中断]</span><span class="sxs-lookup"><span data-stu-id="9bf43-206">Suspend</span></span>  
  
-   <span data-ttu-id="9bf43-207">終了</span><span class="sxs-lookup"><span data-stu-id="9bf43-207">Terminate</span></span>  
  
-   <span data-ttu-id="9bf43-208">スロー</span><span class="sxs-lookup"><span data-stu-id="9bf43-208">Throw</span></span>  
  
-   <span data-ttu-id="9bf43-209">キャッチ</span><span class="sxs-lookup"><span data-stu-id="9bf43-209">Catch</span></span>  
  
-   <span data-ttu-id="9bf43-210">メッセージの割り当て (構築図形に含まれているため)</span><span class="sxs-lookup"><span data-stu-id="9bf43-210">MessageAssignment (because it is part of the Construct shape)</span></span>  
  
-   <span data-ttu-id="9bf43-211">変換 (構築図形に含まれているため)</span><span class="sxs-lookup"><span data-stu-id="9bf43-211">Transform (because it is part of the Construct shape)</span></span>  
  
-   <span data-ttu-id="9bf43-212">ループ</span><span class="sxs-lookup"><span data-stu-id="9bf43-212">Loop</span></span>  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a><span data-ttu-id="9bf43-213">追跡プロファイルを取得しない TPE の展開</span><span class="sxs-lookup"><span data-stu-id="9bf43-213">TPE Not Retrieving Deployed Tracking Profiles</span></span>  
 <span data-ttu-id="9bf43-214">アップグレードまたは再展開の後、展開された追跡プロファイルを取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9bf43-214">After an upgrade or redeployment you may experience difficulties in retrieving deployed tracking profiles.</span></span> <span data-ttu-id="9bf43-215">これは、BizTalkMgmtDb データベースがレジストリ内に保存されているサーバー名に不一致があるために発生します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-215">This can be caused by a mismatch in the manner in which the server name on which BizTalkMgmtDb database is stored in the registry.</span></span>  
  
 <span data-ttu-id="9bf43-216">BizTalkMgmtDb は、グループの構成中にレジストリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-216">The BizTalkMgmtDb is written to the registry during Group configuration.</span></span> <span data-ttu-id="9bf43-217">TPE はエントリを使用して、プライマリ インポート データベースを検索し、追跡プロファイルをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-217">The TPE uses the entry to find the Primary Import database and to filter the tracking profiles.</span></span>  
  
 <span data-ttu-id="9bf43-218">構成中、サーバー名は複数の形式で入力できます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-218">During configuration it is possible to enter the server name in several formats.</span></span> <span data-ttu-id="9bf43-219">例:</span><span class="sxs-lookup"><span data-stu-id="9bf43-219">For example:</span></span>  
  
-   <span data-ttu-id="9bf43-220">mgmtsvr1316267,15001\inst</span><span class="sxs-lookup"><span data-stu-id="9bf43-220">mgmtsvr1316267,15001\inst</span></span>  
  
-   <span data-ttu-id="9bf43-221">MGMTSVR1316267\inst,15001</span><span class="sxs-lookup"><span data-stu-id="9bf43-221">MGMTSVR1316267\inst,15001</span></span>  
  
 <span data-ttu-id="9bf43-222">TPE は、レジストリ エントリの使用時に基本的な文字列比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="9bf43-222">The TPE performs a basic string comparison when using the registry entry.</span></span> <span data-ttu-id="9bf43-223">展開された追跡プロファイルを取得するのには格納されたサーバーおよびデータベースの名前を検査し、それらを TPE で入力するために必要な**管理データベースの設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9bf43-223">To retrieve the deployed tracking profiles it is necessary to inspect the stored server and database names and enter them in the TPE **Set Management Database** dialog box.</span></span>  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a><span data-ttu-id="9bf43-224">サーバー名とデータベース名の構文を確認して、それを、BizTalk 管理データベースに入力するには</span><span class="sxs-lookup"><span data-stu-id="9bf43-224">To determine the syntax for server and database names and enter it in the BizTalk Management database.</span></span>  
  
1.  <span data-ttu-id="9bf43-225">開く、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**カスタム構成マネージャ**です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-225">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**Custom Configuration Manager**.</span></span> <span data-ttu-id="9bf43-226">使用方法について、**カスタム構成マネージャ**を参照してください[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-226">For information about using the **Custom Configuration Manager**, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>  
  
2.  <span data-ttu-id="9bf43-227">ナビゲーション ウィンドウで、次のように選択します。**グループ**グループ構成ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9bf43-227">In the navigation pane, select **Group** to open the group configuration page.</span></span>  
  
3.  <span data-ttu-id="9bf43-228">**データ ストア**グリッドの形式を確認、**サーバー名**と**データベース名**です。</span><span class="sxs-lookup"><span data-stu-id="9bf43-228">In the **Data Stores** grid, observe the formats of the **Server Name** and the **Database Name**.</span></span>  
  
4.  <span data-ttu-id="9bf43-229">TPE を開き、選択、**ツール**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="9bf43-229">Open the TPE and select the **Tools** menu item.</span></span>  
  
5.  <span data-ttu-id="9bf43-230">選択、**管理データベースの設定**メニュー項目を開くには、**管理データベースの設定** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9bf43-230">Select the **Set Management Database** menu item to open the **Set Management Database** dialog box.</span></span>  
  
6.  <span data-ttu-id="9bf43-231">**SQL Server**テキスト ボックスで使用されたサーバー名を入力、**サーバー名**のフィールド、**データ ストア**gridon、**カスタム構成マネージャー**グループのページです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-231">In the **SQL Server** text box, enter the server name that was used in the **Server Name** field of the **Data Stores** gridon the **Custom Configuration Manager** group page.</span></span>  
  
7.  <span data-ttu-id="9bf43-232">**データベース名**テキスト ボックスで使用されていたデータベース名を入力、**データベース名**のフィールド、**データ ストア**gridon、**カスタム構成Manager**グループのページです。</span><span class="sxs-lookup"><span data-stu-id="9bf43-232">In the **Database name** text box, enter the database name that was used in the **Database Name** field of the **Data Stores** gridon the **Custom Configuration Manager** group page.</span></span>  
  
8.  <span data-ttu-id="9bf43-233">クリックして、 **[ok]** エントリを保存するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bf43-233">Click the **OK** button to save the entries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf43-234">参照</span><span class="sxs-lookup"><span data-stu-id="9bf43-234">See Also</span></span>  
 <span data-ttu-id="9bf43-235">[TPE の使用](../core/using-the-tpe.md) </span><span class="sxs-lookup"><span data-stu-id="9bf43-235">[Using the TPE](../core/using-the-tpe.md) </span></span>  
 [<span data-ttu-id="9bf43-236">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="9bf43-236">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)