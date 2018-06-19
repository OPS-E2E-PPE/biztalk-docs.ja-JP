---
title: アクティビティ ビューについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], Activity view [Tracking Profile Editor]
- activities [BAM], definitions
- Tracking Profile Editor, Activity view
- Activity view [Tracking Profile Editor]
ms.assetid: ae6bcdc8-e426-4148-b83d-08a1a5e99ca3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fd27a4de6b2ac86f94b105aabe679df3c88c06d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290386"
---
# <a name="what-is-an-activity-view"></a><span data-ttu-id="8ebf4-103">アクティビティ ビューについて</span><span class="sxs-lookup"><span data-stu-id="8ebf4-103">What Is an Activity View?</span></span>
<span data-ttu-id="8ebf4-104">アクティビティ ビューには、インポートした BAM アクティビティ定義が含まれています。このアクティビティ定義は、Excel 用の BAM アドインで作成します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-104">An activity view contains the imported BAM activity definition that you create with the BAM Add-In for Excel.</span></span> <span data-ttu-id="8ebf4-105">BAM アクティビティ定義は、ビジネス プロセスの追跡要件の抽象概念です。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-105">The BAM activity definition is an abstract of your trace requirements for your business process.</span></span> <span data-ttu-id="8ebf4-106">アクティビティは、複数のオーケストレーションおよびポートにまたがることがあります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-106">An activity can span multiple orchestrations and ports.</span></span> <span data-ttu-id="8ebf4-107">アクティビティ定義をインポートすると、その定義の一部を遂行する各オーケストレーション アイテムまたは各メッセージング アイテムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-107">You import the activity definition once and map it to each orchestration or messaging artifact that fulfills some part of the definition.</span></span>  
  
 <span data-ttu-id="8ebf4-108">アクティビティ ビュー リンクは、追跡プロファイル エディター (TPE) のユーザー インターフェイスの左ペインにあります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-108">The Activity View link is on the left pane of Tracking Profile Editor (TPE) user interface.</span></span>  
  
## <a name="activity-view-elements"></a><span data-ttu-id="8ebf4-109">アクティビティ ビューの要素</span><span class="sxs-lookup"><span data-stu-id="8ebf4-109">Activity view elements</span></span>  
 <span data-ttu-id="8ebf4-110">アクティビティ ビューには、追跡プロファイルの全体構造がツリー ビューで表示されます。このビューには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-110">The activity view displays the overall structure of the tracking profile in tree view and includes the following elements:</span></span>  
  
-   <span data-ttu-id="8ebf4-111">Milestones</span><span class="sxs-lookup"><span data-stu-id="8ebf4-111">Milestones</span></span>  
  
-   <span data-ttu-id="8ebf4-112">アクティビティのデータ項目</span><span class="sxs-lookup"><span data-stu-id="8ebf4-112">Data items for the activity</span></span>  
  
-   <span data-ttu-id="8ebf4-113">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8ebf4-113">Event sources</span></span>  
  
-   <span data-ttu-id="8ebf4-114">データ ソース</span><span class="sxs-lookup"><span data-stu-id="8ebf4-114">Data sources</span></span>  
  
 <span data-ttu-id="8ebf4-115">**マイルス トーン**: マイルス トーンは、特定のプロセスで、ポイントを定義しているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-115">**Milestones**: Milestones are objects which define a point in a given process.</span></span> <span data-ttu-id="8ebf4-116">マイルストーンには、次の 3 つのいずれかの方法でアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-116">Milestones are accessed in one of three ways:</span></span>  
  
-   <span data-ttu-id="8ebf4-117">オーケストレーション スケジュールから図形をドラッグすると、その図形の実行終了時刻がマイルストーンの値として報告されます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-117">You can drag a shape from an orchestration schedule, and the end-time for that shape’s execution is reported by BAM as the milestone value.</span></span>  
  
-   <span data-ttu-id="8ebf4-118">右側にあるスキーマ表現からターゲット マイルストーンに、メッセージ プロパティをドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-118">You can drag a messaging property, from a schematic representation on the right, to a target milestone.</span></span>  
  
-   <span data-ttu-id="8ebf4-119">マイルストーンの値を含んだメッセージ ペイロード スキーマ ノードをドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-119">You can drag a message payload schema node which contains a milestone value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ebf4-120">DATETIME ONLY 型のスキーマ ノードは実行時に評価されます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-120">The DATETIME ONLY type schema nodes are evaluated at run time.</span></span> <span data-ttu-id="8ebf4-121">実行時に変換やキャストの問題が発生すると、イベント ログに追跡エラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-121">Any conversion or casting problem at run time results in a tracking error being placed in the event log.</span></span>  
  
 <span data-ttu-id="8ebf4-122">**データ項目**: データ項目は、メッセージ インスタンス、システム、または昇格させたプロパティの XML スキーマから特定の要素を定義するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-122">**Data items**: Data items are objects which define a particular element from an XML schema for a message instance, system, or promoted property.</span></span> <span data-ttu-id="8ebf4-123">データ項目にアクセスするには、スキーマを展開して該当の要素を検索および選択し、適切なデータ項目型のフォルダーにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-123">You access the data item by expanding the schema to find and select the element you are interested in and dragging the element to the correct data item type folder.</span></span> <span data-ttu-id="8ebf4-124">データ項目に関する情報 (XPath など) がプロファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-124">Information about the data items (for example, XPath) is stored in the profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ebf4-125">TPE では、メッセージ スキーマで特定のデータ フィールド用に定義された 0 対 1 表現のデータ項目のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-125">TPE supports only data items that have a zero-to-one representation as defined in the message schema for a particular data field.</span></span> <span data-ttu-id="8ebf4-126">オーケストレーションを追跡するとき、1 対多表現のデータ項目が存在すると、エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-126">Errors may occur in orchestration tracking when there are data items that have one-to-many representations.</span></span> <span data-ttu-id="8ebf4-127">その場合は、BAM プライマリ インポート データベースにデータが保存されません。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-127">In these situations no data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="8ebf4-128">エラーが発生しない場合でも、どのデータ項目が追跡されるかについては保証されません。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-128">If an error does not occur, then there is no guarantee which of the data item is tracked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ebf4-129">BAM 開発者は、プロパティが BAM ではなく BizTalk Server の処理規則に従って設定されることを認識しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-129">BAM developers need to be aware that properties are populated according to BizTalk Server process rules, and not BAM.</span></span>  
>   
>  <span data-ttu-id="8ebf4-130">たとえば、SMTP アダプターでは、SMTPServer、CC、From などのコンテキスト プロパティには、値が明示的に設定されるまで値がありません。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-130">For example, in the SMTP adapter the context properties, such as SMTPServer, CC, and From, do not contain any values until they are explicitly populated.</span></span> <span data-ttu-id="8ebf4-131">プロパティに値が設定されると、BAM プライマリ インポート データベースに値が反映され、値を追跡できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-131">Once they have been populated their values will appear in the BAM Primary Import database and they will be available for tracking.</span></span>  
  
## <a name="activity-view-context-menus"></a><span data-ttu-id="8ebf4-132">アクティビティ ビューのショートカット メニュー</span><span class="sxs-lookup"><span data-stu-id="8ebf4-132">Activity view context menus</span></span>  
 <span data-ttu-id="8ebf4-133">アクティビティ ビューに使用できるアクションのショートカット メニューは、[オーケストレーションの種類] で選択したノードによって動的に変化します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-133">The context menus of available actions for the activity view dynamically change depending on the node selected in the Orchestration View.</span></span> <span data-ttu-id="8ebf4-134">たとえば、アクティビティ フォルダー ノードを選択した場合のショートカット メニューには、アクティビティ フォルダーで使用するメニュー項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-134">For example, if you select an activity folder node, the shortcut menu will contain the shortcut menu items for that activity folder.</span></span>  
  
 <span data-ttu-id="8ebf4-135">ビジネス アクティビティの項目をイベントおよびデータに関連付けるには、右のソース イベント ペインからアクティビティ ビューのイベント ノードまたはデータ ノードに項目をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-135">You associate events and data to the items in the business activity by dragging them from the source event pane on the right to the event or data node in the Activity view.</span></span>  
  
 <span data-ttu-id="8ebf4-136">アクティビティ ビューのノードのショートカット メニューを表示するには、ツリーのノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-136">The context menus for the nodes in the activity view are accessible by right-clicking a node in the tree.</span></span> <span data-ttu-id="8ebf4-137">次の画面に、アクティビティ ビューのルート ノードを示します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-137">The following screen shows the root node for activity views.</span></span> <span data-ttu-id="8ebf4-138">次の表で、アクティビティ ビューのノード別にショートカット メニューの項目を説明します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-138">The following tables describe the items in the context menus for the different nodes for an activity view.</span></span>  
  
 <span data-ttu-id="8ebf4-139">**アクティビティ定義ツリーのルート ノード**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-139">**Activity Definition Tree root node**</span></span>  
  
 ![](../core/media/activityviewcontextmenu.gif "activityviewcontextmenu")  
  
|<span data-ttu-id="8ebf4-140">メニュー項目</span><span class="sxs-lookup"><span data-stu-id="8ebf4-140">Menu Item</span></span>|<span data-ttu-id="8ebf4-141">使用方法</span><span class="sxs-lookup"><span data-stu-id="8ebf4-141">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="8ebf4-142">[新しい Continuation]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-142">New Continuation</span></span>|<span data-ttu-id="8ebf4-143">新しい Continuation フォルダーをアクティビティ ツリーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-143">Inserts a new Continuation folder into the Activity tree.</span></span> <span data-ttu-id="8ebf4-144">このフォルダーの値は、Continuation の継続元セグメントからマップします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-144">You map the value for this folder from the source segment of a continuation.</span></span><br /><br /> <span data-ttu-id="8ebf4-145">ContinuationID フォルダーと併用することで、同一のアクティビティを設定する複数のコンポーネント間で処理を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-145">Used in conjunction with a ContinuationID folder to provide a means to hand off processing between multiple components that populate the same activity.</span></span> <span data-ttu-id="8ebf4-146">このように使用できるコンポーネントには、BizTalk オーケストレーション、ポート、BufferedEventStreams、DirectEventStreams などがあります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-146">Examples of these components are BizTalk orchestrations, ports, BufferedEventStreams, and DirectEventStreams.</span></span> <span data-ttu-id="8ebf4-147">**注:** Continuation フォルダーの名前は最大 127 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-147">**Note:**  Continuation folder names can contain a maximum of 127 characters.</span></span>|  
|<span data-ttu-id="8ebf4-148">[新しい ContinuationID]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-148">New ContinuationID</span></span>|<span data-ttu-id="8ebf4-149">新しい ContinuationID フォルダーをアクティビティ ツリーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-149">Inserts a ContinuationID folder into the Activity tree.</span></span> <span data-ttu-id="8ebf4-150">このフォルダーは、Continuation の継続先セグメントにマップします。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-150">You map this folder to continued-to segment of a continuation.</span></span> <span data-ttu-id="8ebf4-151">たとえば、オーケストレーション A からオーケストレーション B に継続する場合、このフォルダーをオーケストレーション B の項目にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-151">For example, if orchestration A continues to Orchestration B, this folder must be mapped to an item from Orchestration B.</span></span><br /><br /> <span data-ttu-id="8ebf4-152">Continuation フォルダーと併用することで、同一のアクティビティを設定する複数のコンポーネント間で処理を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-152">Used in conjunction with a Continuation folder to provide a means to hand off processing between multiple components that populate the same activity.</span></span> <span data-ttu-id="8ebf4-153">このように使用できるコンポーネントには、BizTalk オーケストレーション、ポート、BufferedEventStreams、DirectEventStreams などがあります。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-153">Examples of these components are BizTalk orchestrations, ports, BufferedEventStreams, and DirectEventStreams.</span></span> <span data-ttu-id="8ebf4-154">**注:** ContinuationID フォルダーの名前は最大 127 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-154">**Note:**  ContinuationID folder names can contain a maximum of 127 characters.</span></span>|  
|<span data-ttu-id="8ebf4-155">[新しいリレーションシップ]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-155">New Relationship</span></span>|<span data-ttu-id="8ebf4-156">新しい Relationship フォルダーをアクティビティ ツリーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-156">Inserts a new relationship folder into the Activity tree.</span></span> <span data-ttu-id="8ebf4-157">ビューを形成するアクティビティ間のリレーションシップを公開するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-157">Used to publish the relationship between activities that form a view.</span></span> <span data-ttu-id="8ebf4-158">**注:** Relationship フォルダーの名前は最大 128 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-158">**Note:**  Relationship folder names can contain a maximum of 128 characters.</span></span> <span data-ttu-id="8ebf4-159">この名前には、サーバー名および BizTalk 管理データベース名を含めます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-159">The includes the server name and BizTalk Management database name.</span></span>|  
|<span data-ttu-id="8ebf4-160">[新しい Document Reference URL]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-160">New Document Reference URL</span></span>|<span data-ttu-id="8ebf4-161">新しい Document Reference URL フォルダーをアクティビティ ツリーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-161">Inserts a new Document Reference URL folder into the Activity tree.</span></span> <span data-ttu-id="8ebf4-162">このアクティビティに関連するドキュメントが格納されている場所を参照 URL に設定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-162">Used to set a reference URL to a location that contains a document that is related to this activity.</span></span> <span data-ttu-id="8ebf4-163">**注:** Document Reference URL フォルダー名は最大 128 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-163">**Note:**  Document Reference URL folder names can contain a maximum of 128 characters.</span></span>|  
  
 <span data-ttu-id="8ebf4-164">**プロパティ ノード**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-164">**Property Node**</span></span>  
  
|<span data-ttu-id="8ebf4-165">メニュー項目</span><span class="sxs-lookup"><span data-stu-id="8ebf4-165">Menu Item</span></span>|<span data-ttu-id="8ebf4-166">使用方法</span><span class="sxs-lookup"><span data-stu-id="8ebf4-166">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="8ebf4-167">[選択したデータを関連付ける]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-167">Associate Selected Data</span></span>|<span data-ttu-id="8ebf4-168">メッセージ ペイロードまたはコンテキスト プロパティのデータ項目と、BAM アクティビティ データ項目フォルダーの関連付けを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-168">Used to create an association between a message payload or context property data item and the BAM Activity data item folder.</span></span>|  
  
 <span data-ttu-id="8ebf4-169">**イベント ノード**</span><span class="sxs-lookup"><span data-stu-id="8ebf4-169">**Event node**</span></span>  
  
|<span data-ttu-id="8ebf4-170">メニュー項目</span><span class="sxs-lookup"><span data-stu-id="8ebf4-170">Menu Item</span></span>|<span data-ttu-id="8ebf4-171">使用方法</span><span class="sxs-lookup"><span data-stu-id="8ebf4-171">Usage</span></span>|  
|---------------|-----------|  
|<span data-ttu-id="8ebf4-172">[選択したアクションの終了時に関連付ける]</span><span class="sxs-lookup"><span data-stu-id="8ebf4-172">Associate with the end of the selected action</span></span>|<span data-ttu-id="8ebf4-173">オーケストレーション図形、DateTime メッセージ ペイロード、DateTime コンテキスト プロパティのいずれかのデータ項目と、BAM アクティビティ マイルストーン フォルダーの関連付けを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8ebf4-173">Used to create an association between an orchestration shape, DateTime message payload, or DateTime context property data item and the BAM Activity milestone folder.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ebf4-174">参照</span><span class="sxs-lookup"><span data-stu-id="8ebf4-174">See Also</span></span>  
 <span data-ttu-id="8ebf4-175">[BAM アクティビティのイベント ストリームの実装](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="8ebf4-175">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="8ebf4-176">[Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8ebf4-176">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="8ebf4-177">TPE のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="8ebf4-177">Components of the TPE</span></span>](../core/components-of-the-tpe.md)